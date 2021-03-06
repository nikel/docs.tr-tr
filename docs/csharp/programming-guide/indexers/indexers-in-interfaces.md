---
title: Arabirimlerdeki Dizin Oluşturucular (C# Programlama Kılavuzu)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- indexers [C#], in interfaces
- accessors [C#], indexers
ms.assetid: e16b54bd-4a83-4f52-bd75-65819fca79e8
caps.latest.revision: 18
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 478920b5c1dea489db48caa48c045c4bd3da66ec
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="indexers-in-interfaces-c-programming-guide"></a>Arabirimlerdeki Dizin Oluşturucular (C# Programlama Kılavuzu)
Dizin oluşturucular bildirilebilir bir [arabirimi](../../../csharp/language-reference/keywords/interface.md). Arabirim Dizinleyicileri erişimciler erişimci farklı [sınıfı](../../../csharp/language-reference/keywords/class.md) dizin oluşturucular aşağıdaki yollarla:  
  
-   Arabirim erişimciler değiştiricileri kullanmayın.  
  
-   Arabirim erişimci gövde yok.  
  
 Bu nedenle, dizin oluşturucu okuma-yazma, salt okunur veya sadece yazılabilir olduğunu belirtmek için erişimci amacı budur.  
  
 Arabirim dizin oluşturucu erişimci örneği verilmiştir:  
  
 [!code-csharp[csProgGuideIndexers#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_1.cs)]  
  
 Bir dizin oluşturucu imza aynı arabirimde bildirilen tüm diğer dizin oluşturucular imzalarını farklı olmalıdır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, arabirim Dizinleyicileri uygulamak gösterilmiştir.  
  
 [!code-csharp[csProgGuideIndexers#4](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/indexers-in-interfaces_2.cs)]  
  
 Önceki örnekte, arabirim üyesini tam adını kullanarak açık arabirim üye uygulaması kullanabilirsiniz. Örneğin:  
  
```  
public string ISomeInterface.this[int index]   
{   
}   
```  
  
 Ancak, tam adı, yalnızca sınıf aynı dizin oluşturucu imzaya sahip birden fazla arabirimi uygularken Karışıklığı önlemek için gereklidir. Örneğin, bir `Employee` sınıfı iki arabirim uygulama `ICitizen` ve `IEmployee`, ve her iki arabirimde aynı dizin oluşturucu imza açık arabirim üye uygulaması gereklidir. Diğer bir deyişle, aşağıdaki dizin oluşturucu bildirimi:  
  
```  
public string IEmployee.this[int index]   
{   
}   
```  
  
 üzerine dizinleyici uygulayan `IEmployee` arabirimi, aşağıdaki bildirimi sırasında:  
  
```  
public string ICitizen.this[int index]
{   
}   
```  
  
 üzerine dizinleyici uygulayan `ICitizen` arabirimi.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
 [Dizin Oluşturucular](../../../csharp/programming-guide/indexers/index.md)  
 [Özellikler](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [Arabirimler](../../../csharp/programming-guide/interfaces/index.md)
