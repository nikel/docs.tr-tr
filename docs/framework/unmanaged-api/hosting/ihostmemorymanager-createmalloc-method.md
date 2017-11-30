---
title: "IHostMemoryManager::CreateMAlloc Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostMemoryManager.CreateMAlloc
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostMemoryManager::CreateMAlloc
helpviewer_keywords:
- CreateAlloc method [.NET Framework hosting]
- IHostMemoryManager::CreateMAlloc method [.NET Framework hosting]
ms.assetid: 9ee6e052-bef7-4350-9e4f-edfffd99ad6f
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b4f8a23d03b3d839aeab5d2f571cb4f98f1ec5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ihostmemorymanagercreatemalloc-method"></a><span data-ttu-id="49799-102">IHostMemoryManager::CreateMAlloc Yöntemi</span><span class="sxs-lookup"><span data-stu-id="49799-102">IHostMemoryManager::CreateMAlloc Method</span></span>
<span data-ttu-id="49799-103">Bir arabirim işaretçisi alır bir [Ihostmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) ana bilgisayar tarafından oluşturulan bir yığın ayırma isteklerini yapmak için kullanılan örnek.</span><span class="sxs-lookup"><span data-stu-id="49799-103">Gets an interface pointer to an [IHostMAlloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) instance that is used to make allocation requests from a heap created by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49799-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="49799-104">Syntax</span></span>  
  
```  
HRESULT CreateMalloc (  
    [in]  DWORD         dwMallocType,  
    [out] IHostMalloc **ppMalloc  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49799-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="49799-105">Parameters</span></span>  
 `dwMallocType`  
 <span data-ttu-id="49799-106">[in] Bir birleşimini [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) ayrılan bellek özelliklerini belirleyen bayrak.</span><span class="sxs-lookup"><span data-stu-id="49799-106">[in] A combination of [MALLOC_TYPE](../../../../docs/framework/unmanaged-api/hosting/malloc-type-enumeration.md) flags that specifies the characteristics of the memory that is being allocated.</span></span>  
  
 `ppMAlloc`  
 <span data-ttu-id="49799-107">[out] Adresine bir işaretçi bir `IHostMAlloc` ana bilgisayarı tarafından sağlanan örneği.</span><span class="sxs-lookup"><span data-stu-id="49799-107">[out] A pointer to the address of an `IHostMAlloc` instance provided by the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49799-108">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="49799-108">Return Value</span></span>  
  
|<span data-ttu-id="49799-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49799-109">HRESULT</span></span>|<span data-ttu-id="49799-110">Açıklama</span><span class="sxs-lookup"><span data-stu-id="49799-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="49799-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="49799-111">S_OK</span></span>|<span data-ttu-id="49799-112">`CreateMAlloc`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="49799-112">`CreateMAlloc` returned successfully.</span></span>|  
|<span data-ttu-id="49799-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="49799-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="49799-114">Ortak dil çalışma zamanı (CLR) süreç içine yüklü değil veya CLR içinde yönetilen kod çalıştıramaz veya çağrı başarılı bir şekilde işlemek bir durumda.</span><span class="sxs-lookup"><span data-stu-id="49799-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="49799-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="49799-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="49799-116">Arama zaman aşımına uğradı.</span><span class="sxs-lookup"><span data-stu-id="49799-116">The call timed out.</span></span>|  
|<span data-ttu-id="49799-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="49799-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="49799-118">Arayan kilidi kendisine ait değil.</span><span class="sxs-lookup"><span data-stu-id="49799-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="49799-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="49799-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="49799-120">Bir olay engellenmiş iş parçacığı sırasında iptal edildi veya fiber üzerinde beklediği.</span><span class="sxs-lookup"><span data-stu-id="49799-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="49799-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="49799-121">E_FAIL</span></span>|<span data-ttu-id="49799-122">Bilinmeyen yıkıcı bir hata oluştu.</span><span class="sxs-lookup"><span data-stu-id="49799-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="49799-123">Bir yöntem E_FAIL döndüğünde, CLR artık işlemi içinde kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="49799-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="49799-124">Yöntemleri barındırma sonraki çağrılar HOST_E_CLRNOTAVAILABLE döndürür.</span><span class="sxs-lookup"><span data-stu-id="49799-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="49799-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="49799-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="49799-126">Yeterli fiziksel bellek ayırma isteği tamamlamak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="49799-126">Not enough physical memory was available to complete the allocation request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49799-127">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="49799-127">Remarks</span></span>  
 <span data-ttu-id="49799-128">`CreateMAlloc`CLR standart Win32 işlevleri yerine ana bilgisayar üzerinden ayırma istekler yapmasını sağlayan bir nesne döndürür.</span><span class="sxs-lookup"><span data-stu-id="49799-128">`CreateMAlloc` returns an object that allows the CLR to make allocation requests through the host instead of using the standard Win32 functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49799-129">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="49799-129">Requirements</span></span>  
 <span data-ttu-id="49799-130">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49799-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49799-131">**Başlık:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="49799-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="49799-132">**Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil</span><span class="sxs-lookup"><span data-stu-id="49799-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="49799-133">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49799-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49799-134">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="49799-134">See Also</span></span>  
 [<span data-ttu-id="49799-135">Ihostmalloc arabirimi</span><span class="sxs-lookup"><span data-stu-id="49799-135">IHostMalloc Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md)  
 [<span data-ttu-id="49799-136">Ihostmemorymanager arabirimi</span><span class="sxs-lookup"><span data-stu-id="49799-136">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)