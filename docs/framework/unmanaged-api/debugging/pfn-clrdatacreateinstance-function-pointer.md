---
title: "PFN_CLRDataCreateInstance İşlev İşaretçisi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PFN_CLRDataCreateInstance
api_location: mscordbi.dll
api_type: COM
f1_keywords: PFN_CLRDataCreateInstance
helpviewer_keywords: PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7ec5783381c667d666c447b6d9861d9baaad3907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a><span data-ttu-id="fb934-102">PFN_CLRDataCreateInstance İşlev İşaretçisi</span><span class="sxs-lookup"><span data-stu-id="fb934-102">PFN_CLRDataCreateInstance Function Pointer</span></span>
<span data-ttu-id="fb934-103">Belirtilen hedef öğesi için bir arabirimi nesnesi oluşturan bir işlev noktalarına.</span><span class="sxs-lookup"><span data-stu-id="fb934-103">Points to a function that creates an interface object for the specified target item.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb934-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fb934-104">Syntax</span></span>  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb934-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="fb934-105">Parameters</span></span>  
 `iid`  
 <span data-ttu-id="fb934-106">[in] Arabirim örneğinin oluşturulması için tanımlayıcı.</span><span class="sxs-lookup"><span data-stu-id="fb934-106">[in] The identifier of the interface to be instantiated.</span></span>  
  
 `target`  
 <span data-ttu-id="fb934-107">[in] Kullanıcı uygulanan bir işaretçi [Iclrdatatarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) arabirimi nesnesi oluşturulacağı hedef öğeyi temsil eden nesne.</span><span class="sxs-lookup"><span data-stu-id="fb934-107">[in] A pointer to a user-implemented [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) object that represents the target item for which to create the interface object.</span></span>  
  
 `iface`  
 <span data-ttu-id="fb934-108">[out] Döndürülen arabirimi nesnesi adresini gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="fb934-108">[out] A pointer to the address of the returned interface object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb934-109">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="fb934-109">Remarks</span></span>  
 <span data-ttu-id="fb934-110">`ICLRDataTarget` Nesnesi, hata ayıklama uygulama yazıcı tarafından gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="fb934-110">The `ICLRDataTarget` object is implemented by the writer of the debugging application.</span></span> <span data-ttu-id="fb934-111">Uygulama temsil ettiği hedef öğesi türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="fb934-111">The implementation depends on the type of target item being represented.</span></span> <span data-ttu-id="fb934-112">Hedef öğesi, bir işlem, bellek dökümü, uzak makine vb. olabilir.</span><span class="sxs-lookup"><span data-stu-id="fb934-112">The target item may be a process, memory dump, remote machine, and so on.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb934-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fb934-113">Requirements</span></span>  
 <span data-ttu-id="fb934-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb934-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb934-115">**Başlık:** ClrData.idl</span><span class="sxs-lookup"><span data-stu-id="fb934-115">**Header:** ClrData.idl</span></span>  
  
 <span data-ttu-id="fb934-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb934-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb934-117">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb934-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb934-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fb934-118">See Also</span></span>  
 [<span data-ttu-id="fb934-119">Hata ayıklama genel statik işlevleri</span><span class="sxs-lookup"><span data-stu-id="fb934-119">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)