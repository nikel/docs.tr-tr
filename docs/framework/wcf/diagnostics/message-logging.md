---
title: "İleti Günlüğe Kaydetme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6bce0682-75ef-4d65-a659-b328fba4a8b5
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 04e1b881d9aab1c35195794394cddf5172288cc1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="message-logging"></a><span data-ttu-id="26efa-102">İleti Günlüğe Kaydetme</span><span class="sxs-lookup"><span data-stu-id="26efa-102">Message Logging</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="26efa-103">çevrimdışı kullanım için gelen ve giden iletilerini günlüğe kaydetmek için yeteneği sağlar.</span><span class="sxs-lookup"><span data-stu-id="26efa-103"> provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="26efa-104">İleti günlüğe kaydetme, hangi iletisi ve ileti gövdesi görülüyor görmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="26efa-104">Message logging enables you to see what the message and message body looks like.</span></span> <span data-ttu-id="26efa-105">Bu tür günlükleri size ne içinde bağımsız değişken geçirildi ve nasıl XML olarak ifade edilen bağımsız değişken alan uç noktası gördüğünüz bildiren özellikle yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="26efa-105">This type of logging is particularly helpful in letting you know what arguments were passed in and how the receiving endpoint saw the arguments expressed as XML.</span></span> <span data-ttu-id="26efa-106">Ayrıca, alındığı gibi ileti günlüğe kaydetme, nasıl ileti ulaştığında görmek için hatalı biçimlendirilmiş iletileri de tanılamak sağlar.</span><span class="sxs-lookup"><span data-stu-id="26efa-106">In addition, logging the message as it was received allows you to diagnose malformed messages as well as to see how the message arrived.</span></span> <span data-ttu-id="26efa-107">Ayrıca, güvenlik inceleyebilirsiniz kullanılan bir belirtece bölümleri şifrelenip imzalanmış ve bölümleri değişmeden kalır.</span><span class="sxs-lookup"><span data-stu-id="26efa-107">You can also examine the security tokens used, parts encrypted and signed, and parts left intact.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26efa-108">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="26efa-108">In This Section</span></span>  
 [<span data-ttu-id="26efa-109">İleti akışı genel bakış</span><span class="sxs-lookup"><span data-stu-id="26efa-109">Message Flow Overview</span></span>](../../../../docs/framework/wcf/diagnostics/message-flow-overview.md)  
  
 <span data-ttu-id="26efa-110">Bu konu, istemci ve hizmet olayları olay günlüğü iletilerini nasıl ilişkilendirileceğini açıklar.</span><span class="sxs-lookup"><span data-stu-id="26efa-110">This topic describes how event log messages correspond to client and service events.</span></span>  
  
 [<span data-ttu-id="26efa-111">İleti günlüğe kaydetmeyi yapılandırma</span><span class="sxs-lookup"><span data-stu-id="26efa-111">Configuring Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md)  
  
 <span data-ttu-id="26efa-112">Bu konuda, ileti günlüğe kaydetme farklı senaryolar için nasıl yapılandırabileceğiniz açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="26efa-112">This topic describes how you can configure message logging for different scenarios.</span></span>  
  
 [<span data-ttu-id="26efa-113">İleti günlüklerini görüntüleme</span><span class="sxs-lookup"><span data-stu-id="26efa-113">Viewing Message Logs</span></span>](../../../../docs/framework/wcf/diagnostics/viewing-message-logs.md)  
  
 <span data-ttu-id="26efa-114">Bu konuda, ileti günlüklerini nasıl görüntüleyebileceğiniz açıklanır.</span><span class="sxs-lookup"><span data-stu-id="26efa-114">This topic describes how you can view message logs.</span></span>  
  
 [<span data-ttu-id="26efa-115">İleti günlüğe kaydetme ile ilgili güvenlik konuları</span><span class="sxs-lookup"><span data-stu-id="26efa-115">Security Concerns for Message Logging</span></span>](../../../../docs/framework/wcf/diagnostics/security-concerns-for-message-logging.md)  
  
 <span data-ttu-id="26efa-116">Bu konu, ileti günlüğe kaydetme tarafından oluşturulan olayları yanı sıra ileti günlüklerini de sağlanmaktadır hassas verilerinizi nasıl koruyabilirsiniz açıklar.</span><span class="sxs-lookup"><span data-stu-id="26efa-116">This topic describes how you can protect sensitive data from being exposed in message logs, as well as events generated by message logging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26efa-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="26efa-117">See Also</span></span>  
 [<span data-ttu-id="26efa-118">Yönetim ve tanılama</span><span class="sxs-lookup"><span data-stu-id="26efa-118">Administration and Diagnostics</span></span>](../../../../docs/framework/wcf/diagnostics/index.md)