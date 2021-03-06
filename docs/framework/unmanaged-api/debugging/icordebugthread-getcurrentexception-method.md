---
title: ICorDebugThread::GetCurrentException Metodu
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
- ICorDebugThread.GetCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetCurrentException
helpviewer_keywords:
- ICorDebugThread::GetCurrentException method [.NET Framework debugging]
- GetCurrentException method [.NET Framework debugging]
ms.assetid: 331ed465-a195-4359-8584-b82c6098b29b
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c18e2dfa68d425e5ec23d4573428018bc971f8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgetcurrentexception-method"></a>ICorDebugThread::GetCurrentException Metodu
Icordebugvalue nesneye şu anda yönetilen kod tarafından oluşturulan bir özel durum temsil eden bir arabirim işaretçisi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetCurrentException (  
    [out] ICorDebugValue **ppExceptionObject  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppExceptionObject`  
 [out] Adresine bir işaretçi bir `ICorDebugValue` yönetilen kodda şu anda tarafından oluşturulan özel durumu temsil eden nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Özel durum nesnesi özel sonuna kadar durum zamandan bulunacağı `catch` bloğu. Icordebugeval yöntemler tarafından yapılır, bir işlev değerlendirmesi kurulumunu özel durum nesnesi çıkışı temizleyin ve tamamlanma geri yükleyin.  
  
 Özel durumlar iç içe geçirilemez (örneğin, bir özel filtre veya işlev değerlendirmesi durum değilse), olabilir şekilde tek bir iş parçacığı üzerinde birden fazla bekleyen özel durumu. `GetCurrentException`en son istisnası döndürür.  
  
 Özel durum nesnesi ve türü özel kullanım ömrü değişebilir. Örneğin, x türünde bir özel durum oluşturulduktan sonra ortak dil çalışma zamanı (CLR) belleğin tükenmek ve bir bellek yetersiz özel durum yükseltin.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
