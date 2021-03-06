---
title: "Sorgu ifadelerinde özel durumları işleme"
description: "Sorgu ifadelerinde özel durumları nasıl ele alınacağını."
keywords: .NET, .NET core, C#
author: BillWagner
manager: wpickett
ms.author: wiwagn
ms.date: 12/1/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.assetid: 2bf0c397-13fb-4f68-bc2b-531c6c88a167
ms.openlocfilehash: 376bd461bfeb51653471fd374a2215aa15872976
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2017
---
# <a name="handle-exceptions-in-query-expressions"></a>Sorgu ifadelerinde özel durumları işleme

Bir sorgu ifadesi bağlamında herhangi bir yöntemini çağırmak mümkündür. Ancak, veri kaynağı içeriğini değiştirme veya bir özel durum atma gibi bir yan etkisi oluşturabilirsiniz bir sorgu ifadesinde herhangi bir yöntemini çağırmadan kaçının öneririz. Bu örnek, genel özel durum işleme .NET Framework yönergeleri ihlal etmeden sorgu ifadesinde yöntemlerini çağırdığınızda özel durumlarını oluşturma önlemek gösterilmiştir. Verilen bir bağlamda neden oluşturulacaktır anladığınızda, belirli bir özel durum yakalamak için kabul edilebilir bu yönergeleri durumu. Daha fazla bilgi için bkz: [özel durumlar için en iyi uygulamaları](../../standard/exceptions/best-practices-for-exceptions.md).  
  
 Son örnek bir sorgu yürütülmesi sırasında bir özel durum gerekir, bu gibi durumlarda nasıl ele alınacağını gösterir.  
  
## <a name="example"></a>Örnek  

 Aşağıdaki örnek, özel durum kodu bir sorgu ifadesi dışında işleme taşımak gösterilmiştir. Yalnızca yöntemi değişkenlerin sorguya yerel dayanmayacak mümkün olur.  
  
 [!code-csharp[csProgGuideLINQ#10](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_1.cs)]  
  
## <a name="example"></a>Örnek 

 Bazı durumlarda, sorgu yürütme hemen durdurmak için en iyi sorgu içinde oluşturulan bir özel durum yanıta olabilir. Aşağıdaki örnek alanından bir sorgu gövdesi içinde durum özel durumları işleme gösterir. Varsayımında `SomeMethodThatMightThrow` durdurmak için sorgu yürütme gerektiren bir özel durum neden olabilir.  
  
 Unutmayın `try` blok barındırır `foreach` döngü ve sorgunun kendisini değil. Bunun nedeni, `foreach` döngü başlayacağı sorgu gerçekte yürütüldüğünde noktasıdır. Daha fazla bilgi için bkz: [LINQ sorgularına giriş](../programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 [!code-csharp[csProgGuideLINQ#12](../../../samples/snippets/csharp/concepts/linq/how-to-handle-exceptions-in-query-expressions_2.cs)]  
  

## <a name="see-also"></a>Ayrıca Bkz.  
 [LINQ Sorgu ifadeleri](index.md)
