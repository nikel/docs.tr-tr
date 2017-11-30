---
title: "Yan Yana Yürütme için Bileşen Oluşturma Yönergeleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution, multiple application versions
- side-by-side execution, multiple component versions
ms.assetid: 5c540161-6e40-42e9-be92-6175aee2c46a
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 054744612ec54861f675005a27a309e00024b242
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="guidelines-for-creating-components-for-side-by-side-execution"></a><span data-ttu-id="cb7fd-102">Yan Yana Yürütme için Bileşen Oluşturma Yönergeleri</span><span class="sxs-lookup"><span data-stu-id="cb7fd-102">Guidelines for Creating Components for Side-by-Side Execution</span></span>
<span data-ttu-id="cb7fd-103">Yönetilen uygulamalar veya yan yana yürütme için tasarlanmış bileşenleri oluşturmak için aşağıdaki genel yönergeleri izleyin:</span><span class="sxs-lookup"><span data-stu-id="cb7fd-103">Follow these general guidelines to create managed applications or components designed for side-by-side execution:</span></span>  
  
-   <span data-ttu-id="cb7fd-104">Tür kimliği dosya belirli bir sürümü bağlayın.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-104">Bind type identity to a particular version of a file.</span></span>  
  
     <span data-ttu-id="cb7fd-105">Ortak dil çalışma zamanı tür kimliğini tanımlayıcı adlı derlemeler kullanarak belirli dosya sürümüne bağlar.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-105">The common language runtime binds type identity to a particular file version by using strong-named assemblies.</span></span> <span data-ttu-id="cb7fd-106">Bir uygulama veya yan yana yürütme için bileşen oluşturmak için tüm derlemelerin tanımlayıcı bir ad vermeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-106">To create an application or component for side-by-side execution, you must give all assemblies a strong name.</span></span> <span data-ttu-id="cb7fd-107">Bu, kesin türü kimliği oluşturur ve doğru dosya türü çözümlemesi yönlendirilir sağlar.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-107">This creates precise type identity and ensures that any type resolution is directed to the correct file.</span></span> <span data-ttu-id="cb7fd-108">Tanımlayıcı adlı bir derleme, sürüm, kültür ve çalışma zamanı bağlama isteği gerçekleştirmek için doğru dosyayı bulmak için kullandığı yayımcı bilgilerini içerir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-108">A strong-named assembly contains version, culture, and publisher information that the runtime uses to locate the correct file to fulfill a binding request.</span></span>  
  
-   <span data-ttu-id="cb7fd-109">Sürüm algılayan depolama kullanın.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-109">Use version-aware storage.</span></span>  
  
     <span data-ttu-id="cb7fd-110">Çalışma zamanı sürümü kullanan depolama sağlamak için genel derleme önbelleği kullanır.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-110">The runtime uses the global assembly cache to provide version-aware storage.</span></span> <span data-ttu-id="cb7fd-111">Genel Derleme Önbelleği, .NET Framework kullanan her bilgisayarda yüklü bir sürümünü kullanan dizin yapısıdır.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-111">The global assembly cache is a version-aware directory structure installed on every computer that uses the .NET Framework.</span></span> <span data-ttu-id="cb7fd-112">Bu derleme yeni bir sürümü yüklü olduğunda genel derleme önbelleğinde yüklü derlemelerin üzerine yazılmaz.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-112">Assemblies installed in the global assembly cache are not overwritten when a new version of that assembly is installed.</span></span>  
  
-   <span data-ttu-id="cb7fd-113">Bir uygulama veya yalıtımlı şekilde çalışır bileşeni oluşturun.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-113">Create an application or component that runs in isolation.</span></span>  
  
     <span data-ttu-id="cb7fd-114">Bir uygulama veya yalıtımlı şekilde çalışır bileşeni uygulama veya bileşenin iki örneği aynı anda çalıştırırken çakışmaları önlemek için kaynak yönetmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-114">An application or component that runs in isolation must manage resources to avoid conflicts when two instances of the application or component are running simultaneously.</span></span> <span data-ttu-id="cb7fd-115">Ayrıca uygulama veya bileşenin sürüme özgü dosya yapısı kullanmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-115">The application or component must also use a version-specific file structure.</span></span>  
  
