---
title: "Ağ izleme yorumlama"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: deb191f18bda5b00ef4a967f50e8e983289882a4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="cd407-102">Ağ izleme yorumlama</span><span class="sxs-lookup"><span data-stu-id="cd407-102">Interpreting Network Tracing</span></span>
<span data-ttu-id="cd407-103">Ağ izleme etkinleştirildiğinde izleme uygulamanızı yapar çeşitli çağrıları yakalamak için kullanabileceğiniz <xref:System.Net> sınıfı üyeleri.</span><span class="sxs-lookup"><span data-stu-id="cd407-103">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="cd407-104">Bu çağrılar çıkışı aşağıdaki örneklere benzer olabilir.</span><span class="sxs-lookup"><span data-stu-id="cd407-104">The output from these calls may be similar to the following examples.</span></span>  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 <span data-ttu-id="cd407-105">[588] önceki örnekte geçerli iş parçacığının benzersiz tanımlayıcısıdır.</span><span class="sxs-lookup"><span data-stu-id="cd407-105">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="cd407-106">(4357) ve (4387) olan zaman damgaları belirten uygulama başlatıldığından bu yana geçen milisaniye sayısı.</span><span class="sxs-lookup"><span data-stu-id="cd407-106">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="cd407-107">Zaman damgası aşağıdaki veri girme ve yönteminden çıkılıyor uygulama gösterir **Socket.Send**.</span><span class="sxs-lookup"><span data-stu-id="cd407-107">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="cd407-108">Nesne yürütme **Gönder** yöntemi kendi benzersiz tanımlayıcı olarak 33574638 sahiptir.</span><span class="sxs-lookup"><span data-stu-id="cd407-108">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="cd407-109">Yöntemi çıkış izleme dönüş değeri (önceki örnekte 61) içerir.</span><span class="sxs-lookup"><span data-stu-id="cd407-109">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="cd407-110">Ağ izlerini gönderilen veya uygulama düzeyi protokolleri Köprü Metni Aktarım Protokolü (HTTP) gibi kullanarak, uygulama tarafından alınan ağ trafiği yakalayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cd407-110">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="cd407-111">Bu veriler metin olarak yakalanabilir ve isteğe bağlı olarak, onaltılık veri.</span><span class="sxs-lookup"><span data-stu-id="cd407-111">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="cd407-112">Onaltılık veri, belirttiğiniz zaman kullanılabilir **includehex** değeri olarak **İzlemeModu** özniteliği.</span><span class="sxs-lookup"><span data-stu-id="cd407-112">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="cd407-113">(Bu öznitelik hakkında ayrıntılı bilgi için bkz: [nasıl yapılır: yapılandırma ağ izleme](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) Aşağıdaki örnek izleme kullanılarak oluşturulan **includehex**.</span><span class="sxs-lookup"><span data-stu-id="cd407-113">(For detailed information about this attribute, see [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="cd407-114">Onaltılık verileri atlamak için belirtmeniz **protocolonly** değeri olarak **İzlemeModu** özniteliği.</span><span class="sxs-lookup"><span data-stu-id="cd407-114">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="cd407-115">İzleme aşağıdaki örnekte, **protocolonly** belirtilir.</span><span class="sxs-lookup"><span data-stu-id="cd407-115">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="cd407-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cd407-116">See Also</span></span>  
 [<span data-ttu-id="cd407-117">Ağ izlemeyi etkinleştirme</span><span class="sxs-lookup"><span data-stu-id="cd407-117">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="cd407-118">Nasıl yapılır: ağ İzlemeyi Yapılandır</span><span class="sxs-lookup"><span data-stu-id="cd407-118">How to: Configure Network Tracing</span></span>](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)  
 [<span data-ttu-id="cd407-119">.NET Framework'te ağ izleme</span><span class="sxs-lookup"><span data-stu-id="cd407-119">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)