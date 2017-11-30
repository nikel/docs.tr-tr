---
title: "Zaman uyumsuz etkinlikleri WF içinde oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 497e81ed-5eef-460c-ba55-fae73c05824f
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f2fd247348050b8335f4f6354c88664d497dbbf2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-asynchronous-activities-in-wf"></a><span data-ttu-id="418fb-102">Zaman uyumsuz etkinlikleri WF içinde oluşturma</span><span class="sxs-lookup"><span data-stu-id="418fb-102">Creating Asynchronous Activities in WF</span></span>
<span data-ttu-id="418fb-103"><xref:System.Activities.AsyncCodeActivity>Etkinlik yazarlar etkinleştirir ve zaman uyumsuz yürütme mantığını uygulamak için etkinlikler türetilmiş kullanmak için bir temel sınıf sağlar.</span><span class="sxs-lookup"><span data-stu-id="418fb-103"><xref:System.Activities.AsyncCodeActivity> provides activity authors a base class to use that enables derived activities to implement asynchronous execution logic.</span></span> <span data-ttu-id="418fb-104">Bu, zaman uyumsuz iş akışı Zamanlayıcı iş parçacığı tutan ve paralel olarak çalıştırılabilmesi için hiç etkinlik engelleme olmadan gerçekleştirmelisiniz özel etkinlikler için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="418fb-104">This is useful for custom activities that must perform asynchronous work without holding the workflow scheduler thread and blocking any activities that may be able to run in parallel.</span></span> <span data-ttu-id="418fb-105">Bu konu kullanarak zaman uyumsuz özel etkinlikler oluşturmak nasıl bir bakış sunar <xref:System.Activities.AsyncCodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="418fb-105">This topic provides an overview of how to create custom asynchronous activities using <xref:System.Activities.AsyncCodeActivity>.</span></span>  
  
## <a name="using-asynccodeactivity"></a><span data-ttu-id="418fb-106">AsyncCodeActivity kullanma</span><span class="sxs-lookup"><span data-stu-id="418fb-106">Using AsyncCodeActivity</span></span>  
 <span data-ttu-id="418fb-107"><xref:System.Activities?displayProperty=nameWithType>Özel Etkinlik yazarlar farklı temel sınıflarının farklı etkinlik yazma gereksinimlerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="418fb-107"><xref:System.Activities?displayProperty=nameWithType> provides custom activity authors with different base classes for different activity authoring requirements.</span></span> <span data-ttu-id="418fb-108">Her biri belirli bir anlam taşır ve iş akışı yazarı (ve etkinlik çalışma zamanı) karşılık gelen bir sözleşme sağlar.</span><span class="sxs-lookup"><span data-stu-id="418fb-108">Each one carries a particular semantic and provides a workflow author (and the activity runtime) a corresponding contract.</span></span> <span data-ttu-id="418fb-109">Bir <xref:System.Activities.AsyncCodeActivity> tabanlı etkinliktir iş Zamanlayıcı göre zaman uyumsuz olarak gerçekleştirdiği etkinlik yönetilen kodda iş parçacığı ve, yürütme mantığını cinsinden ifade edilir.</span><span class="sxs-lookup"><span data-stu-id="418fb-109">An <xref:System.Activities.AsyncCodeActivity> based activity is an activity that performs work asynchronously relative to the scheduler thread and whose execution logic is expressed in managed code.</span></span> <span data-ttu-id="418fb-110">Zaman uyumsuz, giden sonucunda bir <xref:System.Activities.AsyncCodeActivity> boşta noktanız yürütme sırasında anlamına.</span><span class="sxs-lookup"><span data-stu-id="418fb-110">As a result of going asynchronous, an <xref:System.Activities.AsyncCodeActivity> may induce an idle point during execution.</span></span> <span data-ttu-id="418fb-111">Zaman uyumsuz iş volatile doğası nedeniyle bir <xref:System.Activities.AsyncCodeActivity> her zaman etkinliğin yürütme süresi için hiçbir kalan bloğu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="418fb-111">Due to the volatile nature of asynchronous work, an <xref:System.Activities.AsyncCodeActivity> always creates a no persist block for the duration of the activity’s execution.</span></span> <span data-ttu-id="418fb-112">Bu iş akışı çalışma zamanı iş akışı örneği zaman uyumsuz iş ortasında kalıcı ve ayrıca kaldırma sırada'den zaman uyumsuz kod yürütme iş akışı örneği engeller.</span><span class="sxs-lookup"><span data-stu-id="418fb-112">This prevents the workflow runtime from persisting the workflow instance in the middle of the asynchronous work, and also prevents the workflow instance from unloading while the asynchronous code is executing.</span></span>  
  
