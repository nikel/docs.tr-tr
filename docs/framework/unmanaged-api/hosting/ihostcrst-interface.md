---
title: IHostCrst Arabirimi
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
- IHostCrst
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst
helpviewer_keywords:
- IHostCrst interface [.NET Framework hosting]
ms.assetid: ac298ebd-0815-47e4-a823-30b31baab903
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3a9ed2b390ad741d90f9179ef5101d328d3b639d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ihostcrst-interface"></a>IHostCrst Arabirimi
İş parçacığı oluşturma için önemli bir bölümü ana bilgisayarın gösterimi olarak görev yapar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Enter Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-enter-method.md)|Kritik bölüm girer.|  
|[Leave Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-leave-method.md)|Kritik bölüm bırakır.|  
|[SetSpinCount Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-setspincount-method.md)|Kritik Bölümü için dönüş sayısını ayarlar.|  
|[TryEnter Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-tryenter-method.md)|Kritik bölüm ve raporları başarı veya başarısızlık hemen girmek çalışır.|  
  
## <a name="remarks"></a>Açıklamalar  
 `IHostCrst`Ortak dil çalışma zamanı (CLR) önemli bir bölümü doğrudan ana bilgisayarın gösterimi ile iletişim kurmak için Win32 işlevleri gibi kullanmak yerine sağlar `EnterCriticalSection` veya `LeaveCriticalSection`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICLRSyncManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [IHostSyncManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
