---
title: "GDI+'daki Çokgenler"
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
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26068ab72473a541b1f16aeb2a1f0d43ec7a7313
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="polygons-in-gdi"></a>GDI+'daki Çokgenler
Çokgen üç veya daha fazla düz kenarlar ile kapalı bir Şekil ' dir. Örneğin, bir üçgen üç kenarı sahip bir çokgenin, bir Çokgen dört kenara dikdörtgen şeklinde ve beş kenara sahip bir çokgenin bir pentagon olduğu. Aşağıda birkaç çokgenler gösterilmektedir.  
  
 ![Çokgenler](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Çokgen çizme  
 Çokgen çizmek için size gereken bir <xref:System.Drawing.Graphics> nesne, bir <xref:System.Drawing.Pen> nesne ve bir dizi <xref:System.Drawing.Point> (veya <xref:System.Drawing.PointF>) nesneleri. <xref:System.Drawing.Graphics> Nesnesi sağlar <xref:System.Drawing.Graphics.DrawPolygon%2A> yöntemi. <xref:System.Drawing.Pen> Nesne depolar genişlik ve Çokgen ve dizi oluşturmak için kullanılan çizginin rengini gibi öznitelikleri <xref:System.Drawing.Point> nesnelerini depolayan noktaları düz çizgilerle bağlanması gerekir. <xref:System.Drawing.Pen> Nesne ve bir dizi <xref:System.Drawing.Point> nesneleri bağımsız değişken olarak geçirilen <xref:System.Drawing.Graphics.DrawPolygon%2A> yöntemi. Aşağıdaki örnekte, üç taraflı çokgen çizer. Yalnızca üç noktaları olduğuna dikkat edin `myPointArray`: (0, 0), (50, 30) ve (30, 60). <xref:System.Drawing.Graphics.DrawPolygon%2A> Yöntemi otomatik olarak bir satırından çizerek Çokgen kapatır (30, 60) başlangıç noktası (0, 0) dön.  
  
 [!code-csharp[LinesCurvesAndShapes#111](../../../../samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 Aşağıdaki çizimde Çokgen gösterir.  
  
 ![Çokgen](../../../../docs/framework/winforms/advanced/media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Drawing.Graphics?displayProperty=nameWithType>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 [Çizgiler, Eğriler ve Şekiller](../../../../docs/framework/winforms/advanced/lines-curves-and-shapes.md)  
 [Nasıl yapılır: Kalem Oluşturma](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)
