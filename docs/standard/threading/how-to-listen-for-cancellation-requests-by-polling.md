---
title: "Nasıl Yapılır: Yoklama ile İptal İsteklerini Dinleme"
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
helpviewer_keywords: cancellation, how to poll for requests
ms.assetid: c7f2f022-d08e-4e00-b4eb-ae84844cb1bc
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3f0e05e3f66d591a28d7e84d358934959764dab6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-listen-for-cancellation-requests-by-polling"></a><span data-ttu-id="f8c98-102">Nasıl Yapılır: Yoklama ile İptal İsteklerini Dinleme</span><span class="sxs-lookup"><span data-stu-id="f8c98-102">How to: Listen for Cancellation Requests by Polling</span></span>
<span data-ttu-id="f8c98-103">Aşağıdaki örnekte, kullanıcı kodu bir iptal belirteci iptal çağıran iş parçacığından istedi olup olmadığını görmek için düzenli aralıklarla yoklayabilir bir yolunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="f8c98-103">The following example shows one way that user code can poll a cancellation token at regular intervals to see whether cancellation has been requested from the calling thread.</span></span> <span data-ttu-id="f8c98-104">Bu örnekte <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> türü, ancak aynı düzeni uygular zaman uyumsuz işlemleri doğrudan tarafından oluşturulan <xref:System.Threading.ThreadPool?displayProperty=nameWithType> türü veya <xref:System.Threading.Thread?displayProperty=nameWithType> türü.</span><span class="sxs-lookup"><span data-stu-id="f8c98-104">This example uses the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type, but the same pattern applies to asynchronous operations created directly by the <xref:System.Threading.ThreadPool?displayProperty=nameWithType> type or the <xref:System.Threading.Thread?displayProperty=nameWithType> type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8c98-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="f8c98-105">Example</span></span>  
 <span data-ttu-id="f8c98-106">Yoklama gerektiren bazı tür düzenli aralıklarla Boolean değerini okuyabilirsiniz döngü veya özyinelemeli kodu <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="f8c98-106">Polling requires some kind of loop or recursive code that can periodically read the value of the Boolean <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property.</span></span> <span data-ttu-id="f8c98-107">Kullanıyorsanız <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> türü ve görevinin çağıran iş parçacığında tamamlanmasını bekleyen, kullanabileceğiniz <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> özelliğini denetleyin ve özel durum için yöntem.</span><span class="sxs-lookup"><span data-stu-id="f8c98-107">If you are using the <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> type and you are waiting for the task to complete on the calling thread, you can use the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method to check the property and throw the exception.</span></span> <span data-ttu-id="f8c98-108">Bu yöntemi kullanarak, doğru bir isteğe yanıt olarak özel durum emin olun.</span><span class="sxs-lookup"><span data-stu-id="f8c98-108">By using this method, you ensure that the correct exception is thrown in response to a request.</span></span> <span data-ttu-id="f8c98-109">Kullanıyorsanız bir <xref:System.Threading.Tasks.Task>, sonra da bu yöntemi çağırmadan el ile atma daha iyi bir <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="f8c98-109">If you are using a <xref:System.Threading.Tasks.Task>, then calling this method is better than manually throwing an <xref:System.OperationCanceledException>.</span></span> <span data-ttu-id="f8c98-110">Özel durum gerekmez sonra yalnızca özelliğini denetleyin ve özellik ise döndürme `true`.</span><span class="sxs-lookup"><span data-stu-id="f8c98-110">If you do not have to throw the exception, then you can just check the property and return from the method if the property is `true`.</span></span>  
  
 [!code-csharp[Cancellation#11](../../../samples/snippets/csharp/VS_Snippets_Misc/cancellation/cs/cancellationex11.cs#11)]
 [!code-vb[Cancellation#11](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cancellation/vb/cancellationex11.vb#11)]  
  
 <span data-ttu-id="f8c98-111">Çağırma <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> son derece hızlı bir işlemdir ve döngüler önemli ek yükü sunmaz.</span><span class="sxs-lookup"><span data-stu-id="f8c98-111">Calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> is extremely fast and does not introduce significant overhead in loops.</span></span>  
  
 <span data-ttu-id="f8c98-112">Aradığınız varsa <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, yalnızca açıkça denetlemek sahip <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> yanıt özel durum atma yanı sıra iptal olarak yapmak için diğer iş varsa, özelliği.</span><span class="sxs-lookup"><span data-stu-id="f8c98-112">If you are calling <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A>, you only have to explicitly check the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property if you have other work to do in response to the cancellation besides throwing the exception.</span></span> <span data-ttu-id="f8c98-113">Bu örnekte, kod gerçekte özelliği iki kez erişme görebilirsiniz: bir kez açık erişim ve yeniden <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="f8c98-113">In this example, you can see that the code actually accesses the property twice: once in the explicit access and again in the <xref:System.Threading.CancellationToken.ThrowIfCancellationRequested%2A> method.</span></span> <span data-ttu-id="f8c98-114">Ancak çünkü okuma act <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> özelliği yalnızca bir geçici erişim başına yönerge okuma içerir, çift erişim performans açısından önemli değildir.</span><span class="sxs-lookup"><span data-stu-id="f8c98-114">But because the act of reading the <xref:System.Threading.CancellationToken.IsCancellationRequested%2A> property involves only one volatile read instruction per access, the double access is not significant from a performance perspective.</span></span> <span data-ttu-id="f8c98-115">El ile throw yöntemi çağırmak yerine hala tercih edilir <xref:System.OperationCanceledException>.</span><span class="sxs-lookup"><span data-stu-id="f8c98-115">It is still preferable to call the method rather than manually throw the <xref:System.OperationCanceledException>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8c98-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f8c98-116">See Also</span></span>  
 [<span data-ttu-id="f8c98-117">Yönetilen iş parçacıklarında iptal</span><span class="sxs-lookup"><span data-stu-id="f8c98-117">Cancellation in Managed Threads</span></span>](../../../docs/standard/threading/cancellation-in-managed-threads.md)