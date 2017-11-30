---
title: "IHostThreadPoolManager::SetMinThreads Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMinThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMinThreads
helpviewer_keywords:
- SetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
- IHostThreadPoolManager::SetMinThreads method [.NET Framework hosting]
ms.assetid: 10409db9-9fd2-4e4d-b8cd-cf6fec0afaa2
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ab0b107c050b1c4b686f761ede75ea2349825270
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetminthreads-method"></a><span data-ttu-id="56cac-102">IHostThreadPoolManager::SetMinThreads Yöntemi</span><span class="sxs-lookup"><span data-stu-id="56cac-102">IHostThreadPoolManager::SetMinThreads Method</span></span>
<span data-ttu-id="56cac-103">Konak korumalıdır boş iş parçacığı sayısı alt sınırını istekleri kapatıldığını içinde ayarlar.</span><span class="sxs-lookup"><span data-stu-id="56cac-103">Sets the minimum number of idle threads that the host must maintain in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56cac-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="56cac-104">Syntax</span></span>  
  
```  
HRESULT SetMinThreads (  
    [in] DWORD MinThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56cac-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="56cac-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="56cac-106">[in] Yeni minimum, konak korumalıdır iş parçacığı sayısı.</span><span class="sxs-lookup"><span data-stu-id="56cac-106">[in] The new minimum number of threads that the host must maintain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56cac-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="56cac-107">Return Value</span></span>  
  
|<span data-ttu-id="56cac-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56cac-108">HRESULT</span></span>|<span data-ttu-id="56cac-109">Açıklama</span><span class="sxs-lookup"><span data-stu-id="56cac-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56cac-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="56cac-110">S_OK</span></span>|<span data-ttu-id="56cac-111">`SetMinThreads`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="56cac-111">`SetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="56cac-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="56cac-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="56cac-113">Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="56cac-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="56cac-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="56cac-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="56cac-115">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="56cac-115">The call timed out.</span></span>|  
|<span data-ttu-id="56cac-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="56cac-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="56cac-117">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="56cac-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="56cac-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="56cac-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="56cac-119">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="56cac-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="56cac-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="56cac-120">E_FAIL</span></span>|<span data-ttu-id="56cac-121">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="56cac-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="56cac-122">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="56cac-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="56cac-123">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="56cac-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="56cac-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="56cac-124">E_NOTIMPL</span></span>|<span data-ttu-id="56cac-125">Ana bilgisayar uygulaması sağlamaz `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="56cac-125">The host does not provide an implementation of `SetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56cac-126">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="56cac-126">Remarks</span></span>  
 <span data-ttu-id="56cac-127">Bir ana bilgisayar uygulaması sağlamak için gerekli olmayan `SetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="56cac-127">A host is not required to provide an implementation of `SetMinThreads`.</span></span> <span data-ttu-id="56cac-128">Bu durumda, E_NOTIMPL HRESULT değerini döndürmelidir.</span><span class="sxs-lookup"><span data-stu-id="56cac-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56cac-129">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="56cac-129">Requirements</span></span>  
 <span data-ttu-id="56cac-130">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56cac-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56cac-131">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="56cac-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="56cac-132">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="56cac-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56cac-133">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56cac-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56cac-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="56cac-134">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="56cac-135">GetMinThreads yöntemi</span><span class="sxs-lookup"><span data-stu-id="56cac-135">GetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [<span data-ttu-id="56cac-136">SetMaxThreads yöntemi</span><span class="sxs-lookup"><span data-stu-id="56cac-136">SetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [<span data-ttu-id="56cac-137">Ihostthreadpoolmanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="56cac-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)