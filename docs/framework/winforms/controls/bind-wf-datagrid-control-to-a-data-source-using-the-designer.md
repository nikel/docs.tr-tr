---
title: "Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGrid Denetimini Veri Kaynağına Bağlama"
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
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 378f1d80392ae7b2058d5c3b2d987e4810cbd07b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="14f43-102">Nasıl yapılır: Tasarımcı Kullanarak Windows Formları DataGrid Denetimini Veri Kaynağına Bağlama</span><span class="sxs-lookup"><span data-stu-id="14f43-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="14f43-103"><xref:System.Windows.Forms.DataGridView> Denetimi değiştirir ve işlevlerini ekler <xref:System.Windows.Forms.DataGrid> kontrol; ancak, <xref:System.Windows.Forms.DataGrid> denetim tutulur geriye dönük uyumluluk ve gelecekte kullanım için seçerseniz.</span><span class="sxs-lookup"><span data-stu-id="14f43-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="14f43-104">Daha fazla bilgi için bkz: [farklar arasında Windows Forms DataGridView ve DataGrid denetimleri](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="14f43-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="14f43-105">Windows Forms <xref:System.Windows.Forms.DataGrid> denetimi veri kaynağı bilgilerini görüntülemek için özel olarak tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="14f43-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="14f43-106">Ayarlayarak tasarım zamanında denetimi bağlamak <xref:System.Windows.Forms.DataGrid.DataSource%2A> ve <xref:System.Windows.Forms.DataGrid.DataMember%2A> özelliklerini veya çağırarak çalışma zamanında <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="14f43-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="14f43-107">Çeşitli veri kaynakları verileri görüntüleyebilse de, en tipik veri kümeleri ve veri görünümleri kaynaklardır.</span><span class="sxs-lookup"><span data-stu-id="14f43-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="14f43-108">Tasarım zamanında veri kaynağının kullanılabilir olup olmadığını — Örneğin, form örneği bir veri kümesi veya bir veri görünümü içeriyorsa — kılavuz tasarım zamanında veri kaynağına bağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14f43-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="14f43-109">Sonra veri kılavuzunda nasıl görüneceğini önizlemesini görebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14f43-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="14f43-110">Kılavuz ayrıca programlı ve çalışma zamanında bağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="14f43-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="14f43-111">Çalışma zamanında alma bilgilere dayalı bir veri kaynağı istediğinizde kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="14f43-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="14f43-112">Örneğin, uygulamayı görüntülemek için bir tablo adını belirtin kullanıcı sağlayabilir.</span><span class="sxs-lookup"><span data-stu-id="14f43-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="14f43-113">Ayrıca, burada veri kaynağı tasarım zamanında yok durumlarda gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="14f43-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="14f43-114">Diziler, koleksiyonlar, yazılmayan veri kümeleri ve veri okuyucuları gibi veri kaynakları içerir.</span><span class="sxs-lookup"><span data-stu-id="14f43-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="14f43-115">Aşağıdaki yordam gerektiren bir **Windows uygulaması** içeren bir form ile proje bir <xref:System.Windows.Forms.DataGrid> denetim.</span><span class="sxs-lookup"><span data-stu-id="14f43-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="14f43-116">Böyle bir proje ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir Windows uygulaması projesi oluşturduğunuzda](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) ve [nasıl yapılır: Windows Forms denetimlerine ekleme](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="14f43-116">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="14f43-117">İçinde [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> denetim içinde değil **araç** varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="14f43-117">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="14f43-118">Bu ekleme hakkında daha fazla bilgi için bkz: [nasıl yapılır: araç kutusu öğeleri Ekle](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span><span class="sxs-lookup"><span data-stu-id="14f43-118">For information about adding it, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="14f43-119">Ayrıca, [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], kullanabileceğiniz **veri kaynakları** tasarım zamanı veri bağlama için penceresi.</span><span class="sxs-lookup"><span data-stu-id="14f43-119">Additionally in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="14f43-120">Daha fazla bilgi için bkz: [Visual Studio'da verilere denetimler bağlama](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="14f43-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="14f43-121">Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir.</span><span class="sxs-lookup"><span data-stu-id="14f43-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="14f43-122">Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü.</span><span class="sxs-lookup"><span data-stu-id="14f43-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="14f43-123">Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="14f43-123">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="14f43-124">Veri DataGrid denetimini Tasarımcısı'nda tek bir tabloya bağlamak için</span><span class="sxs-lookup"><span data-stu-id="14f43-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="14f43-125">Denetimin ayarlamak <xref:System.Windows.Forms.DataGrid.DataSource%2A> özelliği bağlamak istediğiniz veri öğeleri içeren nesne.</span><span class="sxs-lookup"><span data-stu-id="14f43-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="14f43-126">Veri kaynağı bir veri kümesi ise <xref:System.Windows.Forms.DataGrid.DataMember%2A> özelliğini bağlamak için tablonun adı.</span><span class="sxs-lookup"><span data-stu-id="14f43-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="14f43-127">Veri kaynağı bir veri kümesi ya da bir veri kümesi tabloya dayalı bir veri görünümü ise, veri kümesini doldurmak üzere formuna kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="14f43-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="14f43-128">Kullandığınız tam kod burada veri kümesi alma bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="14f43-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="14f43-129">Veri kümesi bir veritabanından doğrudan doldurulmuş, genellikle çağırmanız `Fill` adlı bir veri kümesi doldurur aşağıdaki kod örneğinde olduğu gibi bir veri bağdaştırıcısı yöntemi `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="14f43-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="14f43-130">(İsteğe bağlı) Sütun stilleri ve uygun tablo stilleri kılavuzuna ekleyin.</span><span class="sxs-lookup"><span data-stu-id="14f43-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="14f43-131">Hiçbir tablo stilleri varsa Tablo görürsünüz, ancak en az biçimlendirme ile tüm sütunları görünür.</span><span class="sxs-lookup"><span data-stu-id="14f43-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="14f43-132">Veri DataGrid denetimini veri kümesi Tasarımcısı'nda birden fazla tabloya bağlamak için</span><span class="sxs-lookup"><span data-stu-id="14f43-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="14f43-133">Denetimin ayarlamak <xref:System.Windows.Forms.DataGrid.DataSource%2A> özelliği bağlamak istediğiniz veri öğeleri içeren nesne.</span><span class="sxs-lookup"><span data-stu-id="14f43-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="14f43-134">Veri kümesi, ilişkili tabloları içeriyorsa (diğer bir deyişle, bir ilişki nesnesi içeriyorsa) ayarlayın <xref:System.Windows.Forms.DataGrid.DataMember%2A> üst tablo adı özelliği.</span><span class="sxs-lookup"><span data-stu-id="14f43-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="14f43-135">Veri kümesini doldurmak için kod yazma.</span><span class="sxs-lookup"><span data-stu-id="14f43-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f43-136">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="14f43-136">See Also</span></span>  
 [<span data-ttu-id="14f43-137">DataGrid denetimine genel bakış</span><span class="sxs-lookup"><span data-stu-id="14f43-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="14f43-138">Nasıl yapılır: tabloları ekleyebilir ve sütunları Windows Forms DataGrid denetimi</span><span class="sxs-lookup"><span data-stu-id="14f43-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="14f43-139">DataGrid denetimi</span><span class="sxs-lookup"><span data-stu-id="14f43-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="14f43-140">Windows Forms veri bağlama</span><span class="sxs-lookup"><span data-stu-id="14f43-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="14f43-141">Visual Studio'da veri erişimi</span><span class="sxs-lookup"><span data-stu-id="14f43-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)