---
title: "IMetaDataImport2::EnumMethodSpecs Yöntemi"
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
- IMetaDataImport2.EnumMethodSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumMethodSpecs
helpviewer_keywords:
- IMetaDataImport2::EnumMethodSpecs method [.NET Framework metadata]
- EnumMethodSpecs method [.NET Framework metadata]
ms.assetid: b3fc1e6c-bcb6-4915-baf8-7dc0a31b8724
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6e134d19eb6699f39e6d538f93f989b87ed8f37d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimport2enummethodspecs-method"></a>IMetaDataImport2::EnumMethodSpecs Yöntemi
Bir numaralandırıcı MethodSpec belirteçleri belirtilen MethodDef veya MemberRef ilişkili bir dizi belirteci alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT EnumMethodSpecs (  
    [in, out] HCORENUM      *phEnum,   
    [in]      mdToken       tk,  
    [out]     mdMethodSpec  rMethodSpecs[],  
    [in]      ULONG         cMax,  
    [out]     ULONG         *pcMethodSpecs  
);   
```  
  
#### <a name="parameters"></a>Parametreler  
 `phEnum`  
 [içinde out] Numaralandırıcı için bir işaretçi `rMethodSpecs`.  
  
 `tk`  
 [in] Numaralandırılacak olan MethodSpec belirteçler olan yöntemi temsil eden MemberRef veya MethodDef belirteci. Varsa değerini `tk` 0 (sıfır), kapsamdaki tüm MethodSpec belirteçleri numaralandırılır.  
  
 `rMethodSpecs`  
 [out] Numaralandırılacak MethodSpec belirteçleri dizisi.  
  
 `cMax`  
 [in] İstenen sayısı yerleştirmek için belirteçleri `rMethodSpecs`.  
  
 `pcMethodSpecs`  
 [out] Sıraya alınan belirteçleri döndürülen sayısıdır `rMethodSpecs`.  
  
## <a name="return-value"></a>Dönüş Değeri  
  
|HRESULT|Açıklama|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSpecs`başarıyla döndürüldü.|  
|`S_FALSE`|`phEnum`hiç üye öğe yok. Bu durumda, `pcMethodSpecs` 0 (sıfır) olarak ayarlayın.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** Cor.h  
  
 **Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IMetaDataImport2 Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport Arabirimi](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
