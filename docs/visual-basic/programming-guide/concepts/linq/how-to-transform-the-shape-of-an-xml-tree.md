---
title: "Nasıl yapılır: bir XML ağacının (Visual Basic) şekil Dönüştür"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84b60854-48b2-452c-87f2-77d53e1d653a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: cad7e5fc53b59593cf0c367d65d5bd44564bb1c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-transform-the-shape-of-an-xml-tree-visual-basic"></a><span data-ttu-id="f6ef3-102">Nasıl yapılır: bir XML ağacının (Visual Basic) şekil Dönüştür</span><span class="sxs-lookup"><span data-stu-id="f6ef3-102">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="f6ef3-103">*Şekli* bir XML belgesi öğe adları, öznitelik adları ve özellikleri, hiyerarşinin başvuruyor.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-103">The *shape* of an XML document refers to its element names, attribute names, and the characteristics of its hierarchy.</span></span>  
  
 <span data-ttu-id="f6ef3-104">Bazen, bir XML belgesi şeklini değiştirmek gerekir.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-104">Sometimes you will have to change the shape of an XML document.</span></span> <span data-ttu-id="f6ef3-105">Örneğin, var olan bir XML belgesi farklı öğe ve öznitelik adları gerektiren başka bir sisteme gönderme gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-105">For example, you might have to send an existing XML document to another system that requires different element and attribute names.</span></span> <span data-ttu-id="f6ef3-106">Belgenin silmeyi ve daha okunabilir ve sürdürülebilir kodu gerekli, ancak kullanarak işlev yapım sonuç olarak öğeleri yeniden adlandırma gidebilir.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-106">You could go through the document, deleting and renaming elements as required, but using functional construction results in more readable and maintainable code.</span></span> <span data-ttu-id="f6ef3-107">İşlev oluşturma hakkında daha fazla bilgi için bkz: [işlevsel yapımı (LINQ-XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f6ef3-107">For more information about functional construction, see [Functional Construction (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="f6ef3-108">İlk örnek XML belgesi organizasyonu değiştirir.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-108">The first example changes the organization of the XML document.</span></span> <span data-ttu-id="f6ef3-109">Bu karmaşık öğeleri ağacında bir konumdan diğerine taşır.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-109">It moves complex elements from one location in the tree to another.</span></span>  
  
 <span data-ttu-id="f6ef3-110">Bu konudaki ikinci örnek kaynak belgedeki daha farklı bir şekli bir XML belgesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-110">The second example in this topic creates an XML document with a different shape than the source document.</span></span> <span data-ttu-id="f6ef3-111">Öğe adları büyük küçük harf değiştirir, bazı öğelerin yeniden adlandırır ve bazı öğeler kaynak ağaç dönüştürülmüş ağaç dışında bırakır.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-111">It changes the casing of the element names, renames some elements, and leaves some elements from the source tree out of the transformed tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6ef3-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="f6ef3-112">Example</span></span>  
 <span data-ttu-id="f6ef3-113">Aşağıdaki kod katıştırılmış sorgu ifadeleri kullanarak XML dosyasını şeklini değiştirir.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-113">The following code changes the shape of an XML file using embedded query expressions.</span></span>  
  
 <span data-ttu-id="f6ef3-114">Bu örnekte kaynak XML belgesi içeriyor bir `Customers` öğesinin altında `Root` tüm müşteriler içeren öğe.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-114">The source XML document in this example contains a `Customers` element under the `Root` element that contains all customers.</span></span> <span data-ttu-id="f6ef3-115">Ayrıca içeren bir `Orders` öğesinin altında `Root` tüm siparişleri içeren öğe.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-115">It also contains an `Orders` element under the `Root` element that contains all orders.</span></span> <span data-ttu-id="f6ef3-116">Bu örnekte, her bir müşteri için siparişleri içerdiği yeni bir XML ağacı oluşturur bir `Orders` öğesi içinde `Customer` öğesi.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-116">This example creates a new XML tree in which the orders for each customer are contained in an `Orders` element within the `Customer` element.</span></span> <span data-ttu-id="f6ef3-117">Özgün belgeyi de içeren bir `CustomerID` öğesinde `Order` öğesi; yeniden şekilli belgeden kaldırılması bu öğe olacaktır.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-117">The original document also contains a `CustomerID` element in the `Order` element; this element will be removed from the re-shaped document.</span></span>  
  
 <span data-ttu-id="f6ef3-118">Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: müşteriler ve siparişler (LINQ-XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f6ef3-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim co As XElement = XElement.Load("CustomersOrders.xml")  
Dim newCustOrd = _  
    <Root>  
        <%= From cust In co.<Customers>.<Customer> _  
            Select _  
            <Customer>  
                <%= cust.Attributes() %>  
                <%= cust.Elements() %>  
                <Orders>  
                    <%= From ord In co.<Orders>.<Order> _  
                        Where ord.<CustomerID>.Value = cust.@CustomerID _  
                        Select _  
                        <Order>  
                            <%= ord.Attributes() %>  
                            <%= ord.<EmployeeID> %>  
                            <%= ord.<OrderDate> %>  
                            <%= ord.<RequiredDate> %>  
                            <%= ord.<ShipInfo> %>  
                        </Order> _  
                    %>  
                </Orders>  
            </Customer> _  
        %>  
    </Root>  
Console.WriteLine(newCustOrd)  
```  
  
 <span data-ttu-id="f6ef3-119">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f6ef3-119">This code produces the following output:</span></span>  
  
```xml  
        <Root>  
<Customer CustomerID="GREAL">  
  <CompanyName>Great Lakes Food Market</CompanyName>  
  <ContactName>Howard Snyder</ContactName>  
  <ContactTitle>Marketing Manager</ContactTitle>  
  <Phone>(503) 555-7555</Phone>  
  <FullAddress>  
    <Address>2732 Baker Blvd.</Address>  
    <City>Eugene</City>  
    <Region>OR</Region>  
    <PostalCode>97403</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
<Customer CustomerID="HUNGC">  
  <CompanyName>Hungry Coyote Import Store</CompanyName>  
  <ContactName>Yoshi Latimer</ContactName>  
  <ContactTitle>Sales Representative</ContactTitle>  
  <Phone>(503) 555-6874</Phone>  
  <Fax>(503) 555-2376</Fax>  
  <FullAddress>  
    <Address>City Center Plaza 516 Main St.</Address>  
    <City>Elgin</City>  
    <Region>OR</Region>  
    <PostalCode>97827</PostalCode>  
    <Country>USA</Country>  
  </FullAddress>  
  <Orders />  
</Customer>  
. . .  
```  
  
## <a name="example"></a><span data-ttu-id="f6ef3-120">Örnek</span><span class="sxs-lookup"><span data-stu-id="f6ef3-120">Example</span></span>  
 <span data-ttu-id="f6ef3-121">Bu örnekte, bazı öğelerin yeniden adlandırır ve bazı öznitelikler öğelerine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-121">This example renames some elements and converts some attributes to elements.</span></span>  
  
 <span data-ttu-id="f6ef3-122">Kod çağrıları `ConvertAddress`, listesini döndürür <xref:System.Xml.Linq.XElement> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-122">The code calls `ConvertAddress`, which returns a list of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="f6ef3-123">Yöntemin bağımsız değişkeni belirleyen bir sorgudur `Address` karmaşık bir öğe burada `Type` özniteliği değerine sahip `"Shipping"`.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-123">The argument to the method is a query that determines the `Address` complex element where the `Type` attribute has a value of `"Shipping"`.</span></span>  
  
 <span data-ttu-id="f6ef3-124">Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: tipik satın alma siparişi (LINQ-XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f6ef3-124">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Function ConvertAddress(ByVal add As XElement) As IEnumerable(Of XElement)  
    Dim fragment = New List(Of XElement)  
    fragment.Add(<NAME><%= add.<Name>.Value %></NAME>)  
    fragment.Add(<STREET><%= add.<Street>.Value %></STREET>)  
    fragment.Add(<CITY><%= add.<City>.Value %></CITY>)  
    fragment.Add(<ST><%= add.<State>.Value %></ST>)  
    fragment.Add(<POSTALCODE><%= add.<Zip>.Value %></POSTALCODE>)  
    fragment.Add(<COUNTRY><%= add.<Country>.Value %></COUNTRY>)  
    Return fragment  
End Function  
  
Sub Main()  
    Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
    Dim newPo As XElement = _  
        <PO>  
            <ID><%= po.@PurchaseOrderNumber %></ID>  
            <DATE><%= CDate(po.@OrderDate) %></DATE>  
            <%= _  
                ConvertAddress( _  
                (From el In po.<Address> _  
                Where el.@Type = "Shipping" _  
                Select el) _  
                .First() _  
                ) _  
            %>  
        </PO>  
    Console.WriteLine(newPo)  
End Sub  
```  
  
 <span data-ttu-id="f6ef3-125">Bu kod aşağıdaki çıktıyı üretir:</span><span class="sxs-lookup"><span data-stu-id="f6ef3-125">This code produces the following output:</span></span>  
  
```xml  
<PO>  
  <ID>99503</ID>  
  <DATE>1999-10-20T00:00:00</DATE>  
  <NAME>Ellen Adams</NAME>  
  <STREET>123 Maple Street</STREET>  
  <CITY>Mill Valley</CITY>  
  <ST>CA</ST>  
  <POSTALCODE>10999</POSTALCODE>  
  <COUNTRY>USA</COUNTRY>  
</PO>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6ef3-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f6ef3-126">See Also</span></span>  
 [<span data-ttu-id="f6ef3-127">Projeksiyonlar ve dönüştürmeler (LINQ-XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6ef3-127">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)