---
title: 101 - WorkflowInstanceUnhandledExceptionRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ab7d50a0-5347-4390-8445-1def4dfdff6a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0347bf20b17c964763fc2a9a8e1094cdb01586de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="101---workflowinstanceunhandledexceptionrecord"></a><span data-ttu-id="efe98-102">101 - WorkflowInstanceUnhandledExceptionRecord</span><span class="sxs-lookup"><span data-stu-id="efe98-102">101 - WorkflowInstanceUnhandledExceptionRecord</span></span>
## <a name="properties"></a><span data-ttu-id="efe98-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="efe98-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="efe98-104">Kimliği</span><span class="sxs-lookup"><span data-stu-id="efe98-104">Id</span></span>|<span data-ttu-id="efe98-105">101</span><span class="sxs-lookup"><span data-stu-id="efe98-105">101</span></span>|  
|<span data-ttu-id="efe98-106">Anahtar Sözcükler</span><span class="sxs-lookup"><span data-stu-id="efe98-106">Keywords</span></span>|<span data-ttu-id="efe98-107">Sorun giderme, ögesi, WFTracking EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="efe98-107">EndToEndMonitoring, Troubleshooting, HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="efe98-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="efe98-108">Level</span></span>|<span data-ttu-id="efe98-109">Hata</span><span class="sxs-lookup"><span data-stu-id="efe98-109">Error</span></span>|  
|<span data-ttu-id="efe98-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="efe98-110">Channel</span></span>|<span data-ttu-id="efe98-111">Microsoft Windows uygulama sunucusu-uygulamalar/analitik</span><span class="sxs-lookup"><span data-stu-id="efe98-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="efe98-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="efe98-112">Description</span></span>  
 <span data-ttu-id="efe98-113">Bir iş akışı örneği WorkflowInstanceUnhandledExceptionRecord yayar, bu olay tarafından ETW İzleme katılımcı yayınlanır.</span><span class="sxs-lookup"><span data-stu-id="efe98-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceUnhandledExceptionRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="efe98-114">İleti</span><span class="sxs-lookup"><span data-stu-id="efe98-114">Message</span></span>  
 <span data-ttu-id="efe98-115">TrackRecord WorkflowInstanceUnhandledExceptionRecord, örnek kimliği = %1, kayıt numarası = = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = % 7 ' ye SourceTypeName = %8, özel durum = %9, ek açıklamaları = % 10, ProfileName = % 11</span><span class="sxs-lookup"><span data-stu-id="efe98-115">TrackRecord = WorkflowInstanceUnhandledExceptionRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, SourceName = %5, SourceId = %6, SourceInstanceId = %7, SourceTypeName=%8, Exception=%9, Annotations= %10, ProfileName = %11</span></span>  
  
## <a name="details"></a><span data-ttu-id="efe98-116">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="efe98-116">Details</span></span>  
  
