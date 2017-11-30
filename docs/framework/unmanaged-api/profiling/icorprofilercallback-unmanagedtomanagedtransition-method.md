---
title: "ICorProfilerCallback::UnmanagedToManagedTransition Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.UnmanagedToManagedTransition
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 45a2ceb53263e317c5c72695d6bc1e93f8f70bbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a><span data-ttu-id="de880-102">ICorProfilerCallback::UnmanagedToManagedTransition Yöntemi</span><span class="sxs-lookup"><span data-stu-id="de880-102">ICorProfilerCallback::UnmanagedToManagedTransition Method</span></span>
<span data-ttu-id="de880-103">Profil Oluşturucu yönetilmeyen koddan yönetilen koda geçiş oluştuğunu bildirir.</span><span class="sxs-lookup"><span data-stu-id="de880-103">Notifies the profiler that a transition from unmanaged code to managed code has occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de880-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="de880-104">Syntax</span></span>  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de880-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="de880-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="de880-106">[in] Çağrıldığından işlevi kimliği.</span><span class="sxs-lookup"><span data-stu-id="de880-106">[in] The ID of the function that is being called.</span></span>  
  
 `reason`  
 <span data-ttu-id="de880-107">[in] Değerini [cor_prf_transıtıon_reason](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) numaralandırması geçişi yönetilmeyen koddan yönetilen koda bir çağrı nedeniyle veya yönetilen bir adlı yönetilmeyen işlevi bir dönüş nedeniyle oluşup oluşmadığını gösterir.</span><span class="sxs-lookup"><span data-stu-id="de880-107">[in] A value of the [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumeration that indicates whether the transition occurred because of a call into managed code from unmanaged code, or because of a return from an unmanaged function called by a managed one.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de880-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="de880-108">Remarks</span></span>  
 <span data-ttu-id="de880-109">Varsa değerini `reason` COR_PRF_TRANSITION_RETURN olduğu ve `functionId` null olmayan kimliği, yönetilmeyen işlevinin olan ve hiçbir zaman tam zamanında (JIT) derleyici kullanılarak derlenmiştir işlevi değil.</span><span class="sxs-lookup"><span data-stu-id="de880-109">If the value of `reason` is COR_PRF_TRANSITION_RETURN and `functionId` is not null, the function ID is that of the unmanaged function, and will never have been compiled using the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="de880-110">Yönetilmeyen İşlevler bunlarla ilişkili bir ad ve bazı meta verileri gibi bazı temel bilgileri var.</span><span class="sxs-lookup"><span data-stu-id="de880-110">Unmanaged functions have some basic information associated with them, such as a name and some metadata.</span></span>  
  
 <span data-ttu-id="de880-111">Varsa değerini `reason` COR_PRF_TRANSITION_CALL, olduğundan çağrılan işlev (diğer bir deyişle, yönetilen işlevi) henüz JIT derlenmiş olduğunu değil mümkün olabilir.</span><span class="sxs-lookup"><span data-stu-id="de880-111">If the value of `reason` is COR_PRF_TRANSITION_CALL, it may be possible that the called function (that is, the managed function) has not yet been JIT-compiled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de880-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="de880-112">Requirements</span></span>  
 <span data-ttu-id="de880-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de880-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de880-114">**Başlık:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="de880-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="de880-115">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de880-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de880-116">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de880-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de880-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="de880-117">See Also</span></span>  
 [<span data-ttu-id="de880-118">Icorprofilercallback arabirimi</span><span class="sxs-lookup"><span data-stu-id="de880-118">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="de880-119">ManagedToUnmanagedTransition yöntemi</span><span class="sxs-lookup"><span data-stu-id="de880-119">ManagedToUnmanagedTransition Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [<span data-ttu-id="de880-120">C++ (DllImport özniteliği) açık PInvoke kullanma</span><span class="sxs-lookup"><span data-stu-id="de880-120">Using Explicit PInvoke in C++ (DllImport Attribute)</span></span>](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [<span data-ttu-id="de880-121">C++ birlikte çalışması (örtük PInvoke) kullanarak</span><span class="sxs-lookup"><span data-stu-id="de880-121">Using C++ Interop (Implicit PInvoke)</span></span>](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)