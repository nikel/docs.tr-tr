---
title: "Süreölçerler"
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
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fca27cf5261e253c2bb3d3a10fa3db31f28a2415
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="timers"></a><span data-ttu-id="cfeab-102">Süreölçerler</span><span class="sxs-lookup"><span data-stu-id="cfeab-102">Timers</span></span>
<span data-ttu-id="cfeab-103">Zamanlayıcılar belirli bir zamanda çağrılan bir temsilciyi belirtmenize olanak sağlayan hafif nesnelerdir.</span><span class="sxs-lookup"><span data-stu-id="cfeab-103">Timers are lightweight objects that enable you to specify a delegate to be called at a specified time.</span></span> <span data-ttu-id="cfeab-104">İş parçacığı havuzundaki iş parçacığı bekleme işlemi gerçekleştirir.</span><span class="sxs-lookup"><span data-stu-id="cfeab-104">A thread in the thread pool performs the wait operation.</span></span>  
  
 <span data-ttu-id="cfeab-105">Kullanarak <xref:System.Threading.Timer?displayProperty=nameWithType> sınıftır kolay.</span><span class="sxs-lookup"><span data-stu-id="cfeab-105">Using the <xref:System.Threading.Timer?displayProperty=nameWithType> class is straightforward.</span></span> <span data-ttu-id="cfeab-106">Oluşturduğunuz bir **Zamanlayıcı**, geçen bir <xref:System.Threading.TimerCallback> geri çağırma yöntemi, geri arama, bir ilk artırma ile geri çağırmaları arasındaki dönemi temsil eden bir zaman için geçirilen durumunu temsil eden bir nesne için temsilci.</span><span class="sxs-lookup"><span data-stu-id="cfeab-106">You create a **Timer**, passing a <xref:System.Threading.TimerCallback> delegate to the callback method, an object representing state that will be passed to the callback, an initial raise time, and a time representing the period between callback invocations.</span></span> <span data-ttu-id="cfeab-107">Bekleyen süreölçerini iptal çağrısı **Timer.Dispose** işlevi.</span><span class="sxs-lookup"><span data-stu-id="cfeab-107">To cancel a pending timer, call the **Timer.Dispose** function.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cfeab-108">Diğer iki süreölçer sınıfı vardır.</span><span class="sxs-lookup"><span data-stu-id="cfeab-108">There are two other timer classes.</span></span> <span data-ttu-id="cfeab-109"><xref:System.Windows.Forms.Timer?displayProperty=nameWithType> Sınıfı görsel tasarımcılar ile çalışır ve kullanıcı arabirimi bağlamlarda kullanılacak demek bir denetim; kullanıcı arabirimi iş parçacığı olaylarına başlatır.</span><span class="sxs-lookup"><span data-stu-id="cfeab-109">The <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> class is a control that works with visual designers and is meant to be used in user interface contexts; it raises events on the user interface thread.</span></span> <span data-ttu-id="cfeab-110"><xref:System.Timers.Timer?displayProperty=nameWithType> Sınıfı türer <xref:System.ComponentModel.Component>, böylece kullanılabilir görsel tasarımcılar; ayrıca olayları başlatır, ancak üzerinde bunları başlatır bir <xref:System.Threading.ThreadPool> iş parçacığı.</span><span class="sxs-lookup"><span data-stu-id="cfeab-110">The <xref:System.Timers.Timer?displayProperty=nameWithType> class derives from <xref:System.ComponentModel.Component>, so it can be used with visual designers; it also raises events, but it raises them on a <xref:System.Threading.ThreadPool> thread.</span></span> <span data-ttu-id="cfeab-111"><xref:System.Threading.Timer?displayProperty=nameWithType> Sınıfı üzerinde geri aramalar yapacağı bir <xref:System.Threading.ThreadPool> iş parçacığı ve olay modeli hiç kullanmaz.</span><span class="sxs-lookup"><span data-stu-id="cfeab-111">The <xref:System.Threading.Timer?displayProperty=nameWithType> class makes callbacks on a <xref:System.Threading.ThreadPool> thread and does not use the event model at all.</span></span> <span data-ttu-id="cfeab-112">Ayrıca, bir durum nesnesi diğer zamanlayıcılar sağlamadığı geri arama yöntemi sağlar.</span><span class="sxs-lookup"><span data-stu-id="cfeab-112">It also provides a state object to the callback method, which the other timers do not.</span></span> <span data-ttu-id="cfeab-113">Son derece basit.</span><span class="sxs-lookup"><span data-stu-id="cfeab-113">It is extremely lightweight.</span></span>  
  
 <span data-ttu-id="cfeab-114">Aşağıdaki kod örneğinde tuşuna kadar her saniye bir saniye (1000 milisaniye cinsinden) ve çizgilerine sonra başlayan bir süreölçer başlatır **Enter** anahtarı.</span><span class="sxs-lookup"><span data-stu-id="cfeab-114">The following code example starts a timer that starts after one second (1000 milliseconds) and ticks every second until you press the **Enter** key.</span></span> <span data-ttu-id="cfeab-115">Zamanlayıcı başvuru içeren değişken hala çalışırken Zamanlayıcı tabi çöp toplama olmadığından emin olmak için bir sınıf düzeyi alan değildir.</span><span class="sxs-lookup"><span data-stu-id="cfeab-115">The variable containing the reference to the timer is a class-level field, to ensure that the timer is not subject to garbage collection while it is still running.</span></span> <span data-ttu-id="cfeab-116">Agresif çöp toplama hakkında daha fazla bilgi için bkz: <xref:System.GC.KeepAlive%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfeab-116">For more information on aggressive garbage collection, see <xref:System.GC.KeepAlive%2A>.</span></span>  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="cfeab-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cfeab-117">See Also</span></span>  
 <xref:System.Threading.Timer>  
 [<span data-ttu-id="cfeab-118">İş parçacığı nesneleri ve özellikleri</span><span class="sxs-lookup"><span data-stu-id="cfeab-118">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)