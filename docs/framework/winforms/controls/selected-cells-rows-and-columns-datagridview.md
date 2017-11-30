---
title: "Nasıl yapılır: Windows Forms DataGridView Denetiminde Seçili Hücre, Satır ve Sütunları Alma"
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
- selection [Windows Forms], DataGridView control [Windows Forms]
- DataGridView control [Windows Forms], getting selection
- getting selection [Windows Forms], DataGridView control [Windows Forms]
ms.assetid: d93c4b5b-498e-49bc-982a-2229d61778e4
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: aada475af0ccac03dfa6ef9248b0fb07fd86b3ce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-selected-cells-rows-and-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="cfab4-102">Nasıl yapılır: Windows Forms DataGridView Denetiminde Seçili Hücre, Satır ve Sütunları Alma</span><span class="sxs-lookup"><span data-stu-id="cfab4-102">How to: Get the Selected Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="cfab4-103">Seçili hücre, satır veya sütunlarından alabileceğiniz bir <xref:System.Windows.Forms.DataGridView> ilgili özelliklerini kullanarak denetim: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, ve <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span><span class="sxs-lookup"><span data-stu-id="cfab4-103">You can get the selected cells, rows, or columns from a <xref:System.Windows.Forms.DataGridView> control by using the corresponding properties: <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>, and <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>.</span></span> <span data-ttu-id="cfab4-104">Aşağıdaki yordamlarda, seçili hücreleri almak ve satır ve sütun dizinlerini görüntülemek bir <xref:System.Windows.Forms.MessageBox>.</span><span class="sxs-lookup"><span data-stu-id="cfab4-104">In the following procedures, you will get the selected cells and display their row and column indexes in a <xref:System.Windows.Forms.MessageBox>.</span></span>  
  
### <a name="to-get-the-selected-cells-in-a-datagridview-control"></a><span data-ttu-id="cfab4-105">DataGridView denetiminde seçili hücre almak için</span><span class="sxs-lookup"><span data-stu-id="cfab4-105">To get the selected cells in a DataGridView control</span></span>  
  
-   <span data-ttu-id="cfab4-106">Kullanım <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="cfab4-106">Use the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> property.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cfab4-107">Kullanım <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> hücreleri çok sayıda gösteren önlemek için yöntem.</span><span class="sxs-lookup"><span data-stu-id="cfab4-107">Use the <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> method to avoid showing a potentially large number of cells.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#10)]  
  
### <a name="to-get-the-selected-rows-in-a-datagridview-control"></a><span data-ttu-id="cfab4-108">DataGridView denetiminde seçili satırları almak için</span><span class="sxs-lookup"><span data-stu-id="cfab4-108">To get the selected rows in a DataGridView control</span></span>  
  
-   <span data-ttu-id="cfab4-109">Kullanım <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="cfab4-109">Use the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> property.</span></span> <span data-ttu-id="cfab4-110">Satırları seçmek kullanıcıların sağlamak için ayarlamalısınız <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> özelliğine <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> veya <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="cfab4-110">To enable users to select rows, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#20)]  
  
### <a name="to-get-the-selected-columns-in-a-datagridview-control"></a><span data-ttu-id="cfab4-111">DataGridView denetiminde Seçili sütunları almak için</span><span class="sxs-lookup"><span data-stu-id="cfab4-111">To get the selected columns in a DataGridView control</span></span>  
  
-   <span data-ttu-id="cfab4-112">Kullanım <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="cfab4-112">Use the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> property.</span></span> <span data-ttu-id="cfab4-113">Sütunları seçmek kullanıcıların sağlamak için ayarlamalısınız <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> özelliğine <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> veya <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span><span class="sxs-lookup"><span data-stu-id="cfab4-113">To enable users to select columns, you must set the <xref:System.Windows.Forms.DataGridView.SelectionMode%2A> property to <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect> or <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/CS/DataGridViewSelectedCollections.cs#30)]
     [!code-vb[System.Windows.Forms.DataGridViewSelectedCollections#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSelectedCollections/VB/DataGridViewSelectedCollections.vb#30)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cfab4-114">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="cfab4-114">Compiling the Code</span></span>  
 <span data-ttu-id="cfab4-115">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="cfab4-115">This example requires:</span></span>  
  
-   <span data-ttu-id="cfab4-116"><xref:System.Windows.Forms.Button>adlı denetimleri `selectedCellsButton`, `selectedRowsButton`, ve `selectedColumnsButton`, her biri için işleyiciler <xref:System.Windows.Forms.Control.Click> ekli olay.</span><span class="sxs-lookup"><span data-stu-id="cfab4-116"><xref:System.Windows.Forms.Button> controls named `selectedCellsButton`, `selectedRowsButton`, and `selectedColumnsButton`, each with handlers for the <xref:System.Windows.Forms.Control.Click> event attached.</span></span>  
  
-   <span data-ttu-id="cfab4-117">A <xref:System.Windows.Forms.DataGridView> adlı Denetim `dataGridView1`.</span><span class="sxs-lookup"><span data-stu-id="cfab4-117">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="cfab4-118">Başvurular <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, ve <xref:System.Text?displayProperty=nameWithType> derlemeler.</span><span class="sxs-lookup"><span data-stu-id="cfab4-118">References to the <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType>, and <xref:System.Text?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cfab4-119">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="cfab4-119">Robust Programming</span></span>  
 <span data-ttu-id="cfab4-120">Bu konuda açıklanan koleksiyonları, çok sayıda hücre, satır veya sütun seçili olduğunda verimli bir şekilde gerçekleştirmeyin.</span><span class="sxs-lookup"><span data-stu-id="cfab4-120">The collections described in this topic do not perform efficiently when large numbers of cells, rows, or columns are selected.</span></span> <span data-ttu-id="cfab4-121">Bu koleksiyonları büyük miktarlarda veri kullanma hakkında daha fazla bilgi için bkz: [Windows Forms DataGridView denetimini ölçeklendirme için en iyi yöntemler](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="cfab4-121">For more information about using these collections with large amounts of data, see [Best Practices for Scaling the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfab4-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="cfab4-122">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.SelectionMode%2A>  
 <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedRows%2A>  
 <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A>  
 [<span data-ttu-id="cfab4-123">Seçim ve Pano kullanımı Windows Forms DataGridView denetimi ile</span><span class="sxs-lookup"><span data-stu-id="cfab4-123">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)