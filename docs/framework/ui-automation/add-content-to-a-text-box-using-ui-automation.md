---
title: "UI Otomasyonu Kullanarak Metin Kutusuna İçerik Ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- adding content to text boxes
- text boxes, adding content
- UI Automation, adding content to text boxes
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: "13"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 0acd6510e6349917b38e33e487123a118c2e653c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="add-content-to-a-text-box-using-ui-automation"></a><span data-ttu-id="a6a1b-102">UI Otomasyonu Kullanarak Metin Kutusuna İçerik Ekleme</span><span class="sxs-lookup"><span data-stu-id="a6a1b-102">Add Content to a Text Box Using UI Automation</span></span>
> [!NOTE]
>  <span data-ttu-id="a6a1b-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="a6a1b-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="a6a1b-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="a6a1b-105">Bu konuda nasıl kullanılacağını gösteren örnek kodu içeren [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] tek satırlı metin kutusuna metin eklemek için.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-105">This topic contains example code that demonstrates how to use [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] to insert text into a single-line text box.</span></span> <span data-ttu-id="a6a1b-106">Alternatif bir yöntem çok satırlı ve zengin metin denetimleri için sağlanan nerede [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-106">An alternate method is provided for multi-line and rich text controls where [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] is not applicable.</span></span> <span data-ttu-id="a6a1b-107">Karşılaştırma amaçları için örnek ayrıca Win32 yöntemleri aynı sonuçlara ulaşmak için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-107">For comparison purposes, the example also demonstrates how to use Win32 methods to accomplish the same results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6a1b-108">Örnek</span><span class="sxs-lookup"><span data-stu-id="a6a1b-108">Example</span></span>  
 <span data-ttu-id="a6a1b-109">Aşağıdaki örnek adımları metin denetimleri hedef uygulamada bir dizi.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-109">The following example steps through a sequence of text controls in a target application.</span></span> <span data-ttu-id="a6a1b-110">Her metin denetimini olmadığını görmek için test edilmiş bir <xref:System.Windows.Automation.ValuePattern> nesne elde edilebilir kullanarak ondan <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-110">Each text control is tested to see if a <xref:System.Windows.Automation.ValuePattern> object can be obtained from it using the <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> method.</span></span> <span data-ttu-id="a6a1b-111">Metin denetimini destekliyorsa <xref:System.Windows.Automation.ValuePattern>, <xref:System.Windows.Automation.ValuePattern.SetValue%2A> yöntemi metin denetimi kullanıcı tarafından tanımlanan bir dize eklemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-111">If the text control does support <xref:System.Windows.Automation.ValuePattern>, the <xref:System.Windows.Automation.ValuePattern.SetValue%2A> method is used to insert a user-defined string into the text control.</span></span> <span data-ttu-id="a6a1b-112">Aksi takdirde, <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> yöntemi kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-112">Otherwise, the <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> method is used.</span></span>  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## <a name="see-also"></a><span data-ttu-id="a6a1b-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a6a1b-113">See Also</span></span>  
 [<span data-ttu-id="a6a1b-114">TextPattern Ekle metin örneği</span><span class="sxs-lookup"><span data-stu-id="a6a1b-114">TextPattern Insert Text Sample</span></span>](http://msdn.microsoft.com/en-us/67353f93-7ee2-42f2-ab76-5c078cf6ca16)