|<span data-ttu-id="efe98-117">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="efe98-117">Data Item Name</span></span>|<span data-ttu-id="efe98-118">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="efe98-118">Data Item Type</span></span>|<span data-ttu-id="efe98-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="efe98-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="efe98-120">örnek kimliği</span><span class="sxs-lookup"><span data-stu-id="efe98-120">InstanceId</span></span>|<span data-ttu-id="efe98-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="efe98-121">xs:GUID</span></span>|<span data-ttu-id="efe98-122">İş akışı için örnek kimliği</span><span class="sxs-lookup"><span data-stu-id="efe98-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="efe98-123">Kayıt numarası</span><span class="sxs-lookup"><span data-stu-id="efe98-123">RecordNumber</span></span>|<span data-ttu-id="efe98-124">xs:Long</span><span class="sxs-lookup"><span data-stu-id="efe98-124">xs:long</span></span>|<span data-ttu-id="efe98-125">Verilmiş kaydı sıra sayısı</span><span class="sxs-lookup"><span data-stu-id="efe98-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="efe98-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="efe98-126">EventTime</span></span>|<span data-ttu-id="efe98-127">xs: DateTime</span><span class="sxs-lookup"><span data-stu-id="efe98-127">xs:dateTime</span></span>|<span data-ttu-id="efe98-128">Olay gösterilen zaman UTC zamanı</span><span class="sxs-lookup"><span data-stu-id="efe98-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="efe98-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="efe98-129">ActivityDefinitionId</span></span>|<span data-ttu-id="efe98-130">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-130">xs:string</span></span>|<span data-ttu-id="efe98-131">İş akışı Kök etkinlik adı</span><span class="sxs-lookup"><span data-stu-id="efe98-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="efe98-132">SourceName</span><span class="sxs-lookup"><span data-stu-id="efe98-132">SourceName</span></span>|<span data-ttu-id="efe98-133">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-133">xs:string</span></span>|<span data-ttu-id="efe98-134">UnhandledException kaynaklanan hatalı kaynak etkinlik adı</span><span class="sxs-lookup"><span data-stu-id="efe98-134">The source activity name that faulted resulting in the unhandledException</span></span>|  
|<span data-ttu-id="efe98-135">SourceId</span><span class="sxs-lookup"><span data-stu-id="efe98-135">SourceId</span></span>|<span data-ttu-id="efe98-136">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-136">xs:string</span></span>|<span data-ttu-id="efe98-137">Hataya kaynak etkinliğin etkinlik kimliği</span><span class="sxs-lookup"><span data-stu-id="efe98-137">The activity id of the fault source activity</span></span>|  
|<span data-ttu-id="efe98-138">SourceInstanceId</span><span class="sxs-lookup"><span data-stu-id="efe98-138">SourceInstanceId</span></span>|<span data-ttu-id="efe98-139">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-139">xs:string</span></span>|<span data-ttu-id="efe98-140">Hataya kaynak etkinliği etkinlik örnek kimliği</span><span class="sxs-lookup"><span data-stu-id="efe98-140">The activity instance id of the fault source activity</span></span>|  
|<span data-ttu-id="efe98-141">SourceTypeName</span><span class="sxs-lookup"><span data-stu-id="efe98-141">SourceTypeName</span></span>|<span data-ttu-id="efe98-142">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-142">xs:string</span></span>|<span data-ttu-id="efe98-143">UnhandledException kaynaklanan hatalı kaynak etkinlik türü adı</span><span class="sxs-lookup"><span data-stu-id="efe98-143">The source activity type name that faulted resulting in the unhandledException</span></span>|  
|<span data-ttu-id="efe98-144">Özel Durum</span><span class="sxs-lookup"><span data-stu-id="efe98-144">Exception</span></span>|<span data-ttu-id="efe98-145">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-145">xs:string</span></span>|<span data-ttu-id="efe98-146">İşlenmeyen özel durum için özel durum ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="efe98-146">The exception details for the unhandled exception</span></span>|  
|<span data-ttu-id="efe98-147">Ek Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="efe98-147">Annotations</span></span>|<span data-ttu-id="efe98-148">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-148">xs:string</span></span>|<span data-ttu-id="efe98-149">Bu olay için eklenen ek açıklamalar.</span><span class="sxs-lookup"><span data-stu-id="efe98-149">The annotations that were added to this event.</span></span>  <span data-ttu-id="efe98-150">Değerleri bir xml öğesi biçimde depolanır \<öğeleri >\< öğe adı "annotationName" type="System.String =" > annotationValue\</Madde > \< /öğelerini >.</span><span class="sxs-lookup"><span data-stu-id="efe98-150">The values are stored in an xml element in the format \<items>\< item  name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span>  <span data-ttu-id="efe98-151">Ek açıklama dizesi içeriyorsa belirtilmişse \<öğeleri / >.</span><span class="sxs-lookup"><span data-stu-id="efe98-151">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="efe98-152">ETW olay boyutu ETW arabellek boyutu veya bir ETW olayı için en fazla yükü sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="efe98-152">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="efe98-153">Olay boyutu ETW sınırlarını aşıyor sonra olay ek açıklamalar bırakarak ve ek açıklama değeri ile değiştirerek kesilir \<öğeleri >...  \< /öğelerini >.</span><span class="sxs-lookup"><span data-stu-id="efe98-153">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="efe98-154">ProfileName</span><span class="sxs-lookup"><span data-stu-id="efe98-154">ProfileName</span></span>|<span data-ttu-id="efe98-155">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-155">xs:string</span></span>|<span data-ttu-id="efe98-156">Adı veya gösterilmesini bu olay sonuçlandı izleme profili</span><span class="sxs-lookup"><span data-stu-id="efe98-156">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="efe98-157">HostReference</span><span class="sxs-lookup"><span data-stu-id="efe98-157">HostReference</span></span>|<span data-ttu-id="efe98-158">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-158">xs:string</span></span>|<span data-ttu-id="efe98-159">Bu alan, barındırılan web hizmetleri için web hiyerarşi hizmetinde benzersiz olarak tanımlar.</span><span class="sxs-lookup"><span data-stu-id="efe98-159">For web hosted services, this field uniquely identifies the service in the web hierarchy.</span></span>  <span data-ttu-id="efe98-160">Buna ait biçimi olarak tanımlanır ' Web sitesi adı uygulamanın sanal yolu &#124; Hizmet sanal yolu &#124; ServiceName' örnek: ' varsayılan Web sitesi/CalculatorApplication, #124;/CalculatorService.svc &#124; CalculatorService'</span><span class="sxs-lookup"><span data-stu-id="efe98-160">It's format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName' Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'</span></span>|  
|<span data-ttu-id="efe98-161">AppDomain</span><span class="sxs-lookup"><span data-stu-id="efe98-161">AppDomain</span></span>|<span data-ttu-id="efe98-162">xs: String</span><span class="sxs-lookup"><span data-stu-id="efe98-162">xs:string</span></span>|<span data-ttu-id="efe98-163">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="efe98-163">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|