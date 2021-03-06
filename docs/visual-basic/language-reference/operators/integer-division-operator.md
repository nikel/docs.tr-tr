---
title: "\\ İşleci (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38718b109b4b3865238267039908ea1d51d06229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>\ İşleci (Visual Basic)
İki sayıyı böler ve tamsayı sonuç döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Bölümler  
 `expression1`  
 Gerekli. Herhangi bir sayısal ifade.  
  
 `expression2`  
 Gerekli. Herhangi bir sayısal ifade.  
  
## <a name="supported-types"></a>Desteklenen türler  
 İmzasız ve kayan nokta türleri dahil olmak üzere tüm sayısal türler ve `Decimal`.  
  
## <a name="result"></a>Sonuç  
 Tamsayı bölümü, sonucudur `expression1` bölü `expression2`, tüm kalan kısmını atar ve yalnızca tamsayı bölümü korur. Bu olarak bilinir *kesme*.  
  
 Sonuç veri türü sayısal bir tür veri türleri için uygun değil `expression1` ve `expression2`. "Tamsayı aritmetiğini" tablolarda bkz [işleci sonuçlarını veri türleri](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 [/ İşleci (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) kesirli kısmı kalanı korur tam sayının döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bölme gerçekleştirmeden önce Visual Basic herhangi bir kayan nokta sayısal ifade dönüştürmeye çalışır `Long`. Varsa `Option Strict` olan `On`, bir derleyici hatası oluşur. Varsa `Option Strict` olan `Off`, bir <xref:System.OverflowException> değer aralığının dışında olması durumunda mümkündür [uzun veri türünü](../../../visual-basic/language-reference/data-types/long-data-type.md). Dönüştürme `Long` de tabi olduğu *banker yuvarlaması*. Daha fazla bilgi için bkz: "Kesirli bölümleri" [tür dönüştürme işlevleri](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Varsa `expression1` veya `expression2` değerlendiren [hiçbir şey](../../../visual-basic/language-reference/nothing.md), sıfır olarak kabul edilir.  
  
## <a name="attempted-division-by-zero"></a>Denenen sıfıra  
 Varsa `expression2` sıfır olarak değerlendirilir `\` işleci oluşturur bir <xref:System.DivideByZeroException> özel durum. Bu işlenen tüm sayısal veri türleri için geçerlidir.  
  
> [!NOTE]
>  `\` İşleci olabilir *aşırı*, işleneni, sınıf veya yapı türüne sahip olduğunda bir sınıf veya yapı davranışını tanımlayabilirsiniz, anlamına gelir. Bu tür bir sınıf veya yapı üzerinde kodunuzu bu işleç kullanıyorsa, yeniden tanımlanan davranışını anladığınızdan emin olun. Daha fazla bilgi için bkz: [işleç yordamları](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanır `\` tamsayı bölme gerçekleştirmek için işleci. Sonucun tamsayı bölümü iki işlenen, atılan geri kalanı ile temsil eden bir tamsayıdır.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 Önceki örnekte ifadelerde değerler 2, 3, 33 ve -22, sırasıyla döndürür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\\= İşleci](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [/ İşleci (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [Option Strict deyimi](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Aritmetik işleçler](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Visual Basic'de İşleç önceliği](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [İşlevselliğe göre listelenmiş işleçler](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Visual Basic'de aritmetik işleçler](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
