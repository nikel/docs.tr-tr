---
title: "System.TimeSpan yöntemleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9333fee8-1454-4374-855b-8c14c002f48f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: a32b57488b49e9fd2f4e6342391690b27d7ad825
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="systemtimespan-methods"></a><span data-ttu-id="650d4-102">System.TimeSpan yöntemleri</span><span class="sxs-lookup"><span data-stu-id="650d4-102">System.TimeSpan Methods</span></span>
<span data-ttu-id="650d4-103">Üye desteği <xref:System.TimeSpan?displayProperty=nameWithType> büyük ölçüde .NET Framework ve kullandığınız Microsoft SQL Server sürümlerinde bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="650d4-103">Member support for <xref:System.TimeSpan?displayProperty=nameWithType> greatly depends on the versions of the .NET Framework and Microsoft SQL Server that you are using.</span></span>  
  
 <span data-ttu-id="650d4-104">Bir yöntemi, işleci veya özelliği desteklenmiyor; Bu üye için SQL Server üzerinde yürütme LINQ-SQL çeviremez anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="650d4-104">When a method, operator, or property is unsupported; it means that LINQ to SQL cannot translate the member for execution on the SQL Server.</span></span> <span data-ttu-id="650d4-105">Hala bu üyeler, kodunuzda kullanmak mümkün olabilir.</span><span class="sxs-lookup"><span data-stu-id="650d4-105">You may still be able to use these members in your code.</span></span> <span data-ttu-id="650d4-106">Ancak, sorgu Transact-SQL veya veritabanından sonuçları alındıktan sonra çevrilmesi önce bunlar değerlendirilmelidir.</span><span class="sxs-lookup"><span data-stu-id="650d4-106">However, they must be evaluated before the query is translated to Transact-SQL or after the results have been retrieved from the database.</span></span>  
  
## <a name="previous-limitations"></a><span data-ttu-id="650d4-107">Önceki sınırlamaları</span><span class="sxs-lookup"><span data-stu-id="650d4-107">Previous Limitations</span></span>  
 <span data-ttu-id="650d4-108">LINQ-SQL, .NET Framework 3.5 SP1 önce .NET Framework sürümleri ile kullanırken, SQL Server veritabanı alanlarına eşlenemiyor <xref:System.TimeSpan?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="650d4-108">When using LINQ to SQL with versions of the .NET Framework prior to .NET Framework 3.5 SP1, you cannot map SQL Server database fields to <xref:System.TimeSpan?displayProperty=nameWithType>.</span></span> <span data-ttu-id="650d4-109">Ancak, üzerinde işlem <xref:System.TimeSpan> olduğundan desteklenmektedir <xref:System.TimeSpan> değerleri gelen döndürülmesi <xref:System.DateTime> çıkarma veya değişmez değer veya bağlı bir değişken olarak bir ifade halinde sunulan.</span><span class="sxs-lookup"><span data-stu-id="650d4-109">However, operations on <xref:System.TimeSpan> are supported because <xref:System.TimeSpan> values can be returned from <xref:System.DateTime> subtraction or introduced into an expression as a literal or bound variable.</span></span>  
  
## <a name="supported-systemtimespan-method-support"></a><span data-ttu-id="650d4-110">Desteklenen System.TimeSpan yöntemi desteği</span><span class="sxs-lookup"><span data-stu-id="650d4-110">Supported System.TimeSpan Method Support</span></span>  
 <span data-ttu-id="650d4-111">Aşağıdaki LINQ SQL desteklenen yöntem, işleçler ve özellikler, LINQ to SQL sorguları kullanmak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="650d4-111">The following LINQ to SQL-supported methods, operators, and properties are available for you to use in your LINQ to SQL queries.</span></span> <span data-ttu-id="650d4-112">Nesne modeli ya da dış eşleme dosyası eşlenen sonra LINQ-SQL birçok çağrı sayesinde <xref:System.TimeSpan?displayProperty=nameWithType> üyeleri, LINQ to SQL sorguları içinde.</span><span class="sxs-lookup"><span data-stu-id="650d4-112">Once mapped in the object model or external mapping file, LINQ to SQL allows you to call many of the <xref:System.TimeSpan?displayProperty=nameWithType> members inside your LINQ to SQL queries.</span></span>  
  
