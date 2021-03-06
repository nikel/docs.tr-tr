---
title: "Nasıl yapılır: varlık ilişkileri (WCF Veri Hizmetleri) tanımlayın"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a584e78c15d900bad8bdd3a85abe5e090ed47de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-entity-relationships-wcf-data-services"></a>Nasıl yapılır: varlık ilişkileri (WCF Veri Hizmetleri) tanımlayın
Yeni bir varlıkta eklediğinizde [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], yeni varlık ve ilgili varlıklar arasındaki ilişkileri otomatik olarak tanımlanmamış. Oluşturma ve varlık örnekleri arasındaki ilişkileri değiştirmek ve veri hizmeti bu değişiklikleri yansıtmak için istemci kitaplığı sahiptir. Daha fazla bilgi için bkz: [veri hizmeti güncelleştirme](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Bu konudaki örnek Northwind örnek veri hizmeti ve otomatik olarak oluşturulur istemci veri hizmeti sınıflarını kullanır. Bu hizmet ve istemci veri sınıfları tamamladığınızda oluşturduğunuz [WCF Veri Hizmetleri quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek yeni bir nesne örneği oluşturur ve ardından çağırır <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A> yöntemi <xref:System.Data.Services.Client.DataServiceContext> ilgili sipariş bağlantısını birlikte bağlamda öğesi oluşturmak için. Bir HTTP POST iletisi verileri gönderilir ne zaman hizmet <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> yöntemi çağrılır.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl kullanılacağını gösterir <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A> ekleme yöntemi bir `Order_Details` ilgili nesnesine `Orders` nesne belirli bir başvuru `Products` nesnesi. <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> Ve <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> yöntemleri, ilişkileri tanımlayın. Bu örnekte, gezinti özellikleri `Order_Details` nesne aynı zamanda açıkça ayarlayın.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorder)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF Veri Hizmetleri İstemci Kitaplığı](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Nasıl yapılır: Varlık Ekleme, Değiştirme ve Silme](../../../../docs/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services.md)
