---
title: "Nasıl yapılır: ifade ağaçlarını (Visual Basic) yürütme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 45a13f13659472b7620b6df070815ace1d6fb0de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-execute-expression-trees-visual-basic"></a>Nasıl yapılır: ifade ağaçlarını (Visual Basic) yürütme
Bu konuda bir ifade ağacına yürütme gösterilmiştir. Bir ifade ağacına yürütülürken bir değer döndürebilir ya da yalnızca bir yöntemi çağırma gibi bir eylem gerçekleştirebilir.  
  
 Lambda ifadeleri temsil eden ifade ağaçları çalıştırılabilir. Lambda ifadeleri temsil ifade ağaçları türündedir <xref:System.Linq.Expressions.LambdaExpression> veya <xref:System.Linq.Expressions.Expression%601>. Bu ifade ağaçlarını yürütme çağrısı <xref:System.Linq.Expressions.LambdaExpression.Compile%2A> yürütülebilir bir temsilci oluşturma ve temsilci çağırma yöntemi.  
  
> [!NOTE]
>  Temsilci türü bilinmiyor, diğer bir deyişle, lambda ifadesi türü ise <xref:System.Linq.Expressions.LambdaExpression> ve <xref:System.Linq.Expressions.Expression%601>, çağırmalısınız <xref:System.Delegate.DynamicInvoke%2A> doğrudan çağırma yerine temsilci yöntemi.  
  
 Bir ifade ağacına bir lambda ifadesi göstermiyor, özgün ifade ağacına çağırarak kendi gövdesi olarak sahip yeni bir lambda ifadesi oluşturabilirsiniz <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> yöntemi. Ardından, bu bölümde daha önce açıklandığı gibi lambda ifadesi yürütebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir lambda ifadesi oluşturma ve yürütme güç sayıya oluşturma işlemi temsil eden bir ifade ağacına yürütmek gösterilmiştir. Yükseltilmiş numarasını gücünü temsil eder, sonuç görüntülenir.  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
  
-   Zaten başvurulmayan varsa System.Core.dll proje başvurusu ekleyin.  
  
-   System.Linq.Expressions ad alanı içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade ağaçları (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)  
 [Nasıl yapılır: ifade ağaçlarını (Visual Basic) değiştirme](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
