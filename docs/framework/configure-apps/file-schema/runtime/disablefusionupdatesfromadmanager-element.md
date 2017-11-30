---
title: "&lt;disableFusionUpdatesFromADManager&gt; öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d4aa3343e7f3f60bbf6a57340d858c1ef12197bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdisablefusionupdatesfromadmanagergt-element"></a><span data-ttu-id="0ab55-102">&lt;disableFusionUpdatesFromADManager&gt; öğesi</span><span class="sxs-lookup"><span data-stu-id="0ab55-102">&lt;disableFusionUpdatesFromADManager&gt; Element</span></span>
<span data-ttu-id="0ab55-103">Uygulama etki alanı için yapılandırma ayarlarını geçersiz kılmak çalışma zamanı konak izin vermek için varsayılan davranışı devre dışı olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0ab55-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
 <span data-ttu-id="0ab55-104">\<Yapılandırma > öğesi</span><span class="sxs-lookup"><span data-stu-id="0ab55-104">\<configuration> Element</span></span>  
<span data-ttu-id="0ab55-105">\<çalışma zamanı > öğesi</span><span class="sxs-lookup"><span data-stu-id="0ab55-105">\<runtime> Element</span></span>  
<span data-ttu-id="0ab55-106">\<disableFusionUpdatesFromADManager ></span><span class="sxs-lookup"><span data-stu-id="0ab55-106">\<disableFusionUpdatesFromADManager></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ab55-107">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="0ab55-107">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0ab55-108">Öznitelikler ve Öğeler</span><span class="sxs-lookup"><span data-stu-id="0ab55-108">Attributes and Elements</span></span>  
 <span data-ttu-id="0ab55-109">Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="0ab55-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0ab55-110">Öznitelikler</span><span class="sxs-lookup"><span data-stu-id="0ab55-110">Attributes</span></span>  
  
