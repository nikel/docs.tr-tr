---
title: "Özyinelemeli Yordamlar (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], that call themselves
- procedures [Visual Basic], recursive
- procedures [Visual Basic], calling
- recursive procedures
- functions [Visual Basic], calling recursively
- recursion
ms.assetid: ba1d3962-b4c3-48d3-875e-96fdb4198327
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 444eeaf043cf3710c5154fd7e8577590e3ce7d1e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="recursive-procedures-visual-basic"></a>Özyinelemeli Yordamlar (Visual Basic)
A *özyinelemeli* yordam kendisini çağıran bir kullanılır. Genel olarak, bu yazmak için en etkili şekilde değil [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] kodu.  
  
 Aşağıdaki yordamda özyineleme faktöriyelini özgün bağımsız değişkeninin değerini hesaplamak için kullanılır.  
  
 [!code-vb[VbVbcnProcedures#51](./codesnippet/VisualBasic/recursive-procedures_1.vb)]  
  
## <a name="considerations-with-recursive-procedures"></a>Özyinelemeli yordamlar ile ilgili önemli noktalar  
 **Koşullar sınırlama**. Özyineleme sonlandırabilir en az bir koşul için test etmek için bir özyinelemeli yordamı tasarlamanız gerekir ve bu tür bir koşul özyinelemeli çağrılara makul bir dizi içinde nerede sağlanırsa durum işlemesi gerekir. Başarısız karşılanabilir en az bir koşul olmadan yordamınız sonsuz bir döngüde yürütmenin yüksek riskli çalışır.  
  
 **Bellek kullanımı**. Uygulamanızı yerel değişkenler için alan sınırlı miktarda sahiptir. Kendisini bir yordam çağrıları her zaman bu alanı daha fazla yerel değişkenlerini ek kopyalarını kullanır. Bu işlem belirsiz bir süre devam ederse, sonunda neden olan bir <xref:System.StackOverflowException> hata.  
  
 **Verimlilik**. Özyineleme için bir döngü neredeyse her zaman değiştirebilirsiniz. Döngü ek depolama alanı başlatma ve dönüş değerleri argümanları başlatır, yükü yok. Performansınızı özyinelemeli çağrılara daha iyi olabilir.  
  
 **Karşılıklı özyineleme**. İki yordam birbirine çağırırsanız çok düşük performans ya da sonsuz bir döngüde bile, görebilirsiniz. Bu tür bir tasarım tek özyinelemeli yordamla aynı sorunları gösterir, ancak algılamak ve hata ayıklama için daha zor olabilir.  
  
 **Parantezler ile çağırma**. Zaman bir `Function` yordam çağrıları kendisini yinelemeli olarak, hiçbir bağımsız değişken listesi olsa bile parantez yordamı adıyla izlemeniz gerekir. Aksi takdirde, işlev adı geçen işlevi dönüş değerini temsil eden olarak.  
  
 **Sınama**. Bir özyinelemeli yordamı yazarsanız, çok dikkatli bazı sınırlama koşul her zaman karşıladığından emin olmak için test. Ayrıca, çok fazla özyinelemeli çağrılara olması nedeniyle bellek yetersiz çalıştıramazsınız de emin olmalısınız.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.StackOverflowException>  
 [Yordamları](./index.md)  
 [Alt yordamlar](./sub-procedures.md)  
 [İşlev yordamları](./function-procedures.md)  
 [Özellik yordamları](./property-procedures.md)  
 [İşleç yordamları](./operator-procedures.md)  
 [Parametreler ve bağımsız değişkenler](./procedure-parameters-and-arguments.md)  
 [Yordam aşırı yüklemesi](./procedure-overloading.md)  
 [Sorun giderme yordamları](./troubleshooting-procedures.md)  
 [Döngü yapıları](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [Özel durum sorunlarını giderme: System.StackOverflowException](http://msdn.microsoft.com/library/51b71217-c507-4f5b-bc35-0236180d7968)
