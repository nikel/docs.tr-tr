---
title: ICorDebugNativeFrame::GetLocalRegisterMemoryValue Metodu
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
- ICorDebugNativeFrame.GetLocalRegisterMemoryValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue
helpviewer_keywords:
- ICorDebugNativeFrame::GetLocalRegisterMemoryValue method [.NET Framework debugging]
- GetLocalRegisterMemoryValue method [.NET Framework debugging]
ms.assetid: d350f69d-9aff-4f5a-8301-daea22dee2da
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 47520e6ab4c8c3bba7383ddd08b7ff23be9dddc3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugnativeframegetlocalregistermemoryvalue-method"></a>ICorDebugNativeFrame::GetLocalRegisterMemoryValue Metodu
Bir bağımsız değişken veya biri Düşük word ve yüksek word bellek konumunda depolanan ve kayıt, sırasıyla, bu yerel çerçevesi için belirlenen yerel değişken değerini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT GetLocalRegisterMemoryValue (  
    [in] CorDebugRegister   highWordReg,  
    [in] CORDB_ADDRESS      lowWordAddress,  
    [in] ULONG              cbSigBlob,  
    [in] PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `highWordReg`  
 [in] Değerin yüksek sözcüğünü içeren kayıt belirtir "CorDebugRegister" numaralandırma değeri.  
  
 `lowWordAddress`  
 [in] A `CORDB_ADDRESS` değerinin düşük sözcüğünü içeren bellek konumunu belirten değer.  
  
 `cbSigBlob`  
 [in] Tarafından başvurulan ikili meta verileri imza boyutu belirten bir tamsayı `pvSigBlob` parametresi.  
  
 `pvSigBlob`  
 [in] A `PCCOR_SIGNATURE` değerinin türü ikili meta verileri imza gösteren değer.  
  
 `ppValue`  
 [out] Belirtilen kayıt ve bellek konumda depolanır alınan değeri temsil eden bir "ICorDebugValue" nesnesi adresini gösteren bir işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** CorDebug.idl, CorDebug.h  
  
 **Kitaplığı:** CorGuids.lib  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