|<span data-ttu-id="0ab55-111">Öznitelik</span><span class="sxs-lookup"><span data-stu-id="0ab55-111">Attribute</span></span>|<span data-ttu-id="0ab55-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0ab55-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0ab55-113">Etkin</span><span class="sxs-lookup"><span data-stu-id="0ab55-113">enabled</span></span>|<span data-ttu-id="0ab55-114">Gerekli öznitelik.</span><span class="sxs-lookup"><span data-stu-id="0ab55-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="0ab55-115">Fusion ayarlarını geçersiz kılmak için varsayılan özelliği devre dışı olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="0ab55-115">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="0ab55-116">etkin Öznitelik</span><span class="sxs-lookup"><span data-stu-id="0ab55-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="0ab55-117">Değer</span><span class="sxs-lookup"><span data-stu-id="0ab55-117">Value</span></span>|<span data-ttu-id="0ab55-118">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0ab55-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0ab55-119">0</span><span class="sxs-lookup"><span data-stu-id="0ab55-119">0</span></span>|<span data-ttu-id="0ab55-120">Fusion ayarlarını geçersiz kılma yeteneği devre dışı bırakmayın.</span><span class="sxs-lookup"><span data-stu-id="0ab55-120">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="0ab55-121">Sürümünden itibaren varsayılan davranış budur [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0ab55-121">This is the default behavior, starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
|<span data-ttu-id="0ab55-122">1.</span><span class="sxs-lookup"><span data-stu-id="0ab55-122">1</span></span>|<span data-ttu-id="0ab55-123">Fusion ayarlarını geçersiz kılma yeteneği devre dışı bırakın.</span><span class="sxs-lookup"><span data-stu-id="0ab55-123">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="0ab55-124">Bu, .NET Framework'ün önceki sürümlerinde davranışını geri döner.</span><span class="sxs-lookup"><span data-stu-id="0ab55-124">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0ab55-125">Alt Öğeler</span><span class="sxs-lookup"><span data-stu-id="0ab55-125">Child Elements</span></span>  
 <span data-ttu-id="0ab55-126">Yok.</span><span class="sxs-lookup"><span data-stu-id="0ab55-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0ab55-127">Üst Öğeler</span><span class="sxs-lookup"><span data-stu-id="0ab55-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0ab55-128">Öğe</span><span class="sxs-lookup"><span data-stu-id="0ab55-128">Element</span></span>|<span data-ttu-id="0ab55-129">Açıklama</span><span class="sxs-lookup"><span data-stu-id="0ab55-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0ab55-130">Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe.</span><span class="sxs-lookup"><span data-stu-id="0ab55-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="0ab55-131">Derleme bağlama ve atık toplama hakkında bilgi içerir.</span><span class="sxs-lookup"><span data-stu-id="0ab55-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ab55-132">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="0ab55-132">Remarks</span></span>  
 <span data-ttu-id="0ab55-133">İle başlayan [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], varsayılan davranış izin vermektir <xref:System.AppDomainManager> kullanarak yapılandırma ayarlarını geçersiz kılmak için nesne <xref:System.AppDomainSetup.ConfigurationFile%2A> özelliği veya <xref:System.AppDomainSetup.SetConfigurationBytes%2A> yöntemi <xref:System.AppDomainSetup> uygulamanız için geçirilen nesnesi <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> yönteminde, alt <xref:System.AppDomainManager>.</span><span class="sxs-lookup"><span data-stu-id="0ab55-133">Starting with the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)], the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="0ab55-134">Varsayılan uygulama etki alanı için ayarları değiştirmeniz uygulama yapılandırma dosyasında belirtilen ayarları geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="0ab55-134">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="0ab55-135">Diğer uygulama etki alanları için bunlar için geçirilmiş yapılandırma ayarları geçersiz kılar <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> veya <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0ab55-135">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="0ab55-136">Yeni yapılandırma bilgilerini geçirin veya null geçirin (`Nothing` Visual Basic'te) geçirildi yapılandırma bilgilerini ortadan kaldırmak için.</span><span class="sxs-lookup"><span data-stu-id="0ab55-136">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="0ab55-137">Yapılandırma bilgilerini hem de geçmeyin <xref:System.AppDomainSetup.ConfigurationFile%2A> özelliği ve <xref:System.AppDomainSetup.SetConfigurationBytes%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0ab55-137">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="0ab55-138">Yapılandırma bilgilerini hem de geçerse, bilgileri için geçirdiğiniz <xref:System.AppDomainSetup.ConfigurationFile%2A> özelliği göz ardı edilir, çünkü <xref:System.AppDomainSetup.SetConfigurationBytes%2A> yöntemi uygulama yapılandırma dosyasındaki yapılandırma bilgilerini geçersiz kılar.</span><span class="sxs-lookup"><span data-stu-id="0ab55-138">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="0ab55-139">Kullanırsanız <xref:System.AppDomainSetup.ConfigurationFile%2A> özelliği, iletebilir null (`Nothing` Visual Basic'te) için <xref:System.AppDomainSetup.SetConfigurationBytes%2A> çağrısında belirtilen bir yapılandırma bayt ortadan kaldırmak için yöntemi <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> veya <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="0ab55-139">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="0ab55-140">Yapılandırma bilgilerine ek olarak, aşağıdaki ayarları değiştirebilirsiniz <xref:System.AppDomainSetup> uygulamanıza geçirilen nesne <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> yöntemi: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> , <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, ve <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span><span class="sxs-lookup"><span data-stu-id="0ab55-140">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="0ab55-141">Kullanmaya alternatif olarak `<disableFusionUpdatesFromADManager>` öğesini devre dışı bırakabilirsiniz varsayılan davranışı bir kayıt defteri ayarı oluşturarak veya bir ortam değişkeni ayarlayarak.</span><span class="sxs-lookup"><span data-stu-id="0ab55-141">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="0ab55-142">Kayıt defterinde adlı bir DWORD değeri oluşturun `COMPLUS_disableFusionUpdatesFromADManager` altında `HKCU\Software\Microsoft\.NETFramework` veya `HKLM\Software\Microsoft\.NETFramework`ve değerini 1 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="0ab55-142">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="0ab55-143">Komut satırında, ortam değişkenini `COMPLUS_disableFusionUpdatesFromADManager` 1.</span><span class="sxs-lookup"><span data-stu-id="0ab55-143">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ab55-144">Örnek</span><span class="sxs-lookup"><span data-stu-id="0ab55-144">Example</span></span>  
 <span data-ttu-id="0ab55-145">Aşağıdaki örnek kullanarak Fusion ayarlarını geçersiz kılma yeteneği devre dışı bırakma gösterir `<disableFusionUpdatesFromADManager>` öğesi.</span><span class="sxs-lookup"><span data-stu-id="0ab55-145">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ab55-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="0ab55-146">See Also</span></span>  
 [<span data-ttu-id="0ab55-147">Çalışma Zamanı Ayarları Şeması</span><span class="sxs-lookup"><span data-stu-id="0ab55-147">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)  
 [<span data-ttu-id="0ab55-148">Yapılandırma dosyası şeması</span><span class="sxs-lookup"><span data-stu-id="0ab55-148">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)  
 [<span data-ttu-id="0ab55-149">Çalışma zamanı derlemeleri nasıl bulur</span><span class="sxs-lookup"><span data-stu-id="0ab55-149">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)