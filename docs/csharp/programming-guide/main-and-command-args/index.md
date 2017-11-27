---
title: "Ana() ve komut satırı bağımsız değişkenleri (C# programlama Kılavuzu)"
ms.date: 08/02/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab0b93a867ecf252bffd529d284ef9ddcc9163ba
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="43602-102">Ana() ve komut satırı bağımsız değişkenleri (C# programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="43602-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="43602-103">`Main` Yöntemi bir C# uygulamasının giriş noktasıdır.</span><span class="sxs-lookup"><span data-stu-id="43602-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="43602-104">(Kitaplıkları ve Hizmetleri gerektirmez bir `Main` yöntemi bir giriş noktası olarak.) Uygulama başlatıldığında `Main` çağrılan ilk yöntemi bir yöntemdir.</span><span class="sxs-lookup"><span data-stu-id="43602-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="43602-105">Yalnızca bir giriş noktası bir C# programında olabilir.</span><span class="sxs-lookup"><span data-stu-id="43602-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="43602-106">Sahip birden fazla sınıf varsa bir `Main` yöntemi, programınızla birlikte derleme gerekir **/ana** belirtmek için derleyici seçeneği `Main` giriş noktası olarak kullanılacak yöntemi.</span><span class="sxs-lookup"><span data-stu-id="43602-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="43602-107">Daha fazla bilgi için bkz: [/Main (C# Derleyici Seçenekleri)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="43602-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a><span data-ttu-id="43602-108">Genel Bakış</span><span class="sxs-lookup"><span data-stu-id="43602-108">Overview</span></span>

- <span data-ttu-id="43602-109">`Main` Yöntemi bir yürütülebilir program giriş noktasıdır; burada program denetimini başlar ve biter değildir.</span><span class="sxs-lookup"><span data-stu-id="43602-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="43602-110">`Main`bir sınıf veya yapı içinde bildirildi.</span><span class="sxs-lookup"><span data-stu-id="43602-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="43602-111">`Main`olmalıdır [statik](../../../csharp/language-reference/keywords/static.md) ve olmaması [ortak](../../../csharp/language-reference/keywords/public.md).</span><span class="sxs-lookup"><span data-stu-id="43602-111">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="43602-112">(Önceki örnekte, varsayılan erişimini aldığı [özel](../../../csharp/language-reference/keywords/private.md).) Kapsayan sınıfta veya yapı statik olması gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="43602-112">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="43602-113">`Main`ya da sahip bir `void`, `int`, veya C# ile 7.1, başlangıç `Task`, veya `Task<int>` dönüş türü.</span><span class="sxs-lookup"><span data-stu-id="43602-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="43602-114">Yalnızca ve yalnızca, `Main` döndüren bir `Task` veya `Task<int>`, bildirimi `Main` içerebilir [ `async` ](../../language-reference/keywords/async.md) değiştiricisi.</span><span class="sxs-lookup"><span data-stu-id="43602-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="43602-115">Bu özellikle dışlar Not bir `async void Main` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="43602-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="43602-116">`Main` Yöntemi ile veya olmadan bildirilebilir bir `string[]` komut satırı bağımsız değişkenleri içeriyor parametresi.</span><span class="sxs-lookup"><span data-stu-id="43602-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="43602-117">Kullanırken [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] Windows uygulamaları oluşturmak için parametre el ile ekleyin Aksi takdirde kullanmak <xref:System.Environment> komut satırı bağımsız değişkenlerini elde etmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="43602-117">When using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="43602-118">Parametre sıfır dizinli komut satırı bağımsız değişkenleri okunur.</span><span class="sxs-lookup"><span data-stu-id="43602-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="43602-119">C ve C++ aksine, programın adı ilk komut satırı bağımsız değişkeni işlenmez.</span><span class="sxs-lookup"><span data-stu-id="43602-119">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="43602-120">Eklenmesi `async` ve `Task`, `Task<int>` türleri basitleştirir program kodunu konsol uygulamaları başlaması gerekiyorsa dönün ve `await` zaman uyumsuz işlemleri `Main`.</span><span class="sxs-lookup"><span data-stu-id="43602-120">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="43602-121">C# dili belirtimi</span><span class="sxs-lookup"><span data-stu-id="43602-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="43602-122">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="43602-122">See also</span></span>
<span data-ttu-id="43602-123">[Csc.exe ile komut satırı derleme](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
[C# programlama kılavuzu](../../../csharp/programming-guide/index.md)
[yöntemleri](../../../csharp/programming-guide/classes-and-structs/methods.md)
[bir C# programı içinde](../../../csharp/programming-guide/inside-a-program/index.md)</span><span class="sxs-lookup"><span data-stu-id="43602-123">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
[C# Programming Guide](../../../csharp/programming-guide/index.md)
[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md)
[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md)</span></span>