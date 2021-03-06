---
title: "Özel veri hizmeti sağlayıcıları (WCF Veri Hizmetleri)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7db780b97c1a7eadffbfa71f60be4afe590ccb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a>Özel veri hizmeti sağlayıcıları (WCF Veri Hizmetleri)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]geç bağlama veri türlerine bağlı bir veri modeli tanımlamanıza olanak sağlayan bir dizi sağlayıcıları içerir.  
  
|Sağlayıcı|Açıklama|  
|--------------|-----------------|  
|Meta veri sağlayıcısı|Bu, çalışma zamanında bir özel veri modelini uygulayarak tanımlamanıza olanak sağlayan çekirdek özel veri hizmeti sağlayıcısıdır <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> arabirimi.|  
|Sorgu sağlayıcısı|Bu sağlayıcı kullanılarak tanımlanmış bir özel veri modeli sorguları yürütmek sağlar <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> arabirimi. Sorgu sağlayıcısı uygulayarak oluşturulup <xref:System.Data.Services.Providers.IDataServiceQueryProvider> arabirimi.|  
|Sağlayıcı güncelleştirme|Bu sağlayıcı bir özel veri hizmeti sağlayıcısında gösterilen türleri güncelleştirmeler yapmak için ve eşzamanlılık yönetmenize olanak sağlar. Bir güncelleştirme sağlayıcı uygulama tarafından oluşturulan <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> arabirimi|  
|Disk belleği sağlayıcısı|Bu sağlayıcı özel veri hizmeti sağlayıcısı ile sunucu tabanlı sayfalama desteğini etkinleştirmek için kullanılır. Özel veri hizmeti için bir disk belleği sağlayıcı uygulama tarafından oluşturulan <xref:System.Data.Services.Providers.IDataServicePagingProvider> arabirimi.|  
|Akış sağlayıcısı|Bu sağlayıcı ikili büyük nesne veri türlerini akışı olarak kullanıma sunmak etkinleştirir. Bir akış sağlayıcı uygulama tarafından oluşturulan <xref:System.Data.Services.Providers.IDataServiceStreamProvider> arabirimi. Akış sağlayıcısı, Entity Framework ve yansıma veri kaynak sağlayıcıları ile de kullanılabilir. Daha fazla bilgi için bkz: [Akış sağlayıcısı](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).|  
  
 Daha fazla bilgi için bkz: [özel veri hizmeti sağlayıcıları](http://go.microsoft.com/fwlink/?LinkID=186850) ve [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] sağlayıcı araç setindeki [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri Hizmetleri Sağlayıcıları](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Entity Framework Sağlayıcısı](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [Yansıma Sağlayıcısı](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
