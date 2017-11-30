---
title: "Windows Forms Denetimlerinde Kenar Boşluğu Bırakma ve Doldurma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Padding property [Windows Forms]
- layout [Windows Forms], margins and padding
- Windows Forms, layout
- Margin property [Windows Forms]
ms.assetid: 3781b5a1-3085-4072-bed0-44670c23ffdc
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 22d8a73963a8f9f1e3d8b80b6c16f189e0221c55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="margin-and-padding-in-windows-forms-controls"></a><span data-ttu-id="9aa90-102">Windows Forms Denetimlerinde Kenar Boşluğu Bırakma ve Doldurma</span><span class="sxs-lookup"><span data-stu-id="9aa90-102">Margin and Padding in Windows Forms Controls</span></span>
<span data-ttu-id="9aa90-103">Formunuza denetimler tam yerleşimi, pek çok uygulama yüksek önceliktir.</span><span class="sxs-lookup"><span data-stu-id="9aa90-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="9aa90-104"><xref:System.Windows.Forms?displayProperty=nameWithType> Ad alanı, bunu başarmak için birçok yerleşim özellikleri verir.</span><span class="sxs-lookup"><span data-stu-id="9aa90-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout features to accomplish this.</span></span> <span data-ttu-id="9aa90-105">En önemli ikisidir <xref:System.Windows.Forms.Control.Margin%2A> ve <xref:System.Windows.Forms.Control.Padding%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="9aa90-105">Two of the most important are the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties.</span></span>  
  
 <span data-ttu-id="9aa90-106"><xref:System.Windows.Forms.Control.Margin%2A> Özelliği tutar diğer denetimin Kenarlıklar belirtilen uzaklıkta denetimleri denetimi boşluk tanımlar.</span><span class="sxs-lookup"><span data-stu-id="9aa90-106">The <xref:System.Windows.Forms.Control.Margin%2A> property defines the space around the control that keeps other controls a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="9aa90-107"><xref:System.Windows.Forms.Control.Padding%2A> Özelliği denetimin içeriğini tutan bir denetim iç kısmında yer tanımlar (örneğin, değeri kendi <xref:System.Windows.Forms.Control.Text%2A> özelliği) denetimin Kenarlıklar belirtilen uzaklıkta.</span><span class="sxs-lookup"><span data-stu-id="9aa90-107">The <xref:System.Windows.Forms.Control.Padding%2A> property defines the space in the interior of a control that keeps the control's content (for example, the value of its <xref:System.Windows.Forms.Control.Text%2A> property) a specified distance from the control's borders.</span></span>  
  
 <span data-ttu-id="9aa90-108">Aşağıdaki çizimde gösterildiği <xref:System.Windows.Forms.Control.Padding%2A> ve <xref:System.Windows.Forms.Control.Margin%2A> denetim özellikleri.</span><span class="sxs-lookup"><span data-stu-id="9aa90-108">The following illustration shows the <xref:System.Windows.Forms.Control.Padding%2A> and <xref:System.Windows.Forms.Control.Margin%2A> properties on a control.</span></span>  
  
 <span data-ttu-id="9aa90-109">![Doldurma ve kenar boşlukları Windows Forms denetimleri](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span><span class="sxs-lookup"><span data-stu-id="9aa90-109">![Padding And Margin for Windows Forms Controls](../../../../docs/framework/winforms/controls/media/vs-winformpadmargin.gif "VS_WinFormPadMargin")</span></span>  
  
 <span data-ttu-id="9aa90-110">Bu özellik Visual Studio tasarım-zamanı desteği yoktur.</span><span class="sxs-lookup"><span data-stu-id="9aa90-110">There is design-time support for this feature in Visual Studio.</span></span>  <span data-ttu-id="9aa90-111">Ayrıca bkz. [izlenecek yol: yerleştirmede çıkışı Windows Forms denetimleri doldurma, kenar boşlukları ve AutoSize özelliği ile](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="9aa90-111">Also see [Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property](http://msdn.microsoft.com/library/3z3f9e8b\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa90-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9aa90-112">See Also</span></span>  
 <xref:System.Windows.Forms.Control.AutoSize%2A>  
 <xref:System.Windows.Forms.Control.Margin%2A>  
 <xref:System.Windows.Forms.Control.Padding%2A>  
 <xref:System.Windows.Forms.Control.LayoutEngine%2A>  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>