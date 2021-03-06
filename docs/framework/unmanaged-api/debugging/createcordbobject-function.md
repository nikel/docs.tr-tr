---
title: "CreateCordbObject İşlevi"
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
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7007e541e9999e0cb14a83845eb28d71336b3ff6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="createcordbobject-function"></a>CreateCordbObject İşlevi
Hata ayıklayıcı arabirimi oluşturur ([Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)) uzak bir işlem üzerinde yönetilen hata ayıklama oturumu oluşturmak için işlevsellik sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,   
       [out] IUnknown**  ppCordb  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `iDebuggerVersion`  
 [in] Hedef işlemin hata ayıklayıcı sürümü. Bu parametre, uzaktan hata ayıklama için CorDebugVersion_2_0 olması gerekir.  
  
 `ppCordb`  
 [out] İşaretçi için cast bir nesne için bir işaretçi bir [Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) arabirim ve döndürülür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK  
 İşlem CLRs sayısında başarıyla belirlendi ve karşılık gelen tanıtıcısı ve yol dizileri düzgün doldurulmuş.  
  
 E_INVALIDARG  
 `ppCordb`null, veya `iDebuggerVersion` CorDebugVersion_2_0 değil.  
  
 E_OUTOFMEMORY  
 İçin yeterli bellek ayrılamıyor.`ppCordb`  
  
 E_FAIL (veya diğer E_ dönüş kodları)  
 Diğer hataları.  
  
## <a name="remarks"></a>Açıklamalar  
 [Icordebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) döndürülür arabirimi `ppCordb` tüm hata ayıklama Hizmetleri tarafından yönetilen en üst düzey hata ayıklama arabirimidir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Kitaplığı:** mscordbi_macx86.dll  
  
 **.NET framework sürümleri:** 3.5 SP1
