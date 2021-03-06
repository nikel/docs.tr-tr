---
title: "ICorProfilerInfo::ForceGC Yöntemi"
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
- ICorProfilerInfo.ForceGC
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::ForceGC
helpviewer_keywords:
- ICorProfilerInfo::ForceGC method [.NET Framework profiling]
- ForceGC method [.NET Framework profiling]
ms.assetid: 0da1ef80-d242-4636-87d0-43e0470b342a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 89e0e9534b5e074e5a22ceaec4e04467f752281e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfoforcegc-method"></a>ICorProfilerInfo::ForceGC Yöntemi
Ortak dil çalışma zamanı içinde (CLR) gerçekleşmesi için atık toplama zorlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT ForceGC();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `ForceGC` Yöntemi çağrılır, yönetilen kod çalıştırılmadı ve tüm profil oluşturucu geri aramalar kendi yığında yok bir iş. Çağıran profil oluşturucu içinde ayrı bir iş parçacığı oluşturmak için en uygun uygulamasıdır `ForceGC` erdiği zaman.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorProf.idl, CorProf.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorProfilerInfo Arabirimi](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
