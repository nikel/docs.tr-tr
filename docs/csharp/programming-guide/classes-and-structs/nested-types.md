---
title: "İç içe Geçmiş Türler (C# Programlama Kılavuzu)"
ms.date: 07/10/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ab13c68b638062ab89c90dbfc51b51b8d72d3bde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="nested-types-c-programming-guide"></a>İç içe Geçmiş Türler (C# Programlama Kılavuzu)
İçinde tanımlanan bir türü bir [sınıfı](../../../csharp/language-reference/keywords/class.md) veya [yapısı](../../../csharp/language-reference/keywords/struct.md) iç içe geçmiş tür adı verilir. Örneğin:  
  
[!code-csharp[csProgGuideObjects#68](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_1.cs)]  
  
Dış türü bir sınıf veya yapı olup olmadığına bakılmaksızın, iç içe geçmiş türler için varsayılan değer [özel](../../../csharp/language-reference/keywords/private.md); yalnızca içeren kendi türünden erişilebilir. Önceki örnekte, `Nested` sınıfı için dış türleri erişilemiyor. 

Ayrıca belirtebilirsiniz bir [erişim değiştiricisi](../../language-reference/keywords/access-modifiers.md) iç içe geçmiş tür erişilebilirliğini şu şekilde tanımlamak için:

- İç içe geçmiş tür bir **sınıfı** olabilir [ortak](../../../csharp/language-reference/keywords/public.md), [korumalı](../../../csharp/language-reference/keywords/protected.md), [iç](../../../csharp/language-reference/keywords/internal.md), [iç korumalı](../../../csharp/language-reference/keywords/protected-internal.md), [özel](../../../csharp/language-reference/keywords/private.md) veya [korumalı özel](../../../csharp/language-reference/keywords/private-protected.md). 

   Ancak, tanımlama bir `protected`, `protected internal` veya `private protected` sınıf içinde iç içe geçmiş bir [sınıf korumalı](../../language-reference/keywords/sealed.md) derleyici uyarısı oluşturur [CS0628](../../misc/cs0628.md), "yeni korumalı üye korumalı sınıfta bildirildi."
  
- İç içe geçmiş tür bir **yapısı** olabilir [ortak](../../../csharp/language-reference/keywords/public.md), [iç](../../../csharp/language-reference/keywords/internal.md), veya [özel](../../../csharp/language-reference/keywords/private.md).
  
Aşağıdaki örnek yapar `Nested` sınıfı ortak:
  
[!code-csharp[csProgGuideObjects#69](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_2.cs)]  
  
 İç içe ya da iç, türü içeren veya dış, türü erişebilir. Kapsayan tür erişmek için bağımsız değişken olarak iç içe geçmiş tür oluşturucuya geçirin. Örneğin:  
  
 [!code-csharp[csProgGuideObjects#70](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_3.cs)]  
  
 İç içe geçmiş tür içeren türünü erişilebilir üyelerin tümünü erişebilir. Devralınan tüm korumalı üyeleri de dahil olmak üzere içeren türün özel ve korumalı üyeleri erişebilir.  
  
 Sınıfın tam adını önceki bildiriminde `Nested` olan `Container.Nested`. Bu, aşağıdaki gibi iç içe geçmiş sınıf yeni bir örneğini oluşturmak için kullanılan addır:  
  
 [!code-csharp[csProgGuideObjects#71](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/nested-types_4.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [Sınıflar ve yapılar](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Erişim değiştiricileri](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [Oluşturucular](../../../csharp/programming-guide/classes-and-structs/constructors.md)
