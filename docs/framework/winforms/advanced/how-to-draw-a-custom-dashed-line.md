---
title: "Nasıl yapılır: Özel Kesikli Çizgi Çizme"
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
- lines [Windows Forms], custom
- lines [Windows Forms], drawing
- lines [Windows Forms], dashed
ms.assetid: cd0ed96a-cce4-47b9-b58a-3bae2e3d1bee
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 770ce290b21f7d0094a487c30079063b79a7c08d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-custom-dashed-line"></a>Nasıl yapılır: Özel Kesikli Çizgi Çizme
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]listelenen birkaç çizgi stili sağlar <xref:System.Drawing.Drawing2D.DashStyle> numaralandırması. Bu standart çizgi stillerini gereksinimlerinize göre değil, özel tire deseni oluşturabilirsiniz.  
  
## <a name="example"></a>Örnek  
 Özel kesikli çizgi çizmek için bir dizi çizgi ve boşluk uzunlukları koy ve dizi değeri olarak atamak <xref:System.Drawing.Pen.DashPattern%2A> özelliği bir <xref:System.Drawing.Pen> nesnesi. Aşağıdaki örnek dizisine göre özel kesikli çizgi çizer `{5, 2, 15, 4}`. Dizideki öğeler 5 kalem genişliği tarafından Çarp olursa, `{25, 10, 75, 20}`. 25 ve 75 arasındaki uzunluğu görüntülenen tireler alternatif ve uzunluğu 10 ile 20 arasında boşluk alternatif.  
  
 Aşağıdaki çizimde, sonuçta elde edilen kesikli çizgi gösterir. Böylece satırın en son 25 birimden daha kısa olacak şekilde son tire sahip unutmayın (405, 5).  
  
 ![Kalemler](../../../../docs/framework/winforms/advanced/media/pens6.gif "pens6")  
  
 [!code-csharp[System.Drawing.UsingAPen#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.UsingAPen#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
 Bir Windows formu oluşturma ve form ele <xref:System.Windows.Forms.Control.Paint> olay. Önceki kod içine yapıştırma <xref:System.Windows.Forms.Control.Paint> olay işleyicisi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çizgiler ve Şekiller Çizmek için Kalem Kullanma](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