|<span data-ttu-id="650d4-113">Desteklenen <xref:System.TimeSpan> yöntemleri</span><span class="sxs-lookup"><span data-stu-id="650d4-113">Supported <xref:System.TimeSpan> Methods</span></span>|<span data-ttu-id="650d4-114">Desteklenen <xref:System.TimeSpan> işleçleri</span><span class="sxs-lookup"><span data-stu-id="650d4-114">Supported <xref:System.TimeSpan> Operators</span></span>|<span data-ttu-id="650d4-115">Desteklenen <xref:System.TimeSpan> özellikleri</span><span class="sxs-lookup"><span data-stu-id="650d4-115">Supported <xref:System.TimeSpan> Properties</span></span>|  
|------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.TimeSpan.Compare%2A>|<xref:System.TimeSpan.op_Equality%2A>|<xref:System.TimeSpan.Days%2A>|  
|<xref:System.TimeSpan.CompareTo%28System.TimeSpan%29>|<xref:System.TimeSpan.op_GreaterThan%2A>|<xref:System.TimeSpan.Hours%2A>|  
|<xref:System.TimeSpan.Duration%2A>|<xref:System.TimeSpan.op_GreaterThanOrEqual%2A>|<xref:System.TimeSpan.MaxValue>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%2CSystem.TimeSpan%29>|<xref:System.TimeSpan.op_Inequality%2A>|<xref:System.TimeSpan.Milliseconds%2A>|  
|<xref:System.TimeSpan.Equals%28System.TimeSpan%29>|<xref:System.TimeSpan.op_LessThan%2A>|<xref:System.TimeSpan.Minutes%2A>|  
||<xref:System.TimeSpan.op_LessThanOrEqual%2A>|<!--zz <xref:System.TimeSpan.MinValue%2A>-->|  
  
> [!NOTE]
>  <span data-ttu-id="650d4-116">Eşleme özelliğini <xref:System.TimeSpan?displayProperty=nameWithType> bir SQL `TIME` sütunu LINQ-SQL ile .NET Framework 3.5 SP1 gerektirir ve ötesine.</span><span class="sxs-lookup"><span data-stu-id="650d4-116">The ability to map <xref:System.TimeSpan?displayProperty=nameWithType> to a SQL `TIME` column with LINQ to SQL requires the .NET Framework 3.5 SP1 and beyond.</span></span> <span data-ttu-id="650d4-117">SQL `TIME` veri türüdür yalnızca Microsoft SQL Server 2008 ve sonrasındaki kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="650d4-117">The SQL `TIME` data type is only available in Microsoft SQL Server 2008 and beyond.</span></span>  
  
### <a name="addition-and-subtraction"></a><span data-ttu-id="650d4-118">Toplama ve çıkarma</span><span class="sxs-lookup"><span data-stu-id="650d4-118">Addition and Subtraction</span></span>  
 <span data-ttu-id="650d4-119">Ancak CLR <xref:System.TimeSpan?displayProperty=nameWithType> türünü destekleyen toplama ve çıkarma, SQL `TIME` türünü desteklemez.</span><span class="sxs-lookup"><span data-stu-id="650d4-119">Although the CLR <xref:System.TimeSpan?displayProperty=nameWithType> type does support addition and subtraction, the SQL `TIME` type does not.</span></span> <span data-ttu-id="650d4-120">SQL eşlendiğinde toplama ve çıkarma bunlar çalışırsanız, bu nedenle, LINQ to SQL sorguları hataları oluşturacak `TIME` türü.</span><span class="sxs-lookup"><span data-stu-id="650d4-120">Because of this, your LINQ to SQL queries will generate errors if they attempt addition and subtraction when they are mapped to the SQL `TIME` type.</span></span> <span data-ttu-id="650d4-121">SQL tarih ve saat türleri ile çalışmak için diğer konular bulabilirsiniz [SQL CLR türü eşleme](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="650d4-121">You can find other considerations for working with SQL date and time types in [SQL-CLR Type Mapping](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650d4-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="650d4-122">See Also</span></span>  
 [<span data-ttu-id="650d4-123">Sorgu kavramları</span><span class="sxs-lookup"><span data-stu-id="650d4-123">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [<span data-ttu-id="650d4-124">Nesne modeli oluşturma</span><span class="sxs-lookup"><span data-stu-id="650d4-124">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)  
 [<span data-ttu-id="650d4-125">SQL CLR türü eşlemesi</span><span class="sxs-lookup"><span data-stu-id="650d4-125">SQL-CLR Type Mapping</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)  
 [<span data-ttu-id="650d4-126">Veri türleri ve işlevleri</span><span class="sxs-lookup"><span data-stu-id="650d4-126">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)