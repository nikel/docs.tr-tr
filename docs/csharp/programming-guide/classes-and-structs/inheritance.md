---
title: "Devralma (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- abstract methods [C#]
- abstract classes [C#]
- inheritance [C#]
- derived classes [C#]
- virtual methods [C#]
- C# language, inheritance
ms.assetid: 81d64ee4-50f9-4d6c-a8dc-257c348d2eea
caps.latest.revision: "38"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc3d448d311fe0a67839757fa43a209d92141214
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="inheritance-c-programming-guide"></a><span data-ttu-id="e28b9-102">Devralma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="e28b9-102">Inheritance (C# Programming Guide)</span></span>

<span data-ttu-id="e28b9-103">Saklama ve çok biçimlilik, birlikte devralma nesne odaklı programlama üç birincil özelliklerini biridir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-103">Inheritance, together with encapsulation and polymorphism, is one of the three primary characteristics of object-oriented programming.</span></span> <span data-ttu-id="e28b9-104">Devralma yeniden genişletmek ve diğer sınıflarda tanımlanan davranışını yeni sınıflar oluşturmanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="e28b9-104">Inheritance enables you to create new classes that reuse, extend, and modify the behavior that is defined in other classes.</span></span> <span data-ttu-id="e28b9-105">Üyeleri devralındığı sınıfı adlı *temel sınıfı*, bu üyeler devralan sınıf adı verilen ve *türetilmiş sınıf*.</span><span class="sxs-lookup"><span data-stu-id="e28b9-105">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="e28b9-106">Türetilmiş bir sınıf doğrudan yalnızca bir temel sınıf olabilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-106">A derived class can have only one direct base class.</span></span> <span data-ttu-id="e28b9-107">Ancak, devralma geçişli olur.</span><span class="sxs-lookup"><span data-stu-id="e28b9-107">However, inheritance is transitive.</span></span> <span data-ttu-id="e28b9-108">ClassC ClassB türetilmiş ve ClassB ClassA türetilmiş, ClassC ClassB ve ClassA bildirilen üyeleri devralır.</span><span class="sxs-lookup"><span data-stu-id="e28b9-108">If ClassC is derived from ClassB, and ClassB is derived from ClassA, ClassC inherits the members declared in ClassB and ClassA.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e28b9-109">Yapılar devralma desteklemez, ancak arabirimleri uygulayabilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-109">Structs do not support inheritance, but they can implement interfaces.</span></span> <span data-ttu-id="e28b9-110">Daha fazla bilgi için bkz: [arabirimleri](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-110">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
 <span data-ttu-id="e28b9-111">Kavramsal olarak, türetilmiş bir sınıf temel sınıfın uzmanlık ' dir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-111">Conceptually, a derived class is a specialization of the base class.</span></span> <span data-ttu-id="e28b9-112">Örneğin, bir taban sınıf varsa `Animal`, adlı bir türetilmiş sınıf olabilir `Mammal` ve adlı başka bir türetilmiş sınıf `Reptile`.</span><span class="sxs-lookup"><span data-stu-id="e28b9-112">For example, if you have a base class `Animal`, you might have one derived class that is named `Mammal` and another derived class that is named `Reptile`.</span></span> <span data-ttu-id="e28b9-113">A `Mammal` olan bir `Animal`ve bir `Reptile` olan bir `Animal`, ancak her türetilmiş bir sınıf temel sınıfın farklı özelleştirmeleri temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e28b9-113">A `Mammal` is an `Animal`, and a `Reptile` is an `Animal`, but each derived class represents different specializations of the base class.</span></span>  
  
 <span data-ttu-id="e28b9-114">Başka bir sınıftan türeyen bir sınıf tanımladığınızda, türetilmiş sınıf oluşturucular ve sonlandırıcılar dışında temel sınıfın tüm üyeleri örtük olarak kazanır.</span><span class="sxs-lookup"><span data-stu-id="e28b9-114">When you define a class to derive from another class, the derived class implicitly gains all the members of the base class, except for its constructors and finalizers.</span></span> <span data-ttu-id="e28b9-115">Türetilmiş sınıf yeniden uygulamak zorunda kalmadan temel sınıfı kodda böylece yeniden kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e28b9-115">The derived class can thereby reuse the code in the base class without having to re-implement it.</span></span> <span data-ttu-id="e28b9-116">Türetilen sınıfta daha fazla üye ekleyebilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-116">In the derived class, you can add more members.</span></span> <span data-ttu-id="e28b9-117">Bu şekilde, türetilen sınıfın temel sınıf işlevselliğini genişletir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-117">In this manner, the derived class extends the functionality of the base class.</span></span>  
  
 <span data-ttu-id="e28b9-118">Aşağıdaki çizimde bir sınıfı göstermektedir `WorkItem` , bazı iş sürecini iş bir öğeyi temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e28b9-118">The following illustration shows a class `WorkItem` that represents an item of work in some business process.</span></span> <span data-ttu-id="e28b9-119">Öğesinden türetilen tüm sınıflar gibi <xref:System.Object?displayProperty=nameWithType> ve tüm yöntemleri devralır.</span><span class="sxs-lookup"><span data-stu-id="e28b9-119">Like all classes, it derives from <xref:System.Object?displayProperty=nameWithType> and inherits all its methods.</span></span> <span data-ttu-id="e28b9-120">`WorkItem`beş üyeleri kendi ekler.</span><span class="sxs-lookup"><span data-stu-id="e28b9-120">`WorkItem` adds five members of its own.</span></span> <span data-ttu-id="e28b9-121">Oluşturucular devralınmaz çünkü bunlar bir oluşturucu içerir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-121">These include a constructor, because constructors are not inherited.</span></span> <span data-ttu-id="e28b9-122">Sınıf `ChangeRequest` devraldığı `WorkItem` ve belirli bir iş öğesi türünü temsil eder.</span><span class="sxs-lookup"><span data-stu-id="e28b9-122">Class `ChangeRequest` inherits from `WorkItem` and represents a particular kind of work item.</span></span> <span data-ttu-id="e28b9-123">`ChangeRequest`öğesinden devralınan üyeler iki daha fazla üye ekler `WorkItem` ve <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="e28b9-123">`ChangeRequest` adds two more members to the members that it inherits from `WorkItem` and from <xref:System.Object>.</span></span> <span data-ttu-id="e28b9-124">Kendi Oluşturucusu eklemeniz gerekir ve ayrıca ekler `originalItemID`.</span><span class="sxs-lookup"><span data-stu-id="e28b9-124">It must add its own constructor, and it also adds `originalItemID`.</span></span> <span data-ttu-id="e28b9-125">Özellik `originalItemID` sağlayan `ChangeRequest` özgün ile ilişkilendirilecek örneği `WorkItem` değişiklik isteğini geçerli olduğu için.</span><span class="sxs-lookup"><span data-stu-id="e28b9-125">Property `originalItemID` enables the `ChangeRequest` instance to be associated with the original `WorkItem` to which the change request applies.</span></span>  
  
 <span data-ttu-id="e28b9-126">![Sınıf devralma](../../../csharp/programming-guide/classes-and-structs/media/class_inheritance.png "Class_Inheritance")</span><span class="sxs-lookup"><span data-stu-id="e28b9-126">![Class Inheritance](../../../csharp/programming-guide/classes-and-structs/media/class_inheritance.png "Class_Inheritance")</span></span>  
<span data-ttu-id="e28b9-127">Sınıf devralma</span><span class="sxs-lookup"><span data-stu-id="e28b9-127">Class inheritance</span></span>  
  
 <span data-ttu-id="e28b9-128">Aşağıdaki örnekte nasıl önceki çizimde gösterilen sınıf ilişkileri C# ' ta belirtilmiştir gösterir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-128">The following example shows how the class relationships demonstrated in the previous illustration are expressed in C#.</span></span> <span data-ttu-id="e28b9-129">Bu örnek ayrıca gösterir nasıl `WorkItem` sanal yöntemini geçersiz kılar <xref:System.Object.ToString%2A?displayProperty=nameWithType>ve nasıl `ChangeRequest` sınıfının devraldığı `WorkItem` yöntemin kullanımı.</span><span class="sxs-lookup"><span data-stu-id="e28b9-129">The example also shows how `WorkItem` overrides the virtual method <xref:System.Object.ToString%2A?displayProperty=nameWithType>, and how the `ChangeRequest` class inherits the `WorkItem` implementation of the method.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#49](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/inheritance_1.cs)]  
  
## <a name="abstract-and-virtual-methods"></a><span data-ttu-id="e28b9-130">Soyut ve sanal yöntemleri</span><span class="sxs-lookup"><span data-stu-id="e28b9-130">Abstract and Virtual Methods</span></span>  
 <span data-ttu-id="e28b9-131">Ne zaman bir taban sınıf bildiren bir yöntem olarak [sanal](../../../csharp/language-reference/keywords/virtual.md), türetilmiş sınıf [geçersiz kılma](../../../csharp/language-reference/keywords/override.md) kendi uygulama yöntemiyle.</span><span class="sxs-lookup"><span data-stu-id="e28b9-131">When a base class declares a method as [virtual](../../../csharp/language-reference/keywords/virtual.md), a derived class can [override](../../../csharp/language-reference/keywords/override.md) the method with its own implementation.</span></span> <span data-ttu-id="e28b9-132">Bir temel sınıf olarak bir üye bildirirse [soyut](../../../csharp/language-reference/keywords/abstract.md), doğrudan bu sınıfından devralan tüm soyut olmayan sınıfı içinde yöntemi geçersiz kılınmalıdır.</span><span class="sxs-lookup"><span data-stu-id="e28b9-132">If a base class declares a member as [abstract](../../../csharp/language-reference/keywords/abstract.md), that method must be overridden in any non-abstract class that directly inherits from that class.</span></span> <span data-ttu-id="e28b9-133">Türetilmiş bir sınıf kendisi ise soyut, soyut üyelerini uygulamadan devralır.</span><span class="sxs-lookup"><span data-stu-id="e28b9-133">If a derived class is itself abstract, it inherits abstract members without implementing them.</span></span> <span data-ttu-id="e28b9-134">Soyut ve sanal çok biçimlilik, temel nesne odaklı programlama ikinci birincil özelliği olduğu üyeleridir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-134">Abstract and virtual members are the basis for polymorphism, which is the second primary characteristic of object-oriented programming.</span></span> <span data-ttu-id="e28b9-135">Daha fazla bilgi için bkz: [çok biçimlilik](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-135">For more information, see [Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).</span></span>  
  
## <a name="abstract-base-classes"></a><span data-ttu-id="e28b9-136">Soyut taban sınıfları</span><span class="sxs-lookup"><span data-stu-id="e28b9-136">Abstract Base Classes</span></span>  
 <span data-ttu-id="e28b9-137">Bir sınıf olarak bildirebilir [soyut](../../../csharp/language-reference/keywords/abstract.md) kullanarak doğrudan engellemek istiyorsanız [yeni](../../../csharp/language-reference/keywords/new.md) anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="e28b9-137">You can declare a class as [abstract](../../../csharp/language-reference/keywords/abstract.md) if you want to prevent direct instantiation by using the [new](../../../csharp/language-reference/keywords/new.md) keyword.</span></span> <span data-ttu-id="e28b9-138">Bunu yaparsanız, yalnızca yeni bir sınıf türetilmiş sınıf kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-138">If you do this, the class can be used only if a new class is derived from it.</span></span> <span data-ttu-id="e28b9-139">Bir Özet sınıf bir içerebilir veya daha fazla yöntem imzaları, kendilerini soyut olarak bildirilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-139">An abstract class can contain one or more method signatures that themselves are declared as abstract.</span></span> <span data-ttu-id="e28b9-140">Bu imzaları parametreleri belirtin ve dönüş değeri ancak hiçbir uygulaması (yöntem gövdesi) sahip.</span><span class="sxs-lookup"><span data-stu-id="e28b9-140">These signatures specify the parameters and return value but have no implementation (method body).</span></span> <span data-ttu-id="e28b9-141">Bir Özet Sınıf soyut üyelerini içeren gerekmez; Ancak, bir sınıf soyut bir üye içeriyorsa, bu sınıfı soyut olarak bildirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-141">An abstract class does not have to contain abstract members; however, if a class does contain an abstract member, the class itself must be declared as abstract.</span></span> <span data-ttu-id="e28b9-142">Soyut olmayan türetilen sınıflar kendilerini bir soyut taban sınıfından herhangi bir Özet yöntem uygulamasını sağlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-142">Derived classes that are not abstract themselves must provide the implementation for any abstract methods from an abstract base class.</span></span> <span data-ttu-id="e28b9-143">Daha fazla bilgi için bkz: [soyut ve korumalı sınıflar ve sınıf üyeleri](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-143">For more information, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="interfaces"></a><span data-ttu-id="e28b9-144">Arabirimler</span><span class="sxs-lookup"><span data-stu-id="e28b9-144">Interfaces</span></span>  
 <span data-ttu-id="e28b9-145">Bir *arabirimi* yalnızca soyut üyeleri oluşan bir Özet temel sınıf için biraz benzer bir başvuru türüdür.</span><span class="sxs-lookup"><span data-stu-id="e28b9-145">An *interface* is a reference type that is somewhat similar to an abstract base class that consists of only abstract members.</span></span> <span data-ttu-id="e28b9-146">Bir sınıf bir arabirimini uygulayan, arabirimin tüm üyeleri için bir uygulama sağlaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-146">When a class implements an interface, it must provide an implementation for all the members of the interface.</span></span> <span data-ttu-id="e28b9-147">Bu yalnızca bir tek doğrudan taban sınıfından türetilen olsa da bir sınıf birden çok arabirimi uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e28b9-147">A class can implement multiple interfaces even though it can derive from only a single direct base class.</span></span>  
  
 <span data-ttu-id="e28b9-148">Arabirimleri mutlaka olmadığı sınıfları için belirli özelliklerini tanımlamak için kullanılan bir "olan bir" ilişki.</span><span class="sxs-lookup"><span data-stu-id="e28b9-148">Interfaces are used to define specific capabilities for classes that do not necessarily have an "is a" relationship.</span></span> <span data-ttu-id="e28b9-149">Örneğin, <xref:System.IEquatable%601?displayProperty=nameWithType> arabirimi herhangi bir sınıf veya (ancak türü eşdeğer tanımlar) türde iki nesne eşdeğer olup olmadığını belirlemek istemci kodu etkinleştirmek için sahip yapısı tarafından uygulanabilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-149">For example, the <xref:System.IEquatable%601?displayProperty=nameWithType> interface can be implemented by any class or struct that has to enable client code to determine whether two objects of the type are equivalent (however the type defines equivalence).</span></span> <span data-ttu-id="e28b9-150"><xref:System.IEquatable%601>aynı tür göstermez "olan bir" temel sınıf ve türetilmiş bir sınıf arasında var ilişkisi (örneğin, bir `Mammal` olan bir `Animal`).</span><span class="sxs-lookup"><span data-stu-id="e28b9-150"><xref:System.IEquatable%601> does not imply the same kind of "is a" relationship that exists between a base class and a derived class (for example, a `Mammal` is an `Animal`).</span></span> <span data-ttu-id="e28b9-151">Daha fazla bilgi için bkz: [arabirimleri](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-151">For more information, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="preventing-further-derivation"></a><span data-ttu-id="e28b9-152">Daha fazla türetme önleme</span><span class="sxs-lookup"><span data-stu-id="e28b9-152">Preventing Further Derivation</span></span>  
 <span data-ttu-id="e28b9-153">Bir sınıf dışarı ya da, bu grubun üyeleri herhangi kendisini veya üye olarak bildirerek öğesinden devralan diğer sınıflara engelleyebilirsiniz [korumalı](../../../csharp/language-reference/keywords/sealed.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-153">A class can prevent other classes from inheriting from it, or from any of its members, by declaring itself or the member as [sealed](../../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="e28b9-154">Daha fazla bilgi için bkz: [soyut ve korumalı sınıflar ve sınıf üyeleri](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-154">For more information, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="derived-class-hiding-of-base-class-members"></a><span data-ttu-id="e28b9-155">Taban sınıfı üyeleri türetilmiş sınıf gizleme</span><span class="sxs-lookup"><span data-stu-id="e28b9-155">Derived Class Hiding of Base Class Members</span></span>  
 <span data-ttu-id="e28b9-156">Türetilmiş bir sınıf, aynı ad ve imza üyeleriyle bildirerek taban sınıfı üyeleri gizleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e28b9-156">A derived class can hide base class members by declaring members with the same name and signature.</span></span> <span data-ttu-id="e28b9-157">[Yeni](../../../csharp/language-reference/keywords/new.md) değiştiricisi üye bir geçersiz kılma temel üyesinin olması amaçlanmamıştır açıkça belirtmek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e28b9-157">The [new](../../../csharp/language-reference/keywords/new.md) modifier can be used to explicitly indicate that the member is not intended to be an override of the base member.</span></span> <span data-ttu-id="e28b9-158">Kullanımını [yeni](../../../csharp/language-reference/keywords/new.md) gerekli değildir ancak derleyici uyarısı oluşturulan [yeni](../../../csharp/language-reference/keywords/new.md) kullanılmaz.</span><span class="sxs-lookup"><span data-stu-id="e28b9-158">The use of [new](../../../csharp/language-reference/keywords/new.md) is not required, but a compiler warning will be generated if [new](../../../csharp/language-reference/keywords/new.md) is not used.</span></span> <span data-ttu-id="e28b9-159">Daha fazla bilgi için bkz: [geçersiz kılma ve yeni anahtar sözcüklerle sürüm oluşturma](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) ve [kullanımı geçersiz kılma ve yeni anahtar sözcüklerin için bilerek olduğunda](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="e28b9-159">For more information, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e28b9-160">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e28b9-160">See Also</span></span>  
 [<span data-ttu-id="e28b9-161">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="e28b9-161">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="e28b9-162">Sınıflar ve yapılar</span><span class="sxs-lookup"><span data-stu-id="e28b9-162">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="e28b9-163">sınıfı</span><span class="sxs-lookup"><span data-stu-id="e28b9-163">class</span></span>](../../../csharp/language-reference/keywords/class.md)  
 [<span data-ttu-id="e28b9-164">yapısı</span><span class="sxs-lookup"><span data-stu-id="e28b9-164">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)