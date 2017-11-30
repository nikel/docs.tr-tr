---
title: "Nasıl yapılır: Akış İçeriği Öğelerini Satır İçlerinin Özelliği ile Düzenleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 77b6d75b48fd137092600a7e2316cbcf7099de76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a><span data-ttu-id="e2aa7-102">Nasıl yapılır: Akış İçeriği Öğelerini Satır İçlerinin Özelliği ile Düzenleme</span><span class="sxs-lookup"><span data-stu-id="e2aa7-102">How to: Manipulate Flow Content Elements through the Inlines Property</span></span>
<span data-ttu-id="e2aa7-103">Bu örnekler satır içi akış içeriği öğeleri üzerinde gerçekleştirilen daha yaygın işlemlerin bazılarını gösterir (ve bu öğelerin kapsayıcıları gibi <xref:System.Windows.Controls.TextBlock>) aracılığıyla **Inlines** özelliği.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-103">These examples demonstrate some of the more common operations that can be performed on inline flow content elements (and containers of such elements, such as <xref:System.Windows.Controls.TextBlock>) through the **Inlines** property.</span></span> <span data-ttu-id="e2aa7-104">Bu özellik eklemek ve öğeleri kaldırmak için kullanılan <xref:System.Windows.Documents.InlineCollection>.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-104">This property is used to add and remove items from <xref:System.Windows.Documents.InlineCollection>.</span></span> <span data-ttu-id="e2aa7-105">Akış içerik öğeleri bu özellik bir **Inlines** özellik içerir:</span><span class="sxs-lookup"><span data-stu-id="e2aa7-105">Flow content elements that feature an **Inlines** property include:</span></span>  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 <span data-ttu-id="e2aa7-106">Kullanmak için bu örnekler durum <xref:System.Windows.Documents.Span> akış halinde content öğesi, ancak bu teknikler tüm öğeleri veya ana bilgisayar denetimleri için geçerli bir <xref:System.Windows.Documents.InlineCollection> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-106">These examples happen to use <xref:System.Windows.Documents.Span> as the flow content element, but these techniques are applicable to all elements or controls that host an <xref:System.Windows.Documents.InlineCollection> collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2aa7-107">Örnek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-107">Example</span></span>  
 <span data-ttu-id="e2aa7-108">Aşağıdaki örnek yeni bir oluşturur <xref:System.Windows.Documents.Span> nesne ve kullandığı **Ekle** içerik alt öğeleri olarak çalışan iki metin eklemek için yöntemini <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-108">The following example creates a new <xref:System.Windows.Documents.Span> object, and then uses the **Add** method to add two text runs as content children of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a><span data-ttu-id="e2aa7-109">Örnek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-109">Example</span></span>  
 <span data-ttu-id="e2aa7-110">Aşağıdaki örnek yeni bir oluşturur <xref:System.Windows.Documents.Run> öğesi ve başında ekler <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-110">The following example creates a new <xref:System.Windows.Documents.Run> element and inserts it at the beginning of the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a><span data-ttu-id="e2aa7-111">Örnek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-111">Example</span></span>  
 <span data-ttu-id="e2aa7-112">Aşağıdaki örnek en üst düzey sayısını alır <xref:System.Windows.Documents.Inline> içindeki öğe <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-112">The following example gets the number of top-level <xref:System.Windows.Documents.Inline> elements contained in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a><span data-ttu-id="e2aa7-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-113">Example</span></span>  
 <span data-ttu-id="e2aa7-114">Aşağıdaki örnek, son siler <xref:System.Windows.Documents.Inline> öğesinde <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-114">The following example deletes the last <xref:System.Windows.Documents.Inline> element in the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a><span data-ttu-id="e2aa7-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-115">Example</span></span>  
 <span data-ttu-id="e2aa7-116">Aşağıdaki örnekte tüm içeriği siler (<xref:System.Windows.Documents.Inline> öğeleri) gelen <xref:System.Windows.Documents.Span>.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-116">The following example clears all of the contents (<xref:System.Windows.Documents.Inline> elements) from the <xref:System.Windows.Documents.Span>.</span></span>  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a><span data-ttu-id="e2aa7-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e2aa7-117">See Also</span></span>  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [<span data-ttu-id="e2aa7-118">Akış belgesi genel bakış</span><span class="sxs-lookup"><span data-stu-id="e2aa7-118">Flow Document Overview</span></span>](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [<span data-ttu-id="e2aa7-119">Blokların özelliği aracılığıyla FlowDocument işlemek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-119">Manipulate a FlowDocument through the Blocks Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [<span data-ttu-id="e2aa7-120">Bir tablonun sütunlar sütunlar özelliği aracılığıyla yönetmek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-120">Manipulate a Table's Columns through the Columns Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [<span data-ttu-id="e2aa7-121">Tablonun satır grupları RowGroups özelliği aracılığıyla denetlemek</span><span class="sxs-lookup"><span data-stu-id="e2aa7-121">Manipulate a Table's Row Groups through the RowGroups Property</span></span>](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)