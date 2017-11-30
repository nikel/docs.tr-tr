---
title: "Özel Durum İşleme (Görev Paralel Kitaplığı)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: tasks, exceptions
ms.assetid: beb51e50-9061-4d3d-908c-56a4f7c2e8c1
caps.latest.revision: "21"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e62498376d321d8ff22a53315b9d5f18a8865056
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling-task-parallel-library"></a><span data-ttu-id="e218f-102">Özel Durum İşleme (Görev Paralel Kitaplığı)</span><span class="sxs-lookup"><span data-stu-id="e218f-102">Exception Handling (Task Parallel Library)</span></span>
<span data-ttu-id="e218f-103">İçinde bir görevin çalıştığı kullanıcı kodu tarafından oluşturulan işlenmemiş özel durumlardan geri çağırma akışa dışında bu konunun ilerleyen bölümlerinde açıklanan belirli senaryolarda yayılır.</span><span class="sxs-lookup"><span data-stu-id="e218f-103">Unhandled exceptions that are thrown by user code that is running inside a task are propagated back to the calling thread, except in certain scenarios that are described later in this topic.</span></span> <span data-ttu-id="e218f-104">Özel durumlar statik birini kullandığınızda yayılır veya örnek <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> veya <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` yöntemleri ve işlemek bunları çağrısında kapsayan tarafından bir `try` / `catch` deyimi.</span><span class="sxs-lookup"><span data-stu-id="e218f-104">Exceptions are propagated when you use one of the static or instance <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> or <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` methods, and you handle them by enclosing the call in a `try`/`catch` statement.</span></span> <span data-ttu-id="e218f-105">Ekli alt görevler üst bir görevdir ya da birden çok görevlerde bekleyen varsa, birden çok özel durum.</span><span class="sxs-lookup"><span data-stu-id="e218f-105">If a task is the parent of attached child tasks, or if you are waiting on multiple tasks, multiple exceptions could be thrown.</span></span>  
  
 <span data-ttu-id="e218f-106">Tüm özel durumları çağrı yapan iş parçacığına geri yaymak için, Görev altyapısı onları bir <xref:System.AggregateException> örneği içine sarar.</span><span class="sxs-lookup"><span data-stu-id="e218f-106">To propagate all the exceptions back to the calling thread, the Task infrastructure wraps them in an <xref:System.AggregateException> instance.</span></span> <span data-ttu-id="e218f-107"><xref:System.AggregateException> Özel durum olan bir <xref:System.AggregateException.InnerExceptions%2A> oluşturulan özgün durumlar incelemek için numaralandırılmış ve her biri ele (veya değil tanıtıcı) özelliği ayrı ayrı.</span><span class="sxs-lookup"><span data-stu-id="e218f-107">The <xref:System.AggregateException> exception has an <xref:System.AggregateException.InnerExceptions%2A> property that can be enumerated to examine all the original exceptions that were thrown, and handle (or not handle) each one individually.</span></span> <span data-ttu-id="e218f-108">Kullanarak özgün özel durumlar işleyebilir <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="e218f-108">You can also handle the original exceptions by using the <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="e218f-109">Yalnızca bir özel durum olsa bile, yine de kaydırılan bir <xref:System.AggregateException> aşağıdaki örnekte gösterildiği gibi bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="e218f-109">Even if only one exception is thrown, it is still wrapped in an <xref:System.AggregateException> exception, as the following example shows.</span></span>  
  
 [!code-csharp[TPL_Exceptions#21](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling21.cs#21)]
 [!code-vb[TPL_Exceptions#21](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling21.vb#21)]  
  
 <span data-ttu-id="e218f-110">Yalnızca <xref:System.AggregateException> öğesini yakalayarak ve dahili özel durumların hiç birini gözlemeyerek bir işlenmeyen özel durumu önleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e218f-110">You could avoid an unhandled exception by just catching the <xref:System.AggregateException> and not observing any of the inner exceptions.</span></span> <span data-ttu-id="e218f-111">Ancak, temel yakalama için benzer olduğundan, bunu yapmamanızı öneririz <xref:System.Exception> paralel olmayan senaryolarda türü.</span><span class="sxs-lookup"><span data-stu-id="e218f-111">However, we recommend that you do not do this because it is analogous to catching the base <xref:System.Exception> type in non-parallel scenarios.</span></span> <span data-ttu-id="e218f-112">Bir özel durumu yakalayıp bu durumdan kurtulmak için belirli eylemleri yapmazsanız uygulamanız belirsiz bir durumda kalabilir.</span><span class="sxs-lookup"><span data-stu-id="e218f-112">To catch an exception without taking specific actions to recover from it can leave your program in an indeterminate state.</span></span>  
  
 <span data-ttu-id="e218f-113">Çağrılacak istemiyorsanız <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> veya <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` bir görevin tamamlanmasını bekleme yöntemi de alabilirsiniz <xref:System.AggregateException> görevin öğesinden özel durum <xref:System.Threading.Tasks.Task.Exception%2A> özelliği, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="e218f-113">If you do not want to call the <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> or <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` method to wait for a task's completion, you can also retrieve the <xref:System.AggregateException> exception from the task's <xref:System.Threading.Tasks.Task.Exception%2A> property, as the following example shows.</span></span> <span data-ttu-id="e218f-114">Daha fazla bilgi için bkz: [Task.Exception özelliğini kullanarak özel durumlar Gözlemleme](#ExceptionProp) bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="e218f-114">For more information, see the [Observing Exceptions By Using the Task.Exception Property](#ExceptionProp) section in this topic.</span></span>  
  
 [!code-csharp[TPL_Exceptions#29](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handling22.cs#29)]
 [!code-vb[TPL_Exceptions#29](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handling22.vb#29)]  
  
 <span data-ttu-id="e218f-115">Bir özel durum ya da erişim yayan bir görev bekleme durumunda kendi <xref:System.Threading.Tasks.Task.Exception%2A> özelliği, özel görev çöpünün toplanma olduğunda .NET özel durumu ilkesine göre ilerletilen.</span><span class="sxs-lookup"><span data-stu-id="e218f-115">If you do not wait on a task that propagates an exception, or access its <xref:System.Threading.Tasks.Task.Exception%2A> property, the exception is escalated according to the .NET exception policy when the task is garbage-collected.</span></span>  
  
 <span data-ttu-id="e218f-116">Özel durumlar katılma iş parçacığı geri Kabarcık izin verildiğinde bir görev özel durum oluşturulduktan sonra bazı öğeler işlemeye devam edebilir mümkündür.</span><span class="sxs-lookup"><span data-stu-id="e218f-116">When exceptions are allowed to bubble up back to the joining thread, it is possible that a task may continue to process some items after the exception is raised.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e218f-117">"Sadece kendi kodumu" etkinleştirildiğinde, Visual Studio bazı durumlarda, özel durum oluşturur satır başı ve "özel durum kullanıcı kodu tarafından işlenmiyor." diyen bir hata iletisi görüntülenir</span><span class="sxs-lookup"><span data-stu-id="e218f-117">When "Just My Code" is enabled, Visual Studio in some cases will break on the line that throws the exception and display an error message that says "exception not handled by user code."</span></span> <span data-ttu-id="e218f-118">Bu hata zararsız kaynaklanır.</span><span class="sxs-lookup"><span data-stu-id="e218f-118">This error is benign.</span></span> <span data-ttu-id="e218f-119">F5 tuşuna basarak devam edebilir ve bu örneklerde gösterilen özel durum işleme davranışını görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e218f-119">You can press F5 to continue and see the exception-handling behavior that is demonstrated in these examples.</span></span> <span data-ttu-id="e218f-120">Visual Studio ilk hatada kesilmesini önlemek için yalnızca işaretini **sadece kendi kodumu etkinleştir** altındaki onay kutusunu **Araçlar, seçenekleri, hata ayıklama, genel**.</span><span class="sxs-lookup"><span data-stu-id="e218f-120">To prevent Visual Studio from breaking on the first error, just uncheck the **Enable Just My Code** checkbox under **Tools, Options, Debugging, General**.</span></span>  
  
## <a name="attached-child-tasks-and-nested-aggregateexceptions"></a><span data-ttu-id="e218f-121">Eklenen Alt Görevler ve İç İçe Geçmiş AggregateException Öğeleri</span><span class="sxs-lookup"><span data-stu-id="e218f-121">Attached Child Tasks and Nested AggregateExceptions</span></span>  
 <span data-ttu-id="e218f-122">Bir göreve ekli, özel durum oluşturan bir alt görev varsa, o özel durum üst göreve yayılmadan önce bir <xref:System.AggregateException> öğesi içine sarmalanır ve bu da o özel durumu çağıran iş parçacığına geri yaymadan önce kendi <xref:System.AggregateException> öğesine sarmalar.</span><span class="sxs-lookup"><span data-stu-id="e218f-122">If a task has an attached child task that throws an exception, that exception is wrapped in an <xref:System.AggregateException> before it is propagated to the parent task, which wraps that exception in its own <xref:System.AggregateException> before it propagates it back to the calling thread.</span></span> <span data-ttu-id="e218f-123">Böyle durumlarda, <xref:System.AggregateException.InnerExceptions%2A> özelliği <xref:System.AggregateException> sırasında yakalanan özel durum <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> veya <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` veya <xref:System.Threading.Tasks.Task.WaitAny%2A> veya <xref:System.Threading.Tasks.Task.WaitAll%2A> yöntemini içeren bir veya daha fazla <xref:System.AggregateException> örnekleri değil hatasına neden oldu özgün özel durumlar.</span><span class="sxs-lookup"><span data-stu-id="e218f-123">In such cases, the <xref:System.AggregateException.InnerExceptions%2A> property of the <xref:System.AggregateException> exception that is caught at the <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> or <!--zz <xref:System.Threading.Tasks.Task%601.Wait%2A?displayProperty=nameWithType>  --> `Wait` or <xref:System.Threading.Tasks.Task.WaitAny%2A> or <xref:System.Threading.Tasks.Task.WaitAll%2A> method contains one or more <xref:System.AggregateException> instances, not the original exceptions that caused the fault.</span></span> <span data-ttu-id="e218f-124">Üzerinden yinelemek zorunda kalmamak için iç içe geçmiş <xref:System.AggregateException> kullanabileceğiniz özel durumlar, <xref:System.AggregateException.Flatten%2A> tümünü kaldırmak için yöntem iç içe <xref:System.AggregateException> özel durumlar, böylece <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> özelliği, özgün özel durumları içerir.</span><span class="sxs-lookup"><span data-stu-id="e218f-124">To avoid having to iterate over nested <xref:System.AggregateException> exceptions, you can use the <xref:System.AggregateException.Flatten%2A> method to remove all the nested <xref:System.AggregateException> exceptions, so that the <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> property contains the original exceptions.</span></span> <span data-ttu-id="e218f-125">Aşağıdaki örnekte, iç içe geçmiş <xref:System.AggregateException> örnekleri yalnızca tek bir döngüde düzleştirilip işlenir.</span><span class="sxs-lookup"><span data-stu-id="e218f-125">In the following example, nested <xref:System.AggregateException> instances are flattened and handled in just one loop.</span></span>  
  
 [!code-csharp[TPL_Exceptions#22](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/flatten2.cs#22)]
 [!code-vb[TPL_Exceptions#22](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/flatten2.vb#22)]  
  
 <span data-ttu-id="e218f-126">Aynı zamanda <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> birden çok iç özel durum yeniden oluşturulması için yöntemi <xref:System.AggregateException> tek bir birden çok görevi tarafından oluşturulan örnekleri <xref:System.AggregateException> örneği, aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="e218f-126">You can also use the <xref:System.AggregateException.Flatten%2A?displayProperty=nameWithType> method to rethrow the inner exceptions from multiple <xref:System.AggregateException> instances thrown by multiple tasks in a single <xref:System.AggregateException> instance, as the following example shows.</span></span>  
  
 [!code-csharp[TPL_Exceptions#13](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions2.cs#13)]
 [!code-vb[TPL_Exceptions#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions2.vb#13)]  
  
## <a name="exceptions-from-detached-child-tasks"></a><span data-ttu-id="e218f-127">Ayrılmış Alt Görevlerden Gelen Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="e218f-127">Exceptions from Detached Child Tasks</span></span>  
 <span data-ttu-id="e218f-128">Varsayılan olarak, özel durumlar ayrılmış olarak oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="e218f-128">By default, child tasks are created as detached.</span></span> <span data-ttu-id="e218f-129">Ayrılmış görevlerde oluşturulan özel durumlar bir üst görev içinde işlenmeli ve yeniden harekete geçirilmelidir; bu özel durumlar eklenen alt görevlerde olduğu şekilde çağıran iş parçacığına geri yayılmaz.</span><span class="sxs-lookup"><span data-stu-id="e218f-129">Exceptions thrown from detached tasks must be handled or rethrown in the immediate parent task; they are not propagated back to the calling thread in the same way as attached child tasks propagated back.</span></span> <span data-ttu-id="e218f-130">En üstteki üst el ile bir özel durum olarak sarmalamak neden için ayrılmış bir alt gelen yeniden oluşturulması bir <xref:System.AggregateException> çağıran iş parçacığı geri yayıldığı.</span><span class="sxs-lookup"><span data-stu-id="e218f-130">The topmost parent can manually rethrow an exception from a detached child to cause it to be wrapped in an <xref:System.AggregateException> and propagated back to the calling thread.</span></span>  
  
 [!code-csharp[TPL_Exceptions#23](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/detached21.cs#23)]
 [!code-vb[TPL_Exceptions#23](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/detached21.vb#23)]  
  
 <span data-ttu-id="e218f-131">Bir alt görevdeki özel durumu gözlemek için bir devamlılık kullanıyor olsanız bile, özel durum yine de üst görev tarafından gözlenmelidir.</span><span class="sxs-lookup"><span data-stu-id="e218f-131">Even if you use a continuation to observe an exception in a child task, the exception still must be observed by the parent task.</span></span>  
  
## <a name="exceptions-that-indicate-cooperative-cancellation"></a><span data-ttu-id="e218f-132">Birlikte İptal Olduğunu Belirten Özel Durumlar</span><span class="sxs-lookup"><span data-stu-id="e218f-132">Exceptions That Indicate Cooperative Cancellation</span></span>  
 <span data-ttu-id="e218f-133">Bir görevdeki kullanıcı kodu bir iptal isteğine yanıt verdiğinde, doğru işlem isteğin iletildiği iptal belirtecini geçiren bir <xref:System.OperationCanceledException> öğesi oluşturmaktır.</span><span class="sxs-lookup"><span data-stu-id="e218f-133">When user code in a task responds to a cancellation request, the correct procedure is to throw an <xref:System.OperationCanceledException> passing in the cancellation token on which the request was communicated.</span></span> <span data-ttu-id="e218f-134">Özel durumu yaymadan önce, görev örneği, özel durumdaki belirteci, oluşturulurken geçilen belirteçle karşılaştırır.</span><span class="sxs-lookup"><span data-stu-id="e218f-134">Before it attempts to propagate the exception, the task instance compares the token in the exception to the one that was passed to it when it was created.</span></span> <span data-ttu-id="e218f-135">Aynılarsa, görev, <xref:System.Threading.Tasks.TaskCanceledException> öğesine sarmalanmış bir <xref:System.AggregateException> öğesi oluşturur ve bu öğe, iç özel durumlar incelenirken görülebilir.</span><span class="sxs-lookup"><span data-stu-id="e218f-135">If they are the same, the task propagates a <xref:System.Threading.Tasks.TaskCanceledException> wrapped in the <xref:System.AggregateException>, and it can be seen when the inner exceptions are examined.</span></span> <span data-ttu-id="e218f-136">Ancak, çağıran iş parçacığı görevi beklenmiyor varsa, bu bir özel durum dağıtılmaz.</span><span class="sxs-lookup"><span data-stu-id="e218f-136">However, if the calling thread is not waiting on the task, this specific exception will not be propagated.</span></span> <span data-ttu-id="e218f-137">Daha fazla bilgi için bkz: [görev iptali](../../../docs/standard/parallel-programming/task-cancellation.md).</span><span class="sxs-lookup"><span data-stu-id="e218f-137">For more information, see [Task Cancellation](../../../docs/standard/parallel-programming/task-cancellation.md).</span></span>  
  
 [!code-csharp[TPL_Exceptions#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptions.cs#4)]
 [!code-vb[TPL_Exceptions#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/tpl_exceptions.vb#4)]  
  
## <a name="using-the-handle-method-to-filter-inner-exceptions"></a><span data-ttu-id="e218f-138">İç Özel Durumları Filtrelemek İçin Handle Yöntemini Kullanma</span><span class="sxs-lookup"><span data-stu-id="e218f-138">Using the Handle Method to Filter Inner Exceptions</span></span>  
 <span data-ttu-id="e218f-139">İşlenmiş olarak davranabileceğiniz özel durumları başka bir işleme gerek kalmadan filtrelemek için <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> yöntemini kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e218f-139">You can use the <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> method to filter out exceptions that you can treat as "handled" without using any further logic.</span></span> <span data-ttu-id="e218f-140">İçin sağlanan kullanıcı temsilci olarak <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> yöntemi, özel durum türü inceleyebilirsiniz kendi <xref:System.Exception.Message%2A> özelliği veya zararsız olup olmadığını belirlemenize izin veren diğer hakkında bilgiler.</span><span class="sxs-lookup"><span data-stu-id="e218f-140">In the user delegate that is supplied to the <xref:System.AggregateException.Handle%28System.Func%7BSystem.Exception%2CSystem.Boolean%7D%29?displayProperty=nameWithType> method, you can examine the exception type, its <xref:System.Exception.Message%2A> property, or any other information about it that will let you determine whether it is benign.</span></span> <span data-ttu-id="e218f-141">Temsilci döndüğü özel durumlar `false` yeni bir işlenemezse <xref:System.AggregateException> hemen sonra örnek <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> yöntemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="e218f-141">Any exceptions for which the delegate returns `false` are rethrown in a new <xref:System.AggregateException> instance immediately after the <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> method returns.</span></span>  
  
 <span data-ttu-id="e218f-142">Aşağıdaki örnek ilk örnekte her özel durum inceler Bu konu, işlevsel olarak eşdeğerdir <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="e218f-142">The following example is functionally equivalent to the first example in this topic, which examines each exception in the <xref:System.AggregateException.InnerExceptions%2A?displayProperty=nameWithType> collection.</span></span>  <span data-ttu-id="e218f-143">Bunun yerine, bu özel durum işleyici çağırır <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> yöntemi nesne her özel durumu ve değil yalnızca yeniden oluşturur özel durumlar için `CustomException` örnekleri.</span><span class="sxs-lookup"><span data-stu-id="e218f-143">Instead, this exception handler calls the <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> method object for each exception, and only rethrows exceptions that are not `CustomException` instances.</span></span>  
  
 [!code-csharp[TPL_Exceptions#26](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/handlemethod21.cs#26)]
 [!code-vb[TPL_Exceptions#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/handlemethod21.vb#26)]  
  
 <span data-ttu-id="e218f-144">Aşağıdaki kullanır daha kapsamlı bir örnektir <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> yöntemi için özel işleme sağlamak için bir <xref:System.UnauthorizedAccessException> dosyaları numaralandırılırken özel durum.</span><span class="sxs-lookup"><span data-stu-id="e218f-144">The following is a more complete example that uses the <xref:System.AggregateException.Handle%2A?displayProperty=nameWithType> method to provide special handling for an <xref:System.UnauthorizedAccessException> exception when enumerating files.</span></span>  
  
 [!code-csharp[TPL_Exceptions#12](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/taskexceptions.cs#12)]
 [!code-vb[TPL_Exceptions#12](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/taskexceptions.vb#12)]  
  
<a name="ExceptionProp"></a>   
## <a name="observing-exceptions-by-using-the-taskexception-property"></a><span data-ttu-id="e218f-145">Özel durumlar Task.Exception özelliğini kullanarak Gözlemleme</span><span class="sxs-lookup"><span data-stu-id="e218f-145">Observing Exceptions by Using the Task.Exception Property</span></span>  
 <span data-ttu-id="e218f-146">Eğer bir görev <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> durumunda tamamlanırsa, hatayı tam olarak hangi özel durumun oluşturduğunu bulmak için <xref:System.Threading.Tasks.Task.Exception%2A> özelliği incelenebilir.</span><span class="sxs-lookup"><span data-stu-id="e218f-146">If a task completes in the <xref:System.Threading.Tasks.TaskStatus.Faulted?displayProperty=nameWithType> state, its <xref:System.Threading.Tasks.Task.Exception%2A> property can be examined to discover which specific exception caused the fault.</span></span> <span data-ttu-id="e218f-147"><xref:System.Threading.Tasks.Task.Exception%2A> özelliğini incelemenin iyi bir yolu, aşağıdaki örnekte gösterildiği gibi yalnızca öncül görev hata verirse çalışan bir devamlılık kullanmaktır.</span><span class="sxs-lookup"><span data-stu-id="e218f-147">A good way to observe the <xref:System.Threading.Tasks.Task.Exception%2A> property is to use a continuation that runs only if the antecedent task faults, as shown in the following example.</span></span>  
  
 [!code-csharp[TPL_Exceptions#27](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_exceptions/cs/exceptionprop21.cs#27)]
 [!code-vb[TPL_Exceptions#27](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_exceptions/vb/exceptionprop21.vb#27)]  
  
 <span data-ttu-id="e218f-148">Gerçek bir uygulamada, devamlılık temsilcisi özel durum hakkında ayrıntılı bilgi kaydedebilir ve uygulamayı özel durumdan kurtarmak için yeni görevler oluşturabilir.</span><span class="sxs-lookup"><span data-stu-id="e218f-148">In a real application, the continuation delegate could log detailed information about the exception and possibly spawn new tasks to recover from the exception.</span></span>  
  
## <a name="unobservedtaskexception-event"></a><span data-ttu-id="e218f-149">UnobservedTaskException Olayı</span><span class="sxs-lookup"><span data-stu-id="e218f-149">UnobservedTaskException Event</span></span>  
 <span data-ttu-id="e218f-150">Güvenilmeyen eklentileri barındırmak gibi bazı senaryolarda, zararsız özel durumlar sık gerçekleşebilir ve hepsini el ile gözlemek çok zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="e218f-150">In some scenarios, such as when hosting untrusted plug-ins, benign exceptions might be common, and it might be too difficult to manually observe them all.</span></span> <span data-ttu-id="e218f-151">Bu durumlarda, <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType> olayını işleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e218f-151">In these cases, you can handle the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=nameWithType> event.</span></span> <span data-ttu-id="e218f-152">İşleyicinize geçirilen <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType> örneği, gözlemlenmemiş özel durumun birleşen iş parçacığına geri yayılmasını önlemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e218f-152">The <xref:System.Threading.Tasks.UnobservedTaskExceptionEventArgs?displayProperty=nameWithType> instance that is passed to your handler can be used to prevent the unobserved exception from being propagated back to the joining thread.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e218f-153">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e218f-153">See Also</span></span>  
 [<span data-ttu-id="e218f-154">Görev paralel kitaplığı (TPL)</span><span class="sxs-lookup"><span data-stu-id="e218f-154">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)