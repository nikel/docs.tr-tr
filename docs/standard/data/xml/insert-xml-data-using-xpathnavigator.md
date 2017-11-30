---
title: XML XPathNavigator kullanarak verileri ekleme
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 2ed8c28b-b88d-4be7-9c87-92df01f0821f
caps.latest.revision: "2"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 34151590a14c48c0a84677f2d7cae662291edf40
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="insert-xml-data-using-xpathnavigator"></a><span data-ttu-id="6bf90-102">XML XPathNavigator kullanarak verileri ekleme</span><span class="sxs-lookup"><span data-stu-id="6bf90-102">Insert XML Data using XPathNavigator</span></span>
<span data-ttu-id="6bf90-103"><xref:System.Xml.XPath.XPathNavigator> Sınıfı XML belgesinde eş, alt ve öznitelik düğümleri eklemek için kullanılan yöntemler kümesi sağlar.</span><span class="sxs-lookup"><span data-stu-id="6bf90-103">The <xref:System.Xml.XPath.XPathNavigator> class provides a set of methods used to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="6bf90-104">Bu yöntemleri kullanmak için <xref:System.Xml.XPath.XPathNavigator> nesnesi olmalıdır düzenlenebilir, diğer bir deyişle, kendi <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> olmalıdır `true`.</span><span class="sxs-lookup"><span data-stu-id="6bf90-104">In order to use these methods, the <xref:System.Xml.XPath.XPathNavigator> object must be editable, that is, its <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property must be `true`.</span></span>  
  
 <span data-ttu-id="6bf90-105"><xref:System.Xml.XPath.XPathNavigator>tarafından oluşturulan bir XML belgesi düzenleyebilirsiniz nesneleri <xref:System.Xml.XmlDocument.CreateNavigator%2A> yöntemi <xref:System.Xml.XmlDocument> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6bf90-105"><xref:System.Xml.XPath.XPathNavigator> objects that can edit an XML document are created by the <xref:System.Xml.XmlDocument.CreateNavigator%2A> method of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="6bf90-106"><xref:System.Xml.XPath.XPathNavigator>tarafından oluşturulan nesneler <xref:System.Xml.XPath.XPathDocument> sınıfı salt okunur ve herhangi bir düzenleme yöntemlerini kullanmayı dener bir <xref:System.Xml.XPath.XPathNavigator> tarafından oluşturulan nesne bir <xref:System.Xml.XPath.XPathDocument> nesne sonuçlanıyor bir <xref:System.NotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="6bf90-106"><xref:System.Xml.XPath.XPathNavigator> objects created by the <xref:System.Xml.XPath.XPathDocument> class are read-only and any attempt to use the editing methods of an <xref:System.Xml.XPath.XPathNavigator> object created by an <xref:System.Xml.XPath.XPathDocument> object results in a <xref:System.NotSupportedException>.</span></span>  
  
 <span data-ttu-id="6bf90-107">Düzenlenebilir oluşturma hakkında daha fazla bilgi için <xref:System.Xml.XPath.XPathNavigator> nesneleri bkz [XPathDocument ve XmlDocument kullanarak XML veri okunurken](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span><span class="sxs-lookup"><span data-stu-id="6bf90-107">For more information about creating editable <xref:System.Xml.XPath.XPathNavigator> objects, see [Reading XML Data using XPathDocument and XmlDocument](../../../../docs/standard/data/xml/reading-xml-data-using-xpathdocument-and-xmldocument.md).</span></span>  
  
## <a name="inserting-nodes"></a><span data-ttu-id="6bf90-108">Düğümler ekleme</span><span class="sxs-lookup"><span data-stu-id="6bf90-108">Inserting Nodes</span></span>  
 <span data-ttu-id="6bf90-109"><xref:System.Xml.XPath.XPathNavigator> Sınıfı XML belgesinde eş, alt ve öznitelik düğümleri eklemek için yöntemler sağlar.</span><span class="sxs-lookup"><span data-stu-id="6bf90-109">The <xref:System.Xml.XPath.XPathNavigator> class provides methods to insert sibling, child, and attribute nodes in an XML document.</span></span> <span data-ttu-id="6bf90-110">Bu yöntem, geçerli konumu ile ilgili olarak farklı konumlarda düğümleri ve öznitelikler eklemek izin bir <xref:System.Xml.XPath.XPathNavigator> nesne ve aşağıdaki bölümlerde açıklanmıştır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-110">These methods allow you to insert nodes and attributes in different locations in relation to the current position of an <xref:System.Xml.XPath.XPathNavigator> object and are described in the following sections.</span></span>  
  
### <a name="inserting-sibling-nodes"></a><span data-ttu-id="6bf90-111">Eşdüzey düğümleri ekleme</span><span class="sxs-lookup"><span data-stu-id="6bf90-111">Inserting Sibling Nodes</span></span>  
 <span data-ttu-id="6bf90-112"><xref:System.Xml.XPath.XPathNavigator> Sınıfı eşdüzey düğümleri eklemek için aşağıdaki yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="6bf90-112">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert sibling nodes.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A>  
  
 <span data-ttu-id="6bf90-113">Bu yöntemler önce ve sonra düğümün eşdüzey düğümleri Ekle bir <xref:System.Xml.XPath.XPathNavigator> nesnesi üzerinde şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-113">These methods insert sibling nodes before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="6bf90-114"><xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> Ve <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> yöntemlerini aşırı yüklenmiş olan iş ve kabul bir `string`, <xref:System.Xml.XmlReader> nesnesi veya <xref:System.Xml.XPath.XPathNavigator> parametre olarak eklemek için eşdüzey düğüm içeren nesne.</span><span class="sxs-lookup"><span data-stu-id="6bf90-114">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> methods are overloaded and accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the sibling node to add as parameters.</span></span> <span data-ttu-id="6bf90-115">Her iki yöntem aynı zamanda sonuç bir <xref:System.Xml.XmlWriter> eşdüzey düğümleri eklemek için kullanılan nesne.</span><span class="sxs-lookup"><span data-stu-id="6bf90-115">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert sibling nodes.</span></span>  
  
 <span data-ttu-id="6bf90-116"><xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> Ve <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> yöntemleri eklemek tek Eşdüzey Düğüm önce ve sonra düğüm bir <xref:System.Xml.XPath.XPathNavigator> nesne, ad alanı öneki, yerel ad, ad alanı URI'si ve parametre olarak belirtilen değeri kullanarak şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-116">The <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods insert a single sibling node before and after the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="6bf90-117">Aşağıdaki örnekte yeni bir `pages` öğesine önce eklenir `price` ilk alt öğesi `book` öğesinde `contosoBooks.xml` dosya.</span><span class="sxs-lookup"><span data-stu-id="6bf90-117">In the following example a new `pages` element is inserted before the `price` child element of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#19](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#19)]
 [!code-csharp[XPathNavigatorMethods#19](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#19)]
 [!code-vb[XPathNavigatorMethods#19](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#19)]  
  
 <span data-ttu-id="6bf90-118">Örnek alır `contosoBooks.xml` dosyayı bir girdi olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-118">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="6bf90-119">Hakkında daha fazla bilgi için <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> ve <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> yöntemleri bkz <xref:System.Xml.XPath.XPathNavigator> sınıf başvurusu belgelerinde.</span><span class="sxs-lookup"><span data-stu-id="6bf90-119">For more information about the <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertElementAfter%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertElementBefore%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-child-nodes"></a><span data-ttu-id="6bf90-120">Alt düğümler ekleme</span><span class="sxs-lookup"><span data-stu-id="6bf90-120">Inserting Child Nodes</span></span>  
 <span data-ttu-id="6bf90-121"><xref:System.Xml.XPath.XPathNavigator> Sınıfı, alt düğümleri eklemek için aşağıdaki yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="6bf90-121">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert child nodes.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A>  
  
 <span data-ttu-id="6bf90-122">Bu yöntemler ekleme ve alt düğümleri sonuna ve düğümün alt öğelerinin listesi başlangıcını başına bir <xref:System.Xml.XPath.XPathNavigator> nesnesi üzerinde şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-122">These methods append and prepend child nodes to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="6bf90-123">"Eşdüzey düğümleri ekleme" bölümündeki yöntemleri gibi <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> ve <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> yöntemlerini kabul edecek bir `string`, <xref:System.Xml.XmlReader> nesnesi veya <xref:System.Xml.XPath.XPathNavigator> parametre olarak eklemek için alt düğümü içeren bir nesne.</span><span class="sxs-lookup"><span data-stu-id="6bf90-123">Like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods accept a `string`, <xref:System.Xml.XmlReader> object, or <xref:System.Xml.XPath.XPathNavigator> object containing the child node to add as parameters.</span></span> <span data-ttu-id="6bf90-124">Her iki yöntem aynı zamanda sonuç bir <xref:System.Xml.XmlWriter> alt düğümleri eklemek için kullanılan nesne.</span><span class="sxs-lookup"><span data-stu-id="6bf90-124">Both methods also return an <xref:System.Xml.XmlWriter> object used to insert child nodes.</span></span>  
  
 <span data-ttu-id="6bf90-125">Ayrıca, "Eşdüzey düğümleri ekleme" bölümündeki yöntemleri ister <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> ve <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> yöntemleri sonuna ve düğümün alt öğelerinin listesi başına tek alt düğümü Ekle bir <xref:System.Xml.XPath.XPathNavigator> nesnesi, kullanarak şu anda konumlandırılır ad alanı öneki, yerel ad, ad alanı URI'si ve parametre olarak belirtilen değeri.</span><span class="sxs-lookup"><span data-stu-id="6bf90-125">Also like the methods in the "Inserting Sibling Nodes" section, the <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods insert a single child node to the end of and the beginning of the list of child nodes of the node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span>  
  
 <span data-ttu-id="6bf90-126">Aşağıdaki örnekte, yeni bir `pages` alt öğesi ilk alt öğelerinin listesine eklenen `book` öğesinde `contosoBooks.xml` dosya.</span><span class="sxs-lookup"><span data-stu-id="6bf90-126">In the following example, a new `pages` child element is appended to the list of child elements of the first `book` element in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#2](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#2)]
 [!code-csharp[XPathNavigatorMethods#2](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#2)]
 [!code-vb[XPathNavigatorMethods#2](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#2)]  
  
 <span data-ttu-id="6bf90-127">Örnek alır `contosoBooks.xml` dosyayı bir girdi olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-127">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="6bf90-128">Hakkında daha fazla bilgi için <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> ve <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> yöntemleri bkz <xref:System.Xml.XPath.XPathNavigator> sınıf başvurusu belgelerinde.</span><span class="sxs-lookup"><span data-stu-id="6bf90-128">For more information about the <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChildElement%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChildElement%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
### <a name="inserting-attribute-nodes"></a><span data-ttu-id="6bf90-129">Öznitelik düğümleri ekleme</span><span class="sxs-lookup"><span data-stu-id="6bf90-129">Inserting Attribute Nodes</span></span>  
 <span data-ttu-id="6bf90-130"><xref:System.Xml.XPath.XPathNavigator> Sınıfı, öznitelik düğümleri eklemek için aşağıdaki yöntemleri sağlar.</span><span class="sxs-lookup"><span data-stu-id="6bf90-130">The <xref:System.Xml.XPath.XPathNavigator> class provides the following methods to insert attribute nodes.</span></span>  
  
-   <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A>  
  
-   <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A>  
  
 <span data-ttu-id="6bf90-131">Bu yöntemler öğesi düğümde öznitelik düğümleri Ekle bir <xref:System.Xml.XPath.XPathNavigator> nesnesi üzerinde şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-131">These methods insert attribute nodes on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="6bf90-132"><xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> Yöntemi oluşturur öznitelik düğümü öğesi düğümde bir <xref:System.Xml.XPath.XPathNavigator> nesne, ad alanı öneki, yerel ad, ad alanı URI'si ve parametre olarak belirtilen değeri kullanarak şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-132">The <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> method creates an attribute node on the element node an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on using the namespace prefix, local name, namespace URI, and value specified as parameters.</span></span> <span data-ttu-id="6bf90-133"><xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> Yöntemi döndürür bir <xref:System.Xml.XmlWriter> öznitelik düğümleri eklemek için kullanılan nesne.</span><span class="sxs-lookup"><span data-stu-id="6bf90-133">The <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method returns an <xref:System.Xml.XmlWriter> object used to insert attribute nodes.</span></span>  
  
 <span data-ttu-id="6bf90-134">Aşağıdaki örnekte, yeni `discount` ve `currency` öznitelikleri üzerinde oluşturulan `price` ilk alt öğesi `book` öğesinde `contosoBooks.xml` kullanarak dosya <xref:System.Xml.XmlWriter> döndürülen nesne <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> yöntem.</span><span class="sxs-lookup"><span data-stu-id="6bf90-134">In the following example, new `discount` and `currency` attributes are created on the `price` child element of the first `book` element in the `contosoBooks.xml` file using the <xref:System.Xml.XmlWriter> object returned from the <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> method.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#8](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#8)]
 [!code-csharp[XPathNavigatorMethods#8](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#8)]
 [!code-vb[XPathNavigatorMethods#8](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#8)]  
  
 <span data-ttu-id="6bf90-135">Örnek alır `contosoBooks.xml` dosyayı bir girdi olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-135">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="6bf90-136">Hakkında daha fazla bilgi için <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> ve <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> yöntemleri bkz <xref:System.Xml.XPath.XPathNavigator> sınıf başvurusu belgelerinde.</span><span class="sxs-lookup"><span data-stu-id="6bf90-136">For more information about the <xref:System.Xml.XPath.XPathNavigator.CreateAttribute%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods, see the <xref:System.Xml.XPath.XPathNavigator> class reference documentation.</span></span>  
  
## <a name="copying-nodes"></a><span data-ttu-id="6bf90-137">Düğümleri kopyalama</span><span class="sxs-lookup"><span data-stu-id="6bf90-137">Copying Nodes</span></span>  
 <span data-ttu-id="6bf90-138">Bazı durumlarda, bir XML belgesi başka bir XML belgesinden içeriğiyle doldurmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="6bf90-138">In certain cases you may want to populate an XML document with the contents from another XML document.</span></span> <span data-ttu-id="6bf90-139">Her iki <xref:System.Xml.XPath.XPathNavigator> sınıfı ve <xref:System.Xml.XmlWriter> sınıfı düğümlerine Kopyala bir <xref:System.Xml.XmlDocument> varolan bir nesne <xref:System.Xml.XmlReader> nesne veya <xref:System.Xml.XPath.XPathNavigator> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-139">Both the <xref:System.Xml.XPath.XPathNavigator> class and the <xref:System.Xml.XmlWriter> class can copy nodes to an <xref:System.Xml.XmlDocument> object from an existing <xref:System.Xml.XmlReader> object or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="6bf90-140"><xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> Ve <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> yöntemlerinin <xref:System.Xml.XPath.XPathNavigator> tümüne sahip kabul edebilir aşırı sınıf bir <xref:System.Xml.XPath.XPathNavigator> nesnesi veya bir <xref:System.Xml.XmlReader> nesnesini parametre olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-140">The <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A> and <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class all have overloads that can accept an <xref:System.Xml.XPath.XPathNavigator> object or an <xref:System.Xml.XmlReader> object as a parameter.</span></span>  
  
 <span data-ttu-id="6bf90-141"><xref:System.Xml.XmlWriter.WriteNode%2A> Yöntemi <xref:System.Xml.XmlWriter> sınıfına sahip kabul edebilir aşırı bir <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader>, veya <xref:System.Xml.XPath.XPathNavigator> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-141">The <xref:System.Xml.XmlWriter.WriteNode%2A> method of the <xref:System.Xml.XmlWriter> class has overloads that can accept an <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlReader>, or <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
 <span data-ttu-id="6bf90-142">Aşağıdaki örnek, tüm kopyalar `book` bir belgeden öğelerine.</span><span class="sxs-lookup"><span data-stu-id="6bf90-142">The following example copies all the `book` elements from one document to another.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", String.Empty)  
  
Dim newBooks As XPathDocument = New XPathDocument("newBooks.xml")  
Dim newBooksNavigator As XPathNavigator = newBooks.CreateNavigator()  
  
Dim nav As XPathNavigator  
For Each nav in newBooksNavigator.SelectDescendants("book", "", false)  
    navigator.AppendChild(nav)  
Next  
  
document.Save("newBooks.xml");  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", String.Empty);  
  
XPathDocument newBooks = new XPathDocument("newBooks.xml");  
XPathNavigator newBooksNavigator = newBooks.CreateNavigator();  
  
foreach (XPathNavigator nav in newBooksNavigator.SelectDescendants("book", "", false))  
{  
    navigator.AppendChild(nav);  
}  
  
document.Save("newBooks.xml");  
```  
  
## <a name="inserting-values"></a><span data-ttu-id="6bf90-143">Değerleri ekleniyor</span><span class="sxs-lookup"><span data-stu-id="6bf90-143">Inserting Values</span></span>  
 <span data-ttu-id="6bf90-144"><xref:System.Xml.XPath.XPathNavigator> SAX <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> ve <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> bir düğüm için değerler eklemek için yöntemleri bir <xref:System.Xml.XmlDocument> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-144">The <xref:System.Xml.XPath.XPathNavigator> class provides the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> and <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> methods to insert values for a node into an <xref:System.Xml.XmlDocument> object.</span></span>  
  
### <a name="inserting-untyped-values"></a><span data-ttu-id="6bf90-145">Türsüz değerleri ekleniyor</span><span class="sxs-lookup"><span data-stu-id="6bf90-145">Inserting Untyped Values</span></span>  
 <span data-ttu-id="6bf90-146"><xref:System.Xml.XPath.XPathNavigator.SetValue%2A> Yöntemi yalnızca ekler türsüz `string` değeri düğümün değeri olarak bir parametre olarak geçirilen <xref:System.Xml.XPath.XPathNavigator> nesnesi üzerinde şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-146">The <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method simply inserts the untyped `string` value passed as a parameter as the value of the node the <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span> <span data-ttu-id="6bf90-147">Değer, herhangi bir tür olmadan veya şema bilgileri kullanılabiliyorsa, yeni değer düğüm türüne göre geçerli olduğunu doğrulama olmadan eklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-147">The value is inserted without any type or without verifying that the new value is valid according to the type of the node if schema information is available.</span></span>  
  
 <span data-ttu-id="6bf90-148">Aşağıdaki örnekte, <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> yöntemi tüm güncelleştirmek için kullanılan `price` öğelerinde `contosoBooks.xml` dosya.</span><span class="sxs-lookup"><span data-stu-id="6bf90-148">In the following example, the <xref:System.Xml.XPath.XPathNavigator.SetValue%2A> method is used to update all `price` elements in the `contosoBooks.xml` file.</span></span>  
  
 [!code-cpp[XPathNavigatorMethods#47](../../../../samples/snippets/cpp/VS_Snippets_Data/XPathNavigatorMethods/CPP/xpathnavigatormethods.cpp#47)]
 [!code-csharp[XPathNavigatorMethods#47](../../../../samples/snippets/csharp/VS_Snippets_Data/XPathNavigatorMethods/CS/xpathnavigatormethods.cs#47)]
 [!code-vb[XPathNavigatorMethods#47](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XPathNavigatorMethods/VB/xpathnavigatormethods.vb#47)]  
  
 <span data-ttu-id="6bf90-149">Örnek alır `contosoBooks.xml` dosyayı bir girdi olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-149">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
### <a name="inserting-typed-values"></a><span data-ttu-id="6bf90-150">Girilen değerleri ekleniyor</span><span class="sxs-lookup"><span data-stu-id="6bf90-150">Inserting Typed Values</span></span>  
 <span data-ttu-id="6bf90-151">Bir düğüm türü bir basit W3C XML Şeması olduğunda türü, tarafından eklenen yeni değer <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> değer ayarlamadan önce yöntemi basit türe ilişkin modelleri karşı denetlenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-151">When the type of a node is a W3C XML Schema simple type, the new value inserted by the <xref:System.Xml.XPath.XPathNavigator.SetTypedValue%2A> method is checked against the facets of the simple type before the value is set.</span></span> <span data-ttu-id="6bf90-152">Yeni değer düğüm türüne göre geçerli değilse (örneğin, bir değeri ayarlamak `-1` türü olan bir öğe üzerinde `xs:positiveInteger`), bir özel durum oluşur.</span><span class="sxs-lookup"><span data-stu-id="6bf90-152">If the new value is not valid according to the type of the node (for example, setting a value of `-1` on an element whose type is `xs:positiveInteger`), it results in an exception.</span></span>  
  
 <span data-ttu-id="6bf90-153">Aşağıdaki örnek değerini değiştirme girişiminde `price` ilk öğesinin `book` öğesinde `contosoBooks.xml` dosyasını bir <xref:System.DateTime> değeri.</span><span class="sxs-lookup"><span data-stu-id="6bf90-153">The following example attempts to change the value of the `price` element of the first `book` element in the `contosoBooks.xml` file to a <xref:System.DateTime> value.</span></span> <span data-ttu-id="6bf90-154">XML şema türü olduğundan `price` öğesi olarak tanımlanır `xs:decimal` içinde `contosoBooks.xsd` dosyaları, bu sonuçları bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="6bf90-154">Because the XML Schema type of the `price` element is defined as `xs:decimal` in the `contosoBooks.xsd` files, this results in an exception.</span></span>  
  
```vb  
Dim settings As XmlReaderSettings = New XmlReaderSettings()  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd")  
settings.ValidationType = ValidationType.Schema  
  
Dim reader As XmlReader = XmlReader.Create("contosoBooks.xml", settings)  
  
Dim document As XmlDocument = New XmlDocument()  
document.Load(reader)  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books")  
navigator.MoveToChild("book", "http://www.contoso.com/books")  
navigator.MoveToChild("price", "http://www.contoso.com/books")  
  
navigator.SetTypedValue(DateTime.Now)  
```  
  
```csharp  
XmlReaderSettings settings = new XmlReaderSettings();  
settings.Schemas.Add("http://www.contoso.com/books", "contosoBooks.xsd");  
settings.ValidationType = ValidationType.Schema;  
  
XmlReader reader = XmlReader.Create("contosoBooks.xml", settings);  
  
XmlDocument document = new XmlDocument();  
document.Load(reader);  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.MoveToChild("bookstore", "http://www.contoso.com/books");  
navigator.MoveToChild("book", "http://www.contoso.com/books");  
navigator.MoveToChild("price", "http://www.contoso.com/books");  
  
navigator.SetTypedValue(DateTime.Now);  
```  
  
 <span data-ttu-id="6bf90-155">Örnek alır `contosoBooks.xml` dosyayı bir girdi olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-155">The example takes the `contosoBooks.xml` file as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#2](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xml#2)]  
  
 <span data-ttu-id="6bf90-156">Bu örnek ayrıca alır `contosoBooks.xsd` bir girdi olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-156">The example also takes the `contosoBooks.xsd` as an input.</span></span>  
  
 [!code-xml[XPathXMLExamples#3](../../../../samples/snippets/xml/VS_Snippets_Data/XPathXMLExamples/XML/contosoBooks.xsd#3)]  
  
## <a name="the-innerxml-and-outerxml-properties"></a><span data-ttu-id="6bf90-157">InnerXml ve OuterXml özellikleri</span><span class="sxs-lookup"><span data-stu-id="6bf90-157">The InnerXml and OuterXml Properties</span></span>  
 <span data-ttu-id="6bf90-158"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> Ve <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> özelliklerini <xref:System.Xml.XPath.XPathNavigator> sınıfı düğümlerin XML biçimlendirmesini değiştirme bir <xref:System.Xml.XPath.XPathNavigator> nesnesi üzerinde şu anda konumlandırılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-158">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties of the <xref:System.Xml.XPath.XPathNavigator> class change the XML markup of the nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on.</span></span>  
  
 <span data-ttu-id="6bf90-159"><xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> Özellik alt düğümlerin XML biçimlendirme değişiklikleri bir <xref:System.Xml.XPath.XPathNavigator> nesne şu anda konumlandırılır üzerinde verilen XML ayrıştırılmış içeriğini `string`.</span><span class="sxs-lookup"><span data-stu-id="6bf90-159">The <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on with the parsed contents of the given XML `string`.</span></span> <span data-ttu-id="6bf90-160">Benzer şekilde, <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> özellik alt düğümlerin XML biçimlendirme değişiklikleri bir <xref:System.Xml.XPath.XPathNavigator> nesne şu anda konumlandırılır üzerinde geçerli düğüm yanı sıra.</span><span class="sxs-lookup"><span data-stu-id="6bf90-160">Similarly, the <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> property changes the XML markup of the child nodes an <xref:System.Xml.XPath.XPathNavigator> object is currently positioned on as well as the current node itself.</span></span>  
  
 <span data-ttu-id="6bf90-161">Bu konuda, açıklanan yöntemlerden yanı sıra <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> ve <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> özellikleri, bir XML belgesi düğümleri ve değerler eklemek için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-161">In addition to the methods described in this topic, the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties can be used to insert nodes and values in an XML document.</span></span> <span data-ttu-id="6bf90-162">Kullanma hakkında daha fazla bilgi için <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> ve <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> düğümleri ve değerler eklemek için özellikleri görmek [XML XPathNavigator kullanarak verileri değiştirme](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) konu.</span><span class="sxs-lookup"><span data-stu-id="6bf90-162">For more information about using the <xref:System.Xml.XPath.XPathNavigator.InnerXml%2A> and <xref:System.Xml.XPath.XPathNavigator.OuterXml%2A> properties to insert nodes and values, see the [Modify XML Data using XPathNavigator](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md) topic.</span></span>  
  
## <a name="namespace-and-xmllang-conflicts"></a><span data-ttu-id="6bf90-163">Namespace ve XML: lang çakışıyor</span><span class="sxs-lookup"><span data-stu-id="6bf90-163">Namespace and xml:lang Conflicts</span></span>  
 <span data-ttu-id="6bf90-164">İlgili ad alanı kapsamını belirli çakışma ve `xml:lang` bildirimleri XML verileri kullanarak eklerken oluşabilir <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> ve <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> yöntemlerinin <xref:System.Xml.XPath.XPathNavigator> elesınıfı<xref:System.Xml.XmlReader>parametre olarak nesneleri.</span><span class="sxs-lookup"><span data-stu-id="6bf90-164">Certain conflicts related to the scope of namespace and `xml:lang` declarations can occur when inserting XML data using the <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A> and <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class that take <xref:System.Xml.XmlReader> objects as parameters.</span></span>  
  
 <span data-ttu-id="6bf90-165">Olası ad alanı çakışmalarını verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-165">The following are the possible namespace conflicts.</span></span>  
  
-   <span data-ttu-id="6bf90-166">Bir ad alanı içinde-kapsamı içinde ise <xref:System.Xml.XmlReader> nesnenin bağlamı, burada önek ad alanı URI eşlemesi içinde değil <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlamı, yeni bir ad alanı bildiriminin yeni eklenen düğümüne eklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-166">If there is a namespace in-scope within the <xref:System.Xml.XmlReader> object's context, where the prefix to namespace URI mapping is not in the <xref:System.Xml.XPath.XPathNavigator> object's context, a new namespace declaration is added to the newly inserted node.</span></span>  
  
-   <span data-ttu-id="6bf90-167">Aynı ad alanı URI'si kapsam içinde ise öğesinde hem de <xref:System.Xml.XmlReader> nesnenin bağlamı ve <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlamı, ancak her iki bağlamlarda eşlenmiş farklı bir önek vardır, yeni bir ad alanı bildiriminin önekiyle yeni eklenen düğümüne eklenir ve ad alanı URI'si alınan <xref:System.Xml.XmlReader> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-167">If the same namespace URI is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different prefix mapped to it in both contexts, a new namespace declaration is added to the newly inserted node, with the prefix and namespace URI taken from the <xref:System.Xml.XmlReader> object.</span></span>  
  
-   <span data-ttu-id="6bf90-168">Aynı ad alanı öneki kapsam içinde ise öğesinde hem de <xref:System.Xml.XmlReader> nesnenin bağlamı ve <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlamı, ancak sahip farklı bir ad alanı URI eşlenmesi için her iki bağlamlarda yeni bir ad alanı bildiriminin yeni eklenen düğümüne eklenir, Bu ad alanı URI'si alınan önekiyle yeniden bildirir <xref:System.Xml.XmlReader> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-168">If the same namespace prefix is in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but has a different namespace URI mapped to it in both contexts, a new namespace declaration is added to the newly inserted node which re-declares that prefix with the namespace URI taken from <xref:System.Xml.XmlReader> object.</span></span>  
  
-   <span data-ttu-id="6bf90-169">Hem de ad alanı URI'si yanı sıra önek <xref:System.Xml.XmlReader> nesnenin bağlamı ve <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlam aynıdır, yeni bir ad alanı bildiriminin yeni eklenen düğümüne eklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-169">If the prefix as well as the namespace URI in both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context is the same, no new namespace declaration is added to the newly inserted node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bf90-170">Yukarıdaki açıklamayı boş olan ad alanı bildirimleri için de geçerlidir. `string` bir önek (örneğin, varsayılan ad alanı bildiriminin) olarak.</span><span class="sxs-lookup"><span data-stu-id="6bf90-170">The description above also applies to namespace declarations with the empty `string` as a prefix (for example, the default namespace declaration).</span></span>  
  
 <span data-ttu-id="6bf90-171">Olası şunlardır `xml:lang` çakışıyor.</span><span class="sxs-lookup"><span data-stu-id="6bf90-171">The following are the possible `xml:lang` conflicts.</span></span>  
  
-   <span data-ttu-id="6bf90-172">Varsa bir `xml:lang` içinde kapsamında özniteliği <xref:System.Xml.XmlReader> nesnenin bağlam de <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlamı bir `xml:lang` öznitelik değeri, gelen alınır <xref:System.Xml.XmlReader> nesne yeni eklenen düğümüne eklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-172">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XmlReader> object's context but not in the <xref:System.Xml.XPath.XPathNavigator> object's context, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
-   <span data-ttu-id="6bf90-173">Varsa bir `xml:lang` içinde-kapsamında hem öznitelik <xref:System.Xml.XmlReader> nesnenin bağlamı ve <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlamı, ancak her farklı bir değere sahip bir `xml:lang` öznitelik değeri, gelen alınır <xref:System.Xml.XmlReader> nesne eklenir Yeni eklenen düğüm.</span><span class="sxs-lookup"><span data-stu-id="6bf90-173">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each has a different value, an `xml:lang` attribute whose value is taken from the <xref:System.Xml.XmlReader> object is added to the newly inserted node.</span></span>  
  
-   <span data-ttu-id="6bf90-174">Varsa bir `xml:lang` içinde-kapsamında hem öznitelik <xref:System.Xml.XmlReader> nesnenin bağlamı ve <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlamı, ancak her yeni aynı değere sahip `xml:lang` özniteliği yeni eklenen düğümüne eklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-174">If there is an `xml:lang` attribute in-scope within both the <xref:System.Xml.XmlReader> object's context and the <xref:System.Xml.XPath.XPathNavigator> object's context, but each with the same value, no new `xml:lang` attribute is added on the newly inserted node.</span></span>  
  
-   <span data-ttu-id="6bf90-175">Varsa bir `xml:lang` içinde kapsamında özniteliği <xref:System.Xml.XPath.XPathNavigator> nesnenin bağlam ancak hiçbiri mevcut <xref:System.Xml.XmlReader> nesnenin bağlamı, Hayır `xml:lang` özniteliği yeni eklenen düğümüne eklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-175">If there is an `xml:lang` attribute in-scope within the <xref:System.Xml.XPath.XPathNavigator> object's context, but none existing in the <xref:System.Xml.XmlReader> object's context, no `xml:lang` attribute is added to the newly inserted node.</span></span>  
  
## <a name="inserting-nodes-with-xmlwriter"></a><span data-ttu-id="6bf90-176">XmlWriter ile düğüm ekleme</span><span class="sxs-lookup"><span data-stu-id="6bf90-176">Inserting Nodes with XmlWriter</span></span>  
 <span data-ttu-id="6bf90-177">"Düğümler ve değerler ekleme" bölümünde açıklanan eşdüzey, alt ve öznitelik düğümleri eklemek için kullanılan yöntemleri aşırı yüklendi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-177">The methods used to insert sibling, child and attribute nodes described in the "Inserting Nodes and Values" section are overloaded.</span></span> <span data-ttu-id="6bf90-178"><xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> Ve <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> yöntemlerinin <xref:System.Xml.XPath.XPathNavigator> sınıfının return bir <xref:System.Xml.XmlWriter> düğümlerini eklemek için kullanılan nesne.</span><span class="sxs-lookup"><span data-stu-id="6bf90-178">The <xref:System.Xml.XPath.XPathNavigator.InsertAfter%2A>, <xref:System.Xml.XPath.XPathNavigator.InsertBefore%2A>, <xref:System.Xml.XPath.XPathNavigator.AppendChild%2A>, <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> and <xref:System.Xml.XPath.XPathNavigator.CreateAttributes%2A> methods of the <xref:System.Xml.XPath.XPathNavigator> class return an <xref:System.Xml.XmlWriter> object used to insert nodes.</span></span>  
  
### <a name="unsupported-xmlwriter-methods"></a><span data-ttu-id="6bf90-179">Desteklenmeyen XmlWriter yöntemleri</span><span class="sxs-lookup"><span data-stu-id="6bf90-179">Unsupported XmlWriter Methods</span></span>  
 <span data-ttu-id="6bf90-180">Tüm bilgileri kullanarak bir XML belgesi yazmak için kullanılan yöntemleri <xref:System.Xml.XmlWriter> sınıfı tarafından desteklenen <xref:System.Xml.XPath.XPathNavigator> XPath veri modeli ve belge nesne modeli (DOM) arasındaki fark nedeniyle sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6bf90-180">Not all of the methods used for writing information to an XML document using the <xref:System.Xml.XmlWriter> class are supported by the <xref:System.Xml.XPath.XPathNavigator> class due to difference between the XPath data model and the Document Object Model (DOM).</span></span>  
  
 <span data-ttu-id="6bf90-181">Aşağıdaki tabloda açıklanmaktadır <xref:System.Xml.XmlWriter> sınıfı tarafından desteklenmeyen yöntemlerinin <xref:System.Xml.XPath.XPathNavigator> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6bf90-181">The following table describes the <xref:System.Xml.XmlWriter> class methods not supported by the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>  
  
|<span data-ttu-id="6bf90-182">Yöntem</span><span class="sxs-lookup"><span data-stu-id="6bf90-182">Method</span></span>|<span data-ttu-id="6bf90-183">Açıklama</span><span class="sxs-lookup"><span data-stu-id="6bf90-183">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.XmlWriter.WriteEntityRef%2A>|<span data-ttu-id="6bf90-184">Atan bir <xref:System.NotSupportedException> özel durum.</span><span class="sxs-lookup"><span data-stu-id="6bf90-184">Throws a <xref:System.NotSupportedException> exception.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteDocType%2A>|<span data-ttu-id="6bf90-185">Atar ve kök düzeyiyle göz ardı bir <xref:System.NotSupportedException> XML belgesi diğer düzeyinde çağrıldıklarında özel durum.</span><span class="sxs-lookup"><span data-stu-id="6bf90-185">Ignored at the root level and throws a <xref:System.NotSupportedException> exception if called at any other level in the XML document.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCData%2A>|<span data-ttu-id="6bf90-186">Çağrısı olarak kabul <xref:System.Xml.XmlWriter.WriteString%2A> eşdeğer karakter veya karakter yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-186">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteCharEntity%2A>|<span data-ttu-id="6bf90-187">Çağrısı olarak kabul <xref:System.Xml.XmlWriter.WriteString%2A> eşdeğer karakter veya karakter yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-187">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
|<xref:System.Xml.XmlWriter.WriteSurrogateCharEntity%2A>|<span data-ttu-id="6bf90-188">Çağrısı olarak kabul <xref:System.Xml.XmlWriter.WriteString%2A> eşdeğer karakter veya karakter yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6bf90-188">Treated as a call to the <xref:System.Xml.XmlWriter.WriteString%2A> method for the equivalent character or characters.</span></span>|  
  
 <span data-ttu-id="6bf90-189">Hakkında daha fazla bilgi için <xref:System.Xml.XmlWriter> sınıfı için bkz: <xref:System.Xml.XmlWriter> sınıf başvurusu belgelerinde.</span><span class="sxs-lookup"><span data-stu-id="6bf90-189">For more information about the <xref:System.Xml.XmlWriter> class, see the <xref:System.Xml.XmlWriter> class reference documentation.</span></span>  
  
### <a name="multiple-xmlwriter-objects"></a><span data-ttu-id="6bf90-190">Birden çok XmlWriter nesnesi</span><span class="sxs-lookup"><span data-stu-id="6bf90-190">Multiple XmlWriter Objects</span></span>  
 <span data-ttu-id="6bf90-191">Birden çok olması mümkündür <xref:System.Xml.XPath.XPathNavigator> nesneleri farklı bir XML bölümlerine işaret eden bir veya daha fazla açıkken belge <xref:System.Xml.XmlWriter> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="6bf90-191">It is possible to have multiple <xref:System.Xml.XPath.XPathNavigator> objects pointing to different parts of an XML document with one or more open <xref:System.Xml.XmlWriter> objects.</span></span> <span data-ttu-id="6bf90-192">Birden çok <xref:System.Xml.XmlWriter> nesneleri izin verilen ve tek iş parçacıklı senaryolarında desteklenir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-192">Multiple <xref:System.Xml.XmlWriter> objects are allowed and supported in single-threaded scenarios.</span></span>  
  
 <span data-ttu-id="6bf90-193">Birden çok kullanırken dikkate alınması gereken önemli notlar şunlardır <xref:System.Xml.XmlWriter> nesneleri.</span><span class="sxs-lookup"><span data-stu-id="6bf90-193">The following are important notes to consider when using multiple <xref:System.Xml.XmlWriter> objects.</span></span>  
  
-   <span data-ttu-id="6bf90-194">XML parçaları tarafından yazılan <xref:System.Xml.XmlWriter> nesneleri XML'e eklenen ne zaman belge <xref:System.Xml.XmlWriter.Close%2A> yöntemi her <xref:System.Xml.XmlWriter> nesne çağrılır.</span><span class="sxs-lookup"><span data-stu-id="6bf90-194">XML fragments written by <xref:System.Xml.XmlWriter> objects are added to the XML document when the <xref:System.Xml.XmlWriter.Close%2A> method of each <xref:System.Xml.XmlWriter> object is called.</span></span> <span data-ttu-id="6bf90-195">O noktaya kadar <xref:System.Xml.XmlWriter> nesne bağlantısı kesilmiş bir parça yazma.</span><span class="sxs-lookup"><span data-stu-id="6bf90-195">Until that point, the <xref:System.Xml.XmlWriter> object is writing a disconnected fragment.</span></span> <span data-ttu-id="6bf90-196">Bir işlem tarafından yazılan tüm parçaları XML belgesi üzerinde gerçekleştirilirse bir <xref:System.Xml.XmlWriter> nesnesi, önce <xref:System.Xml.XmlWriter.Close%2A> çağrıldı, etkilenmez.</span><span class="sxs-lookup"><span data-stu-id="6bf90-196">If an operation is performed on the XML document, any fragments being written by an <xref:System.Xml.XmlWriter> object, before the <xref:System.Xml.XmlWriter.Close%2A> has been called, are not affected.</span></span>  
  
-   <span data-ttu-id="6bf90-197">Açık ise <xref:System.Xml.XmlWriter> nesne belirli bir XML alt ağacı ve bu alt ağaç üzerinde silinir, <xref:System.Xml.XmlWriter> nesne alt ağaç hala eklemek.</span><span class="sxs-lookup"><span data-stu-id="6bf90-197">If there is an open <xref:System.Xml.XmlWriter> object on a particular XML subtree and that subtree is deleted, the <xref:System.Xml.XmlWriter> object may still add to the sub-tree.</span></span> <span data-ttu-id="6bf90-198">Alt ağaç, yalnızca silinmiş bir parçası haline gelir.</span><span class="sxs-lookup"><span data-stu-id="6bf90-198">The subtree simply becomes a deleted fragment.</span></span>  
  
-   <span data-ttu-id="6bf90-199">Birden çok <xref:System.Xml.XmlWriter> nesneleri XML belgesindeki bir aynı noktada açıldığında, hangi sırayla XML belgesinde eklendikten <xref:System.Xml.XmlWriter> nesneleri kapalı, bunlar açılan sırasını içinde değil.</span><span class="sxs-lookup"><span data-stu-id="6bf90-199">If multiple <xref:System.Xml.XmlWriter> objects are opened at the same point in the XML document, they are added to the XML document in the order in which the <xref:System.Xml.XmlWriter> objects are closed, not in the order in which they were opened.</span></span>  
  
 <span data-ttu-id="6bf90-200">Aşağıdaki örnekte bir <xref:System.Xml.XmlDocument> nesne, oluşturur bir <xref:System.Xml.XPath.XPathNavigator> nesne ve kullandığı <xref:System.Xml.XmlWriter> tarafından döndürülen nesne <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> ilk Defteri'nde yapısını oluşturmak için yöntemi `books.xml` dosya.</span><span class="sxs-lookup"><span data-stu-id="6bf90-200">The following example creates an <xref:System.Xml.XmlDocument> object, creates an <xref:System.Xml.XPath.XPathNavigator> object, and then uses the <xref:System.Xml.XmlWriter> object returned by the <xref:System.Xml.XPath.XPathNavigator.PrependChild%2A> method to create the structure of the first book in the `books.xml` file.</span></span> <span data-ttu-id="6bf90-201">Örnek olarak sonra kaydeder `book.xml` dosya.</span><span class="sxs-lookup"><span data-stu-id="6bf90-201">The example then saves it as the `book.xml` file.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
Dim navigator As XPathNavigator = document.CreateNavigator()  
  
Using writer As XmlWriter = navigator.PrependChild()  
  
    writer.WriteStartElement("bookstore")  
    writer.WriteStartElement("book")  
    writer.WriteAttributeString("genre", "autobiography")  
    writer.WriteAttributeString("publicationdate", "1981-03-22")  
    writer.WriteAttributeString("ISBN", "1-861003-11-0")  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin")  
    writer.WriteStartElement("author")  
    writer.WriteElementString("first-name", "Benjamin")  
    writer.WriteElementString("last-name", "Franklin")  
    writer.WriteElementString("price", "8.99")  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
    writer.WriteEndElement()  
  
End Using  
  
document.Save("book.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
XPathNavigator navigator = document.CreateNavigator();  
  
using (XmlWriter writer = navigator.PrependChild())  
{  
    writer.WriteStartElement("bookstore");  
    writer.WriteStartElement("book");  
    writer.WriteAttributeString("genre", "autobiography");  
    writer.WriteAttributeString("publicationdate", "1981-03-22");  
    writer.WriteAttributeString("ISBN", "1-861003-11-0");  
    writer.WriteElementString("title", "The Autobiography of Benjamin Franklin");  
    writer.WriteStartElement("author");  
    writer.WriteElementString("first-name", "Benjamin");  
    writer.WriteElementString("last-name", "Franklin");  
    writer.WriteElementString("price", "8.99");  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
    writer.WriteEndElement();  
}  
document.Save("book.xml");  
```  
  
## <a name="saving-an-xml-document"></a><span data-ttu-id="6bf90-202">Bir XML belgesi kaydetme</span><span class="sxs-lookup"><span data-stu-id="6bf90-202">Saving an XML Document</span></span>  
 <span data-ttu-id="6bf90-203">Yapılan değişiklikler kaydedilirken bir <xref:System.Xml.XmlDocument> nesne bu konuda açıklanan yöntemlerden sonucunu yöntemleri kullanılarak gerçekleştirilir gibi <xref:System.Xml.XmlDocument> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="6bf90-203">Saving changes made to an <xref:System.Xml.XmlDocument> object as the result of the methods described in this topic is performed using the methods of the <xref:System.Xml.XmlDocument> class.</span></span> <span data-ttu-id="6bf90-204">Yapılan değişiklikleri kaydetme hakkında daha fazla bilgi için bir <xref:System.Xml.XmlDocument> nesne için bkz: [kaydetme ve bir belgeyi yazma](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span><span class="sxs-lookup"><span data-stu-id="6bf90-204">For more information about saving changes made to an <xref:System.Xml.XmlDocument> object, see [Saving and Writing a Document](../../../../docs/standard/data/xml/saving-and-writing-a-document.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bf90-205">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6bf90-205">See Also</span></span>  
 <xref:System.Xml.XmlDocument>  
 <xref:System.Xml.XPath.XPathDocument>  
 <xref:System.Xml.XPath.XPathNavigator>  
 [<span data-ttu-id="6bf90-206">XPath veri modelini kullanarak işlem XML verileri</span><span class="sxs-lookup"><span data-stu-id="6bf90-206">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 [<span data-ttu-id="6bf90-207">XML XPathNavigator kullanarak verileri değiştirme</span><span class="sxs-lookup"><span data-stu-id="6bf90-207">Modify XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/modify-xml-data-using-xpathnavigator.md)  
 [<span data-ttu-id="6bf90-208">XML XPathNavigator kullanarak verileri Kaldır</span><span class="sxs-lookup"><span data-stu-id="6bf90-208">Remove XML Data using XPathNavigator</span></span>](../../../../docs/standard/data/xml/remove-xml-data-using-xpathnavigator.md)