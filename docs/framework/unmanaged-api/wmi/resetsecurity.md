---
title: "ResetSecurity işlevi (yönetilmeyen API Başvurusu)"
description: "ResetSecurity işlevi, geçerli iş parçacığına kimliğe bürünme simgesi atar."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bacee65633d25e705d978d3902a6804516a88bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="resetsecurity-function"></a>ResetSecurity işlevi
Sağlanan kimliğe bürünme belirteci geçerli iş parçacığına atar.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a>Parametreler

`token`  
[in] Geçerli iş parçacığı ile ilişkilendirmek için kimliğe bürünme belirteci. Değerini olabilir `null`. 

## <a name="return-value"></a>Dönüş değeri

İşlev başarılı olursa, dönüş değeri olan `S_OK` (0).

İşlev başarısız olursa, dönüş değeri sıfır olmayan bir hata kodudur. Genişletilmiş hata bilgilerini için arama [Geterrorınfo](geterrorinfo.md) işlevi.
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** WMINet_Utils.idl  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Ayrıca bkz.  
[WMI ve performans sayaçları (yönetilmeyen API Başvurusu)](index.md)
