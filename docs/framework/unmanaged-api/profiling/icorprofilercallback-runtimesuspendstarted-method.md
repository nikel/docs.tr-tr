---
title: "ICorProfilerCallback::RuntimeSuspendStarted Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: dc1b229a21b59a842a5bcc47620302711cecdc42
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted Yöntemi
Profil Oluşturucu çalışma zamanı hakkında tüm çalışma zamanı iş parçacıklarını askıya alma olduğunu bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `suspendReason`  
 [in] Değerini [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) askıya nedenini belirten numaralandırma.  
  
## <a name="remarks"></a>Açıklamalar  
 Yönetilmeyen kod içinde tüm çalışma zamanı iş parçacıklarının bunlar çalışma zamanı yeniden girmeyi deneyin kadar çalışmaya devam etmek için izin verilir. Çalışma zamanı yeniden devam edene dek bu noktada bunlar da askıya alınır. Bu durum, çalışma zamanı girin yeni iş parçacığı için de geçerlidir. Tüm iş parçacıklarının çalışma zamanında ya da kesilebilir kodda zaten oldukları veya kesilebilir kod ulaştığında askıya almak için sorulan hemen askıya ' dir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorProfilerCallback Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [RuntimeSuspendFinished Yöntemi](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
