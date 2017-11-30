---
title: "Kaynak Yönetimi: use Anahtar Sözcüğü (F#)"
description: "F # anahtar sözcüğü 'use' ve yayın kaynakların ve başlatma denetleyebilirsiniz 'kullanılarak' işlevi hakkında bilgi edinin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 00c3040e-859f-4dad-a7b5-7b8d44dc232c
ms.openlocfilehash: d4e8626f07f1c77e52e8fabd5ccc07dbf1fa8ddd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="resource-management-the-use-keyword"></a><span data-ttu-id="c7cda-104">Kaynak Yönetimi: use Anahtar Sözcüğü</span><span class="sxs-lookup"><span data-stu-id="c7cda-104">Resource Management: The use Keyword</span></span>

<span data-ttu-id="c7cda-105">Bu konu, anahtar sözcüğü açıklar `use` ve `using` başlatma ve kaynakları sürümü kontrol edebilirsiniz işlevi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-105">This topic describes the keyword `use` and the `using` function, which can control the initialization and release of resources.</span></span>

## <a name="resources"></a><span data-ttu-id="c7cda-106">Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="c7cda-106">Resources</span></span>
<span data-ttu-id="c7cda-107">Terim *kaynak* birden fazla şekilde kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c7cda-107">The term *resource* is used in more than one way.</span></span> <span data-ttu-id="c7cda-108">Kaynak dizeleri, grafik ve benzeri gibi ancak bu bağlamda bir uygulamanın kullandığı veri Evet, olabilir *kaynakları* grafik cihaz bağlamları, dosya tanıtıcısı, ağ gibi yazılım ve işletim sistemi kaynaklarına başvuruyor ve veritabanı bağlantıları, bekleme tanıtıcıları vb. gibi eşzamanlılık nesneleri.</span><span class="sxs-lookup"><span data-stu-id="c7cda-108">Yes, resources can be data that an application uses, such as strings, graphics, and the like, but in this context, *resources* refers to software or operating system resources, such as graphics device contexts, file handles, network and database connections, concurrency objects such as wait handles, and so on.</span></span> <span data-ttu-id="c7cda-109">Bu kaynakların uygulamalar tarafından kullanımını işletim sistemi veya başka bir uygulamaya sağlanan böylece daha sonraki bir sürümü kaynak tarafından havuzuna ve ardından diğer kaynak sağlayıcısı kaynaktan alımını içerir.</span><span class="sxs-lookup"><span data-stu-id="c7cda-109">The use of these resources by applications involves the acquisition of the resource from the operating system or other resource provider, followed by the later release of the resource to the pool so that it can be provided to another application.</span></span> <span data-ttu-id="c7cda-110">Uygulamaları ortak havuzuna kaynakları serbest bırakmak değil sorunları oluşur.</span><span class="sxs-lookup"><span data-stu-id="c7cda-110">Problems occur when applications do not release resources back to the common pool.</span></span>

## <a name="managing-resources"></a><span data-ttu-id="c7cda-111">Kaynakları yönetme</span><span class="sxs-lookup"><span data-stu-id="c7cda-111">Managing Resources</span></span>
<span data-ttu-id="c7cda-112">Bir uygulamadaki kaynakları verimli bir şekilde ve sorumlu bir şekilde yönetmek için hemen ve tahmin edilebilir bir şekilde kaynakları serbest bırakmalısınız.</span><span class="sxs-lookup"><span data-stu-id="c7cda-112">To efficiently and responsibly manage resources in an application, you must release resources promptly and in a predictable manner.</span></span> <span data-ttu-id="c7cda-113">.NET Framework sağlayarak bunu yardımcı olan `System.IDisposable` arabirimi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-113">The .NET Framework helps you do this by providing the `System.IDisposable` interface.</span></span> <span data-ttu-id="c7cda-114">Uygulayan bir tür `System.IDisposable` sahip `System.IDisposable.Dispose` doğru kaynakları serbest bırakır yöntemi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-114">A type that implements `System.IDisposable` has the `System.IDisposable.Dispose` method, which correctly frees resources.</span></span> <span data-ttu-id="c7cda-115">İyi yazılmış uygulamalar garanti `System.IDisposable.Dispose` sınırlı bir kaynağa tutan herhangi bir nesne artık gerekli olmadığında derhal denir.</span><span class="sxs-lookup"><span data-stu-id="c7cda-115">Well-written applications guarantee that `System.IDisposable.Dispose` is called promptly when any object that holds a limited resource is no longer needed.</span></span> <span data-ttu-id="c7cda-116">Neyse ki, çoğu .NET dillerini kolaylaştırmak için destek sağlar ve F # aynı durum geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="c7cda-116">Fortunately, most .NET languages provide support to make this easier, and F# is no exception.</span></span> <span data-ttu-id="c7cda-117">Dispose deseni destekleyen iki yararlı dil yapıları vardır: `use` bağlama ve `using` işlevi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-117">There are two useful language constructs that support the dispose pattern: the `use` binding and the `using` function.</span></span>

