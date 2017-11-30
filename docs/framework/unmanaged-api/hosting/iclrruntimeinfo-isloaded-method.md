---
title: "ICLRRuntimeInfo::IsLoaded Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.IsLoaded
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::IsLoaded
helpviewer_keywords:
- IsLoaded method [.NET Framework hosting]
- ICLRRuntimeInfo::IsLoaded method [.NET Framework hosting]
ms.assetid: fdc5a3a7-71ff-4025-99a1-59e4ee0bfe1b
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac7ed77dd4cb141257a1b73ccd433c7d17ee1f38
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoisloaded-method"></a><span data-ttu-id="3a95a-102">ICLRRuntimeInfo::IsLoaded Yöntemi</span><span class="sxs-lookup"><span data-stu-id="3a95a-102">ICLRRuntimeInfo::IsLoaded Method</span></span>
<span data-ttu-id="3a95a-103">Ortak dil çalışma zamanı (CLR) ile ilişkili olup olmadığını gösteren [Iclrruntimeınfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) arabirimi süreç içine yüklenir.</span><span class="sxs-lookup"><span data-stu-id="3a95a-103">Indicates whether the common language runtime (CLR) associated with the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface is loaded into a process.</span></span> <span data-ttu-id="3a95a-104">Bir çalışma zamanı da başlatılmadan yüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="3a95a-104">A runtime can be loaded without also being started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a95a-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="3a95a-105">Syntax</span></span>  
  
```  
HRESULT IsLoaded(  
[in]  HANDLE hndProcess,  
[out, retval] BOOL *pbLoaded);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3a95a-106">Parametreler</span><span class="sxs-lookup"><span data-stu-id="3a95a-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="3a95a-107">[in] İşlem için bir tanıtıcı.</span><span class="sxs-lookup"><span data-stu-id="3a95a-107">[in] A handle to the process.</span></span>  
  
 `pbLoaded`  
 <span data-ttu-id="3a95a-108">[out] `true` CLR işlemine yüklenen; Aksi takdirde ise `false`.</span><span class="sxs-lookup"><span data-stu-id="3a95a-108">[out] `true` if the CLR is loaded into the process; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a95a-109">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="3a95a-109">Return Value</span></span>  
 <span data-ttu-id="3a95a-110">Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.</span><span class="sxs-lookup"><span data-stu-id="3a95a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3a95a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a95a-111">HRESULT</span></span>|<span data-ttu-id="3a95a-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="3a95a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a95a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a95a-113">S_OK</span></span>|<span data-ttu-id="3a95a-114">Yöntem başarıyla tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="3a95a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="3a95a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3a95a-115">E_POINTER</span></span>|<span data-ttu-id="3a95a-116">`pbLoaded`null şeklindedir.</span><span class="sxs-lookup"><span data-stu-id="3a95a-116">`pbLoaded` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a95a-117">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="3a95a-117">Remarks</span></span>  
 <span data-ttu-id="3a95a-118">Geriye dönük olarak uyumlu bu yöntem aşağıdaki işlevler ve arabirimleri ile:</span><span class="sxs-lookup"><span data-stu-id="3a95a-118">This method is backward-compatible with the following functions and interfaces:</span></span>  
  
-   <span data-ttu-id="3a95a-119">[Icorruntimehost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) arabirimi (.NET Framework sürüm 1 barındırma API).</span><span class="sxs-lookup"><span data-stu-id="3a95a-119">[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface (in the .NET Framework version 1 hosting API).</span></span>  
  
-   <span data-ttu-id="3a95a-120">[Iclrruntimehost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) arabirimi (API barındırma .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="3a95a-120">[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface (in the .NET Framework 2.0 hosting API).</span></span>  
  
-   <span data-ttu-id="3a95a-121">Kullanım dışı `CorBindTo*` işlevleri (bkz [kullanım dışı CLR barındırma işlevleri](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) API barındırma .NET Framework 2.0).</span><span class="sxs-lookup"><span data-stu-id="3a95a-121">Deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span>  
  
 <span data-ttu-id="3a95a-122">Bir ana bilgisayar kullanım dışı birini çağırabilir `CorBindTo*` gibi işlevleri [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) CLR belirli bir sürümünü oluşturmak için işlevi.</span><span class="sxs-lookup"><span data-stu-id="3a95a-122">A host may call one of the deprecated `CorBindTo*` functions, such as the [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md) function, to instantiate a specific version of the CLR.</span></span> <span data-ttu-id="3a95a-123">Ana bilgisayar ardından çağırabilirsiniz [Iclrmetahost::getruntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) yöntemi ve almak için aynı sürüm numarası belirtin bir [Iclrruntimeınfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) arabirimi.</span><span class="sxs-lookup"><span data-stu-id="3a95a-123">The host could then call the [ICLRMetaHost::GetRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-getruntime-method.md) method and specify the same version number to obtain a [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="3a95a-124">Konak sonra çağırırsa `IsLoaded` yöntemi döndürülen [Iclrruntimeınfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) arabirimi, `pbLoaded` döndürür `true`; Aksi takdirde döndürdüğü `false`.</span><span class="sxs-lookup"><span data-stu-id="3a95a-124">If the host then calls the `IsLoaded` method on the returned [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface, `pbLoaded` returns `true`; otherwise, it returns `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a95a-125">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="3a95a-125">Requirements</span></span>  
 <span data-ttu-id="3a95a-126">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a95a-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a95a-127">**Başlık:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3a95a-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a95a-128">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="3a95a-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a95a-129">**.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a95a-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a95a-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="3a95a-130">See Also</span></span>  
 [<span data-ttu-id="3a95a-131">Iclrruntimeınfo arabirimi</span><span class="sxs-lookup"><span data-stu-id="3a95a-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="3a95a-132">Barındırma arabirimleri</span><span class="sxs-lookup"><span data-stu-id="3a95a-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="3a95a-133">Barındırma</span><span class="sxs-lookup"><span data-stu-id="3a95a-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)