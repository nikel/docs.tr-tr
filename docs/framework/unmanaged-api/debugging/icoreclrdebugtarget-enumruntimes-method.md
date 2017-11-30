---
title: "ICoreClrDebugTarget::EnumRuntimes Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICoreClrDebugTarget.EnumRuntimes
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d28e5f3f529f72607e2ddd84789e89f82dcdaba0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="5ebac-102">ICoreClrDebugTarget::EnumRuntimes Yöntemi</span><span class="sxs-lookup"><span data-stu-id="5ebac-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="5ebac-103">Ortak dil çalışma zamanları (CLRs) bir uzak bilgisayarda çalışan belirtilen işlemde numaralandırır.</span><span class="sxs-lookup"><span data-stu-id="5ebac-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ebac-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="5ebac-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ebac-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="5ebac-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="5ebac-106">[in] Çalışma zamanları listeleme istediğiniz işlemin iç işlem kimliği.</span><span class="sxs-lookup"><span data-stu-id="5ebac-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="5ebac-107">Bu `m_dwInternalID` karşılık gelen gelen [Coreclrdebugprocınfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="5ebac-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="5ebac-108">[out] Döndürülen çalışma zamanları sayısı `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="5ebac-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="5ebac-109">Bu değer, 0 (sıfır) olabilir.</span><span class="sxs-lookup"><span data-stu-id="5ebac-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="5ebac-110">[out] Bir dizi [Coreclrdebugruntimeınfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) çalışma zamanları temsil eden yapılar uzak hedefe işleminde yüklendi.</span><span class="sxs-lookup"><span data-stu-id="5ebac-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ebac-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="5ebac-111">Return Value</span></span>  
 <span data-ttu-id="5ebac-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5ebac-112">S_OK</span></span>  
 <span data-ttu-id="5ebac-113">Başarılı.</span><span class="sxs-lookup"><span data-stu-id="5ebac-113">Success.</span></span>  
  
 <span data-ttu-id="5ebac-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5ebac-114">S_FALSE</span></span>  
 <span data-ttu-id="5ebac-115">`dwInternalProcessID`işlemin sonlandırıldığından bilgisayar üzerinde çalışan herhangi bir işlem büyük olasılıkla eşleşmiyor.</span><span class="sxs-lookup"><span data-stu-id="5ebac-115">`dwInternalProcessID` does not match any process that is running on the computer, probably because the process was terminated.</span></span> <span data-ttu-id="5ebac-116">`pcRuntimes`ve `ppRuntimes` null olur.</span><span class="sxs-lookup"><span data-stu-id="5ebac-116">`pcRuntimes` and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="5ebac-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5ebac-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="5ebac-118">İçin yeterli bellek ayrılamıyor `ppRuntimes`.</span><span class="sxs-lookup"><span data-stu-id="5ebac-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="5ebac-119">E_FAIL (veya diğer E_ dönüş kodları)</span><span class="sxs-lookup"><span data-stu-id="5ebac-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="5ebac-120">Diğer hataları.</span><span class="sxs-lookup"><span data-stu-id="5ebac-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ebac-121">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="5ebac-121">Remarks</span></span>  
 <span data-ttu-id="5ebac-122">Bu yöntem tarafından ayrılan belleği boşaltmak için çağrı [Icoreclrdebugtarget::freememory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="5ebac-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ebac-123">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="5ebac-123">Requirements</span></span>  
 <span data-ttu-id="5ebac-124">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ebac-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ebac-125">**Başlık:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="5ebac-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="5ebac-126">**Kitaplığı:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="5ebac-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="5ebac-127">**.NET framework sürümleri:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5ebac-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebac-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5ebac-128">See Also</span></span>  
 [<span data-ttu-id="5ebac-129">Icoreclrdebugtarget arabirimi</span><span class="sxs-lookup"><span data-stu-id="5ebac-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)