## <a name="use-binding"></a><span data-ttu-id="c7cda-118">Bağlama kullanın</span><span class="sxs-lookup"><span data-stu-id="c7cda-118">use Binding</span></span>
<span data-ttu-id="c7cda-119">`use` Anahtar sözcüğü vardır, benzer bir form `let` bağlama:</span><span class="sxs-lookup"><span data-stu-id="c7cda-119">The `use` keyword has a form that resembles that of the `let` binding:</span></span>

<span data-ttu-id="c7cda-120">kullanmak *değeri* = *ifadesi*</span><span class="sxs-lookup"><span data-stu-id="c7cda-120">use *value* = *expression*</span></span>

<span data-ttu-id="c7cda-121">İle aynı işlevselliği sağlayan bir `let` bağlama ancak yapılan bir çağrı ekler `Dispose` değeri kapsam dışına çıktığında değeri.</span><span class="sxs-lookup"><span data-stu-id="c7cda-121">It provides the same functionality as a `let` binding but adds a call to `Dispose` on the value when the value goes out of scope.</span></span> <span data-ttu-id="c7cda-122">Değeri olması durumunda olacak şekilde derleyici değeri, null denetimi ekler Not `null`, çağrısı `Dispose` değil denenir.</span><span class="sxs-lookup"><span data-stu-id="c7cda-122">Note that the compiler inserts a null check on the value, so that if the value is `null`, the call to `Dispose` is not attempted.</span></span>

<span data-ttu-id="c7cda-123">Aşağıdaki örnek, bir dosyayı kullanarak otomatik olarak kapatmak gösterilmiştir `use` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="c7cda-123">The following example shows how to close a file automatically by using the `use` keyword.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6301.fs)]

