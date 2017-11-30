---
title: 221 - MessageReceivedFromTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4f977f938844f48182be6662f489506e8119fe67
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="4cf0d-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="4cf0d-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="4cf0d-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="4cf0d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4cf0d-104">Kimlik</span><span class="sxs-lookup"><span data-stu-id="4cf0d-104">ID</span></span>|<span data-ttu-id="4cf0d-105">221</span><span class="sxs-lookup"><span data-stu-id="4cf0d-105">221</span></span>|  
|<span data-ttu-id="4cf0d-106">Anahtar Sözcükler</span><span class="sxs-lookup"><span data-stu-id="4cf0d-106">Keywords</span></span>|<span data-ttu-id="4cf0d-107">Sorun giderme, ServiceModel EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="4cf0d-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="4cf0d-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="4cf0d-108">Level</span></span>|<span data-ttu-id="4cf0d-109">Bilgiler</span><span class="sxs-lookup"><span data-stu-id="4cf0d-109">Information</span></span>|  
|<span data-ttu-id="4cf0d-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="4cf0d-110">Channel</span></span>|<span data-ttu-id="4cf0d-111">Microsoft Windows uygulama sunucusu-uygulamalar/analitik</span><span class="sxs-lookup"><span data-stu-id="4cf0d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4cf0d-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4cf0d-112">Description</span></span>  
 <span data-ttu-id="4cf0d-113">Bu olay, hizmet modeli aktarımdan bir ileti aldığında yayınlanır.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4cf0d-114">İleti</span><span class="sxs-lookup"><span data-stu-id="4cf0d-114">Message</span></span>  
 <span data-ttu-id="4cf0d-115">Dağıtıcı aktarımdan bir ileti aldı.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="4cf0d-116">Bağıntı Kimliği '%1' ==.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4cf0d-117">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="4cf0d-117">Details</span></span>  
  
|<span data-ttu-id="4cf0d-118">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="4cf0d-118">Data Item Name</span></span>|<span data-ttu-id="4cf0d-119">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="4cf0d-119">Data Item Type</span></span>|<span data-ttu-id="4cf0d-120">Açıklama</span><span class="sxs-lookup"><span data-stu-id="4cf0d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4cf0d-121">Bağıntı Kimliği</span><span class="sxs-lookup"><span data-stu-id="4cf0d-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="4cf0d-122">Etkinlik ilişkilendirmek için kullanılan bir `MessageSentToTransport` ilgili olayı bir hizmeti veya istemci `MessageReceivedFromTransport` diğer uçtaki.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="4cf0d-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="4cf0d-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="4cf0d-124">Bu alan, Web barındırılan hizmetler için Web hiyerarşi hizmetinde benzersiz olarak tanımlar.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="4cf0d-125">Biçimi olarak tanımlanan ' Web sitesi adı uygulamanın sanal yolu &#124; Hizmet sanal yolu &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="4cf0d-126">Örnek: ' varsayılan Web sitesi/CalculatorApplication, #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="4cf0d-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4cf0d-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="4cf0d-128">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="4cf0d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|