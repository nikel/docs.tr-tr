---
title: '&lt;soapProcessing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e8707027-e6b8-4539-893d-3cd7c13fbc18
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e53225399e3acba275d2d95533c4baad20386a4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ltsoapprocessinggt"></a><span data-ttu-id="7571b-102">&lt;soapProcessing&gt;</span><span class="sxs-lookup"><span data-stu-id="7571b-102">&lt;soapProcessing&gt;</span></span>

<span data-ttu-id="7571b-103">Farklı bağlama türleri ve ileti sürümleri arasında iletileri sıralama için kullanılan istemci uç nokta davranışını tanımlar.</span><span class="sxs-lookup"><span data-stu-id="7571b-103">Defines the client endpoint behavior used to marshal messages between different binding types and message versions.</span></span>

<span data-ttu-id="7571b-104">**\<Sistem. ServiceModel >** </span><span class="sxs-lookup"><span data-stu-id="7571b-104">**\<system.ServiceModel>** </span></span>  
<span data-ttu-id="7571b-105">&nbsp;&nbsp;**\<davranışları >** </span><span class="sxs-lookup"><span data-stu-id="7571b-105">&nbsp;&nbsp;**\<behaviors>** </span></span>  
<span data-ttu-id="7571b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors >** </span><span class="sxs-lookup"><span data-stu-id="7571b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<endpointBehaviors>** </span></span>  
<span data-ttu-id="7571b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<davranışı >** </span><span class="sxs-lookup"><span data-stu-id="7571b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<behavior>** </span></span>  
<span data-ttu-id="7571b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing >**</span><span class="sxs-lookup"><span data-stu-id="7571b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<soapProcessing>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7571b-109">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="7571b-109">Syntax</span></span>

