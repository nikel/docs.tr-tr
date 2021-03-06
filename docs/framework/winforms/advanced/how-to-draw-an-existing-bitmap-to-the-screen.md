---
title: "Nasıl yapılır: Ekrana Mevcut bir Bit Eşlemi Çizme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b3c8aef4aee74fbcdcc80301f5d5c1020883341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a>Nasıl yapılır: Ekrana Mevcut bir Bit Eşlemi Çizme
Bu gibi durumlarda, var olan bir görüntüsünü kolayca ekranda çizebilirsiniz. Önce oluşturmak için gereken bir <xref:System.Drawing.Bitmap> bir dosya adı alan bit eşlem oluşturucu kullanılarak nesne <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>. Bu oluşturucu, BMP, GIF, JPEG, PNG ve TIFF de dahil olmak üzere birkaç farklı dosya biçimleri görüntülerle kabul eder. Oluşturduktan sonra <xref:System.Drawing.Bitmap> nesne, bu geçirmek <xref:System.Drawing.Bitmap> nesnesini <xref:System.Drawing.Graphics.DrawImage%2A> yöntemi bir <xref:System.Drawing.Graphics> nesnesi.  
  
## <a name="example"></a>Örnek  
 Bu örnekte bir <xref:System.Drawing.Bitmap> JPEG dosyadan nesne ve bit eşlem'i, sol üst köşede ile çizer (60, 10).  
  
 Aşağıda belirtilen konumda çizilmiş bit eşlem gösterilmiştir.  
  
 ![Görüntü konumu](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Önceki örnekte Windows Forms ile kullanılmak üzere tasarlanmış ve gerektirip <xref:System.Windows.Forms.PaintEventArgs> `e`, parametre olarak olduğu <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Forms’da Grafikler ve Çizim](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Görüntüler, Bit Eşlemler, Simgeler ve Meta Dosyaları ile Çalışma](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
