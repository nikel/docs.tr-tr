---
title: "Nasıl yapılır: Windows Formlarını Yeniden Boyutlandırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- resizing Windows Forms
- Windows Forms, resizing
ms.assetid: 5d9dd47e-e68c-48c9-a0a3-a9ff34ba009d
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e38339eceef97c4d6f64dffdea9ac04c598b70a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-windows-forms"></a><span data-ttu-id="35158-102">Nasıl yapılır: Windows Formlarını Yeniden Boyutlandırma</span><span class="sxs-lookup"><span data-stu-id="35158-102">How to: Resize Windows Forms</span></span>
<span data-ttu-id="35158-103">Windows Form boyutunu çeşitli yollarla belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35158-103">You can specify the size of your Windows Form in several ways.</span></span> <span data-ttu-id="35158-104">İçin yeni bir değer ayarlayarak yükseklik ve formun genişliğini program aracılığıyla değiştirebilirsiniz <xref:System.Windows.Forms.Form.Size%2A> özelliği veya ayarla <xref:System.Windows.Forms.Control.Height%2A> veya <xref:System.Windows.Forms.Control.Width%2A> özellikleri ayrı ayrı.</span><span class="sxs-lookup"><span data-stu-id="35158-104">You can change both the height and the width of the form programmatically by setting a new value for the <xref:System.Windows.Forms.Form.Size%2A> property, or adjust the <xref:System.Windows.Forms.Control.Height%2A> or <xref:System.Windows.Forms.Control.Width%2A> properties individually.</span></span> <span data-ttu-id="35158-105">Kullanıyorsanız [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], Windows Forms Tasarımcısı'nı kullanarak boyutunu değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="35158-105">If you are using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], you can change the size using the Windows Forms Designer.</span></span> <span data-ttu-id="35158-106">Ayrıca bkz. [nasıl yapılır: yeniden boyutlandırma Windows formları kullanarak Tasarımcı](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="35158-106">Also see [How to: Resize Windows Forms Using the Designer](http://msdn.microsoft.com/library/37k2zkwx\(v=vs.110\)).</span></span>  
  
### <a name="to-resize-a-form-programmatically"></a><span data-ttu-id="35158-107">Bir form programlı olarak yeniden boyutlandırmak için</span><span class="sxs-lookup"><span data-stu-id="35158-107">To resize a form programmatically</span></span>  
  
-   <span data-ttu-id="35158-108">Ayarlayarak çalışma zamanında bir form boyutunu tanımlamaya <xref:System.Windows.Forms.Form.Size%2A> formun özelliği.</span><span class="sxs-lookup"><span data-stu-id="35158-108">Define the size of a form at run time by setting the <xref:System.Windows.Forms.Form.Size%2A> property of the form.</span></span>  
  
     <span data-ttu-id="35158-109">Aşağıdaki kod örneğinde form boyutu 100 × 100 piksel ayarını gösterir.</span><span class="sxs-lookup"><span data-stu-id="35158-109">The following code example shows the form size set to 100 × 100 pixels.</span></span>  
  
    ```vb  
    Form1.Size = New System.Drawing.Size(100, 100)  
    ```  
  
    ```csharp  
    Form1.Size = new System.Drawing.Size(100, 100);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(100, 100);  
    ```  
  
### <a name="to-change-form-width-and-height-programmatically"></a><span data-ttu-id="35158-110">Form genişlik ve yükseklik programlı olarak değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="35158-110">To change form width and height programmatically</span></span>  
  
-   <span data-ttu-id="35158-111">Sonra <xref:System.Windows.Forms.Form.Size%2A> olan tanımlanmış formu yükseklik veya genişliği kullanarak değiştirme <xref:System.Windows.Forms.Control.Width%2A> veya <xref:System.Windows.Forms.Control.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="35158-111">After the <xref:System.Windows.Forms.Form.Size%2A> is defined, change either the form height or width by using the <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="35158-112">Yükseklik sabit kalır ancak aşağıdaki kod örneğinde form sol kenarından 300 piksel olarak ayarlanan formun genişliğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="35158-112">The following code example shows the width of the form set to 300 pixels from the left edge of the form, whereas the height stays constant.</span></span>  
  
    ```vb  
    Form1.Width = 300  
    ```  
  
    ```csharp  
    Form1.Width = 300;  
    ```  
  
    ```cpp  
    Form1->Width = 300;  
    ```  
  
     <span data-ttu-id="35158-113">veya</span><span class="sxs-lookup"><span data-stu-id="35158-113">-or-</span></span>  
  
     <span data-ttu-id="35158-114">Değişiklik <xref:System.Drawing.Size.Width%2A> veya <xref:System.Drawing.Size.Height%2A> ayarlayarak <xref:System.Windows.Forms.Form.Size%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="35158-114">Change <xref:System.Drawing.Size.Width%2A> or <xref:System.Drawing.Size.Height%2A> by setting the <xref:System.Windows.Forms.Form.Size%2A> property.</span></span>  
  
     <span data-ttu-id="35158-115">Ancak, aşağıdaki kod örneğinde gösterildiği gibi bu yaklaşım yalnızca ayarlamaktan daha kullanışsız <xref:System.Windows.Forms.Control.Width%2A> veya <xref:System.Windows.Forms.Control.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="35158-115">However, as the following code example shows, this approach is more cumbersome than just setting <xref:System.Windows.Forms.Control.Width%2A> or <xref:System.Windows.Forms.Control.Height%2A> properties.</span></span>  
  
    ```vb  
    Form1.Size = New Size(300, Form1.Size.Height)  
    ```  
  
    ```csharp  
    Form1.Size = new Size(300, Form1.Size.Height);  
    ```  
  
    ```cpp  
    Form1->Size = System::Drawing::Size(300, Form1->Size.Height);  
    ```  
  
