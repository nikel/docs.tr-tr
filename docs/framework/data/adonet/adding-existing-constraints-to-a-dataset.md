---
title: "Varolan kısıtlamaları bir veri kümesine ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 307d2809-208b-4cf8-b6a9-5d16f15fc16c
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e457113eff471c620ccdbf78337d2013d7a62bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="adding-existing-constraints-to-a-dataset"></a><span data-ttu-id="9b3a4-102">Varolan kısıtlamaları bir veri kümesine ekleme</span><span class="sxs-lookup"><span data-stu-id="9b3a4-102">Adding Existing Constraints to a DataSet</span></span>
<span data-ttu-id="9b3a4-103">**Doldurun** yöntemi **DataAdapter** doldurur bir <xref:System.Data.DataSet> yalnızca tablo sütunları ve satırları veri kaynağından; sahip ancak kısıtlamaları yaygın olarak ayarlanmış veri kaynağı tarafından **doldurun** yöntemi için bu şema bilgileri eklemez **DataSet** varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-103">The **Fill** method of the **DataAdapter** fills a <xref:System.Data.DataSet> only with table columns and rows from a data source; though constraints are commonly set by the data source, the **Fill** method does not add this schema information to the **DataSet** by default.</span></span> <span data-ttu-id="9b3a4-104">Doldurmak için bir **DataSet** ya da arama yapabileceğiniz bir veri kaynağından var olan birincil anahtar kısıtlaması bilgilerle **FillSchema** yöntemi **DataAdapter**, veya ayarlayın **MissingSchemaAction** özelliği **DataAdapter** için **AddWithKey** çağırmadan önce **doldurun**.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-104">To populate a **DataSet** with existing primary key constraint information from a data source, you can either call the **FillSchema** method of the **DataAdapter**, or set the **MissingSchemaAction** property of the **DataAdapter** to **AddWithKey** before calling **Fill**.</span></span> <span data-ttu-id="9b3a4-105">Bu birincil anahtara sağlayacak kısıtlamalar **veri kümesi** bu veri kaynağında yansıtır.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-105">This will ensure that primary key constraints in the **DataSet** reflect those at the data source.</span></span> <span data-ttu-id="9b3a4-106">Yabancı anahtar kısıtlaması bilgileri dahil değildir ve açıkça gösterildiği gibi oluşturulmalıdır [DataTable kısıtlamalarını](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="9b3a4-106">Foreign key constraint information is not included and must be created explicitly, as shown in [DataTable Constraints](../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="9b3a4-107">Şema bilgilerini ekleme bir **DataSet** verilerle doldurma birincil anahtar kısıtlamalarını birlikte garantiler önce <xref:System.Data.DataTable> nesnelerini **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-107">Adding schema information to a **DataSet** before filling it with data ensures that primary key constraints are included with the <xref:System.Data.DataTable> objects in the **DataSet**.</span></span> <span data-ttu-id="9b3a4-108">Sonuç olarak, ek zaman doldurmak için çağrıları **DataSet** yapılan, birincil anahtar sütun bilgileri, veri kaynağından yeni satırlar her geçerli satır ile eşleştirmek için kullanılır **DataTable**ve geçerli verileri tabloları veri kaynağı ile yazılır.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-108">As a result, when additional calls to fill the **DataSet** are made, the primary key column information is used to match new rows from the data source with current rows in each **DataTable**, and current data in the tables is overwritten with data from the data source.</span></span> <span data-ttu-id="9b3a4-109">Veri kaynağından yeni satırlar eklenir şema bilgileri **DataSet**, yinelenen satırları sonuç.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-109">Without the schema information, the new rows from the data source are appended to the **DataSet**, resulting in duplicate rows.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b3a4-110">Bir veri kaynağı bir sütunda otomatik artan olarak belirlenirse **FillSchema** yöntemini veya **doldurun** yöntemi ile bir **MissingSchemaAction** ,  **AddWithKey**, oluşturur bir **DataColumn** ile bir **AutoIncrement** özelliğini `true`.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-110">If a column in a data source is identified as auto-incrementing, the **FillSchema** method, or the **Fill** method with a **MissingSchemaAction** of **AddWithKey**, creates a **DataColumn** with an **AutoIncrement** property set to `true`.</span></span> <span data-ttu-id="9b3a4-111">Ancak, ayarlamak gerekir **AutoIncrementStep değeri** ve **AutoIncrementSeed** kendiniz değerleri.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-111">However, you will need to set the **AutoIncrementStep** and **AutoIncrementSeed** values yourself.</span></span> <span data-ttu-id="9b3a4-112">Sütunları otomatik artırma hakkında daha fazla bilgi için bkz: [oluşturma AutoIncrement sütunları](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span><span class="sxs-lookup"><span data-stu-id="9b3a4-112">For more information about auto-incrementing columns, see [Creating AutoIncrement Columns](../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-autoincrement-columns.md).</span></span>  
  
 <span data-ttu-id="9b3a4-113">Kullanarak **FillSchema** veya ayar **MissingSchemaAction** için **AddWithKey** birincil anahtar sütunu bilgileri belirlemek için veri kaynağında ek işleme gerektirir.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-113">Using **FillSchema** or setting the **MissingSchemaAction** to **AddWithKey** requires extra processing at the data source to determine primary key column information.</span></span> <span data-ttu-id="9b3a4-114">Bu ek işleme performansı düşürür.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-114">This additional processing can hinder performance.</span></span> <span data-ttu-id="9b3a4-115">Tasarım zamanında birincil anahtar bilgilerini biliyorsanız, açıkça birincil anahtar sütunu veya sütun en iyi performans elde etmek için belirttiğiniz öneririz.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-115">If you know the primary key information at design time, we recommend that you explicitly specify the primary key column or columns in order to achieve optimal performance.</span></span> <span data-ttu-id="9b3a4-116">Açıkça bir tablo için birincil anahtar bilgilerini ayarlama hakkında daha fazla bilgi için bkz: [tanımlama birincil anahtarlar](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span><span class="sxs-lookup"><span data-stu-id="9b3a4-116">For information about explicitly setting primary key information for a table, see [Defining Primary Keys](../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md).</span></span>  
  
 <span data-ttu-id="9b3a4-117">Aşağıdaki kod örneğinde, şema bilgi eklemek gösterilmiştir bir **DataSet** kullanarak **FillSchema**.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-117">The following code example shows how to add schema information to a **DataSet** using **FillSchema**.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers")  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.FillSchema(custDataSet, SchemaType.Source, "Customers");  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
 <span data-ttu-id="9b3a4-118">Aşağıdaki kod örneğinde, şema bilgi eklemek gösterilmiştir bir **DataSet** kullanarak **MissingSchemaAction.AddWithKey** özelliği **doldurun** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-118">The following code example shows how to add schema information to a **DataSet** using the **MissingSchemaAction.AddWithKey** property of the **Fill** method.</span></span>  
  
