---
title: "Kaynak Office Açık XML belge (C#) oluşturma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 653c8cdb-73be-4dc2-927f-924cfb4ed9ed
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 378a83db02c6e07a070fb3770b042ed657860560
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-the-source-office-open-xml-document-c"></a><span data-ttu-id="5c790-102">Kaynak Office Açık XML belge (C#) oluşturma</span><span class="sxs-lookup"><span data-stu-id="5c790-102">Creating the Source Office Open XML Document (C#)</span></span>
<span data-ttu-id="5c790-103">Bu konu diğer örnekleri Bu öğreticide kullanmak Office Açık XML WordprocessingML belgesi nasıl oluşturacağınızı gösterir.</span><span class="sxs-lookup"><span data-stu-id="5c790-103">This topic shows how to create the Office Open XML WordprocessingML document that the other examples in this tutorial use.</span></span> <span data-ttu-id="5c790-104">Bu yönergeleri izleyin, her örnekte sağlanan çıkış, çıktı eşleşir.</span><span class="sxs-lookup"><span data-stu-id="5c790-104">If you follow these instructions, your output will match the output provided in each example.</span></span>  
  
 <span data-ttu-id="5c790-105">Ancak, Bu öğretici örneklerde sahip herhangi bir geçerli WordprocessingML belgeyi çalışır.</span><span class="sxs-lookup"><span data-stu-id="5c790-105">However, the examples in this tutorial will work with any valid WordprocessingML document.</span></span>  
  
 <span data-ttu-id="5c790-106">Bu öğretici kullanır belge oluşturmak için Microsoft Office 2007 ya da sahip olmalıdır veya sonraki bir sürümünün yüklü veya Word, Excel ve PowerPoint 2007 dosya biçimleri için Microsoft Office Uyumluluk Paketi ile Microsoft Office 2003 olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="5c790-106">To create the document that this tutorial uses, you must either have Microsoft Office 2007 or later installed, or you must have Microsoft Office 2003 with the Microsoft Office Compatibility Pack for Word, Excel, and PowerPoint 2007 File Formats.</span></span>  
  
## <a name="creating-the-wordprocessingml-document"></a><span data-ttu-id="5c790-107">WordprocessingML belge oluşturma</span><span class="sxs-lookup"><span data-stu-id="5c790-107">Creating the WordprocessingML Document</span></span>  
  
#### <a name="to-create-the-wordprocessingml-document"></a><span data-ttu-id="5c790-108">WordprocessingML belge oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="5c790-108">To create the WordprocessingML document</span></span>  
  
1.  <span data-ttu-id="5c790-109">Yeni bir Microsoft Word belgesi oluşturun.</span><span class="sxs-lookup"><span data-stu-id="5c790-109">Create a new Microsoft Word document.</span></span>  
  
2.  <span data-ttu-id="5c790-110">Aşağıdaki metni yeni bir belgeye yapıştırın:</span><span class="sxs-lookup"><span data-stu-id="5c790-110">Paste the following text into the new document:</span></span>  
  
    ```  
    Parsing WordprocessingML with LINQ to XML  
  
    The following example prints to the console.  
  
    using System;  
  
    class Program {  
        public static void Main(string[] args) {  
            Console.WriteLine("Hello World");  
        }  
    }  
  
    This example produces the following output:  
  
    Hello World  
    ```  
  
3.  <span data-ttu-id="5c790-111">İlk satırı "Başlık 1" stili ile biçimlendirin.</span><span class="sxs-lookup"><span data-stu-id="5c790-111">Format the first line with the style "Heading 1".</span></span>  
  
4.  <span data-ttu-id="5c790-112">C# kodu içeren satırları seçin.</span><span class="sxs-lookup"><span data-stu-id="5c790-112">Select the lines that contain the C# code.</span></span> <span data-ttu-id="5c790-113">İlk satırı ile başlayan `using` anahtar sözcüğü.</span><span class="sxs-lookup"><span data-stu-id="5c790-113">The first line starts with the `using` keyword.</span></span> <span data-ttu-id="5c790-114">Son kapanış ayracı son satırdır.</span><span class="sxs-lookup"><span data-stu-id="5c790-114">The last line is the last closing brace.</span></span> <span data-ttu-id="5c790-115">Courier yazı tipi içeren satırları biçimlendirin.</span><span class="sxs-lookup"><span data-stu-id="5c790-115">Format the lines with the courier font.</span></span> <span data-ttu-id="5c790-116">İle yeni bir stil biçimlendirmek ve yeni stil "Code" olarak adlandırın.</span><span class="sxs-lookup"><span data-stu-id="5c790-116">Format them with a new style, and name the new style "Code".</span></span>  
  
5.  <span data-ttu-id="5c790-117">Son olarak, çıktı içeren tüm satırı seçin ve ile biçimlendirmeniz `Code` stili.</span><span class="sxs-lookup"><span data-stu-id="5c790-117">Finally, select the entire line that contains the output, and format it with the `Code` style.</span></span>  
  
6.  <span data-ttu-id="5c790-118">Belgeyi kaydedin ve SampleDoc.docx olarak adlandırın.</span><span class="sxs-lookup"><span data-stu-id="5c790-118">Save the document, and name it SampleDoc.docx.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5c790-119">Microsoft Word 2003 kullanıyorsanız seçin **Word 2007 belgesi** içinde **farklı türde Kaydet** aşağı açılan liste.</span><span class="sxs-lookup"><span data-stu-id="5c790-119">If you are using Microsoft Word 2003, select **Word 2007 Document** in the **Save as Type** drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c790-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="5c790-120">See Also</span></span>  
 [<span data-ttu-id="5c790-121">Öğretici: Düzenleme içeriği WordprocessingML belgesinde (C#)</span><span class="sxs-lookup"><span data-stu-id="5c790-121">Tutorial: Manipulating Content in a WordprocessingML Document (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-manipulating-content-in-a-wordprocessingml-document.md)