---
title: "&lt;Özet&gt; (C# programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5a8aa1f8a07019ff6ccefe90f03b217067ae22c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="d986e-102">&lt;Özet&gt; (C# programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="d986e-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="d986e-103">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="d986e-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d986e-104">Parametreler</span><span class="sxs-lookup"><span data-stu-id="d986e-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d986e-105">Nesne özeti.</span><span class="sxs-lookup"><span data-stu-id="d986e-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d986e-106">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="d986e-106">Remarks</span></span>  
 <span data-ttu-id="d986e-107">\<Özet > etiketi, bir tür veya bir tür üyesi açıklamak için kullanılmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d986e-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="d986e-108">Kullanım [ \<açıklamalar >](../../../csharp/programming-guide/xmldoc/remarks.md) türü açıklaması için ek bilgiler eklemek için.</span><span class="sxs-lookup"><span data-stu-id="d986e-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="d986e-109">Kullanım [cref özniteliği](../../../csharp/programming-guide/xmldoc/cref-attribute.md) belgelerine araçları gibi etkinleştirmek için [Sandcastle](https://github.com/EWSoftware/SHFB) kod öğeleri için belgeleri sayfalara iç köprüler oluşturmak için.</span><span class="sxs-lookup"><span data-stu-id="d986e-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="d986e-110">Metni \<Özet > etiketi IntelliSense türüyle ilgili bilgiler yalnızca kaynağı ve ayrıca nesne tarayıcı penceresinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="d986e-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="d986e-111">İle derleme [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) bir dosyaya işlem belgesi açıklamaları için.</span><span class="sxs-lookup"><span data-stu-id="d986e-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="d986e-112">Derleyicinin ürettiği dosyasını temel alarak son belgeleri oluşturmak için özel bir araç oluşturabilir, veya gibi bir araç kullanın [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="d986e-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d986e-113">Örnek</span><span class="sxs-lookup"><span data-stu-id="d986e-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 <span data-ttu-id="d986e-114">Önceki örnekte şu XML dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d986e-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="d986e-115">Örnek</span><span class="sxs-lookup"><span data-stu-id="d986e-115">Example</span></span>  
 <span data-ttu-id="d986e-116">Aşağıdaki örnekte nasıl yapılacağını gösteren bir `cref` genel bir tür referansı.</span><span class="sxs-lookup"><span data-stu-id="d986e-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 <span data-ttu-id="d986e-117">Önceki örnekte şu XML dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d986e-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d986e-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d986e-118">See Also</span></span>  
 [<span data-ttu-id="d986e-119">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="d986e-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d986e-120">Belge açıklamaları için önerilen etiketler</span><span class="sxs-lookup"><span data-stu-id="d986e-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)