```vb  
Dim custDataSet As DataSet = New DataSet()  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
custAdapter.Fill(custDataSet, "Customers")  
```  
  
```csharp  
DataSet custDataSet = new DataSet();  
  
custAdapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
custAdapter.Fill(custDataSet, "Customers");  
```  
  
## <a name="handling-multiple-result-sets"></a><span data-ttu-id="9b3a4-119">Birden çok sonuç kümesi işleme</span><span class="sxs-lookup"><span data-stu-id="9b3a4-119">Handling Multiple Result Sets</span></span>  
 <span data-ttu-id="9b3a4-120">Varsa **DataAdapter** döndürülen birden çok sonuç kümesi karşılaştığında **SelectCommand**, birden fazla tabloya oluşturacak **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-120">If the **DataAdapter** encounters multiple result sets returned from the **SelectCommand**, it will create multiple tables in the **DataSet**.</span></span> <span data-ttu-id="9b3a4-121">Tabloları bir sıfır tabanlı artımlı varsayılan adı verilen **tablo** *N*sürümünden itibaren **tablo** "Table0" yerine.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-121">The tables will be given a zero-based incremental default name of **Table** *N*, starting with **Table** instead of "Table0".</span></span> <span data-ttu-id="9b3a4-122">Bağımsız değişken olarak bir tablo adı geçip geçmediğini **FillSchema** yöntemi, tablolar sıfır tabanlı bir artımlı adı verilir **TableName** *N* sürümündenitibaren**TableName** "TableName0" yerine.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-122">If a table name is passed as an argument to the **FillSchema** method, the tables will be given a zero-based incremental name of **TableName** *N*, starting with **TableName** instead of "TableName0".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b3a4-123">Varsa **FillSchema** yöntemi **OleDbDataAdapter** nesne birden çok sonuç kümesi döndüren bir komutu için çağrılır, yalnızca şema bilgileri ilk sonuç kümesinden döndürülür.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-123">If the **FillSchema** method of the **OleDbDataAdapter** object is called for a command that returns multiple result sets, only the schema information from the first result set is returned.</span></span> <span data-ttu-id="9b3a4-124">Birden çok sonuç için şema bilgileri döndüren zaman ayarlar kullanarak **OleDbDataAdapter**, önerilen, belirttiğiniz bir **MissingSchemaAction** , **AddWithKey** ve çağrılırken şema bilgileri elde **doldurun** yöntemi.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-124">When returning schema information for multiple result sets using the **OleDbDataAdapter**, it is recommended that you specify a **MissingSchemaAction** of **AddWithKey** and obtain the schema information when calling the **Fill** method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3a4-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9b3a4-125">See Also</span></span>  
 [<span data-ttu-id="9b3a4-126">DataAdapters ve DataReader</span><span class="sxs-lookup"><span data-stu-id="9b3a4-126">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)  
 [<span data-ttu-id="9b3a4-127">Veri kümeleri, DataTable ve DataView</span><span class="sxs-lookup"><span data-stu-id="9b3a4-127">DataSets, DataTables, and DataViews</span></span>](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="9b3a4-128">Alma ve ADO.NET veri değiştirme</span><span class="sxs-lookup"><span data-stu-id="9b3a4-128">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [<span data-ttu-id="9b3a4-129">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="9b3a4-129">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)