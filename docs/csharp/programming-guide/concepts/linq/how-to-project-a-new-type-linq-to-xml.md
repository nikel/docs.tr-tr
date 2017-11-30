---
title: "Nasıl yapılır: Proje yeni türü (LINQ-XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7d3deb826bdccdc2a24db84c006fe317a2321442
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="7d293-102">Nasıl yapılır: Proje yeni türü (LINQ-XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7d293-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>
<span data-ttu-id="7d293-103">Bu bölümdeki diğer örnekler, sonuç olarak döndüren sorgular göstermiştir <xref:System.Collections.Generic.IEnumerable%601> , <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> , `string`, ve <xref:System.Collections.Generic.IEnumerable%601> , `int`.</span><span class="sxs-lookup"><span data-stu-id="7d293-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="7d293-104">Bu ortak sonuç türleri olan, ancak her senaryo için uygun değildir.</span><span class="sxs-lookup"><span data-stu-id="7d293-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="7d293-105">Çoğu durumda döndürülecek sorgularınızı isteyeceksiniz bir <xref:System.Collections.Generic.IEnumerable%601> başka bir tür.</span><span class="sxs-lookup"><span data-stu-id="7d293-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d293-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="7d293-106">Example</span></span>  
 <span data-ttu-id="7d293-107">Bu örnek nesneleri örneği gösterilmektedir `select` yan tümcesi.</span><span class="sxs-lookup"><span data-stu-id="7d293-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="7d293-108">Kod ilk bir oluşturucuya sahip yeni bir sınıf tanımlar ve ardından değiştirir `select` deyimi ifade yeni sınıfının yeni bir örneğini olmasını sağlayın.</span><span class="sxs-lookup"><span data-stu-id="7d293-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="7d293-109">Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: tipik satın alma siparişi (LINQ-XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="7d293-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
        XElement po = XElement.Load("PurchaseOrder.xml");  
  
        IEnumerable<NameQty> nqList =  
            from n in po.Descendants("Item")  
            select new NameQty(  
                    (string)n.Element("ProductName"),  
                    (int)n.Element("Quantity")  
                );  
  
        foreach (NameQty n in nqList)  
            Console.WriteLine(n.name + ":" + n.qty);  
    }  
}  
```  
  
 <span data-ttu-id="7d293-110">Bu örnekte `M:System.Xml.Linq.XElement.Element` konu başlığı altında tanıtılan yöntemi [nasıl yapılır: tek bir alt öğe (LINQ-XML) alma (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="7d293-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="7d293-111">Tarafından döndürülen öğelerinin değerlerini almak için atamalar da kullandığı `M:System.Xml.Linq.XElement.Element` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7d293-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="7d293-112">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="7d293-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  
## <a name="see-also"></a><span data-ttu-id="7d293-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7d293-113">See Also</span></span>  
 [<span data-ttu-id="7d293-114">Projeksiyonlar ve dönüştürmeler (LINQ-XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="7d293-114">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)