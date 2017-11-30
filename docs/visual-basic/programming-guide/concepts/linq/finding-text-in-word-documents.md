---
title: Word belgeleri (Visual Basic) metin bulma
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eea9819b-a78a-4552-bf13-8837fc0e7a37
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4907aacfae333544448da399f0fd7169a36fc505
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="finding-text-in-word-documents-visual-basic"></a><span data-ttu-id="bc722-102">Word belgeleri (Visual Basic) metin bulma</span><span class="sxs-lookup"><span data-stu-id="bc722-102">Finding Text in Word Documents (Visual Basic)</span></span>
<span data-ttu-id="bc722-103">Bu konu yararlı bir şeyler için önceki sorgular genişletir: bir dizenin tüm oluşumlarını belgesinde bulunamadı.</span><span class="sxs-lookup"><span data-stu-id="bc722-103">This topic extends the previous queries to do something useful: find all occurrences of a string in the document.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc722-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="bc722-104">Example</span></span>  
 <span data-ttu-id="bc722-105">Bu örnek, belirli bir metin parçası olan tüm oluşum belgede bulmak için bir WordprocessingML belge işler.</span><span class="sxs-lookup"><span data-stu-id="bc722-105">This example processes a WordprocessingML document, to find all the occurences of a specific piece of text in the document.</span></span> <span data-ttu-id="bc722-106">Bunu yapmak için "Hello" dizesini bulan bir sorgu kullanırız.</span><span class="sxs-lookup"><span data-stu-id="bc722-106">To do this, we use a query that finds the string "Hello".</span></span> <span data-ttu-id="bc722-107">Bu örnek önceki örnekler üzerinde Bu öğreticide oluşturur.</span><span class="sxs-lookup"><span data-stu-id="bc722-107">This example builds on the previous examples in this tutorial.</span></span> <span data-ttu-id="bc722-108">Yeni sorgu aşağıdaki kodu açıklamalarda belirtilmiştir.</span><span class="sxs-lookup"><span data-stu-id="bc722-108">The new query is called out in comments in the code below.</span></span>  
  
 <span data-ttu-id="bc722-109">Bu örnek için kaynak belge oluşturma yönergeleri için bkz: [kaynak Office Açık XML belgesi (Visual Basic) oluşturulmasını](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="bc722-109">For instructions for creating the source document for this example, see [Creating the Source Office Open XML Document (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-the-source-office-open-xml-document.md).</span></span>  
  
 <span data-ttu-id="bc722-110">Bu örnek WindowsBase derlemesinde sınıfları kullanır.</span><span class="sxs-lookup"><span data-stu-id="bc722-110">This example uses classes found in the WindowsBase assembly.</span></span> <span data-ttu-id="bc722-111">Türlerinde kullanan <xref:System.IO.Packaging?displayProperty=nameWithType> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="bc722-111">It uses types in the <xref:System.IO.Packaging?displayProperty=nameWithType> namespace.</span></span>  
  
```vb  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As String In source  
            sb.Append(s)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item))  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As T In source  
            sb.Append(s).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String), ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item)).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    Public Function ParagraphText(ByVal e As XElement) As String  
        Dim w As XNamespace = e.Name.Namespace  
        Return (e.<w:r>.<w:t>).StringConcatenate(Function(element) CStr(element))  
    End Function  
  
    ' Following function is required because VB does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Retrieve the text of each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = ParagraphText(para.ParagraphNode) _  
            }  
  
        ' Following is the new query that retrieves all paragraphs  
        ' that have specific text in them.  
        Dim helloParagraphs = _  
            From para In paraWithText _  
            Where para.Text.Contains("Hello") _  
            Select New With _  
            { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.Text _  
            }  
  
        For Each p In helloParagraphs  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="bc722-112">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="bc722-112">This example produces the following output:</span></span>  
  
```  
StyleName:Code >        Console.WriteLine("Hello World")<  
StyleName:Code >Hello World<  
```  
  
 <span data-ttu-id="bc722-113">Elbette, böylece belirli bir stil satırıyla arar arama değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="bc722-113">You can, of course, modify the search so that it searches for lines with a specific style.</span></span> <span data-ttu-id="bc722-114">Aşağıdaki sorgu, kod stili sahip tüm boş satırları bulur:</span><span class="sxs-lookup"><span data-stu-id="bc722-114">The following query finds all blank lines that have the Code style:</span></span>  
  
```vb  
Imports System.IO.Packaging  
Imports <xmlns:w="http://schemas.openxmlformats.org/wordprocessingml/2006/main">  
  
Module Module1  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(ByVal source As IEnumerable(Of String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As String In source  
            sb.Append(s)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String)) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item))  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each s As T In source  
            sb.Append(s).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    <System.Runtime.CompilerServices.Extension()> _  
    Public Function StringConcatenate(Of T)(ByVal source As IEnumerable(Of T), _  
    ByVal func As Func(Of T, String), ByVal separator As String) As String  
        Dim sb As StringBuilder = New StringBuilder()  
        For Each item As T In source  
            sb.Append(func(item)).Append(separator)  
        Next  
        Return sb.ToString()  
    End Function  
  
    Public Function ParagraphText(ByVal e As XElement) As String  
        Dim w As XNamespace = e.Name.Namespace  
        Return (e.<w:r>.<w:t>).StringConcatenate(Function(element) CStr(element))  
    End Function  
  
    ' Following function is required because VB does not support short circuit evaluation  
    Private Function GetStyleOfParagraph(ByVal styleNode As XElement, ByVal defaultStyle As String) As String  
        If (styleNode Is Nothing) Then  
            Return defaultStyle  
        Else  
            Return styleNode.@w:val  
        End If  
    End Function  
  
    Sub Main()  
        Dim fileName = "SampleDoc.docx"  
  
        Dim documentRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/officeDocument"  
        Dim stylesRelationshipType = "http://schemas.openxmlformats.org/officeDocument/2006/relationships/styles"  
        Dim wordmlNamespace = "http://schemas.openxmlformats.org/wordprocessingml/2006/main"  
        Dim xDoc As XDocument = Nothing  
        Dim styleDoc As XDocument = Nothing  
  
        Using wdPackage As Package = Package.Open(fileName, FileMode.Open, FileAccess.Read)  
            Dim docPackageRelationship As PackageRelationship = wdPackage.GetRelationshipsByType(documentRelationshipType).FirstOrDefault()  
            If (docPackageRelationship IsNot Nothing) Then  
                Dim documentUri As Uri = PackUriHelper.ResolvePartUri(New Uri("/", UriKind.Relative), docPackageRelationship.TargetUri)  
                Dim documentPart As PackagePart = wdPackage.GetPart(documentUri)  
  
                '  Load the document XML in the part into an XDocument instance.  
                xDoc = XDocument.Load(XmlReader.Create(documentPart.GetStream()))  
  
                '  Find the styles part. There will only be one.  
                Dim styleRelation As PackageRelationship = documentPart.GetRelationshipsByType(stylesRelationshipType).FirstOrDefault()  
                If (styleRelation IsNot Nothing) Then  
                    Dim styleUri As Uri = PackUriHelper.ResolvePartUri(documentUri, styleRelation.TargetUri)  
                    Dim stylePart As PackagePart = wdPackage.GetPart(styleUri)  
  
                    '  Load the style XML in the part into an XDocument instance.  
                    styleDoc = XDocument.Load(XmlReader.Create(stylePart.GetStream()))  
                End If  
            End If  
        End Using  
  
        Dim defaultStyle As String = _  
            ( _  
                From style In styleDoc.Root.<w:style> _  
                Where style.@w:type = "paragraph" And _  
                      style.@w:default = "1" _  
                Select style _  
            ).First().@w:styleId  
  
        ' Find all paragraphs in the document.  
        Dim paragraphs = _  
            From para In xDoc.Root.<w:body>...<w:p> _  
        Let styleNode As XElement = para.<w:pPr>.<w:pStyle>.FirstOrDefault _  
        Select New With { _  
            .ParagraphNode = para, _  
            .StyleName = GetStyleOfParagraph(styleNode, defaultStyle) _  
        }  
  
        ' Retrieve the text of each paragraph.  
        Dim paraWithText = _  
            From para In paragraphs _  
            Select New With { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = ParagraphText(para.ParagraphNode) _  
            }  
  
        ' Retrieve all paragraphs that have no text and are styled Code.  
        Dim blankCodeParagraphs = _  
            From para In paraWithText _  
            Where String.IsNullOrEmpty(para.Text) And para.StyleName.Equals("Code") _  
            Select New With _  
            { _  
                .ParagraphNode = para.ParagraphNode, _  
                .StyleName = para.StyleName, _  
                .Text = para.Text _  
            }  
  
        For Each p In blankCodeParagraphs  
            Console.WriteLine("StyleName:{0} >{1}<", p.StyleName, p.Text)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="bc722-115">Bu örnek şu çıkışı üretir:</span><span class="sxs-lookup"><span data-stu-id="bc722-115">This example produces the following output:</span></span>  
  