>[!NOTE]
<span data-ttu-id="c7cda-124">Kullanabileceğiniz `use` hesaplama ifadelerde özelleştirilmiş bir sürümünü durumda içinde `use` ifade kullanılır.</span><span class="sxs-lookup"><span data-stu-id="c7cda-124">You can use `use` in computation expressions, in which case a customized version of the `use` expression is used.</span></span> <span data-ttu-id="c7cda-125">Daha fazla bilgi için bkz: [sıraları](sequences.md), [zaman uyumsuz iş akışları](asynchronous-workflows.md), ve [hesaplama ifadeleri](computation-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="c7cda-125">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>


## <a name="using-function"></a><span data-ttu-id="c7cda-126">using işlevi</span><span class="sxs-lookup"><span data-stu-id="c7cda-126">using Function</span></span>
<span data-ttu-id="c7cda-127">`using` İşlevi aşağıdaki biçime sahiptir:</span><span class="sxs-lookup"><span data-stu-id="c7cda-127">The `using` function has the following form:</span></span>

<span data-ttu-id="c7cda-128">`using`(*İfade1*) *işlevi veya lambda*</span><span class="sxs-lookup"><span data-stu-id="c7cda-128">`using` (*expression1*) *function-or-lambda*</span></span>

<span data-ttu-id="c7cda-129">İçinde bir `using` ifadesi *İfade1* çıkarılması gerekir nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c7cda-129">In a `using` expression, *expression1* creates the object that must be disposed.</span></span> <span data-ttu-id="c7cda-130">Sonucu *İfade1* (çıkarılması gerekir nesnesi) bir bağımsız değişken hale *değeri*, *işlevi veya lambda*, tek bir bekliyor ya da bir işlevi olan bağımsız değişken değeri ile eşleşen bir tür kalan üretilen *İfade1*, ya da bu türünde bir bağımsız değişken bekler bir lambda ifadesi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-130">The result of *expression1* (the object that must be disposed) becomes an argument, *value*, to *function-or-lambda*, which is either a function that expects a single remaining argument of a type that matches the value produced by *expression1*, or a lambda expression that expects an argument of that type.</span></span> <span data-ttu-id="c7cda-131">Çalışma zamanı yürütme işlevi işlemi sonunda, çağıran `Dispose` ve kaynakları serbest bırakır (değer değilse `null`, bu durumda Dispose çağrısı bulunulmadı).</span><span class="sxs-lookup"><span data-stu-id="c7cda-131">At the end of the execution of the function, the runtime calls `Dispose` and frees the resources (unless the value is `null`, in which case the call to Dispose is not attempted).</span></span>

<span data-ttu-id="c7cda-132">Aşağıdaki örnekte gösterilmiştir `using` lambda ifadesi ile ifadesi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-132">The following example demonstrates the `using` expression with a lambda expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6302.fs)]

<span data-ttu-id="c7cda-133">Sonraki örnekte gösterildiği `using` bir işlevi olan ifade.</span><span class="sxs-lookup"><span data-stu-id="c7cda-133">The next example shows the `using` expression with a function.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6303.fs)]

<span data-ttu-id="c7cda-134">Not işlevi bazı bağımsız değişkenler uygulanmış olan bir işlev olabilir.</span><span class="sxs-lookup"><span data-stu-id="c7cda-134">Note that the function could be a function that has some arguments applied already.</span></span> <span data-ttu-id="c7cda-135">Aşağıdaki kod örneğinde bu gösterir.</span><span class="sxs-lookup"><span data-stu-id="c7cda-135">The following code example demonstrates this.</span></span> <span data-ttu-id="c7cda-136">Dizeyi içeren bir dosya oluşturur `XYZ`.</span><span class="sxs-lookup"><span data-stu-id="c7cda-136">It creates a file that contains the string `XYZ`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6304.fs)]

<span data-ttu-id="c7cda-137">`using` İşlevi ve `use` aynı şeyi yapmanın neredeyse eşdeğer yolu bağlanır.</span><span class="sxs-lookup"><span data-stu-id="c7cda-137">The `using` function and the `use` binding are nearly equivalent ways to accomplish the same thing.</span></span> <span data-ttu-id="c7cda-138">`using` Anahtar sözcüğü ne zaman üzerinde daha fazla denetim sağlar `Dispose` olarak adlandırılır.</span><span class="sxs-lookup"><span data-stu-id="c7cda-138">The `using` keyword provides more control over when `Dispose` is called.</span></span> <span data-ttu-id="c7cda-139">Kullandığınızda `using`, `Dispose` kullandığınızda işlevi veya lambda ifadesi; sonunda çağrılır `use` anahtar sözcüğü, `Dispose` içeren kod bloğu sonunda çağrılır.</span><span class="sxs-lookup"><span data-stu-id="c7cda-139">When you use `using`, `Dispose` is called at the end of the function or lambda expression; when you use the `use` keyword, `Dispose` is called at the end of the containing code block.</span></span> <span data-ttu-id="c7cda-140">Genel olarak, kullanmayı tercih ederseniz `use` yerine `using` işlevi.</span><span class="sxs-lookup"><span data-stu-id="c7cda-140">In general, you should prefer to use `use` instead of the `using` function.</span></span>


## <a name="see-also"></a><span data-ttu-id="c7cda-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c7cda-141">See Also</span></span>
[<span data-ttu-id="c7cda-142">F # dili başvurusu</span><span class="sxs-lookup"><span data-stu-id="c7cda-142">F# Language Reference</span></span>](index.md)