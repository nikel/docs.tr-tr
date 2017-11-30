---
title: "WorkFlow Hizmet Kayıt Aracı (WFServicesReg.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9e92c87b-99c5-4e8d-9d53-7944cc2b47d3
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f88d5f63ce77eae013e4df995956dc35771a0274
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="workflow-service-registration-tool-wfservicesregexe"></a><span data-ttu-id="2a67d-102">WorkFlow Hizmet Kayıt Aracı (WFServicesReg.exe)</span><span class="sxs-lookup"><span data-stu-id="2a67d-102">WorkFlow Service Registration Tool (WFServicesReg.exe)</span></span>
<span data-ttu-id="2a67d-103">İş akışı hizmetleri kayıt aracı (WFServicesReg.exe) eklemek, kaldırmak veya Windows Workflow Foundation (WF) Hizmetleri için yapılandırma öğeleri onarmak için kullanılan tek başına bir araçtır.</span><span class="sxs-lookup"><span data-stu-id="2a67d-103">Workflow Services Registration tool (WFServicesReg.exe) is a stand-alone tool that can be used to add, remove, or repair the configuration elements for Windows Workflow Foundation (WF) services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a67d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="2a67d-104">Syntax</span></span>  
  
```  
WFServicesReg.exe [-c | -r | -v | -m | -i]  
```  
  
## <a name="remarks"></a><span data-ttu-id="2a67d-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="2a67d-105">Remarks</span></span>  
 <span data-ttu-id="2a67d-106">Aracı bulunabilir [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] yükleme konumu, özellikle, % windir%\Microsoft.NET\Framework\v3.5 veya 64-bit makinelerde %windir%\Microsoft.NET\Framework64\v3.5.</span><span class="sxs-lookup"><span data-stu-id="2a67d-106">The tool can be found at the [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] installation location, specifically, %windir%\Microsoft.NET\Framework\v3.5, or at %windir%\Microsoft.NET\Framework64\v3.5 in 64-bit machines.</span></span>  
  
 <span data-ttu-id="2a67d-107">Aşağıdaki tablolarda, iş akışı hizmetleri kayıt aracı (WFServicesReg.exe) ile kullanılabilir seçenekleri açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="2a67d-107">The following tables describe the options that can be used with the Workflow Services Registration tool (WFServicesReg.exe).</span></span>  
  
|<span data-ttu-id="2a67d-108">Seçenek</span><span class="sxs-lookup"><span data-stu-id="2a67d-108">Option</span></span>|<span data-ttu-id="2a67d-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="2a67d-109">Description</span></span>|  
|------------|-----------------|  
|`/c`|<span data-ttu-id="2a67d-110">Windows iş akışı hizmetleri yapılandırır.</span><span class="sxs-lookup"><span data-stu-id="2a67d-110">Configures Windows Workflow Services.</span></span> <span data-ttu-id="2a67d-111">Yüklemek için kullanılan ve senaryoları onarın.</span><span class="sxs-lookup"><span data-stu-id="2a67d-111">Used in install and repair scenarios.</span></span>|  
|`/r`|<span data-ttu-id="2a67d-112">Windows iş akışı Hizmetleri yapılandırmasını kaldırır.</span><span class="sxs-lookup"><span data-stu-id="2a67d-112">Removes Windows Workflow Services Configuration.</span></span>|  
|`/v`|<span data-ttu-id="2a67d-113">Yazdırma ayrıntılı bilgilerini (yapılandırma veya kaldırma).</span><span class="sxs-lookup"><span data-stu-id="2a67d-113">Print verbose information (for either configuration or removal).</span></span>|  
|`/m`|<span data-ttu-id="2a67d-114">MSI günlük biçimini sağlar.</span><span class="sxs-lookup"><span data-stu-id="2a67d-114">Enables MSI logging format.</span></span>|  
|`/i`|<span data-ttu-id="2a67d-115">Uygulamayı çalıştırdığında, pencerenin en aza indirir.</span><span class="sxs-lookup"><span data-stu-id="2a67d-115">Minimizes the window when the application runs.</span></span>|  
  
