---
title: "Nasıl yapılır: karmaşık türleri döndüren bir sorgu yürütme"
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
ms.assetid: c2209fdb-70ef-4dea-8bb8-097fe96f5563
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: cae0cc50b18641634fc8109fb29eeb30e9cf7cd8
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-execute-a-query-that-returns-complex-types"></a>Nasıl yapılır: karmaşık türleri döndüren bir sorgu yürütme
Bu konuda nasıl yürütüleceği gösterilmektedir bir [!INCLUDE[esql](../../../../../includes/esql-md.md)] bir karmaşık türde bir özellik, içeren türde nesne varlık döndüren sorgu.  
  
### <a name="to-run-the-code-in-this-example"></a>Bu örnekte kodu çalıştırmak için  
  
1.  Ekleme [AdventureWorks satış modeli](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) projenize ve kullanmak için projenizin yapılandırma [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Daha fazla bilgi için bkz: [nasıl yapılır: Varlık veri modeli Sihirbazı'nı](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Uygulamanız için kod sayfasında aşağıdakileri ekleyin `using` deyimleri (`Imports` Visual Basic'te):  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Modelinde görüntülemek üzere .edmx dosyasına çift tıklayın [modeli tarayıcı penceresini](http://msdn.microsoft.com/library/94e836e8-a5ea-47ff-aa3e-599d8a02ebfd) Entity Designer. Entity Designer yüzeyine seçin `Email` ve `Phone` özelliklerini `Contact` varlık türü, sonra sağ tıklatın ve seçin **yeni karmaşık tür yeniden düzenlemeniz**.  
  
4.  Seçili olan yeni bir karmaşık tür `Email` ve `Phone` özellikler eklenir **modeli tarayıcısı**. Karmaşık türü bir varsayılan adı verilir: türünü yeniden adlandırmak `EmailPhone` içinde **özellikleri** penceresi. Ayrıca, yeni `ComplexProperty` özellik eklenir `Contact` varlık türü. Özelliği yeniden adlandırma`EmailPhoneComplexType.`  
  
     Oluşturma ve karmaşık türler, varlık veri modeli Sihirbazı'nı kullanarak değiştirme hakkında daha fazla bilgi için bkz [nasıl yapılır: bir karmaşık tür özelliği mevcut özelliklerine yeniden düzenlemeniz](http://msdn.microsoft.com/library/5b2eb3b3-693d-42cb-b43a-405812d677eb) ve [nasıl yapılır: oluşturmak ve karmaşık türler değiştirme](http://msdn.microsoft.com/library/afb8e206-0ffe-4597-b6d4-6ab566897e1d).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek koleksiyonu döndüren bir sorgu yürütür `Contact` nesneleri ve iki özelliklerini görüntüler `Contact` nesneleri: `ContactID` ve değerlerini `EmailPhoneComplexType` karmaşık tür.  
  
 [!code-csharp[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#complextypewithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ComplexTypeWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#complextypewithentitycommand)]
