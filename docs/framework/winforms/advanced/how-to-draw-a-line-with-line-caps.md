---
title: "Nasıl yapılır: Çizgi Uçlarıyla Çizgi Çizme"
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
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1e2d5a5aba4a7634e0ea8480aa9744a5a7b9721d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-draw-a-line-with-line-caps"></a><span data-ttu-id="e1f5b-102">Nasıl yapılır: Çizgi Uçlarıyla Çizgi Çizme</span><span class="sxs-lookup"><span data-stu-id="e1f5b-102">How to: Draw a Line with Line Caps</span></span>
<span data-ttu-id="e1f5b-103">Başlangıç ya da bir satırın sonuna satır caps adlı birkaç şekiller birinde çizebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-103">You can draw the start or end of a line in one of several shapes called line caps.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e1f5b-104">gidiş, kare, Karo ve Ok ucunu gibi birkaç satır caps destekler.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-104"> supports several line caps, such as round, square, diamond, and arrowhead.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1f5b-105">Örnek</span><span class="sxs-lookup"><span data-stu-id="e1f5b-105">Example</span></span>  
 <span data-ttu-id="e1f5b-106">Satır caps başlangıç satırı (Başlangıç cap), (son cap) satırın sonuna veya kesik çizgi (tire cap) tireler belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-106">You can specify line caps for the start of a line (start cap), the end of a line (end cap), or the dashes of a dashed line (dash cap).</span></span>  
  
 <span data-ttu-id="e1f5b-107">Aşağıdaki örnekte bir ok ucunu bir uçta ve diğer uçtaki yuvarlak bir uç satırıyla çizilmiştir.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-107">The following example draws a line with an arrowhead at one end and a round cap at the other end.</span></span> <span data-ttu-id="e1f5b-108">Sonuçta elde edilen satır çizimde gösterilmektedir:</span><span class="sxs-lookup"><span data-stu-id="e1f5b-108">The illustration shows the resulting line:</span></span>  
  
 <span data-ttu-id="e1f5b-109">![Kalemler](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span><span class="sxs-lookup"><span data-stu-id="e1f5b-109">![Pens](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")</span></span>  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e1f5b-110">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="e1f5b-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="e1f5b-111">Bir Windows formu oluşturma ve form ele <xref:System.Windows.Forms.Control.Paint> olay.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-111">Create a Windows Form and handle the form's <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="e1f5b-112">Örnek kod içine yapıştırma <xref:System.Windows.Forms.Control.Paint> geçirme olay işleyicisi `e` olarak <xref:System.Windows.Forms.PaintEventArgs>.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-112">Paste the example code into the <xref:System.Windows.Forms.Control.Paint> event handler passing `e` as <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f5b-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e1f5b-113">See Also</span></span>  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [<span data-ttu-id="e1f5b-114">Grafikler ve Windows Forms'ta çizme</span><span class="sxs-lookup"><span data-stu-id="e1f5b-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="e1f5b-115">Çizgiler ve şekiller çizmek için kalem kullanma</span><span class="sxs-lookup"><span data-stu-id="e1f5b-115">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)