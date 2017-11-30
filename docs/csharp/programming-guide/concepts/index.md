---
title: "Programlama Kavramları (C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 3227afd5-4794-484b-b83b-0f1f94a0476b
caps.latest.revision: "4"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9c82430ec58b81f37a33f4c246ea40f6da465af8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="programming-concepts-c"></a><span data-ttu-id="7748d-102">Programlama Kavramları (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-102">Programming Concepts (C#)</span></span>
<span data-ttu-id="7748d-103">Bu bölümde, C# dilinde programlama kavramları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7748d-103">This section explains programming concepts in the C# language.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7748d-104">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="7748d-104">In This Section</span></span>  
  
|<span data-ttu-id="7748d-105">Başlık</span><span class="sxs-lookup"><span data-stu-id="7748d-105">Title</span></span>|<span data-ttu-id="7748d-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7748d-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="7748d-107">Derlemeler ve Genel Derleme Önbelleği (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-107">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../csharp/programming-guide/concepts/assemblies-gac/index.md)|<span data-ttu-id="7748d-108">Derlemeler oluşturma ve kullanma açıklar.</span><span class="sxs-lookup"><span data-stu-id="7748d-108">Describes how to create and use assemblies.</span></span>|  
|[<span data-ttu-id="7748d-109">Zaman uyumsuz programlama ile async ve await (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-109">Asynchronous Programming with async and await (C#)</span></span>](../../../csharp/programming-guide/concepts/async/index.md)|<span data-ttu-id="7748d-110">Zaman uyumsuz çözümleri kullanarak yazma açıklar [zaman uyumsuz](../../../csharp/language-reference/keywords/async.md) ve [await](../../../csharp/language-reference/keywords/await.md) C# anahtar sözcükleri.</span><span class="sxs-lookup"><span data-stu-id="7748d-110">Describes how to write asynchronous solutions by using the [async](../../../csharp/language-reference/keywords/async.md) and [await](../../../csharp/language-reference/keywords/await.md) keywords in C#.</span></span> <span data-ttu-id="7748d-111">Bir kılavuz içerir.</span><span class="sxs-lookup"><span data-stu-id="7748d-111">Includes a walkthrough.</span></span>|  
|[<span data-ttu-id="7748d-112">Öznitelikler (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-112">Attributes (C#)</span></span>](../../../csharp/programming-guide/concepts/attributes/index.md)|<span data-ttu-id="7748d-113">Öznitelikleri kullanarak türleri, alanları, yöntemleri ve özellikleri gibi programlama hakkında ek bilgi sağlamak nasıl ele alınmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7748d-113">Discusses how to provide additional information about programming elements such as types, fields, methods, and properties by using attributes.</span></span>|  
|[<span data-ttu-id="7748d-114">Arayan bilgileri (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-114">Caller Information (C#)</span></span>](../../../csharp/programming-guide/concepts/caller-information.md)|<span data-ttu-id="7748d-115">Bir yöntemin çağıran hakkında bilgi edinmek açıklar.</span><span class="sxs-lookup"><span data-stu-id="7748d-115">Describes how to obtain information about the caller of a method.</span></span> <span data-ttu-id="7748d-116">Bu bilgiler, dosya yolunu ve kaynak kodu satır sayısı ve arayan üye adı içerir.</span><span class="sxs-lookup"><span data-stu-id="7748d-116">This information includes the file path and the line number of the source code and the member name of the caller.</span></span>|  
|[<span data-ttu-id="7748d-117">Koleksiyonlar (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-117">Collections (C#)</span></span>](../../../csharp/programming-guide/concepts/collections.md)|<span data-ttu-id="7748d-118">.NET Framework tarafından sağlanan koleksiyonları türlerini bazıları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7748d-118">Describes some of the types of collections provided by the .NET Framework.</span></span> <span data-ttu-id="7748d-119">Basit koleksiyonlar ve anahtar/değer çiftlerinin koleksiyonu nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="7748d-119">Demonstrates how to use simple collections and collections of key/value pairs.</span></span>|  
|[<span data-ttu-id="7748d-120">Kovaryans ve kontravaryans (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-120">Covariance and Contravariance (C#)</span></span>](../../../csharp/programming-guide/concepts/covariance-contravariance/index.md)|<span data-ttu-id="7748d-121">Genel tür parametreleri arabirimleri ve temsilciler örtük dönüştürülmesini etkinleştirmek gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="7748d-121">Shows how to enable implicit conversion of generic type parameters in interfaces and delegates.</span></span>|  
|[<span data-ttu-id="7748d-122">İfade ağaçları (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-122">Expression Trees (C#)</span></span>](../../../csharp/programming-guide/concepts/expression-trees/index.md)|<span data-ttu-id="7748d-123">Dinamik yürütülebilir kodunun değiştirilmesini etkinleştirmek için ifade ağaçları nasıl kullanabileceğiniz açıklanır.</span><span class="sxs-lookup"><span data-stu-id="7748d-123">Explains how you can use expression trees to enable dynamic modification of executable code.</span></span>|  
|[<span data-ttu-id="7748d-124">Yineleyiciler (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-124">Iterators (C#)</span></span>](../../../csharp/programming-guide/concepts/iterators.md)|<span data-ttu-id="7748d-125">Koleksiyonlar üzerinden adım ve öğeleri tek bir defada döndürmek için kullanılan yineleyiciler açıklar.</span><span class="sxs-lookup"><span data-stu-id="7748d-125">Describes iterators, which are used to step through collections and return elements one at a time.</span></span>|  
|[<span data-ttu-id="7748d-126">Dil ile tümleşik sorgu (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-126">Language-Integrated Query (LINQ) (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/index.md)|<span data-ttu-id="7748d-127">C# dili sözdizimi ve ilişkisel veritabanları, XML belgeleri, veri kümeleri ve bellek içi koleksiyonları sorgulamak için model güçlü sorgu özellikleri açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7748d-127">Discusses the powerful query capabilities in the language syntax of C#, and the model for querying relational databases, XML documents, datasets, and in-memory collections.</span></span>|  
|[<span data-ttu-id="7748d-128">Nesne odaklı programlama (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-128">Object-Oriented Programming (C#)</span></span>](../../../csharp/programming-guide/concepts/object-oriented-programming.md)|<span data-ttu-id="7748d-129">Kapsülleme, devralma ve çok biçimlilik gibi ortak nesne yönelimli kavramlarını açıklar.</span><span class="sxs-lookup"><span data-stu-id="7748d-129">Describes common object-oriented concepts, including encapsulation, inheritance, and polymorphism.</span></span>|  
|[<span data-ttu-id="7748d-130">Yansıma (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-130">Reflection (C#)</span></span>](../../../csharp/programming-guide/concepts/reflection.md)|<span data-ttu-id="7748d-131">Yansıma dinamik olarak bir türünün bir örneği oluşturmak, var olan bir nesne için bağ türü veya varolan bir nesneden türünü almak ve onun yöntemleri çağırma veya özellikleri ve alanları erişim için nasıl kullanılacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="7748d-131">Explains how to use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span>|  
|[<span data-ttu-id="7748d-132">Seri hale getirme (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-132">Serialization (C# )</span></span>](../../../csharp/programming-guide/concepts/serialization/index.md)|<span data-ttu-id="7748d-133">İkili dosya, XML, anahtar kavramlarını açıklar ve SOAP seri hale getirme.</span><span class="sxs-lookup"><span data-stu-id="7748d-133">Describes key concepts in binary, XML, and SOAP serialization.</span></span>|  
|[<span data-ttu-id="7748d-134">İş parçacığı (C#)</span><span class="sxs-lookup"><span data-stu-id="7748d-134">Threading (C#)</span></span>](../../../csharp/programming-guide/concepts/threading/index.md)|<span data-ttu-id="7748d-135">.NET iş parçacığı modeline genel bakış sağlar ve uygulamalarınızın yanıtlama hızı ve performansı artırmak için aynı anda birden çok görevleri gerçekleştirir kodunun nasıl yazılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="7748d-135">Provides an overview of the .NET threading model and shows how to write code that performs multiple tasks at the same time to improve the performance and responsiveness of your applications.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="7748d-136">İlgili Bölümler</span><span class="sxs-lookup"><span data-stu-id="7748d-136">Related Sections</span></span>  
  
|||  
|---|---|  
|<span data-ttu-id="7748d-137">[Performans İpuçları](https://msdn.microsoft.com/library/ms173196(VS.110).aspx)</span><span class="sxs-lookup"><span data-stu-id="7748d-137">[Performance Tips](https://msdn.microsoft.com/library/ms173196(VS.110).aspx)</span></span> | <span data-ttu-id="7748d-138">Uygulamanızın performansını artırmaya yardımcı olabilecek çeşitli temel kurallar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7748d-138">Discusses several basic rules that may help you increase the performance of your application.</span></span>|