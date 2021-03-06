---
title: Dil ile tümleşik sorgu (LINQ)
description: C# dil ile tümleşik sorgu (LINQ) sunar
keywords: .NET, .NET core, LINQ, C#
author: BillWagner
ms.author: wiwagn
ms.date: 11/30/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 007cc736-f5cf-4919-b99b-0c00ab2814ce
ms.openlocfilehash: c4c26e2b7b0693ec940958a9b7d2d306001090e7
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="language-integrated-query-linq"></a>Dil ile tümleşik sorgu (LINQ)

Dil ile tümleşik sorgu (LINQ) C# dili doğrudan sorgu özellikleri tümleştirme temel teknoloji adıdır. Geleneksel olarak, veri sorguları zaman veya IntelliSense desteği tür adresindeki denetlemesi olmadan basit dizeler derleme olarak ifade edilir. Ayrıca, her veri kaynağı türü için farklı sorgu dili öğrenmeniz gerekir: SQL veritabanları, XML belgeleri, çeşitli Web Hizmetleri ve benzeri. LINQ ile bir sorgu sınıfları, yöntemleri, olayları gibi bir birinci sınıf dil yapısı ' dir.

Sorguları Yazar bir geliştirici için en görünür "dil ile tümleşik" LINQ sorgu ifadesi bir parçasıdır. Sorgu ifadeleri bir tanımlayıcı yazılır *sorgu sözdizimi*. Sorgu sözdizimi kullanılarak filtreleme, sıralama ve kod en az veri kaynaklarında gruplandırma işlemleri gerçekleştirebilir. Aynı temel sorgu ifade desenleri sorgu ve veri SQL veritabanları, ADO .NET veri kümeleri, .NET koleksiyonları, XML belgelerini ve akışlar dönüştürmek için kullanın.

Aşağıdaki örnekte, tam bir sorgu işlemi gösterilmektedir. Veri kaynağı oluşturma, sorgu ifadesi tanımlama ve sorgu yürütme işlemi tamamlamak içeren bir `foreach` deyimi.

[!code-csharp[csProgGuideLINQ#11](../../../samples/snippets/csharp/concepts/linq/index_1.cs)]

## <a name="query-expression-overview"></a>Sorgu ifadesi genel bakış

-   Sorgu ifadeleri, sorgu ve tüm LINQ etkin veri kaynağı dönüştürmek için kullanılabilir. Örneğin, tek bir sorgu, bir SQL veritabanından veri almak ve bir XML akışı çıktı olarak üretir.  
  
-   Sorgu ifadeleri tanıdık birçok C# dil yapıları kullandığından ana kolaydır.  
  
-   Çoğu durumda derleyici Infer çünkü türü açıkça sağlamanız gerekmez ancak bir sorgu ifadesinde değişkenleri tüm kesinlikle, yazılmalıdır. Daha fazla bilgi için bkz: [tür ilişkileri LINQ Sorgu işlemleri](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
-   Sorgu değişkeni yineleme kadar bir sorgu yürütülmedi Örneğin, bir `foreach` deyimi. Daha fazla bilgi için bkz: [LINQ sorgularına giriş](../programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
-   Derleme zamanında sorgu ifadeleri standart sorgu işleci yöntem çağrılarını İleri C# belirtiminde ayarlamak kurallarına göre dönüştürülür. Sorgu sözdizimi kullanılarak ifade herhangi bir sorgu yöntem sözdizimi kullanılarak da belirtilebilir. Bununla birlikte, çoğu durumda, daha okunabilir ve kısa sorgu sözdizimi. Daha fazla bilgi için bkz: [C# dil belirtimi](../language-reference/language-specification/index.md) ve [standart sorgu işleçlerine genel bakış](../programming-guide/concepts/linq/standard-query-operators-overview.md).  
  
-   LINQ sorguları yazma, bir kural olarak, mümkün olduğunda sorgu sözdizimi ve yöntem sözdizimi gerektiğinde kullanmanızı öneririz. Yoksa Hayır anlamsal veya performans iki farklı form arasında fark. Sorgu ifadeleri olan genellikle daha yöntemi sözdiziminde yazılan eşdeğer ifadeleri daha okunabilir.  
  
-   Bazı sorgu işlemleri gibi <xref:System.Linq.Enumerable.Count%2A> veya <xref:System.Linq.Enumerable.Max%2A>, hiçbir eşdeğer sorgu ifadesi yan tümcesi varsa ve bu nedenle bir yöntem çağrısı ifade edilmesi gerekir. Çeşitli şekillerde sorgu sözdizimi ile yöntem sözdizimi birleştirilebilir. Daha fazla bilgi için bkz: [sorgu sözdizimi ve yöntem sözdizimi LINQ](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
-   Sorgu ifadeleri ifade ağaçları veya sorgu uygulandığı türüne bağlı olarak temsilciler derlenebilir. <xref:System.Collections.Generic.IEnumerable%601>sorguları temsilcileri derlenir. <xref:System.Linq.IQueryable>ve <xref:System.Linq.IQueryable%601> sorgular için ifade ağaçları derlenir. Daha fazla bilgi için bkz: [ifade ağaçları](../expression-trees.md).  

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla ayrıntı LINQ hakkında bilgi edinmek için bazı temel kavramları hakkında bilgi sahibi olma olarak Başlat [sorgu ifadesi Temelleri](query-expression-basics.md), ve hangi, ilgi LINQ teknolojisi belgelerine bakın:   
-   XML belgeleri: [LINQ-XML](../programming-guide/concepts/linq/linq-to-xml.md)  
  
-   ADO.NET Entity Framework: [LINQ to entities](../../framework/data/adonet/ef/language-reference/linq-to-entities.md)  
  
-   .NET koleksiyonları, dosyaları, dizeleri vb.: [nesnelere LINQ](../programming-guide/concepts/linq/linq-to-objects.md)

Bir daha derin LINQ genel olarak anlaşılması için bkz: [C# üzerinde LINQ](linq-in-csharp.md).

C# üzerinde LINQ ile çalışmaya başlamak için öğretici bkz [LINQ ile çalışma](../tutorials/working-with-linq.md).


