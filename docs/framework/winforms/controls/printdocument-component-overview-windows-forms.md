---
title: "PrintDocument Bileşenine Genel Bakış (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a>PrintDocument Bileşenine Genel Bakış (Windows Forms)
Windows Forms [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) bileşen ne yazdırma açıklayın özellikleri ve Windows tabanlı uygulamalar içinde belge yazdırma olanağı ayarlamak için kullanılır. İle birlikte kullanılabilir [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) belge yazdırma tüm yönlerini denetiminde olmasını bileşeni.  
  
## <a name="working-with-the-printdocument-component"></a>PrintDocument bileşeni ile çalışma  
 İki içeren ana senaryo <xref:System.Drawing.Printing.PrintDocument> bileşen şunlardır:  
  
-   Bir tek tek metin dosyası yazdırma gibi basit yazdırma işlerini. Böyle bir durumda, eklediğiniz <xref:System.Drawing.Printing.PrintDocument> bir Windows formu bileşene sonra bir dosyada yazdırır programlama mantığı eklemek <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay işleyicisi. Programlama mantığı ile culminate <xref:System.Drawing.Printing.PrintDocument.Print%2A> belgeyi yazdırmayı yöntemi. Bu yöntem gönderir bir <xref:System.Drawing.Graphics> içinde yer alan nesne <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> özelliği <xref:System.Drawing.Printing.PrintPageEventArgs> yazıcıya sınıfı. Bir metin belgesini kullanarak yazdırma gösteren bir örnek <xref:System.Drawing.Printing.PrintDocument> bileşeni Bkz [nasıl yapılır: Windows Forms'ta çok sayfalı metin dosyası yazdırma](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Daha karmaşık yazdırma işlerini yazdırma mantığı yazdığınız yeniden istediğiniz bir durum gibi. Böyle bir durumda yeni bir bileşenden türetin <xref:System.Drawing.Printing.PrintDocument> bileşeni ve geçersiz kılma (bkz [geçersiz kılmaları](~/docs/visual-basic/language-reference/modifiers/overrides.md) Visual Basic veya [geçersiz kılma](~/docs/csharp/language-reference/keywords/override.md) için C#) <xref:System.Drawing.Printing.PrintDocument.PrintPage> olay.  
  
 Bir form için eklendiğinde <xref:System.Drawing.Printing.PrintDocument> Tepsisi Windows Forms Tasarımcısı'nın altındaki Bileşen görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Windows Forms Yazdırma Desteği](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [PrintDocument Bileşeni](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
