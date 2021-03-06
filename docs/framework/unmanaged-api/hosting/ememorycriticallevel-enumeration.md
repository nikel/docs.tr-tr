---
title: "EMemoryCriticalLevel Numaralandırması"
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
- EMemoryCriticalLevel
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryCriticalLevel
helpviewer_keywords:
- EMemoryCriticalLevel enumeration [.NET Framework hosting]
ms.assetid: 2ca8a7a2-7b54-4ba3-8e73-277c7df485f3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fb279402b2b677546f775b9a8badfbe2095fe4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ememorycriticallevel-enumeration"></a>EMemoryCriticalLevel Numaralandırması
Bir hata etkisi belirli bellek ayırma istendi ancak memnun olamaz belirten değerleri içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
typedef enum {  
    eTaskCritical      = 0,  
    eAppDomainCritical = 1,  
    eProcessCritical   = 2  
} EMemoryCriticalLevel;  
```  
  
## <a name="members"></a>Üyeler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|`eAppDomainCritical`|Ayırma ayırma istedi etki alanında yönetilen kod yürütmek için önemli olduğunu gösterir. Bellek ayrılamıyor, CLR etki alanı hala kullanılabilir garanti edemez. Konak ayırma karşılanamayan olduğunda gerçekleştirilecek eylemi karar verir. İptal etmek için CLR söyleyebilirsiniz `AppDomain` otomatik olarak veya üzerinde yöntemler çağrılarak çalıştırmaya devam etmesine izin [Iclrpolicymanager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).|  
|`eProcessCritical`|Ayırma işleminde yönetilen kod yürütülmesi için önemli olduğunu gösterir. Bu değer, başlatma sırasında ve sonlandırıcılar çalıştırılırken kullanılır. Bellek ayrılamıyor, CLR işleminde çalışamaz. Ayırma başarısız olursa, CLR etkili bir şekilde devre dışı bırakılır. CLR tüm sonraki çağrılar ile HOST_E_CLRNOTAVAILABLE başarısız.|  
|`eTaskCritical`|Ayırma ayırma istedi görevi çalıştırmak için önemli olduğunu gösterir. Bellek ayrılamıyor, CLR görev yürütülen garanti edemez. CLR hatası durumunda başlatır bir <xref:System.Threading.ThreadAbortException> fiziksel işlemi sistem iş parçacığı üzerinde.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tanımlanan bellek ayırma yöntemlerini [Ihostmemorymanager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md) ve [Ihostmalloc](../../../../docs/framework/unmanaged-api/hosting/ihostmalloc-interface.md) arabirimler bu türde bir parametre yararlanabilir. Bir hata önem derecesi bağlı olarak, bir konak ayırma isteği hemen başarısız mı, yoksa, karşılanabilir kadar beklemeniz karar verebilirsiniz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** MSCorEE.dll  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICLRMemoryNotificationCallback Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)  
 [Barındırma Sabit Listeleri](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