## <a name="registration"></a><span data-ttu-id="2a67d-116">Kayıt</span><span class="sxs-lookup"><span data-stu-id="2a67d-116">Registration</span></span>  
 <span data-ttu-id="2a67d-117">Aracı Web.config dosyasını inceler ve aşağıdaki kaydeder:</span><span class="sxs-lookup"><span data-stu-id="2a67d-117">The tool inspects the Web.config file and registers the following:</span></span>  
  
-   [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)]<span data-ttu-id="2a67d-118">başvuru derlemeleri.</span><span class="sxs-lookup"><span data-stu-id="2a67d-118"> reference assemblies.</span></span>  
  
-   <span data-ttu-id="2a67d-119">Derleme Sağlayıcısı .xoml dosyaları için.</span><span class="sxs-lookup"><span data-stu-id="2a67d-119">A build provider for .xoml files.</span></span>  
  
-   <span data-ttu-id="2a67d-120">HTTP işleyicileri .xoml ve .rules dosyaları.</span><span class="sxs-lookup"><span data-stu-id="2a67d-120">HTTP handlers for .xoml and .rules files.</span></span>  
  
 <span data-ttu-id="2a67d-121">Aracı Machine.config dosyasının inceler ve aşağıdaki uzantılar kaydeder:</span><span class="sxs-lookup"><span data-stu-id="2a67d-121">The tool inspects the Machine.config file and registers the following extensions:</span></span>  
  
-   <span data-ttu-id="2a67d-122">behaviorExtensions</span><span class="sxs-lookup"><span data-stu-id="2a67d-122">behaviorExtensions</span></span>  
  
-   <span data-ttu-id="2a67d-123">bindingElementExtensions</span><span class="sxs-lookup"><span data-stu-id="2a67d-123">bindingElementExtensions</span></span>  
  
-   <span data-ttu-id="2a67d-124">bindingExtensions</span><span class="sxs-lookup"><span data-stu-id="2a67d-124">bindingExtensions</span></span>  
  
 <span data-ttu-id="2a67d-125">Araç ayrıca aşağıdaki istemci meta veri ımporters kaydeder:</span><span class="sxs-lookup"><span data-stu-id="2a67d-125">The tool also registers the following client metadata importers:</span></span>  
  
-   <span data-ttu-id="2a67d-126">policyImporters</span><span class="sxs-lookup"><span data-stu-id="2a67d-126">policyImporters</span></span>  
  
