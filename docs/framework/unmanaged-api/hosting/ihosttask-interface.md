---
title: IHostTask Arabirimi
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
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bbffe2a171c112d4e9650b2c1b2a9ce1f010f382
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttask-interface"></a>IHostTask Arabirimi
Ortak dil çalışma zamanı (CLR) görevleri yönetmek için konak ile iletişim kurmasına izin yöntemleri sağlar.  
  
## <a name="methods"></a>Yöntemler  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Alert Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Ana bilgisayar tarafından geçerli temsil görev Uyandırma isteklerini `IHostTask` görevi durduruldu şekilde örneği.|  
|[GetPriority Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Geçerli tarafından temsil edilen görev iş parçacığı öncelik düzeyini alır `IHostTask` örneği.|  
|[Join Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Geçerli tarafından temsil edilen görev kadar arama görev engeller `IHostTask` örneği tamamlandıktan, belirtilen zaman aralığı sona erdiğinde, veya [Ihosttask::alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) olarak adlandırılır.|  
|[SetCLRTask Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|İlişkilendiren bir [Iclrtask arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) geçerli örnekle `IHostTask` örneği.|  
|[SetPriority Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Düzey istekler ana iş parçacığı önceliği ayarlamak için geçerli tarafından temsil edilen görev `IHostTask` örneği.|  
|[Start Yöntemi](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Taşıma geçerli tarafından temsil edilen görevi konak istekleri `IHostTask` askıya alınma durumundaysa bir örnekten, kod yürütülebilir canlı bir duruma.|  
  
## <a name="remarks"></a>Açıklamalar  
 CLR tarafından tanımlanan yöntemlerini çağıran `IHostTask` iş parçacığı önceliği bir görevi başlatmak için level vb. ayarlayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** MSCorEE.h  
  
 **Kitaplığı:** bir kaynak olarak MSCorEE.dll dahil  
  
 **.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ICLRTask Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTaskManager Arabirimi](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Barındırma Arabirimleri](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
