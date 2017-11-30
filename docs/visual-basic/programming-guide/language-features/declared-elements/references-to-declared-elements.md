---
title: "Bildirilmiş Öğelere Başvurular (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- declared elements [Visual Basic]
- references [Visual Basic], declared elements
- qualified names [Visual Basic]
ms.assetid: d6301709-f4cc-4b7a-b8ba-80898f14ab46
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9b3847164b4e577a9265a746b9329218b4af928b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="references-to-declared-elements-visual-basic"></a><span data-ttu-id="80f4e-102">Bildirilmiş Öğelere Başvurular (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="80f4e-102">References to Declared Elements (Visual Basic)</span></span>
<span data-ttu-id="80f4e-103">Kodunuz için bildirilen bir öğe, başvurduğunda [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] derleyici adının uygun bildirimi, başvuru adı ile eşleşir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-103">When your code refers to a declared element, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler matches the name in your reference to the appropriate declaration of that name.</span></span> <span data-ttu-id="80f4e-104">Aynı ada sahip birden fazla öğe bildirilirse, bu öğeler tarafından başvurulacak olduğu denetleyebilirsiniz *belirleme* adı.</span><span class="sxs-lookup"><span data-stu-id="80f4e-104">If more than one element is declared with the same name, you can control which of those elements is to be referenced by *qualifying* its name.</span></span>  
  
 <span data-ttu-id="80f4e-105">Derleme adı bildirimiyle adı referansı eşleştirmeyi dener *dar kapsamı*.</span><span class="sxs-lookup"><span data-stu-id="80f4e-105">The compiler attempts to match a name reference to a name declaration with the *narrowest scope*.</span></span> <span data-ttu-id="80f4e-106">Bunun anlamı başvuru yapma kodu ile başlar ve dışa öğeleri içeren art arda gelen düzeyleri ile çalışır.</span><span class="sxs-lookup"><span data-stu-id="80f4e-106">This means it starts with the code making the reference and works outward through successive levels of containing elements.</span></span>  
  
 <span data-ttu-id="80f4e-107">Aşağıdaki örnek, aynı ada sahip iki değişken başvuruları gösterir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-107">The following example shows references to two variables with the same name.</span></span> <span data-ttu-id="80f4e-108">Bu örnek iki değişken bildirir, her adlı `totalCount`, modüldeki kapsamının farklı düzeylerde `container`.</span><span class="sxs-lookup"><span data-stu-id="80f4e-108">The example declares two variables, each named `totalCount`, at different levels of scope in module `container`.</span></span> <span data-ttu-id="80f4e-109">Zaman yordamı `showCount` görüntüler `totalCount` nitelik olmadan [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] derleyici çözümler dar kapsamı, yani yerel bildirimi içinde bildirimiyle referansı `showCount`.</span><span class="sxs-lookup"><span data-stu-id="80f4e-109">When the procedure `showCount` displays `totalCount` without qualification, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler resolves the reference to the declaration with the narrowest scope, namely the local declaration inside `showCount`.</span></span> <span data-ttu-id="80f4e-110">Ne zaman niteleyen `totalCount` içeren modülü ile `container`, daha geniş kapsamlı bildirimi referansı derleyici giderir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-110">When it qualifies `totalCount` with the containing module `container`, the compiler resolves the reference to the declaration with the broader scope.</span></span>  
  
```vb  
' Assume these two modules are both in the same assembly.  
Module container  
    Public totalCount As Integer = 1  
    Public Sub showCount()  
        Dim totalCount As Integer = 6000  
        ' The following statement displays the local totalCount (6000).  
        MsgBox("Unqualified totalCount is " & CStr(totalCount))  
        ' The following statement displays the module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
Module callingModule  
    Public Sub displayCount()  
        container.showCount()  
        ' The following statement displays the containing module's totalCount (1).  
        MsgBox("container.totalCount is " & CStr(container.totalCount))  
    End Sub  
End Module  
```  
  
## <a name="qualifying-an-element-name"></a><span data-ttu-id="80f4e-111">Bir öğe adı niteleme</span><span class="sxs-lookup"><span data-stu-id="80f4e-111">Qualifying an Element Name</span></span>  
 <span data-ttu-id="80f4e-112">Bu arama işlemi geçersiz kılmak ve bir ad gerekir daha geniş bir kapsamda bildirilen belirtmek istiyorsanız *nitelemek* içeren bir öğesiyle daha geniş kapsam adı.</span><span class="sxs-lookup"><span data-stu-id="80f4e-112">If you want to override this search process and specify a name declared in a broader scope, you must *qualify* the name with the containing element of the broader scope.</span></span> <span data-ttu-id="80f4e-113">Bazı durumlarda, kapsayan öğe nitelemek olabilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-113">In some cases, you might also have to qualify the containing element.</span></span>  
  
 <span data-ttu-id="80f4e-114">Uygun hedef öğe tanımlandığı tanımlayan bilgiler ile kaynak deyiminde önceki adı anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-114">Qualifying a name means preceding it in your source statement with information that identifies where the target element is defined.</span></span> <span data-ttu-id="80f4e-115">Bu bilgileri olarak adlandırılan bir *niteliğe dize*.</span><span class="sxs-lookup"><span data-stu-id="80f4e-115">This information is called a *qualification string*.</span></span> <span data-ttu-id="80f4e-116">Bir içerebilir veya daha fazla ad alanları ve bir modül sınıf veya yapı.</span><span class="sxs-lookup"><span data-stu-id="80f4e-116">It can include one or more namespaces and a module, class, or structure.</span></span>  
  
 <span data-ttu-id="80f4e-117">Niteliğe dize belirsizliğe modülü, sınıf veya yapı hedef öğe içeren belirtmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-117">The qualification string should unambiguously specify the module, class, or structure containing the target element.</span></span> <span data-ttu-id="80f4e-118">Kapsayıcı sırayla başka bir kapsayıcı öğe, genellikle bir ad alanı bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-118">The container might in turn be located in another containing element, usually a namespace.</span></span> <span data-ttu-id="80f4e-119">Niteliğe dizesine birkaç içeren öğe eklemek gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-119">You might need to include several containing elements in the qualification string.</span></span>  
  
#### <a name="to-access-a-declared-element-by-qualifying-its-name"></a><span data-ttu-id="80f4e-120">Bildirilen öğe adını niteleme tarafından erişmek için</span><span class="sxs-lookup"><span data-stu-id="80f4e-120">To access a declared element by qualifying its name</span></span>  
  
1.  <span data-ttu-id="80f4e-121">Öğe tanımlanmış konum belirleyin.</span><span class="sxs-lookup"><span data-stu-id="80f4e-121">Determine the location in which the element has been defined.</span></span> <span data-ttu-id="80f4e-122">Bu, bir ad alanı veya hatta ad alanları hiyerarşisi içerebilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-122">This might include a namespace, or even a hierarchy of namespaces.</span></span> <span data-ttu-id="80f4e-123">En düşük düzeyde ad alanı içinde bir modül, sınıf veya yapı öğesi bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="80f4e-123">Within the lowest-level namespace, the element must be contained in a module, class, or structure.</span></span>  
  
    ```vb  
    ' Assume the following hierarchy exists outside your code.  
    Namespace outerSpace  
        Namespace innerSpace  
            Module holdsTotals  
                Public Structure totals  
                    Public thisTotal As Integer  
                    Public Shared grandTotal As Long  
                End Structure  
            End Module  
        End Namespace  
    End Namespace  
    ```  
  
2.  <span data-ttu-id="80f4e-124">Hedef öğenin konum temelinde bir nitelenmiş yola belirler.</span><span class="sxs-lookup"><span data-stu-id="80f4e-124">Determine a qualification path based on the target element's location.</span></span> <span data-ttu-id="80f4e-125">En üst düzey ad alanıyla başlatmak, düşük düzeyli ad alanına devam ve modülü, sınıf ya da hedef öğe içeren yapısı ile bitmelidir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-125">Start with the highest-level namespace, proceed to the lowest-level namespace, and end with the module, class, or structure containing the target element.</span></span> <span data-ttu-id="80f4e-126">Her bir öğe yolu, kendisini izleyen öğesi içermelidir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-126">Each element in the path must contain the element that follows it.</span></span>  
  
     <span data-ttu-id="80f4e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span><span class="sxs-lookup"><span data-stu-id="80f4e-127">`outerSpace` → `innerSpace` → `holdsTotals` → `totals`</span></span>  
  
3.  <span data-ttu-id="80f4e-128">Niteliğe dize hedef öğe için hazırlayın.</span><span class="sxs-lookup"><span data-stu-id="80f4e-128">Prepare the qualification string for the target element.</span></span> <span data-ttu-id="80f4e-129">Bir süre yerleştirin (`.`) yolundaki her öğesinden sonra.</span><span class="sxs-lookup"><span data-stu-id="80f4e-129">Place a period (`.`) after every element in the path.</span></span> <span data-ttu-id="80f4e-130">Uygulamanızı her öğenin niteliğe dizenizi erişiminiz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="80f4e-130">Your application must have access to every element in your qualification string.</span></span>  
  
    ```vb  
    outerSpace.innerSpace.holdsTotals.totals.  
    ```  
  
4.  <span data-ttu-id="80f4e-131">İfade veya normal şekilde hedef öğesine başvuran atama ifadesi yazın.</span><span class="sxs-lookup"><span data-stu-id="80f4e-131">Write the expression or assignment statement referring to the target element in the normal way.</span></span>  
  
    ```vb  
    grandTotal = 9000  
    ```  
  
5.  <span data-ttu-id="80f4e-132">Hedef öğe adı niteliğe dizesiyle koyun.</span><span class="sxs-lookup"><span data-stu-id="80f4e-132">Precede the target element name with the qualification string.</span></span> <span data-ttu-id="80f4e-133">Adı hemen dönem izlemelidir (`.`) modülü, sınıf veya öğeyi içeren yapısını izler.</span><span class="sxs-lookup"><span data-stu-id="80f4e-133">The name should immediately follow the period (`.`) that follows the module, class, or structure that contains the element.</span></span>  
  
    ```vb  
    ' Assume the following module is part of your code.  
    Module accessGrandTotal  
        Public Sub setGrandTotal()  
            outerSpace.innerSpace.holdsTotals.totals.grandTotal = 9000  
        End Sub  
    End Module  
    ```  
  
6.  <span data-ttu-id="80f4e-134">Derleyici niteliğe dize olduğu hedef öğe başvurusu eşleştirebilirsiniz açık ve anlaşılır bir bildirimi bulmak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="80f4e-134">The compiler uses the qualification string to find a clear, unambiguous declaration to which it can match the target element reference.</span></span>  
  
 <span data-ttu-id="80f4e-135">Uygulamanız aynı ada sahip birden fazla programlama öğesi erişimi varsa bir adı başvurusu nitelemek olabilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-135">You might also have to qualify a name reference if your application has access to more than one programming element that has the same name.</span></span> <span data-ttu-id="80f4e-136">Örneğin, <xref:System.Windows.Forms> ve <xref:System.Web.UI.WebControls> her iki ad alanları içeren bir `Label` sınıfı (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> ve <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="80f4e-136">For example, the <xref:System.Windows.Forms> and <xref:System.Web.UI.WebControls> namespaces both contain a `Label` class (<xref:System.Windows.Forms.Label?displayProperty=nameWithType> and <xref:System.Web.UI.WebControls.Label?displayProperty=nameWithType>).</span></span> <span data-ttu-id="80f4e-137">Uygulamanız her ikisi de kullanıyorsa ya da kendi tanımladığı `Label` sınıfı, farklı ayırdetmek `Label` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="80f4e-137">If your application uses both, or if it defines its own `Label` class, you must distinguish the different `Label` objects.</span></span> <span data-ttu-id="80f4e-138">İçe veya ad alanı diğer adı içinde değişken bildirimi içerir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-138">Include the namespace or import alias in the variable declaration.</span></span> <span data-ttu-id="80f4e-139">Aşağıdaki örnek, içeri aktarma diğer ad kullanır.</span><span class="sxs-lookup"><span data-stu-id="80f4e-139">The following example uses the import alias.</span></span>  
  
```vb  
' The following statement must precede all your declarations.  
Imports win = System.Windows.Forms, web = System.Web.UI.WebControls  
' The following statement references the Windows.Forms.Label class.  
Dim winLabel As New win.Label()  
```  
  
## <a name="members-of-other-containing-elements"></a><span data-ttu-id="80f4e-140">Diğer içeren öğelerini üyeleri</span><span class="sxs-lookup"><span data-stu-id="80f4e-140">Members of Other Containing Elements</span></span>  
 <span data-ttu-id="80f4e-141">Başka bir sınıf veya yapı paylaşılmayan üyesi kullandığınızda, değişken veya sınıf veya yapı örneğine işaret ifade üye adıyla nitelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-141">When you use a nonshared member of another class or structure, you must first qualify the member name with a variable or expression that points to an instance of the class or structure.</span></span> <span data-ttu-id="80f4e-142">Aşağıdaki örnekte, `demoClass` adlı bir sınıf örneği `class1`.</span><span class="sxs-lookup"><span data-stu-id="80f4e-142">In the following example, `demoClass` is an instance of a class named `class1`.</span></span>  
  
```vb  
Dim demoClass As class1 = New class1()  
demoClass.someSub[(argumentlist)]  
```  
  
 <span data-ttu-id="80f4e-143">Değil üyesi nitelemek için sınıf adı kullanamazsınız [paylaşılan](../../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="80f4e-143">You cannot use the class name itself to qualify a member that is not [Shared](../../../../visual-basic/language-reference/modifiers/shared.md).</span></span> <span data-ttu-id="80f4e-144">Önce bir nesne değişkeni örneğini oluşturmanız gerekir (Bu durumda `demoClass`) ve değişken adıyla başvuru.</span><span class="sxs-lookup"><span data-stu-id="80f4e-144">You must first create an instance in an object variable (in this case `demoClass`) and then reference it by the variable name.</span></span>  
  
 <span data-ttu-id="80f4e-145">Bir sınıf veya yapı varsa bir `Shared` üye, bu üye sınıf veya yapı adı veya bir değişkeni veya bir örneğine işaret ifade ile uygun.</span><span class="sxs-lookup"><span data-stu-id="80f4e-145">If a class or structure has a `Shared` member, you can qualify that member either with the class or structure name or with a variable or expression that points to an instance.</span></span>  
  
 <span data-ttu-id="80f4e-146">Bir modül ayrı bir örneğe sahip değil ve tüm üyeleri olan `Shared` varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="80f4e-146">A module does not have any separate instances, and all its members are `Shared` by default.</span></span> <span data-ttu-id="80f4e-147">Bu nedenle, modül adına sahip bir modül üye nitelemek.</span><span class="sxs-lookup"><span data-stu-id="80f4e-147">Therefore, you qualify a module member with the module name.</span></span>  
  
 <span data-ttu-id="80f4e-148">Aşağıdaki örnek, tam modül üye yordam başvurularını gösterir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-148">The following example shows qualified references to module member procedures.</span></span> <span data-ttu-id="80f4e-149">İki örnek bildirir `Sub` yordamları, her ikisi de adlı `perform`, farklı bir proje modüllerde.</span><span class="sxs-lookup"><span data-stu-id="80f4e-149">The example declares two `Sub` procedures, both named `perform`, in different modules in a project.</span></span> <span data-ttu-id="80f4e-150">Her biri kendi modülü içinde niteliğe olmadan belirtildi ancak başka bir yerde gelen başvurulan tam olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-150">Each one can be specified without qualification within its own module but must be qualified if referenced from anywhere else.</span></span> <span data-ttu-id="80f4e-151">Son başvuru olduğundan `module3` uygun değil `perform`, derleyici, başvurusu çözümlenemiyor.</span><span class="sxs-lookup"><span data-stu-id="80f4e-151">Because the final reference in `module3` does not qualify `perform`, the compiler cannot resolve that reference.</span></span>  
  
```vb  
' Assume these three modules are all in the same assembly.  
Module module1  
    Public Sub perform()  
        MsgBox("module1.perform() now returning")  
    End Sub  
End Module  
Module module2  
    Public Sub perform()  
        MsgBox("module2.perform() now returning")  
    End Sub  
    Public Sub doSomething()  
        ' The following statement calls perform in module2, the active module.  
        perform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
    End Sub  
End Module  
Module module3  
    Public Sub callPerform()  
        ' The following statement calls perform in module1.  
        module1.perform()  
        ' The following statement makes an unresolvable name reference  
        ' and therefore generates a COMPILER ERROR.  
        perform() ' INVALID statement  
    End Sub  
End Module  
```  
  
## <a name="references-to-projects"></a><span data-ttu-id="80f4e-152">Proje başvuruları</span><span class="sxs-lookup"><span data-stu-id="80f4e-152">References to Projects</span></span>  
 <span data-ttu-id="80f4e-153">Kullanmak için [ortak](../../../../visual-basic/language-reference/modifiers/public.md) öğesi, başka bir projede tanımlandı ilk ayarlamalısınız bir *başvuru* projenin derleme veya tür kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="80f4e-153">To use [Public](../../../../visual-basic/language-reference/modifiers/public.md) elements defined in another project, you must first set a *reference* to that project's assembly or type library.</span></span> <span data-ttu-id="80f4e-154">Bir başvuru ayarlamak için tıklatın **Başvuru Ekle** üzerinde **proje** menüsü veya kullanım [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) komut satırı derleyici seçeneği.</span><span class="sxs-lookup"><span data-stu-id="80f4e-154">To set a reference, click **Add Reference** on the **Project** menu, or use the [/reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) command-line compiler option.</span></span>  
  
 <span data-ttu-id="80f4e-155">Örneğin, XML nesne modelini kullanabilirsiniz [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="80f4e-155">For example, you can use the XML object model of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="80f4e-156">Bir başvuru ayarlayın, <xref:System.Xml> ad alanı, bildirme ve onun sınıflarından herhangi biriyle gibi kullanma <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="80f4e-156">If you set a reference to the <xref:System.Xml> namespace, you can declare and use any of its classes, such as <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="80f4e-157">Aşağıdaki örnek kullanır <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="80f4e-157">The following example uses <xref:System.Xml.XmlDocument>.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As System.Xml.XmlDocument  
```  
  
## <a name="importing-containing-elements"></a><span data-ttu-id="80f4e-158">Öğeleri içeren içeri aktarma</span><span class="sxs-lookup"><span data-stu-id="80f4e-158">Importing Containing Elements</span></span>  
 <span data-ttu-id="80f4e-159">Kullanabileceğiniz [Imports deyimi (.NET Namespace ve türü)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) için *alma* modüller veya kullanmak istediğiniz sınıfları içeren ad alanları.</span><span class="sxs-lookup"><span data-stu-id="80f4e-159">You can use the [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to *import* the namespaces that contain the modules or classes that you want to use.</span></span> <span data-ttu-id="80f4e-160">Bu, tam olarak nitelikli kendi adlar olmadan içeri aktarılan ad alanında tanımlanan öğe başvurmak sağlar.</span><span class="sxs-lookup"><span data-stu-id="80f4e-160">This enables you to refer to the elements defined in an imported namespace without fully qualifying their names.</span></span> <span data-ttu-id="80f4e-161">Aşağıdaki örnek almak için önceki örnekte yeniden yazar <xref:System.Xml> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="80f4e-161">The following example rewrites the previous example to import the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As XmlDocument  
```  
  
 <span data-ttu-id="80f4e-162">Ayrıca, `Imports` deyimi tanımlayabilirsiniz bir *diğer alma* içeri aktarılan her ad alanı için.</span><span class="sxs-lookup"><span data-stu-id="80f4e-162">In addition, the `Imports` statement can define an *import alias* for each imported namespace.</span></span> <span data-ttu-id="80f4e-163">Bu, kaynak kodu daha kısa ve daha kolay okunabilir hale getirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80f4e-163">This can make the source code shorter and easier to read.</span></span> <span data-ttu-id="80f4e-164">Aşağıdaki örnek kullanmak için önceki örnekte yeniden yazar `xD` için diğer ad olarak <xref:System.Xml> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="80f4e-164">The following example rewrites the previous example to use `xD` as an alias for the <xref:System.Xml> namespace.</span></span>  
  
```vb  
' Assume this project has a reference to System.Xml  
' The following statement must precede all your declarations.  
Imports xD = System.Xml  
' The following statement creates xDoc as an XML document object.  
Dim xDoc As xD.XmlDocument  
```  
  
 <span data-ttu-id="80f4e-165">`Imports` Deyimi yapmaz başka proje öğelerinden uygulamanız için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-165">The `Imports` statement does not make elements from other projects available to your application.</span></span> <span data-ttu-id="80f4e-166">Diğer bir deyişle, bir başvuru ayarlama yer almaz.</span><span class="sxs-lookup"><span data-stu-id="80f4e-166">That is, it does not take the place of setting a reference.</span></span> <span data-ttu-id="80f4e-167">Bir ad alanı yalnızca içeri aktarma, bu ad alanında tanımlı adları nitelemeniz gereksinimini ortadan kaldırır.</span><span class="sxs-lookup"><span data-stu-id="80f4e-167">Importing a namespace just removes the requirement to qualify the names defined in that namespace.</span></span>  
  
 <span data-ttu-id="80f4e-168">Aynı zamanda `Imports` modülleri, sınıflar, yapılar ve numaralandırmalar almak için deyimi.</span><span class="sxs-lookup"><span data-stu-id="80f4e-168">You can also use the `Imports` statement to import modules, classes, structures, and enumerations.</span></span> <span data-ttu-id="80f4e-169">Daha sonra içeri aktarılan bu öğeler niteliğe olmadan üyeleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80f4e-169">You can then use the members of such imported elements without qualification.</span></span> <span data-ttu-id="80f4e-170">Bununla birlikte, her zaman sınıfları ve yapıları değişkeni ya da bir sınıf veya yapı örneğine değerlendirir ifade ile paylaşılmayan üyeleri nitelemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-170">However, you must always qualify nonshared members of classes and structures with a variable or expression that evaluates to an instance of the class or structure.</span></span>  
  
## <a name="naming-guidelines"></a><span data-ttu-id="80f4e-171">Adlandırma yönergeleri</span><span class="sxs-lookup"><span data-stu-id="80f4e-171">Naming Guidelines</span></span>  
 <span data-ttu-id="80f4e-172">Aynı ada sahip iki veya daha fazla programlama öğeleri tanımlarken bir *ad belirsizliği* derleyici bu adı için bir başvuru çözümlemeye çalışırken neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-172">When you define two or more programming elements that have the same name, a *name ambiguity* can result when the compiler attempts to resolve a reference to that name.</span></span> <span data-ttu-id="80f4e-173">Kapsamında birden çok tek bir tanım ise veya tanım kapsamları dahilinde olması durumunda irresolvable başvurudur.</span><span class="sxs-lookup"><span data-stu-id="80f4e-173">If more than one definition is in scope, or if no definition is in scope, the reference is irresolvable.</span></span> <span data-ttu-id="80f4e-174">Örneğin, "Tam başvuru örnek" üzerinde bu yardım sayfasına bakın.</span><span class="sxs-lookup"><span data-stu-id="80f4e-174">For an example, see "Qualified Reference Example" on this Help page.</span></span>  
  
 <span data-ttu-id="80f4e-175">Tüm öğeleri benzersiz adlar sağlayarak ad belirsizliği önleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80f4e-175">You can avoid name ambiguity by giving all your elements unique names.</span></span> <span data-ttu-id="80f4e-176">Daha sonra bir ad alanı, modül veya sınıf adıyla nitelemek gerek kalmadan herhangi bir öğeye başvuru yapabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="80f4e-176">Then you can make reference to any element without having to qualify its name with a namespace, module, or class.</span></span> <span data-ttu-id="80f4e-177">Ayrıca, yanlışlıkla yanlış öğesine başvuran olasılığını de azaltın.</span><span class="sxs-lookup"><span data-stu-id="80f4e-177">You also reduce the chances of accidentally referring to the wrong element.</span></span>  
  
## <a name="shadowing"></a><span data-ttu-id="80f4e-178">Gölgeleme</span><span class="sxs-lookup"><span data-stu-id="80f4e-178">Shadowing</span></span>  
 <span data-ttu-id="80f4e-179">İki programlama öğeleri aynı adı paylaşan, bunlardan birini gizleyebilirsiniz, veya *gölge*, diğerinde.</span><span class="sxs-lookup"><span data-stu-id="80f4e-179">When two programming elements share the same name, one of them can hide, or *shadow*, the other one.</span></span> <span data-ttu-id="80f4e-180">Gölgeli bir öğe için başvuru kullanılabilir değil; Bunun yerine, kodunuzu kullandığında gölgeli öğe adı [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] derleyici onu gölgeleme öğesine giderir.</span><span class="sxs-lookup"><span data-stu-id="80f4e-180">A shadowed element is not available for reference; instead, when your code uses the shadowed element name, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler resolves it to the shadowing element.</span></span> <span data-ttu-id="80f4e-181">Örnekleri içeren daha ayrıntılı bir açıklaması için bkz: [Visual Basic'de gölgeleme](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="80f4e-181">For a more detailed explanation with examples, see [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f4e-182">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="80f4e-182">See Also</span></span>  
 [<span data-ttu-id="80f4e-183">Bildirilen öğe adları</span><span class="sxs-lookup"><span data-stu-id="80f4e-183">Declared Element Names</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [<span data-ttu-id="80f4e-184">Bildirilen öğe özellikleri</span><span class="sxs-lookup"><span data-stu-id="80f4e-184">Declared Element Characteristics</span></span>](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [<span data-ttu-id="80f4e-185">Proje ve çözüm özelliklerini yönetme</span><span class="sxs-lookup"><span data-stu-id="80f4e-185">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="80f4e-186">Değişkenleri</span><span class="sxs-lookup"><span data-stu-id="80f4e-186">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="80f4e-187">Imports deyimi (.NET Namespace ve türü)</span><span class="sxs-lookup"><span data-stu-id="80f4e-187">Imports Statement (.NET Namespace and Type)</span></span>](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [<span data-ttu-id="80f4e-188">New işleci</span><span class="sxs-lookup"><span data-stu-id="80f4e-188">New Operator</span></span>](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [<span data-ttu-id="80f4e-189">Ortak</span><span class="sxs-lookup"><span data-stu-id="80f4e-189">Public</span></span>](../../../../visual-basic/language-reference/modifiers/public.md)