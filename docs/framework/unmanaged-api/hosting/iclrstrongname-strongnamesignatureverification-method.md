---
title: "ICLRStrongName::StrongNameSignatureVerification Yöntemi"
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
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1d8cb0ac6c671dae6ca5985e4082e2d3e71d89e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>ICLRStrongName::StrongNameSignatureVerification Yöntemi
Derleme bildirimi sağlanan yolunda belirtilen bayrakları göre doğrulanır bir tanımlayıcı ad imzası içerip içermediğini gösteren bir değer alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `wszFilePath`  
 [in] Taşınabilir yürütülebilir (.dll veya .exe) dosyayı doğrulamak derleme yolu.  
  
 `dwInFlags`  
 [in] Doğrulama davranışını değiştirmek için işaretler. Aşağıdaki değerleri desteklenir:  
  
-   `SN_INFLAG_FORCE_VER`(0x00000001) - kayıt defteri ayarlarını geçersiz kılmak gerekli olduğu halde doğrulama zorlar.  
  
-   `SN_INFLAG_INSTALL`(0x00000002) - Bu bildirimi doğrulanır ilk kez olduğunu belirtir.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0x00000004) - önbelleğe erişimi yalnızca yönetici ayrıcalıklarına sahip olan kullanıcılara izin verip belirtir.  
  
-   `SN_INFLAG_USER_ACCESS`(0x00000008) - derleme yalnızca geçerli kullanıcıya erişilebilir olacağını belirtir.  
  
-   `SN_INFLAG_ALL_ACCESS`(0x00000010) - önbellek garanti erişim kısıtlama sağlayacak belirtir.  
  
-   `SN_INFLAG_RUNTIME`(0x80000000) - iç hata ayıklama için ayrılmış.  
  
 `pdwOutFlags`  
 [out] Tanımlayıcı ad imzası doğrulandı olup olmadığını belirten işaretler. Aşağıdaki değeri desteklenir:  
  
-   `SN_OUTFLAG_WAS_VERIFIED`(0x00000001) - bu değeri ayarı `false` doğrulama kayıt defteri ayarları nedeniyle başarılı olduğunu belirtmek için.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `S_OK`Yöntem başarıyla tamamlandı Aksi takdirde hata belirten bir HRESULT değeri (bkz [ortak HRESULT değerleri](http://go.microsoft.com/fwlink/?LinkId=213878) bir listesi için).  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MetaHost.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [StrongNameSignatureVerificationEx Yöntemi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [ICLRStrongName Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
