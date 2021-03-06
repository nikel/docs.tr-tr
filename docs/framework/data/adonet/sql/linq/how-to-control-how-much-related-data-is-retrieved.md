---
title: "Nasıl yapılır: ilgili ne kadar veri alındığını denetleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3beb6f6b019535e273df7103e2e22f1be669797a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a>Nasıl yapılır: ilgili ne kadar veri alındığını denetleme
Kullanım <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> yöntemi ana hedefiniz ilgili hangi verileri belirtmek için aynı anda alınan. Örneğin, müşterilerin siparişler hakkında bilgi gerekir biliyorsanız, kullanabileceğiniz <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> sipariş bilgileri, müşteri bilgileri aynı zamanda alınır emin olmak için. Bu yaklaşımın iki bilgi için veritabanı içinde yalnızca bir seyahat sonuçlanır.  
  
> [!NOTE]
>  Müşteriler hedeflediğinizde siparişleri alma gibi bir büyük projeksiyon olarak çapraz ürün alarak sorgunuzu ana hedefe ilgili verileri alabilir. Ancak bu yaklaşım genellikle dezavantajları vardır. Örneğin, yalnızca tahminleri ve değil, değiştirilebilir ve tarafından kalıcı varlıkları sonucu olan [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Ve çok fazla ihtiyacınız olmayan veri alma.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte, tüm `Orders` tüm `Customers` kimin Londra'da buluna alınır sorgunun yürütüldüğü zaman. Sonuç olarak, art arda gelen erişimi `Orders` özelliği bir `Customer` nesne yeni bir veritabanı sorgusu tetiklemez.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veritabanını Sorgulama](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