-   <span data-ttu-id="2a67d-127">wsdlImporters</span><span class="sxs-lookup"><span data-stu-id="2a67d-127">wsdlImporters</span></span>  
  
 <span data-ttu-id="2a67d-128">Aracı, IIS metatabanı .xoml ve .rules kod haritalarını ve işleyicileri de kaydeder.</span><span class="sxs-lookup"><span data-stu-id="2a67d-128">The tool also registers .xoml and .rules scriptmaps and handlers in the IIS metabase.</span></span>  
  
 <span data-ttu-id="2a67d-129">Üzerinde [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] ve [!INCLUDE[wxp](../../../includes/wxp-md.md)] makineler (IIS 5.1 ve [!INCLUDE[iis601](../../../includes/iis601-md.md)]), .xoml ayarlayın ve .rules kod haritalarını kayıtlı.</span><span class="sxs-lookup"><span data-stu-id="2a67d-129">On [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] and [!INCLUDE[wxp](../../../includes/wxp-md.md)] machines (IIS 5.1 and [!INCLUDE[iis601](../../../includes/iis601-md.md)]), one set of .xoml and .rules scriptmaps are registered.</span></span>  
  
 <span data-ttu-id="2a67d-130">64-bit makinelerde aracı WOW modu kod haritalarını kaydeder `Enable32BitAppOnWin64` anahtarı ise etkin ya da yerel 64 bit kod haritalarını `Enable32BitAppOnWin64` anahtar devre dışıdır.</span><span class="sxs-lookup"><span data-stu-id="2a67d-130">On 64-bit machines, the tool registers WOW mode scriptmaps if the `Enable32BitAppOnWin64` switch is enabled, or native 64-bit scriptmaps if the `Enable32BitAppOnWin64` switch is disabled.</span></span>  
  
 <span data-ttu-id="2a67d-131">Üzerinde [!INCLUDE[wv](../../../includes/wv-md.md)] ve Windows Server 2008 (IIS 7.0 ve üstü) makineler, iki adet .xoml ve .rules işleyicileri kayıtlı: tümleşik mod, diğeri Klasik mod için.</span><span class="sxs-lookup"><span data-stu-id="2a67d-131">On [!INCLUDE[wv](../../../includes/wv-md.md)] and Windows Server 2008 (IIS 7.0 and above) machines, two sets of .xoml and .rules handlers are registered: one for Integrated mode and one for Classic mode.</span></span>  
  
 <span data-ttu-id="2a67d-132">64-bit makinelerde işleyicileri üç kümesi kaydedilir (durumu ne olursa olsun `Enable32BitAppOnWin64` geçiş): tümleşik mod, biri WOW Klasik mod için ve biri yerel 64 bit Klasik mod için bir tane.</span><span class="sxs-lookup"><span data-stu-id="2a67d-132">On 64-bit machines, three sets of handlers are registered (regardless of the state of the `Enable32BitAppOnWin64` switch): one for Integrated mode, one for WOW Classic mode and one for native 64-bit Classic mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a67d-133">ServiceModelreg.exe WFServicesReg.exe ekleme, kaldırma veya kod haritalarını veya belirli bir Web sitesi için işleyiciler onarma izin vermiyor.</span><span class="sxs-lookup"><span data-stu-id="2a67d-133">Unlike ServiceModelreg.exe, WFServicesReg.exe does not allow adding, removing, or repairing scriptmaps or handlers for a particular Web site.</span></span> <span data-ttu-id="2a67d-134">Bu sorun için bir geçici çözüm için "Kod haritalarını onarma" bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="2a67d-134">For a workaround to this issue, see the "Repairing the Scriptmaps" section.</span></span>  
  
## <a name="usage-scenarios"></a><span data-ttu-id="2a67d-135">Kullanım senaryoları</span><span class="sxs-lookup"><span data-stu-id="2a67d-135">Usage Scenarios</span></span>  
  
### <a name="installing-iis-after-net-framework-35-is-installed"></a><span data-ttu-id="2a67d-136">.NET Framework 3.5 yüklendikten sonra IIS yükleme</span><span class="sxs-lookup"><span data-stu-id="2a67d-136">Installing IIS after .NET Framework 3.5 is installed</span></span>  
 <span data-ttu-id="2a67d-137">Üzerinde bir [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] makine [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] IIS yükleme önce yüklenir.</span><span class="sxs-lookup"><span data-stu-id="2a67d-137">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed prior to IIS installation.</span></span> <span data-ttu-id="2a67d-138">IIS metatabanı yüklenmesi kullanılamazlık nedeniyle [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] .xoml ve .rules kod haritalarını yüklemeden başarılı olur.</span><span class="sxs-lookup"><span data-stu-id="2a67d-138">Due to the unavailability of the IIS metabase, installation of [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] succeeds without installing .xoml and .rules scriptmaps.</span></span>  
  
 <span data-ttu-id="2a67d-139">IIS yüklendikten sonra WFServicesReg.exe aracıyla kullanabilirsiniz `/c` bu belirli kod haritalarını yüklemek için anahtar.</span><span class="sxs-lookup"><span data-stu-id="2a67d-139">After IIS is installed, you can use the WFServicesReg.exe tool with the `/c` switch to install these specific scriptmaps.</span></span>  
  
