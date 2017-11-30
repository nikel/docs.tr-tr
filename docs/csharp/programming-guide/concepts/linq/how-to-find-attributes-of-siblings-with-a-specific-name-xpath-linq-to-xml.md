---
title: "Nasıl yapılır: belirli bir ada (XPath-LINQ-XML) ile eş özniteliklerini Bul (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5a67d502289b10dca95bbc91b16cbc2beae90cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="8bc01-102">Nasıl yapılır: belirli bir ada (XPath-LINQ-XML) ile eş özniteliklerini Bul (C#)</span><span class="sxs-lookup"><span data-stu-id="8bc01-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="8bc01-103">Bu konu, bağlam düğümünün eşdüzeyi tüm özniteliklerini bulmak gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="8bc01-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="8bc01-104">Yalnızca belirli bir ada sahip öznitelik koleksiyonu döndürülür.</span><span class="sxs-lookup"><span data-stu-id="8bc01-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="8bc01-105">XPath ifadesi şöyledir:</span><span class="sxs-lookup"><span data-stu-id="8bc01-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="8bc01-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="8bc01-106">Example</span></span>  
 <span data-ttu-id="8bc01-107">Bu örnek ilk bulur bir `Book` öğesi ve tüm kardeş öğeler adlı bulur `Book`ve ardından tüm öznitelikleri adlı bulur `id`.</span><span class="sxs-lookup"><span data-stu-id="8bc01-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="8bc01-108">Sonuç öznitelikleri koleksiyonudur.</span><span class="sxs-lookup"><span data-stu-id="8bc01-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="8bc01-109">Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: Books (LINQ-XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8bc01-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="8bc01-110">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="8bc01-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="8bc01-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="8bc01-111">See Also</span></span>  
 [<span data-ttu-id="8bc01-112">LINQ-XML XPath kullanıcıların (C#)</span><span class="sxs-lookup"><span data-stu-id="8bc01-112">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)