## <a name="application-and-component-isolation"></a><span data-ttu-id="cb7fd-116">Uygulama ve bileşen yalıtımı</span><span class="sxs-lookup"><span data-stu-id="cb7fd-116">Application and Component Isolation</span></span>  
 <span data-ttu-id="cb7fd-117">Bir uygulama veya bileşen yan yana yürütme için başarıyla tasarlamak için bir yalıtım anahtardır.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-117">One key to successfully designing an application or component for side-by-side execution is isolation.</span></span> <span data-ttu-id="cb7fd-118">Uygulamanın veya bileşenin gerekir tüm kaynakları yönetebilir, özellikle g/ç, yalıtılmış bir şekilde dosya.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-118">The application or component must manage all resources, particularly file I/O, in an isolated manner.</span></span> <span data-ttu-id="cb7fd-119">Uygulama veya bileşenin yalıtım modunda çalışacağından emin olmak için aşağıdaki yönergeleri izleyin:</span><span class="sxs-lookup"><span data-stu-id="cb7fd-119">Follow these guidelines to make sure your application or component runs in isolation:</span></span>  
  
-   <span data-ttu-id="cb7fd-120">Kayıt defterine bir sürüme özgü biçimde yazın.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-120">Write to the registry in a version-specific way.</span></span> <span data-ttu-id="cb7fd-121">Değerleri kovanları veya sürüm belirtmek ve bilgi ya da durum bileşen sürümleri arasında paylaştırma anahtarları depolayın.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-121">Store values in hives or keys that indicate the version, and do not share information or state across versions of a component.</span></span> <span data-ttu-id="cb7fd-122">Bu iki uygulamanın ya da bilgi üzerine yazılmasını aynı anda çalışan bileşenleri önler.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-122">This prevents two applications or components running at the same time from overwriting information.</span></span>  
  
-   <span data-ttu-id="cb7fd-123">Böylece bir yarış durumu oluşmaz adlandırılmış çekirdek nesneleri sürüme özgü yapın.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-123">Make named kernel objects version-specific so that a race condition does not occur.</span></span> <span data-ttu-id="cb7fd-124">Bir yarış durumu gibi aynı uygulamanın iki sürümlerinden iki semafor diğer bağlı bekleme oluşur.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-124">For example, a race condition occurs when two semaphores from two versions of the same application wait on each other.</span></span>  
  
-   <span data-ttu-id="cb7fd-125">Dosya ve dizin adları sürüm farkında olun.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-125">Make file and directory names version-aware.</span></span> <span data-ttu-id="cb7fd-126">Bu dosya yapıları sürümü bilgilerini yararlanmalıdır anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-126">This means that file structures should rely on version information.</span></span>  
  
-   <span data-ttu-id="cb7fd-127">Kullanıcı hesapları ve grupları bir sürüme özgü şekilde oluşturun.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-127">Create user accounts and groups in a version-specific manner.</span></span> <span data-ttu-id="cb7fd-128">Kullanıcı hesapları ve grupları bir uygulama tarafından oluşturulan sürümü tarafından tanıtılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-128">User accounts and groups created by an application should be identified by version.</span></span> <span data-ttu-id="cb7fd-129">Kullanıcı hesapları ve grupları uygulama sürümleri arasında paylaşmayın.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-129">Do not share user accounts and groups between versions of an application.</span></span>  
  
## <a name="installing-and-uninstalling-versions"></a><span data-ttu-id="cb7fd-130">Yükleme ve sürümleri kaldırma</span><span class="sxs-lookup"><span data-stu-id="cb7fd-130">Installing and Uninstalling Versions</span></span>  
 <span data-ttu-id="cb7fd-131">Yan yana yürütme için bir uygulama tasarlarken, yükleme ve sürümleri kaldırma ile ilgili aşağıdaki yönergeleri izleyin:</span><span class="sxs-lookup"><span data-stu-id="cb7fd-131">When designing an application for side-by-side execution, follow these guidelines concerning installing and uninstalling versions:</span></span>  
  
