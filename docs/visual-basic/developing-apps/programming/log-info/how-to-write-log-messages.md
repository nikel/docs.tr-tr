---
title: "Nasıl Yapılır: Günlük İletileri Yazma (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ae4d875fd4f95ca51fff565551009e780b17d07a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-log-messages-visual-basic"></a>Nasıl Yapılır: Günlük İletileri Yazma (Visual Basic)
Kullanabileceğiniz `My.Application.Log` ve `My.Log` uygulamanız ile ilgili bilgileri günlüğe kaydetmek için nesneleri. Bu örnek nasıl kullanılacağını gösterir `My.Application.Log.WriteEntry` izleme bilgileri günlüğe kaydetmek için yöntem.  
  
 Özel durum bilgilerini günlüğe kaydetme için kullanmak `My.Application.Log.WriteException` yöntemi; bkz: [nasıl yapılır: günlük özel durumları](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).  
  
## <a name="example"></a>Örnek  
 Bu örnekte `My.Application.Log.WriteEntry` izleme bilgilerini yazmak için yöntem.  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 Kullanıcı parolaları gibi hassas bilgileri günlüğe yaz veri içermediğinden emin olun. Daha fazla bilgi için bkz: [uygulama günlükleriyle çalışma](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [Uygulama günlükleriyle çalışma](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [Nasıl yapılır: günlük özel durumları](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [İzlenecek yol: My.Application.log günlüğünün bilgileri nereye yazdığını belirleme](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [İzlenecek yol: My.Application.Log günlüğünün bilgileri yazdığı değiştirme](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [İzlenecek yol: My.Application.Log çıktısını filtreleme](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
