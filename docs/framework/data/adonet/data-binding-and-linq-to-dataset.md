---
title: "Veri bağlama ve LINQ-DataSet"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b3b097f9bca790d1f19da9d75f834c6277507d8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-and-linq-to-dataset"></a><span data-ttu-id="52e88-102">Veri bağlama ve LINQ-DataSet</span><span class="sxs-lookup"><span data-stu-id="52e88-102">Data Binding and LINQ to DataSet</span></span>
<span data-ttu-id="52e88-103">*Veri bağlama* uygulama kullanıcı Arabirimi iş mantığı arasında bir bağlantı kurar işlemidir.</span><span class="sxs-lookup"><span data-stu-id="52e88-103">*Data binding* is the process that establishes a connection between the application UI and business logic.</span></span> <span data-ttu-id="52e88-104">Bağlama doğru ayarları varsa ve veri değeri değiştiğinde veri uygun bildirimleri sağlarsa, veriye bağlı öğeleri değişiklikleri otomatik olarak yansıtır.</span><span class="sxs-lookup"><span data-stu-id="52e88-104">If the binding has the correct settings and the data provides the proper notifications, when the data changes its value, the elements that are bound to the data reflect changes automatically.</span></span> <span data-ttu-id="52e88-105"><xref:System.Data.DataSet> Tutarlı bir ilişkisel programlama modeli, içerdiği veri kaynağını bakılmaksızın sağlayan veri bellek içi gösterimidir.</span><span class="sxs-lookup"><span data-stu-id="52e88-105">The <xref:System.Data.DataSet> is an in- memory representation of data that provides a consistent relational programming model, regardless of the source of the data it contains.</span></span> <span data-ttu-id="52e88-106">ADO.NET 2.0 <xref:System.Data.DataView> depolanan verilerini sıralama ve filtreleme sağlar bir <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="52e88-106">The ADO.NET 2.0 <xref:System.Data.DataView> enables you to sort and filter the data stored in a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="52e88-107">Bu işlevsellik, genellikle veri bağlama uygulamalarda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="52e88-107">This functionality is often used in data-binding applications.</span></span> <span data-ttu-id="52e88-108">Kullanarak bir <xref:System.Data.DataView>farklı sıralamalar olan bir tabloda veri getirebilir ve veri satırı durum ya da bir filtre ifadesi göre göre filtre uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="52e88-108">By using a <xref:System.Data.DataView>, you can expose the data in a table with different sort orders, and you can filter the data by row state or based on a filter expression.</span></span> <span data-ttu-id="52e88-109">Hakkında daha fazla bilgi için <xref:System.Data.DataView> nesne için bkz: [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span><span class="sxs-lookup"><span data-stu-id="52e88-109">For more information about the <xref:System.Data.DataView> object, see [DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).</span></span>  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="52e88-110">üzerinden karmaşık ve güçlü sorgular oluşturmak geliştiriciler sağlayan bir <xref:System.Data.DataSet> kullanarak [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52e88-110"> allows developers to create complex, powerful queries over a <xref:System.Data.DataSet> by using [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)].</span></span> <span data-ttu-id="52e88-111">Ancak, bir [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sorgunun döndürdüğü numaralandırması <xref:System.Data.DataRow> kolayca bağlama senaryolarda kullanılmayan nesneler.</span><span class="sxs-lookup"><span data-stu-id="52e88-111">However, a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query returns an enumeration of <xref:System.Data.DataRow> objects, which is not easily used in a binding scenario.</span></span> <span data-ttu-id="52e88-112">Bağlama kolaylaştırmak için oluşturabileceğiniz bir <xref:System.Data.DataView> gelen bir [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] sorgu.</span><span class="sxs-lookup"><span data-stu-id="52e88-112">To make binding easier, you can create a <xref:System.Data.DataView> from a [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] query.</span></span> <span data-ttu-id="52e88-113">Bu <xref:System.Data.DataView> filtreleme ve sorguda belirtilen sıralama kullanır, ancak daha iyi veri bağlaması için uygundur.</span><span class="sxs-lookup"><span data-stu-id="52e88-113">This <xref:System.Data.DataView> uses the filtering and sorting specified in the query, but is better suited for data binding.</span></span> [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]<span data-ttu-id="52e88-114">işlevselliğini genişleten <xref:System.Data.DataView> sağlayarak [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] ifade tabanlı filtreleme ve sıralama, veren çok daha karmaşık ve güçlü filtreleme ve sıralama daha dize tabanlı filtreleme ve sıralama işlemleri.</span><span class="sxs-lookup"><span data-stu-id="52e88-114"> extends the functionality of the <xref:System.Data.DataView> by providing [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] expression-based filtering and sorting, which allows for much more complex and powerful filtering and sorting operations than string-based filtering and sorting.</span></span>  
  
 <span data-ttu-id="52e88-115">Unutmayın <xref:System.Data.DataView> sorgu temsil eder ve sorgu en üstünde bir görünüm değil.</span><span class="sxs-lookup"><span data-stu-id="52e88-115">Note that the <xref:System.Data.DataView> represents the query itself and is not a view on top of the query.</span></span> <span data-ttu-id="52e88-116"><xref:System.Data.DataView> Gibi UI denetimine bağlı bir <xref:System.Windows.Forms.DataGrid> veya <xref:System.Windows.Forms.DataGridView>, basit veri bağlama modelini sağlama.</span><span class="sxs-lookup"><span data-stu-id="52e88-116">The <xref:System.Data.DataView> is bound to a UI control, such as a <xref:System.Windows.Forms.DataGrid> or a <xref:System.Windows.Forms.DataGridView>, providing a simple data binding model.</span></span> <span data-ttu-id="52e88-117">A <xref:System.Data.DataView> de oluşturulabilir bir <xref:System.Data.DataTable>, bu tablonun varsayılan görünüm sağlar.</span><span class="sxs-lookup"><span data-stu-id="52e88-117">A <xref:System.Data.DataView> can also be created from a <xref:System.Data.DataTable>, providing a default view of that table.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52e88-118">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="52e88-118">In This Section</span></span>  
 [<span data-ttu-id="52e88-119">DataView nesnesi oluşturma</span><span class="sxs-lookup"><span data-stu-id="52e88-119">Creating a DataView Object</span></span>](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 <span data-ttu-id="52e88-120">Oluşturma hakkında bilgi sağlayan bir <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="52e88-120">Provides information about creating a <xref:System.Data.DataView>.</span></span>  
  
 [<span data-ttu-id="52e88-121">DataView ile filtreleme</span><span class="sxs-lookup"><span data-stu-id="52e88-121">Filtering with DataView</span></span>](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 <span data-ttu-id="52e88-122">Filtrele açıklar <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="52e88-122">Describes how to filter with the <xref:System.Data.DataView>.</span></span>  
  
 [<span data-ttu-id="52e88-123">DataView ile sıralama</span><span class="sxs-lookup"><span data-stu-id="52e88-123">Sorting with DataView</span></span>](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 <span data-ttu-id="52e88-124">İle sıralama açıklar <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="52e88-124">Describes how to sort with the <xref:System.Data.DataView>.</span></span>  
  
 [<span data-ttu-id="52e88-125">DataView DataRowView koleksiyonunda sorgulama</span><span class="sxs-lookup"><span data-stu-id="52e88-125">Querying the DataRowView Collection in a DataView</span></span>](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 <span data-ttu-id="52e88-126">Sorgulama hakkında bilgi sağlayan <xref:System.Data.DataRowView> koleksiyonu kullanıma sunulan <xref:System.Data.DataView>.</span><span class="sxs-lookup"><span data-stu-id="52e88-126">Provides information about querying the <xref:System.Data.DataRowView> collection exposed by <xref:System.Data.DataView>.</span></span>  
  
 [<span data-ttu-id="52e88-127">DataView performansı</span><span class="sxs-lookup"><span data-stu-id="52e88-127">DataView Performance</span></span>](../../../../docs/framework/data/adonet/dataview-performance.md)  
 <span data-ttu-id="52e88-128">Hakkında bilgi sağlar <xref:System.Data.DataView> ve performans.</span><span class="sxs-lookup"><span data-stu-id="52e88-128">Provides information about <xref:System.Data.DataView> and performance.</span></span>  
  
 [<span data-ttu-id="52e88-129">Nasıl yapılır: bir DataView nesnesi bir Windows Forms DataGridView denetimine bağlama</span><span class="sxs-lookup"><span data-stu-id="52e88-129">How to: Bind a DataView Object to a Windows Forms DataGridView Control</span></span>](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 <span data-ttu-id="52e88-130">' E nasıl bağlanacağını açıklar bir <xref:System.Data.DataView> nesnesine bir <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="52e88-130">Describes how to bind a <xref:System.Data.DataView> object to a <xref:System.Windows.Forms.DataGridView>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52e88-131">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="52e88-131">See Also</span></span>  
 [<span data-ttu-id="52e88-132">Programlama Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="52e88-132">Programming Guide</span></span>](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)