-   <span data-ttu-id="cb7fd-132">Bilgi farklı bir .NET Framework sürümü altında çalışan diğer uygulamalar tarafından gerekli olabilecek kayıt defterinden silmeyin.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-132">Do not delete information from the registry that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="cb7fd-133">Farklı bir .NET Framework sürümü altında çalışan diğer uygulamalar tarafından gerekli olabilecek kayıt defterindeki bilgiler değiştirmeyin.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-133">Do not replace information in the registry that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="cb7fd-134">Farklı bir .NET Framework sürümü altında çalışan diğer uygulamalar tarafından gerekli olabilecek COM bileşenlerini kaydı yok.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-134">Do not unregister COM components that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="cb7fd-135">Değiştirmeyin **Inprocserver32** veya diğer kayıt defteri girdileri zaten kayıtlı bir COM sunucusu.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-135">Do not change **InprocServer32** or other registry entries for a COM server that was already registered.</span></span>  
  
-   <span data-ttu-id="cb7fd-136">Kullanıcı hesapları veya farklı bir .NET Framework sürümü altında çalışan diğer uygulamalar tarafından gerekli olabilecek silmeyin.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-136">Do not delete user accounts or groups that may be needed by other applications running under a different version of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="cb7fd-137">Herhangi bir sürüm bilgisi olmayan yolu içeren kayıt defterine eklemeyin.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-137">Do not add anything to the registry that contains an unversioned path.</span></span>  
  
## <a name="file-version-number-and-assembly-version-number"></a><span data-ttu-id="cb7fd-138">Dosya sürüm numarası ve derleme sürüm numarası</span><span class="sxs-lookup"><span data-stu-id="cb7fd-138">File Version Number and Assembly Version Number</span></span>  
 <span data-ttu-id="cb7fd-139">Dosya, çalışma zamanı tarafından kullanılmayan bir Win32 sürümü kaynak sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-139">File version is a Win32 version resource that is not used by the runtime.</span></span> <span data-ttu-id="cb7fd-140">Genel olarak, bir yerinde güncelleştirme için bile dosya sürümünü güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-140">In general, you update the file version even for an in-place update.</span></span> <span data-ttu-id="cb7fd-141">İki özdeş dosyaların farklı dosya sürümü bilgilerini olabilir ve iki farklı dosyaları aynı dosya sürümü bilgilerini olabilir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-141">Two identical files can have different file version information, and two different files can have the same file version information.</span></span>  
  
 <span data-ttu-id="cb7fd-142">Derleme sürümü için derleme bağlama çalışma zamanı tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-142">The assembly version is used by the runtime for assembly binding.</span></span> <span data-ttu-id="cb7fd-143">İki özdeş derlemeleri farklı sürüm numaralarını ile iki farklı derlemeleri olarak çalışma zamanı tarafından kabul edilir.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-143">Two identical assemblies with different version numbers are treated as two different assemblies by the runtime.</span></span>  
  
 <span data-ttu-id="cb7fd-144">[Genel Derleme Önbelleği Aracı (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) yalnızca dosyanın sürüm numarası daha yeni olduğunda bütünleştirilmiş değiştirmenizi sağlar.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-144">The [Global Assembly Cache tool (Gacutil.exe)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) allows you to replace an assembly when only the file version number is newer.</span></span> <span data-ttu-id="cb7fd-145">Derleme sürüm numarasını büyük olmadıkça yükleyici bütünleştirilmiş genellikle yüklemez.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-145">The installer generally does not install over an assembly unless the assembly version number is greater.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7fd-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cb7fd-146">See Also</span></span>  
 [<span data-ttu-id="cb7fd-147">Yan yana yürütme</span><span class="sxs-lookup"><span data-stu-id="cb7fd-147">Side-by-Side Execution</span></span>](../../../docs/framework/deployment/side-by-side-execution.md)  
 [<span data-ttu-id="cb7fd-148">Nasıl yapılır: etkinleştirme ve otomatik bağlama yönlendirmesini devre dışı</span><span class="sxs-lookup"><span data-stu-id="cb7fd-148">How to: Enable and Disable Automatic Binding Redirection</span></span>](../../../docs/framework/configure-apps/how-to-enable-and-disable-automatic-binding-redirection.md)