### <a name="to-change-form-size-by-increments-programmatically"></a><span data-ttu-id="35158-116">Form boyutunu artışlarla programlı olarak değiştirmek için</span><span class="sxs-lookup"><span data-stu-id="35158-116">To change form size by increments programmatically</span></span>  
  
-   <span data-ttu-id="35158-117">Formun boyutunu artırmak için ayarlanmış <xref:System.Drawing.Size.Width%2A> ve <xref:System.Drawing.Size.Height%2A> özellikleri.</span><span class="sxs-lookup"><span data-stu-id="35158-117">To increment the size of the form, set the <xref:System.Drawing.Size.Width%2A> and <xref:System.Drawing.Size.Height%2A> properties.</span></span>  
  
     <span data-ttu-id="35158-118">Aşağıdaki kod örneği, geçerli boyuttan daha geniş 200 piksel için ayarlanan formun genişliğini gösterir.</span><span class="sxs-lookup"><span data-stu-id="35158-118">The following code example shows the width of the form set to 200 pixels wider than the current setting.</span></span>  
  
    ```vb  
    Form1.Width += 200  
    ```  
  
    ```csharp  
    Form1.Width += 200;  
    ```  
  
    ```cpp  
    Form1->Width += 200;  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="35158-119">Her zaman kullanmak <xref:System.Drawing.Size.Height%2A> veya <xref:System.Drawing.Size.Width%2A> ayarlayarak aynı anda yükseklik ve genişlik boyutlarını ayarlıyorsanız sürece bir form boyutunu değiştirmek için özellik <xref:System.Windows.Forms.Form.Size%2A> yeni bir özellik <xref:System.Drawing.Size> yapısı.</span><span class="sxs-lookup"><span data-stu-id="35158-119">Always use the <xref:System.Drawing.Size.Height%2A> or <xref:System.Drawing.Size.Width%2A> property to change a dimension of a form, unless you are setting both height and width dimensions at the same time by setting the <xref:System.Windows.Forms.Form.Size%2A> property to a new <xref:System.Drawing.Size> structure.</span></span> <span data-ttu-id="35158-120"><xref:System.Windows.Forms.Form.Size%2A> Özelliği döndürür bir <xref:System.Drawing.Size> bir değer türü yapısı.</span><span class="sxs-lookup"><span data-stu-id="35158-120">The <xref:System.Windows.Forms.Form.Size%2A> property returns a <xref:System.Drawing.Size> structure, which is a value type.</span></span> <span data-ttu-id="35158-121">Değer türü özelliği için yeni bir değer atayamazsınız.</span><span class="sxs-lookup"><span data-stu-id="35158-121">You cannot assign a new value to the property of a value type.</span></span> <span data-ttu-id="35158-122">Bu nedenle, aşağıdaki kod örneğinde derlenmez.</span><span class="sxs-lookup"><span data-stu-id="35158-122">Therefore, the following code example will not compile.</span></span>  
  
    ```vb  
    ' NOTE: CODE WILL NOT COMPILE  
    Dim f As New Form()  
    f.Size.Width += 100  
    ```  
  
    ```csharp  
    // NOTE: CODE WILL NOT COMPILE  
    Form f = new Form();  
    f.Size.Width += 100;  
    ```  
  
    ```cpp  
    // NOTE: CODE WILL NOT COMPILE  
    Form^ f = gcnew Form();  
    f->Size->X += 100;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="35158-123">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="35158-123">See Also</span></span>  
 [<span data-ttu-id="35158-124">Windows Forms'a Başlarken</span><span class="sxs-lookup"><span data-stu-id="35158-124">Getting Started with Windows Forms</span></span>](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [<span data-ttu-id="35158-125">Windows Forms uygulamalarını geliştirme</span><span class="sxs-lookup"><span data-stu-id="35158-125">Enhancing Windows Forms Applications</span></span>](../../../docs/framework/winforms/advanced/index.md)