### <a name="repairing-the-scriptmaps"></a><span data-ttu-id="2a67d-140">Komut dosyası eşleştirmelerini onarma</span><span class="sxs-lookup"><span data-stu-id="2a67d-140">Repairing the Scriptmaps</span></span>  
  
#### <a name="scriptmap-deleted-under-web-sites-node"></a><span data-ttu-id="2a67d-141">Komut dosyası eşlemesini Web siteleri düğümünde silindi</span><span class="sxs-lookup"><span data-stu-id="2a67d-141">Scriptmap deleted under Web Sites node</span></span>  
 <span data-ttu-id="2a67d-142">Üzerinde bir [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] makine, .xoml ya da .rules Web siteleri düğümden silinmiş yanlışlıkla.</span><span class="sxs-lookup"><span data-stu-id="2a67d-142">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from the Web Sites node.</span></span> <span data-ttu-id="2a67d-143">Bu WFServicesReg.exe aracıyla çalıştırarak onarılabilir `/c` geçin.</span><span class="sxs-lookup"><span data-stu-id="2a67d-143">This can be repaired by running the WFServicesReg.exe tool with the `/c` switch.</span></span>  
  
#### <a name="scriptmap-deleted-under-a-particular-web-site"></a><span data-ttu-id="2a67d-144">Komut dosyası eşlemesini altında belirli bir Web sitesi silindi</span><span class="sxs-lookup"><span data-stu-id="2a67d-144">Scriptmap deleted under a particular Web site</span></span>  
 <span data-ttu-id="2a67d-145">Üzerinde bir [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] makine, .xoml ya da .rules yanlışlıkla silindiğinden belirli bir Web sitesinden (örneğin, varsayılan Web sitesi) yerine, Web siteleri düğümü.</span><span class="sxs-lookup"><span data-stu-id="2a67d-145">On a [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] machine, .xoml or .rules is accidentally deleted from a particular Web site (for example, the Default Web Site) rather than from the Web Sites node.</span></span>  
  
 <span data-ttu-id="2a67d-146">Belirli bir Web sitesi için silinen işleyiciler onarmak için "WFServicesReg.exe r" çalışması gerektiğini işleyicileri tüm Web sitelerinden kaldırmak için ardından "WFServicesReg.exe c" çalıştırın uygun işleyicileri için tüm Web siteleri oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="2a67d-146">To repair deleted handlers for a particular Web site, you should run "WFServicesReg.exe /r" to remove handlers from all Web sites, then run "WFServicesReg.exe /c" to create the appropriate handlers for all Web sites.</span></span>  
  
### <a name="configuring-handlers-after-switching-iis-mode"></a><span data-ttu-id="2a67d-147">IIS modu değiştirdikten sonra işleyicileri yapılandırma</span><span class="sxs-lookup"><span data-stu-id="2a67d-147">Configuring handlers after switching IIS mode</span></span>  
 <span data-ttu-id="2a67d-148">IIS paylaşılan Yapılandırması modunda olduğunda ve [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] olan yüklü, IIS metatabanı paylaşılan bir konum altında yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="2a67d-148">When IIS is in shared configuration mode and [!INCLUDE[netfx35_short](../../../includes/netfx35-short-md.md)] is installed, the IIS metabase is configured under a shared location.</span></span> <span data-ttu-id="2a67d-149">IIS yapılandırma paylaşılmayan moduna geçiş yaparsanız yerel metatabanı gerekli işleyicileri içermez.</span><span class="sxs-lookup"><span data-stu-id="2a67d-149">If you switch IIS to non-shared configuration mode, the local metabase will not contain the required handlers.</span></span> <span data-ttu-id="2a67d-150">Yerel metatabanı düzgün bir şekilde yapılandırmak için "yerel metatabanı yapılandıran yerel ya da çalışma WFServicesReg.exe /c", paylaşılan metabase ya da içeri aktarabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="2a67d-150">To configure the local metabase properly, you can either import the shared metabase to local, or run "WFServicesReg.exe /c", which configures the local metabase.</span></span>