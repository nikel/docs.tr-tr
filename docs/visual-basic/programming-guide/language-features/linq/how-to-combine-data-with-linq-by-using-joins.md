---
title: "Nasıl yapılır: Birleştirmeleri Kullanarak Verileri LINQ İle Birleştirme (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- queries [LINQ in Visual Basic], joins
- joins [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- Group Join clause [Visual Basic]
- joining [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 5b00a478-035b-41c6-8918-be1a97728396
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 432be646ce4353fd4627a34f363e7562f6181e92
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-combine-data-with-linq-by-using-joins-visual-basic"></a><span data-ttu-id="d58d7-102">Nasıl yapılır: Birleştirmeleri Kullanarak Verileri LINQ İle Birleştirme (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d58d7-102">How to: Combine Data with LINQ by Using Joins (Visual Basic)</span></span>
<span data-ttu-id="d58d7-103">Visual Basic sağlar `Join` ve `Group Join` sorgu yan tümceleri, koleksiyonları arasında ortak değerlere göre birden fazla koleksiyonun içeriğini birleştirmenize olanak sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="d58d7-103">Visual Basic provides the `Join` and `Group Join` query clauses to enable you to combine the contents of multiple collections based on common values between the collections.</span></span> <span data-ttu-id="d58d7-104">Bu değerler olarak da bilinir *anahtar* değerleri.</span><span class="sxs-lookup"><span data-stu-id="d58d7-104">These values are known as *key* values.</span></span> <span data-ttu-id="d58d7-105">Geliştiriciler ilişkisel veritabanı kavramlarını algılayacağı `Join` olarak INNER JOIN yan tümcesi ve `Group Join` olarak, etkili bir şekilde bir LEFT OUTER JOIN yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d58d7-105">Developers familiar with relational database concepts will recognize the `Join` clause as an INNER JOIN and the `Group Join` clause as, effectively, a LEFT OUTER JOIN.</span></span>  
  
 <span data-ttu-id="d58d7-106">Bu konudaki örnekler kullanarak veri birleştirme için birkaç yol göstermek `Join` ve `Group Join` sorgu yan tümceleri.</span><span class="sxs-lookup"><span data-stu-id="d58d7-106">The examples in this topic demonstrate a few ways to combine data by using the `Join` and `Group Join` query clauses.</span></span>  
  
## <a name="create-a-project-and-add-sample-data"></a><span data-ttu-id="d58d7-107">Bir proje oluşturma ve örnek veri ekleme</span><span class="sxs-lookup"><span data-stu-id="d58d7-107">Create a Project and Add Sample Data</span></span>  
  
#### <a name="to-create-a-project-that-contains-sample-data-and-types"></a><span data-ttu-id="d58d7-108">Örnek veriler ve türlerini içeren bir proje oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="d58d7-108">To create a project that contains sample data and types</span></span>  
  
1.  <span data-ttu-id="d58d7-109">Bu konudaki örnekler çalıştırmak için Visual Studio'yu açın ve yeni bir Visual Basic konsol uygulama projesi ekleyin.</span><span class="sxs-lookup"><span data-stu-id="d58d7-109">To run the samples in this topic, open Visual Studio and add a new Visual Basic Console Application project.</span></span> <span data-ttu-id="d58d7-110">Visual Basic tarafından oluşturulan Module1.vb dosyasını çift tıklatın.</span><span class="sxs-lookup"><span data-stu-id="d58d7-110">Double-click the Module1.vb file created by Visual Basic.</span></span>  
  
2.  <span data-ttu-id="d58d7-111">Bu konuda kullanım örnekleri `Person` ve `Pet` türleri ve aşağıdaki kod örneğinde verileri.</span><span class="sxs-lookup"><span data-stu-id="d58d7-111">The samples in this topic use the `Person` and `Pet` types and data from the following code example.</span></span> <span data-ttu-id="d58d7-112">Bu kod varsayılan kopyalama `Module1` Visual Basic tarafından oluşturulan modülü.</span><span class="sxs-lookup"><span data-stu-id="d58d7-112">Copy this code into the default `Module1` module created by Visual Basic.</span></span>  
  
     [!code-vb[VbLINQHowTos#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_1.vb)]  
    [!code-vb[VbLINQHowTos#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_2.vb)]  
  
## <a name="perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="d58d7-113">JOIN yan tümcesi kullanarak bir iç birleştirme gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="d58d7-113">Perform an Inner Join by Using the Join Clause</span></span>  
 <span data-ttu-id="d58d7-114">INNER JOIN iki koleksiyon verileri birleştirir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-114">An INNER JOIN combines data from two collections.</span></span> <span data-ttu-id="d58d7-115">Kendisi için belirtilen anahtar değerleriyle eşleşen öğeleri dahil edilir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-115">Items for which the specified key values match are included.</span></span> <span data-ttu-id="d58d7-116">Eşleşen bir öğe diğer koleksiyonunda yok ya da koleksiyon öğelerinden hariç tutulur.</span><span class="sxs-lookup"><span data-stu-id="d58d7-116">Any items from either collection that do not have a matching item in the other collection are excluded.</span></span>  
  
 <span data-ttu-id="d58d7-117">Visual Basic'te LINQ bir iç birleştirme gerçekleştirmek için iki seçenek sağlar: dolaylı bir birleşim ve açık bir birleştirme.</span><span class="sxs-lookup"><span data-stu-id="d58d7-117">In Visual Basic, LINQ provides two options for performing an INNER JOIN: an implicit join and an explicit join.</span></span>  
  
 <span data-ttu-id="d58d7-118">Dolaylı bir birleşim birleştirilecek olan koleksiyonları belirtir bir `From` yan tümcesi ve eşleşen anahtar alanları tanımlayan bir `Where` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d58d7-118">An implicit join specifies the collections to be joined in a `From` clause and identifies the matching key fields in a `Where` clause.</span></span> <span data-ttu-id="d58d7-119">Visual Basic, belirtilen anahtar alanlara göre iki koleksiyon örtük olarak birleştirir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-119">Visual Basic implicitly joins the two collections based on the specified key fields.</span></span>  
  
 <span data-ttu-id="d58d7-120">Açık bir birleşim kullanarak belirtebilirsiniz `Join` birleştirme kullanmak için hangi anahtar alanlar hakkında belirli olmasını istediğiniz zaman yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="d58d7-120">You can specify an explicit join by using the `Join` clause when you want to be specific about which key fields to use in the join.</span></span> <span data-ttu-id="d58d7-121">Bu durumda, bir `Where` yan tümcesi hala sorgu sonuçlarını filtrelemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-121">In this case, a `Where` clause can still be used to filter the query results.</span></span>  
  
#### <a name="to-perform-an-inner-join-by-using-the-join-clause"></a><span data-ttu-id="d58d7-122">INNER JOIN JOIN yan tümcesi kullanarak gerçekleştirmek için</span><span class="sxs-lookup"><span data-stu-id="d58d7-122">To perform an Inner Join by using the Join clause</span></span>  
  
1.  <span data-ttu-id="d58d7-123">Aşağıdaki kodu ekleyin `Module1` iki örtük ve açık iç birleşim örnekleri görmek için projenizdeki modülü.</span><span class="sxs-lookup"><span data-stu-id="d58d7-123">Add the following code to the `Module1` module in your project to see examples of both an implicit and explicit inner join.</span></span>  
  
     [!code-vb[VbLINQHowTos#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_3.vb)]  
  
## <a name="perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="d58d7-124">Group Join tümcesi kullanarak bir sol dış birleşim gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="d58d7-124">Perform a Left Outer Join by Using the Group Join Clause</span></span>  
 <span data-ttu-id="d58d7-125">Bir sol dış birleştirme sol taraftaki koleksiyondaki tüm öğeleri birleştirme ve yalnızca eşleşen değerleri katılma sağ taraftaki koleksiyonundan içerir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-125">A LEFT OUTER JOIN includes all the items from the left-side collection of the join and only matching values from the right-side collection of the join.</span></span> <span data-ttu-id="d58d7-126">Eşleşen bir öğe sol taraftaki koleksiyonunda bulunmayan tüm öğeleri katılma sağ taraftaki koleksiyonundan gelen sorgu sonucu hariç tutulur.</span><span class="sxs-lookup"><span data-stu-id="d58d7-126">Any items from the right-side collection of the join that do not have a matching item in the left-side collection are excluded from the query result.</span></span>  
  
 <span data-ttu-id="d58d7-127">`Group Join` Yan tümcesi gerçekleştirir, uygulamada LEFT OUTER JOIN.</span><span class="sxs-lookup"><span data-stu-id="d58d7-127">The `Group Join` clause performs, in effect, a LEFT OUTER JOIN.</span></span> <span data-ttu-id="d58d7-128">Ne genellikle bir LEFT OUTER JOIN bilinir ve ne arasındaki farkı `Group Join` yan tümcesi döndürür da `Group Join` birleştirme sol taraftaki koleksiyondaki her öğe için sağ taraftaki koleksiyonundan yan tümcesi grupları sonuçları.</span><span class="sxs-lookup"><span data-stu-id="d58d7-128">The difference between what is typically known as a LEFT OUTER JOIN and what the `Group Join` clause returns is that the `Group Join` clause groups results from the right-side collection of the join for each item in the left-side collection.</span></span> <span data-ttu-id="d58d7-129">İlişkisel bir veritabanında, her iki koleksiyon birleştirme eşleşen öğeleri, sorgudaki her öğe neden bir gruplanmamış sonucunu içerir bir LEFT OUTER JOIN döndürür.</span><span class="sxs-lookup"><span data-stu-id="d58d7-129">In a relational database, a LEFT OUTER JOIN returns an ungrouped result in which each item in the query result contains matching items from both collections in the join.</span></span> <span data-ttu-id="d58d7-130">Bu durumda, birleştirmenin sol taraftaki koleksiyonundan öğeleri sağ taraftaki koleksiyonundan eşleşen her öğe için yinelenir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-130">In this case, the items from the left-side collection of the join are repeated for each matching item from the right-side collection.</span></span> <span data-ttu-id="d58d7-131">Bir sonraki yordamı tamamladıktan sonra bu nasıl göründüğünü görürsünüz.</span><span class="sxs-lookup"><span data-stu-id="d58d7-131">You will see what this looks like when you complete the next procedure.</span></span>  
  
 <span data-ttu-id="d58d7-132">Sonuçları almak bir `Group Join` sorgu her gruplandırılmış sorgu sonucu için bir öğe döndürülecek sorgunuzu genişletme tarafından gruplanmamış bir sonucu olarak.</span><span class="sxs-lookup"><span data-stu-id="d58d7-132">You can retrieve the results of a `Group Join` query as an ungrouped result by extending your query to return an item for each grouped query result.</span></span> <span data-ttu-id="d58d7-133">Bunu başarmak için üzerinde sorgu olun sahip `DefaultIfEmpty` gruplandırılmış koleksiyonunun yöntemi.</span><span class="sxs-lookup"><span data-stu-id="d58d7-133">To accomplish this, you have to ensure that you query on the `DefaultIfEmpty` method of the grouped collection.</span></span> <span data-ttu-id="d58d7-134">Bu, sağ taraftaki koleksiyonundan eşleşen hiçbir sonuç olsa bile birleştirmenin sol taraftaki koleksiyonundan öğeleri hala sorgu sonucunda içerdiği sağlar.</span><span class="sxs-lookup"><span data-stu-id="d58d7-134">This ensures that items from the left-side collection of the join are still included in the query result even if they have no matching results from the right-side collection.</span></span> <span data-ttu-id="d58d7-135">Sorgunuz katılma sağ taraftaki koleksiyonundan eşleşen hiçbir değer bulunduğunda bir varsayılan sonuç değeri sağlamak için kod ekleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d58d7-135">You can add code to your query to provide a default result value when there is no matching value from the right-side collection of the join.</span></span>  
  
#### <a name="to-perform-a-left-outer-join-by-using-the-group-join-clause"></a><span data-ttu-id="d58d7-136">Left Outer JOIN Grup JOIN yan tümcesi kullanarak gerçekleştirmek için</span><span class="sxs-lookup"><span data-stu-id="d58d7-136">To perform a Left Outer Join by using the Group Join clause</span></span>  
  
1.  <span data-ttu-id="d58d7-137">Aşağıdaki kodu ekleyin `Module1` gruplandırılmış bir sol dış birleştirme ve gruplanmamış sol dış birleşim örnekleri görmek için projenizdeki modülü.</span><span class="sxs-lookup"><span data-stu-id="d58d7-137">Add the following code to the `Module1` module in your project to see examples of both a grouped left outer join and an ungrouped left outer join.</span></span>  
  
     [!code-vb[VbLINQHowTos#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_4.vb)]  
  
## <a name="perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="d58d7-138">Bileşik bir anahtar kullanarak bir birleştirme gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="d58d7-138">Perform a Join by Using a Composite Key</span></span>  
 <span data-ttu-id="d58d7-139">Kullanabileceğiniz `And` in anahtar sözcüğü bir `Join` veya `Group Join` eşleştirme yapılırken kullanılacak birden çok anahtar alanları tanımlamak için yan tümceyi birleştirilen koleksiyonlarından değerleri.</span><span class="sxs-lookup"><span data-stu-id="d58d7-139">You can use the `And` keyword in a `Join` or `Group Join` clause to identify multiple key fields to use when matching values from the collections being joined.</span></span> <span data-ttu-id="d58d7-140">`And` Anahtar sözcüğü belirtir belirtilen tüm anahtar alanları için birleştirilecek öğeleri eşleşmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="d58d7-140">The `And` keyword specifies that all specified key fields must match for items to be joined.</span></span>  
  
#### <a name="to-perform-a-join-by-using-a-composite-key"></a><span data-ttu-id="d58d7-141">Bileşik bir anahtar kullanarak bir birleştirme gerçekleştirme</span><span class="sxs-lookup"><span data-stu-id="d58d7-141">To perform a Join by using a composite key</span></span>  
  
1.  <span data-ttu-id="d58d7-142">Aşağıdaki kodu ekleyin `Module1` bileşik bir anahtar kullanan bir birleşim örnekleri görmek için projenizdeki modülü.</span><span class="sxs-lookup"><span data-stu-id="d58d7-142">Add the following code to the `Module1` module in your project to see examples of a join that uses a composite key.</span></span>  
  
     [!code-vb[VbLINQHowTos#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_5.vb)]  
  
## <a name="run-the-code"></a><span data-ttu-id="d58d7-143">Kodu çalıştırma</span><span class="sxs-lookup"><span data-stu-id="d58d7-143">Run the Code</span></span>  
  
#### <a name="to-add-code-to-run-the-examples"></a><span data-ttu-id="d58d7-144">Örneklerini çalıştırmak üzere kod eklemek için</span><span class="sxs-lookup"><span data-stu-id="d58d7-144">To add code to run the examples</span></span>  
  
1.  <span data-ttu-id="d58d7-145">Değiştir `Sub Main` içinde `Module1` bu konudaki örnekler çalıştırmak için aşağıdaki kod projenizle modülünde.</span><span class="sxs-lookup"><span data-stu-id="d58d7-145">Replace the `Sub Main` in the `Module1` module in your project with the following code to run the examples in this topic.</span></span>  
  
     [!code-vb[VbLINQHowTos#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-combine-data-with-linq-by-using-joins_6.vb)]  
  
2.  <span data-ttu-id="d58d7-146">Örnekleri çalıştırmak için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="d58d7-146">Press F5 to run the examples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58d7-147">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d58d7-147">See Also</span></span>  
 [<span data-ttu-id="d58d7-148">LINQ</span><span class="sxs-lookup"><span data-stu-id="d58d7-148">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="d58d7-149">Visual Basic'de LINQ'e giriş</span><span class="sxs-lookup"><span data-stu-id="d58d7-149">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="d58d7-150">Join tümcesi</span><span class="sxs-lookup"><span data-stu-id="d58d7-150">Join Clause</span></span>](../../../../visual-basic/language-reference/queries/join-clause.md)  
 [<span data-ttu-id="d58d7-151">Group Join tümcesi</span><span class="sxs-lookup"><span data-stu-id="d58d7-151">Group Join Clause</span></span>](../../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [<span data-ttu-id="d58d7-152">From yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="d58d7-152">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)  
 [<span data-ttu-id="d58d7-153">Burada yan tümcesi</span><span class="sxs-lookup"><span data-stu-id="d58d7-153">Where Clause</span></span>](../../../../visual-basic/language-reference/queries/where-clause.md)  
 [<span data-ttu-id="d58d7-154">Sorguları</span><span class="sxs-lookup"><span data-stu-id="d58d7-154">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="d58d7-155">LINQ (C#) ile veri dönüştürmeler</span><span class="sxs-lookup"><span data-stu-id="d58d7-155">Data Transformations with LINQ (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/data-transformations-with-linq.md)