```  
StyleName:Code ><  
```  
  
 <span data-ttu-id="bc722-116">Elbette, bu örnek, çeşitli yollarla iyileştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="bc722-116">Of course, this example could be enhanced in a number of ways.</span></span> <span data-ttu-id="bc722-117">Örneğin, normal ifadeler metni aramak için kullanırız, biz belirli dizin ve benzeri tüm Word dosyaları yinelemek.</span><span class="sxs-lookup"><span data-stu-id="bc722-117">For example, we could use regular expressions to search for text, we could iterate through all the Word files in a particular directory, and so on.</span></span>  
  
 <span data-ttu-id="bc722-118">Tek bir sorgu yazılmış gibi bu örnek yaklaşık de gerçekleştirmediğini unutmayın.</span><span class="sxs-lookup"><span data-stu-id="bc722-118">Note that this example performs approximately as well as if it were written as a single query.</span></span> <span data-ttu-id="bc722-119">Her sorgu yavaş, ertelenmiş biçimde uygulandığı için sorgu yinelendiğinde kadar her sorgu sonuçlarını vermez.</span><span class="sxs-lookup"><span data-stu-id="bc722-119">Because each query is implemented in a lazy, deferred fashion, each query does not yield its results until the query is iterated.</span></span> <span data-ttu-id="bc722-120">Yürütme ve geç değerlendirme hakkında daha fazla bilgi için bkz: [ertelenmiş yürütme ve LINQ-XML (Visual Basic) geç değerlendirme](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bc722-120">For more information about execution and lazy evaluation, see [Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bc722-121">Sonraki Adımlar</span><span class="sxs-lookup"><span data-stu-id="bc722-121">Next Steps</span></span>  
 <span data-ttu-id="bc722-122">Sonraki bölümde WordprocessingML belgeler hakkında daha fazla bilgi verilmektedir:</span><span class="sxs-lookup"><span data-stu-id="bc722-122">The next section provides more information about WordprocessingML documents:</span></span>  
  
-   [<span data-ttu-id="bc722-123">Ayrıntılar Office Açık XML WordprocessingML belgeleri (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc722-123">Details of Office Open XML WordprocessingML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/details-of-office-open-xml-wordprocessingml-documents.md)  
  
## <a name="see-also"></a><span data-ttu-id="bc722-124">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="bc722-124">See Also</span></span>  
 [<span data-ttu-id="bc722-125">Öğretici: Düzenleme içeriği WordprocessingML belgesinde (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc722-125">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)  
 [<span data-ttu-id="bc722-126">Saf işlevi (Visual Basic) kullanarak yeniden düzenleme</span><span class="sxs-lookup"><span data-stu-id="bc722-126">Refactoring Using a Pure Function (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/refactoring-using-a-pure-function.md)  
 [<span data-ttu-id="bc722-127">Ertelenmiş yürütme ve geç değerlendirme LINQ-XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc722-127">Deferred Execution and Lazy Evaluation in LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)