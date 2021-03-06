---
title: ICorDebugNativeFrame2::GetStackParameterSize Metodu
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
- ICorDebugNativeFrame2.GetStackParameterSize Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize
helpviewer_keywords:
- ICorDebugNativeFrame2::GetStackParameterSize method [.NET Framework debugging]
- GetStackParameterSize method [.NET Framework debugging]
ms.assetid: f6a449c8-a941-43ba-9a90-c98b29ae3c36
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fa7e67c252f2ece16c072e22d0333e085fbc4f65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframe2getstackparametersize-method"></a>ICorDebugNativeFrame2::GetStackParameterSize Metodu
İşletim sistemleri x86 yığında parametreleri toplam boyutu döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetStackParameterSize([out] ULONG32 * pSize)  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSize`  
 [out] Yığın parametreleri toplam boyutu için bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki belirli HRESULTs yanı sıra HRESULT yöntem hatası olduğunu gösteren hatalar.  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|S_OK|Yığın boyutunu başarıyla döndürüldü.|  
|S_FALSE|`GetStackParameterSize`x86 olmayan platformda çağrıldı.|  
|E_FAIL|`The size of the parameters could not be returned`.|  
|E_INVALIDARG|`pSize`Olan `null`.|  
  
## <a name="exceptions"></a>Özel Durumlar  
  
## <a name="remarks"></a>Açıklamalar  
 [Icordebugstackwalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) yöntemleri yığına parametreler için yığın işaretçisi Ayarla değil. Bunun yerine, tarafından döndürülen değer kullanabilirsiniz `GetStackParameterSize` parametrelerini ayarlamak bir yerel unwinder oluşturmak için yığın işaretçisi ayarlamak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICorDebugNativeFrame2 Arabirimi](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 [Hata Ayıklama Arabirimleri](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Hata Ayıklama](../../../../docs/framework/unmanaged-api/debugging/index.md)