### <a name="asynccodeactivity-methods"></a><span data-ttu-id="418fb-113">AsyncCodeActivity yöntemleri</span><span class="sxs-lookup"><span data-stu-id="418fb-113">AsyncCodeActivity Methods</span></span>  
 <span data-ttu-id="418fb-114">Öğesinden türetilen etkinlikleri <xref:System.Activities.AsyncCodeActivity> zaman uyumsuz yürütme mantığını kılarak oluşturabilirsiniz <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> ve <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> özel kod yöntemleriyle.</span><span class="sxs-lookup"><span data-stu-id="418fb-114">Activities that derive from <xref:System.Activities.AsyncCodeActivity> can create asynchronous execution logic by overriding the <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> and <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> methods with custom code.</span></span> <span data-ttu-id="418fb-115">Çalışma zamanı tarafından çağrıldığında, bu yöntemleri geçirilen bir <xref:System.Activities.AsyncCodeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="418fb-115">When called by the runtime, these methods are passed an <xref:System.Activities.AsyncCodeActivityContext>.</span></span> <span data-ttu-id="418fb-116"><xref:System.Activities.AsyncCodeActivityContext>Paylaşılan durum arasında sağlamak üzere etkinlik Yazar verir <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> /  <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> bağlamın içinde <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="418fb-116"><xref:System.Activities.AsyncCodeActivityContext> allows the activity author to provide shared state across <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>/ <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> in the context’s <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> property.</span></span> <span data-ttu-id="418fb-117">Aşağıdaki örnekte, bir `GenerateRandom` etkinlik rastgele bir sayı zaman uyumsuz olarak oluşturur.</span><span class="sxs-lookup"><span data-stu-id="418fb-117">In the following example, a `GenerateRandom` activity generates a random number asynchronously.</span></span>  
  
 [!code-csharp[CFX_ActivityExample#8](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#8)]  
  
 <span data-ttu-id="418fb-118">Önceki örnek etkinlik türetilen <xref:System.Activities.AsyncCodeActivity%601>, ve yükseltilmiş `OutArgument<int>` adlı `Result`.</span><span class="sxs-lookup"><span data-stu-id="418fb-118">The previous example activity derives from <xref:System.Activities.AsyncCodeActivity%601>, and has an elevated `OutArgument<int>` named `Result`.</span></span> <span data-ttu-id="418fb-119">Tarafından döndürülen değer `GetRandom` yöntemi ayıklanır ve tarafından döndürülen <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A> geçersiz kılma ve bu değer olarak ayarlanır `Result` değeri.</span><span class="sxs-lookup"><span data-stu-id="418fb-119">The value returned by the `GetRandom` method is extracted and returned by the <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A> override, and this value is set as the `Result` value.</span></span> <span data-ttu-id="418fb-120">Bir sonuç döndürmeyen zaman uyumsuz etkinlikleri türetilen <xref:System.Activities.AsyncCodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="418fb-120">Asynchronous activities that do not return a result should derive from <xref:System.Activities.AsyncCodeActivity>.</span></span> <span data-ttu-id="418fb-121">Aşağıdaki örnekte, bir `DisplayRandom` etkinlik öğesinden türetilen tanımlanmış <xref:System.Activities.AsyncCodeActivity>.</span><span class="sxs-lookup"><span data-stu-id="418fb-121">In the following example, a `DisplayRandom` activity is defined which derives from <xref:System.Activities.AsyncCodeActivity>.</span></span> <span data-ttu-id="418fb-122">Bu etkinlik benzer `GetRandom` etkinlik ancak sonucu döndürerek yerine bir ileti konsola gösterir.</span><span class="sxs-lookup"><span data-stu-id="418fb-122">This activity is like the `GetRandom` activity but instead of returning a result it displays a message to the console.</span></span>  
  
 [!code-csharp[CFX_ActivityExample#11](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#11)]  
  
 <span data-ttu-id="418fb-123">Hiçbir değer döndürmeyen olduğundan unutmayın `DisplayRandom` kullanan bir <xref:System.Action> yerine bir <xref:System.Func%602> kendi temsilci ve temsilci çağırmak için herhangi bir değer döndürür.</span><span class="sxs-lookup"><span data-stu-id="418fb-123">Note that because there is no return value, `DisplayRandom` uses an <xref:System.Action> instead of a <xref:System.Func%602> to invoke its delegate, and the delegate returns no value.</span></span>  
  
 <span data-ttu-id="418fb-124"><xref:System.Activities.AsyncCodeActivity>Ayrıca sağlayan bir <xref:System.Activities.AsyncCodeActivity.Cancel%2A> geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="418fb-124"><xref:System.Activities.AsyncCodeActivity> also provides a <xref:System.Activities.AsyncCodeActivity.Cancel%2A> override.</span></span> <span data-ttu-id="418fb-125">Sırada <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> ve <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> gerekli geçersiz kılmalar olan <xref:System.Activities.AsyncCodeActivity.Cancel%2A> isteğe bağlıdır ve onu yüklenirken etkinliği bekleyen zaman uyumsuz durumuna temizleyebilirsiniz şekilde kılınabilir iptal edildi veya iptal edildi.</span><span class="sxs-lookup"><span data-stu-id="418fb-125">While <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> and <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> are required overrides, <xref:System.Activities.AsyncCodeActivity.Cancel%2A> is optional, and can be overridden so the activity can clean up its outstanding asynchronous state when it is being canceled or aborted.</span></span> <span data-ttu-id="418fb-126">Temizleme mümkün olup olmadığını ve `AsyncCodeActivity.ExecutingActivityInstance.IsCancellationRequested` olan `true`, etkinlik çağırmalıdır <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>.</span><span class="sxs-lookup"><span data-stu-id="418fb-126">If clean up is possible and `AsyncCodeActivity.ExecutingActivityInstance.IsCancellationRequested` is `true`, the activity should call <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A>.</span></span> <span data-ttu-id="418fb-127">Bu yöntemle karşılaşılan özel durumlar için iş akışı örneği önemli.</span><span class="sxs-lookup"><span data-stu-id="418fb-127">Any exceptions thrown from this method are fatal to the workflow instance.</span></span>  
  
 [!code-csharp[CFX_ActivityExample#10](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#10)]  
  
### <a name="invoking-asynchronous-methods-on-a-class"></a><span data-ttu-id="418fb-128">Bir sınıfı zaman uyumsuz yöntemleri çağırma</span><span class="sxs-lookup"><span data-stu-id="418fb-128">Invoking Asynchronous Methods on a Class</span></span>  
 <span data-ttu-id="418fb-129">Sınıflarda birçoğu [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] zaman uyumsuz işlevselliği sağlamak ve bu işlevselliği kullanarak zaman uyumsuz olarak çağrılabilir bir <xref:System.Activities.AsyncCodeActivity> etkinlik tabanlı.</span><span class="sxs-lookup"><span data-stu-id="418fb-129">Many of the classes in the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provide asynchronous functionality, and this functionality can be asynchronously invoked by using an <xref:System.Activities.AsyncCodeActivity> based activity.</span></span> <span data-ttu-id="418fb-130">Aşağıdaki örnekte [kullanarak AsyncOperationContext bir etkinlikte](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md), bir etkinlik zaman uyumsuz olarak kullanarak bir dosyayı oluşturan oluşturulur <xref:System.IO.FileStream> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="418fb-130">In the following example from the [Using AsyncOperationContext in an Activity](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md), an activity is created that asynchronously creates a file by using the <xref:System.IO.FileStream> class.</span></span>  
  
 [!code-csharp[CFX_ActivityExample#12](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#12)]  
  
### <a name="sharing-state-between-the-beginexecute-and-endexecute-methods"></a><span data-ttu-id="418fb-131">Durum BeginExecute ve EndExecute yöntemleri arasında paylaşma</span><span class="sxs-lookup"><span data-stu-id="418fb-131">Sharing State Between the BeginExecute and EndExecute Methods</span></span>  
 <span data-ttu-id="418fb-132">Önceki örnekte, <xref:System.IO.FileStream> oluşturulan nesne <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> içinde eriştiğiniz <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="418fb-132">In the previous example, the <xref:System.IO.FileStream> object that was created in <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> was accessed in the <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>.</span></span> <span data-ttu-id="418fb-133">Bu olasıdır çünkü `file` değişken olarak geçirilen <xref:System.Activities.AsyncCodeActivityContext.UserState%2A?displayProperty=nameWithType> özelliğinde <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="418fb-133">This is possible because the `file` variable was passed in the <xref:System.Activities.AsyncCodeActivityContext.UserState%2A?displayProperty=nameWithType> property in <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>.</span></span> <span data-ttu-id="418fb-134">Bu, durumu arasında paylaşmak için doğru yöntemdir <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> ve <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>.</span><span class="sxs-lookup"><span data-stu-id="418fb-134">This is the correct method for sharing state between <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> and <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>.</span></span> <span data-ttu-id="418fb-135">Türetilen sınıfta bir üye değişkenine kullanmak için geçersiz (`FileWriter` bu durumda) durumu arasında paylaşmak için <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> ve <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> etkinliği nesnesi birden çok etkinlik örnekleri tarafından başvurulabilir olduğundan.</span><span class="sxs-lookup"><span data-stu-id="418fb-135">It is incorrect to use a member variable in the derived class (`FileWriter` in this case) to share state between <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> and <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> because the activity object may be referenced by multiple activity instances.</span></span> <span data-ttu-id="418fb-136">Durum paylaşmak için bir üye değişkenine kullanılmaya çalışılıyor birinden değerlerde sonuçlanabilir <xref:System.Activities.ActivityInstance> üzerine yazmaya veya başka bir değer tüketen <xref:System.Activities.ActivityInstance>.</span><span class="sxs-lookup"><span data-stu-id="418fb-136">Attempting to use a member variable to share state can result in values from one <xref:System.Activities.ActivityInstance> overwriting or consuming values from another <xref:System.Activities.ActivityInstance>.</span></span>  
  
### <a name="accessing-argument-values"></a><span data-ttu-id="418fb-137">Bağımsız değişken değerleri erişme</span><span class="sxs-lookup"><span data-stu-id="418fb-137">Accessing Argument Values</span></span>  
 <span data-ttu-id="418fb-138">Ortamının bir <xref:System.Activities.AsyncCodeActivity> faaliyete tanımlı değişkenlerin oluşur.</span><span class="sxs-lookup"><span data-stu-id="418fb-138">The environment of an <xref:System.Activities.AsyncCodeActivity> consists of the arguments defined on the activity.</span></span> <span data-ttu-id="418fb-139">Bu bağımsız değişkenler erişilebilen <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> / <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> kullanarak geçersiz kılar <xref:System.Activities.AsyncCodeActivityContext> parametresi.</span><span class="sxs-lookup"><span data-stu-id="418fb-139">These arguments can be accessed from the <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>/<xref:System.Activities.AsyncCodeActivity.EndExecute%2A> overrides using the <xref:System.Activities.AsyncCodeActivityContext> parameter.</span></span> <span data-ttu-id="418fb-140">Bağımsız değişkenler temsilci, ancak bağımsız değişken değerleri erişilemiyor veya istenen herhangi bir veri parametrelerini kullanarak temsilci geçirilebilir.</span><span class="sxs-lookup"><span data-stu-id="418fb-140">The arguments cannot be accessed in the delegate, but the argument values or any other desired data can be passed in to the delegate using its parameters.</span></span> <span data-ttu-id="418fb-141">Aşağıdaki örnekte, rastgele bir sayı oluştururken etkinlik (bunlar dahil) bir üst sınır gelen edindiği tanımlanır kendi `Max` bağımsız değişkeni.</span><span class="sxs-lookup"><span data-stu-id="418fb-141">In the following example, a random number-generating activity is defined that obtains the inclusive upper bound from its `Max` argument.</span></span> <span data-ttu-id="418fb-142">Temsilci çağrıldığında bağımsız değişkeninin değeri için zaman uyumsuz koduna geçirilen.</span><span class="sxs-lookup"><span data-stu-id="418fb-142">The value of the argument is passed in to the asynchronous code when the delegate is invoked.</span></span>  
  
 [!code-csharp[CFX_ActivityExample#9](../../../samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#9)]  
  
### <a name="scheduling-actions-or-child-activities-using-asynccodeactivity"></a><span data-ttu-id="418fb-143">Zamanlama eylemler veya alt etkinlikleri AsyncCodeActivity kullanma</span><span class="sxs-lookup"><span data-stu-id="418fb-143">Scheduling Actions or Child Activities Using AsyncCodeActivity</span></span>  
 <span data-ttu-id="418fb-144"><xref:System.Activities.AsyncCodeActivity>türetilen özel etkinlikler iş akışı iş parçacığı açısından zaman uyumsuz olarak gerçekleştirmek için bir yöntem sağlar, ancak alt etkinlikler veya Eylemler zamanlama yeteneği sağlamaz.</span><span class="sxs-lookup"><span data-stu-id="418fb-144"><xref:System.Activities.AsyncCodeActivity> derived custom activities  provide a method for performing work asynchronously with regard to the workflow thread, but do not provide the ability to schedule child activities or actions.</span></span> <span data-ttu-id="418fb-145">Ancak, zaman uyumsuz davranışı alt etkinliklerin birleşim aracılığıyla zamanlama ile birleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="418fb-145">However, asynchronous behavior can be incorporated with scheduling of child activities through composition.</span></span> <span data-ttu-id="418fb-146">Zaman uyumsuz bir etkinlik oluşturulabilir ve ardından ile oluşan bir <xref:System.Activities.Activity> veya <xref:System.Activities.NativeActivity> zaman uyumsuz davranışı ve alt etkinlikler veya Eylemler zamanlama sağlamak üzere etkinlik türetilmiş.</span><span class="sxs-lookup"><span data-stu-id="418fb-146">An asynchronous activity can be created, and then composed with an <xref:System.Activities.Activity> or <xref:System.Activities.NativeActivity> derived activity to provide asynchronous behavior and scheduling of child activities or actions.</span></span> <span data-ttu-id="418fb-147">Örneğin, bir etkinlik öğesinden türetilen oluşturulamadı <xref:System.Activities.Activity>ve kendi uygulamanızda bir <xref:System.Activities.Statements.Sequence> etkinliğin mantığını uygulayan iyi diğer etkinlikler olarak zaman uyumsuz etkinliğini içeren.</span><span class="sxs-lookup"><span data-stu-id="418fb-147">For example, an activity could be created that derives from <xref:System.Activities.Activity>, and has as its implementation a <xref:System.Activities.Statements.Sequence> containing the asynchronous activity as well the other activities that implement the logic of the activity.</span></span> <span data-ttu-id="418fb-148">Kullanarak etkinlikleri oluşturma hakkında daha fazla örnekleri için <xref:System.Activities.Activity> ve <xref:System.Activities.NativeActivity>, bkz: [nasıl yapılır: bir etkinlik oluşturmak](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md), [etkinlik yazma seçenekleri](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)ve [bileşik](../../../docs/framework/windows-workflow-foundation/samples/composite.md) etkinlik örnekleri.</span><span class="sxs-lookup"><span data-stu-id="418fb-148">For more examples of composing activities using <xref:System.Activities.Activity> and <xref:System.Activities.NativeActivity>, see [How to: Create an Activity](../../../docs/framework/windows-workflow-foundation/how-to-create-an-activity.md), [Activity Authoring Options](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md), and the [Composite](../../../docs/framework/windows-workflow-foundation/samples/composite.md) activity samples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="418fb-149">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="418fb-149">See Also</span></span>  
 <xref:System.Action>  
 <xref:System.Func%602>  
 [<span data-ttu-id="418fb-150">AsyncOperationContext bir etkinlikte kullanma</span><span class="sxs-lookup"><span data-stu-id="418fb-150">Using AsyncOperationContext in an Activity</span></span>](../../../docs/framework/windows-workflow-foundation/samples/using-asyncoperationcontext-in-an-activity-sample.md)