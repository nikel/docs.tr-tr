---
title: "Öğeleri, öznitelikleri ve düğümler XML ağacından (Visual Basic) kaldırılıyor"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c1662f0cd1461cc00a8859464b8da3ecb8fd9faf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a>Öğeleri, öznitelikleri ve düğümler XML ağacından (Visual Basic) kaldırılıyor
Bir XML ağacı öğeleri, öznitelikleri ve diğer tür düğüm kaldırma değiştirebilirsiniz.  
  
 Tek bir öğe veya tek bir öznitelik bir XML belgesinden kaldırma basittir. Ancak, koleksiyonları öğelerin veya özniteliklerin kaldırırken, ilk listesini koleksiyona gerçekleştirmeye ve gerekir öznitelikler ve öğeler listeden silin. Kullanmak için en iyi yaklaşımdır <xref:System.Xml.Linq.Extensions.Remove%2A> bu sizin için yapar genişletme yöntemi.  
  
 Bunu yapmak için ana nedeni, bir XML ağacından almak koleksiyonları çoğunu kullanılarak ertelenmiş yürütme verdiğini olduğunu olmasıdır. İlk önce bunları bir liste olarak gerçekleştirmeye değil ya da uzantı yöntemleri kullanmazsanız, belirli bir sınıf hataların karşılaştığınız mümkündür. Daha fazla bilgi için bkz: [karma bildirim temelli kod/kesinliği kod hataları (LINQ-XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).  
  
 Aşağıdaki yöntemlerden bir XML ağacından düğümleri ve öznitelikleri kaldırın.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Remove%2A?displayProperty=nameWithType>|Kaldırır bir <xref:System.Xml.Linq.XAttribute> kendi üst öğesinden.|  
|<xref:System.Xml.Linq.XContainer.RemoveNodes%2A?displayProperty=nameWithType>|Alt düğümleri kaldırır bir <xref:System.Xml.Linq.XContainer>.|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=nameWithType>|İçerik kaldırır ve özniteliklerini bir <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=nameWithType>|Özniteliklerini kaldırır bir <xref:System.Xml.Linq.XElement>.|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=nameWithType>|Geçirirseniz `null` öznitelik için değer, ardından kaldırır.|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=nameWithType>|Geçirirseniz `null` için değer, sonra alt öğeyi kaldırır.|  
|<xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=nameWithType>|Kaldırır bir <xref:System.Xml.Linq.XNode> kendi üst öğesinden.|  
|<xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=nameWithType>|Her öznitelik veya öğenin üst öğesi kaynak koleksiyondan kaldırır.|  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Bu örnek, öğe kaldırma için üç yaklaşım gösterir. İlk olarak, tek bir öğe kaldırır. İkinci olarak, öğe koleksiyonunu alır, bunları gerçeğe kullanarak <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> işleci ve koleksiyon kaldırır. Son olarak, öğe koleksiyonunu alır ve bunları kaldırır kullanarak <xref:System.Xml.Linq.Extensions.Remove%2A> genişletme yöntemi.  
  
 Daha fazla bilgi için <xref:System.Linq.Enumerable.ToList%2A> işleci, bkz: [dönüştürme veri türleri (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
### <a name="code"></a>Kod  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
```  
  
### <a name="comments"></a>Açıklamalar  
 Bu kod aşağıdaki çıktıyı üretir:  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 İlk en alt öğe kaldırıldığı bildirimi `Child1`. Tüm alt bağımlı öğelere öğeleri kaldırılmış olan `Child2` ve `Child3`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML ağaçları (LINQ-XML) değiştirme (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