```xml
<soapProcessing processMessages="true|false" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="7571b-110">Öznitelikler ve öğeler</span><span class="sxs-lookup"><span data-stu-id="7571b-110">Attributes and elements</span></span>

<span data-ttu-id="7571b-111">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7571b-111">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="7571b-112">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="7571b-112">Attributes</span></span>

|                   | <span data-ttu-id="7571b-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7571b-113">Description</span></span> |
| ----------------- | ----------- |
| `processMessages` | <span data-ttu-id="7571b-114">İletileri SOAP iletisi sürümler arasında sıralanmış olup olmadığını belirten bir Boole değeri.</span><span class="sxs-lookup"><span data-stu-id="7571b-114">A Boolean value that specifies whether messages should be marshaled between SOAP message versions.</span></span> |

### <a name="child-elements"></a><span data-ttu-id="7571b-115">Alt öğeleri</span><span class="sxs-lookup"><span data-stu-id="7571b-115">Child elements</span></span>

<span data-ttu-id="7571b-116">Yok.</span><span class="sxs-lookup"><span data-stu-id="7571b-116">None</span></span>

### <a name="parent-elements"></a><span data-ttu-id="7571b-117">Üst öğeler</span><span class="sxs-lookup"><span data-stu-id="7571b-117">Parent elements</span></span>

|     | <span data-ttu-id="7571b-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="7571b-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7571b-119">**\<davranışı >**</span><span class="sxs-lookup"><span data-stu-id="7571b-119">**\<behavior>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) | <span data-ttu-id="7571b-120">Bir uç nokta davranışını belirtir.</span><span class="sxs-lookup"><span data-stu-id="7571b-120">Specifies an endpoint behavior.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7571b-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="7571b-121">Remarks</span></span>

<span data-ttu-id="7571b-122">SOAP işleme iletileri ileti sürümleri arasında burada dönüştürülür işlemidir.</span><span class="sxs-lookup"><span data-stu-id="7571b-122">SOAP processing is the process where messages are converted between message versions.</span></span>

<span data-ttu-id="7571b-123">[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Yönlendirme hizmeti dönüştürebilir iletileri bir protokolünden diğerine.</span><span class="sxs-lookup"><span data-stu-id="7571b-123">The [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Routing Service can convert messages from one protocol to another.</span></span> <span data-ttu-id="7571b-124">Gelen ve giden ileti sürümleri farklıysa, doğru sürümünün yeni bir ileti oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="7571b-124">If the incoming and outgoing Message Versions are different, a new message of the correct version is created.</span></span> <span data-ttu-id="7571b-125">İleti birinden işleme <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion` başka bir yeni oluşturarak elde edilir [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] gövde bölümü ve ilgili üstbilgi gelen içeren ileti [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] ileti.</span><span class="sxs-lookup"><span data-stu-id="7571b-125">Processing messages from one <!--zz <xref:System.ServiceModel.Channel.MessageVersion> --> `MessageVersion`  to another is accomplished by constructing a new [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message that contains the body part and relevant headers from the incoming [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] message.</span></span> <span data-ttu-id="7571b-126">Adresleme için belirli olan veya, anladım yönlendirici düzeyinde kullanılmaz yeni WCF ileti oluşturma sırasında bu üstbilgileri ya da (söz konusu olduğunda üstbilgileri adresleme) farklı bir sürüm olması veya bir parçası olarak işlenen üstbilgileri yönlendirici ile istemci arasındaki iletişim.</span><span class="sxs-lookup"><span data-stu-id="7571b-126">Headers that are specific to addressing, or that are understood at the router level, are not used during construction of the new WCF message because these headers are either of a different version (in the case of addressing headers) or have been processed as part of the communication between the client and the router.</span></span>

<span data-ttu-id="7571b-127">Üstbilgi giden iletisinde olup bulunuyor olsun veya olmasın, gelen kanal katmanını geçti olarak anladım olarak işaretlendi tarafından belirlenir.</span><span class="sxs-lookup"><span data-stu-id="7571b-127">Whether a header is placed in the outbound message is determined by whether or not it was marked as understood as it passed through the incoming channel layer.</span></span> <span data-ttu-id="7571b-128">(Özel üstbilgiler gibi) anlaşılmayan üstbilgileri kaldırılmıyor ve bu nedenle yönlendirme hizmeti aracılığıyla Giden iletiye kopyalanmasını tarafından geçirin.</span><span class="sxs-lookup"><span data-stu-id="7571b-128">Headers that are not understood (such as custom headers) are not removed and so pass through the routing service by being copied to the outbound message.</span></span> <span data-ttu-id="7571b-129">Giden iletinin ileti gövdesini kopyalanır.</span><span class="sxs-lookup"><span data-stu-id="7571b-129">The body of the message is copied to the outbound message.</span></span> <span data-ttu-id="7571b-130">İleti Giden kanal çıkış gönderilir, tüm üstbilgiler ve belirli diğer Zarf verileri için iletişimin noktada, Protokolü/Aktarım oluşturulan eklendi ve.</span><span class="sxs-lookup"><span data-stu-id="7571b-130">The message is then sent out the outbound channel, at which point all of the headers and other envelope data specific to that communication protocol/transport will be created and added.</span></span>

<span data-ttu-id="7571b-131">SOAP işleme davranışını belirtildiğinde bu tür işleme adımları gerçekleşir.</span><span class="sxs-lookup"><span data-stu-id="7571b-131">Such processing steps take place when the SOAP processing behavior is specified.</span></span> <span data-ttu-id="7571b-132">Bu [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) yönlendirme hizmeti başladığında, tüm (giden) istemci uç noktaları için uygulanan bir uç noktası davranışı bir davranıştır.</span><span class="sxs-lookup"><span data-stu-id="7571b-132">This [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior is an endpoint behavior that is applied to all client (outgoing) endpoints when the Routing Service starts up.</span></span> <span data-ttu-id="7571b-133">Varsayılan, [ \<yönlendirme >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) davranışı oluşturur ve yeni bir iliştirir [ \<soapProcessingExtension >](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) davranışa `processMessages` kümesine `true` her İstemci uç noktası.</span><span class="sxs-lookup"><span data-stu-id="7571b-133">default, the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior creates and attaches a new [\<soapProcessingExtension>](../../../../../docs/framework/configure-apps/file-schema/wcf/soapprocessing.md) behavior with `processMessages` set to `true` for each client endpoint.</span></span> <span data-ttu-id="7571b-134">Yönlendirme hizmeti değil anlamak veya davranış işleme varsayılan geçersiz kılma istediğiniz protokol varsa, tüm yönlendirme hizmeti veya yalnızca belirli uç noktaları için işleme SOAP devre dışı bırakabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="7571b-134">If you have a protocol that the Routing Service does not understand, or wish to override the default processing behavior, you can disable SOAP processing either for the entire Routing Service or just for particular endpoints.</span></span>  <span data-ttu-id="7571b-135">Tüm yönlendirme hizmeti tüm bitiş noktalarında işlemeyi SOAP devre dışı bırakmak için ayarlanmış `soapProcessing` özniteliği [ \<yönlendirme >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) davranışına `false`.</span><span class="sxs-lookup"><span data-stu-id="7571b-135">To disable SOAP processing for the entire routing service on all endpoints, set the `soapProcessing` attribute of the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior to `false`.</span></span> <span data-ttu-id="7571b-136">Belirli bir uç nokta için işleme SOAP kapatmak için bu davranış kullanın ve ayarlayın, `processMessages` özniteliğini `false`, bu davranış, istediğiniz adresindeki çalıştırmak için kod işleme varsayılan uç nokta ekleme.</span><span class="sxs-lookup"><span data-stu-id="7571b-136">To turn off SOAP processing for a particular endpoint, use this behavior and set its `processMessages` attribute to `false`, then attach this behavior to the endpoint you do not want the default processing code to run at.</span></span>  <span data-ttu-id="7571b-137">Zaman [ \<yönlendirme >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) davranışını ayarlar yönlendirme hizmeti, zaten bir tane olduğundan uç noktası davranışı yeniden uygulanması atlar.</span><span class="sxs-lookup"><span data-stu-id="7571b-137">When the [\<routing>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing-of-servicebehavior.md) behavior sets up the Routing Service, it will skip reapplying the endpoint behavior since one already exists.</span></span>