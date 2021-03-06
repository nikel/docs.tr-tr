---
title: "Nasıl yapılır: bir XmlReader (Visual Basic) bir ağacı oluşturma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ceae7c2bee85e7b368322c8ba195dea9feff672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Nasıl yapılır: bir XmlReader (Visual Basic) bir ağacı oluşturma
Bu konuda, doğrudan bir XML ağacı oluşturmak gösterilmiştir bir <xref:System.Xml.XmlReader>. Oluşturmak için bir <xref:System.Xml.Linq.XElement> gelen bir <xref:System.Xml.XmlReader>, getirin gerekir <xref:System.Xml.XmlReader> bir öğe düğümü üzerinde. <xref:System.Xml.XmlReader> Açıklamaları atlar ve işlem, ancak yönergeleri <xref:System.Xml.XmlReader> konumlandırılmış bir metin düğümü üzerinde bir hata oluşturulur. Bu tür hataları önlemek için her zaman getirin <xref:System.Xml.XmlReader> bir XML ağacından oluşturmadan önce bir öğede <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Örnek  
 Bu örnekte aşağıdaki XML belgesi kullanır: [örnek XML dosyası: Books (LINQ-XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Aşağıdaki kod oluşturur bir `T:System.Xml.XmlReader` nesne ve ilk öğe düğüm bulana kadar okuma düğümleri. Daha sonra yükler <xref:System.Xml.Linq.XElement> nesnesi.  
  
```vb  
Dim r As XmlReader = XmlReader.Create("books.xml")  
Do While r.NodeType <> XmlNodeType.Element  
    r.Read()  
Loop  
Dim e As XElement = XElement.Load(r)  
Console.WriteLine(e)  
```  
  
 Bu örnek şu çıkışı üretir:  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ayrıştırma XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
