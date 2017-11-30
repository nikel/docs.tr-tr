---
title: "Nasıl yapılır: Çalışma Zamanında bir Denetimler Koleksiyonuna Ekleme veya Kaldırma"
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
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3b359679df68bf3caa9bab1bdbadedadcde45ac5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="4d0ce-102">Nasıl yapılır: Çalışma Zamanında bir Denetimler Koleksiyonuna Ekleme veya Kaldırma</span><span class="sxs-lookup"><span data-stu-id="4d0ce-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="4d0ce-103">Uygulama geliştirme, ortak görevler için denetimler ekleme ve herhangi bir kapsayıcı denetimi, formlarında denetimleri kaldırma (gibi <xref:System.Windows.Forms.Panel> veya <xref:System.Windows.Forms.GroupBox> denetim veya formun kendisi bile).</span><span class="sxs-lookup"><span data-stu-id="4d0ce-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="4d0ce-104">Tasarım zamanında denetimleri doğrudan Masası veya grup kutusu sürüklenebilir.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="4d0ce-105">Bu denetimler çalışma zamanında korumak bir `Controls` hangi denetimlerin üzerine yerleştirilen izler koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d0ce-106">Aşağıdaki kod örneğinde içindeki denetimler koleksiyonuna tutar herhangi bir denetimi uygular.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="4d0ce-107">Bir denetim program aracılığıyla bir koleksiyona eklemek için</span><span class="sxs-lookup"><span data-stu-id="4d0ce-107">To add a control to a collection programmatically</span></span>  
  
1.  <span data-ttu-id="4d0ce-108">Eklenecek denetim örneği oluşturun.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-108">Create an instance of the control to be added.</span></span>  
  
2.  <span data-ttu-id="4d0ce-109">Yeni denetim özelliklerini ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-109">Set properties of the new control.</span></span>  
  
3.  <span data-ttu-id="4d0ce-110">Denetimine ekleme `Controls` üst denetim koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="4d0ce-111">Aşağıdaki kod örneğinde bir örneğini oluşturmak gösterilmiştir <xref:System.Windows.Forms.Button> denetim.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="4d0ce-112">Bir formla gerektiren bir <xref:System.Windows.Forms.Panel> denetimi ve bu düğme için olay işleme yöntemi oluşturuluyor, `NewPanelButton_Click`, zaten mevcut.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="4d0ce-113">Denetimlerini programlı olarak koleksiyondan kaldırmak için</span><span class="sxs-lookup"><span data-stu-id="4d0ce-113">To remove controls from a collection programmatically</span></span>  
  
1.  <span data-ttu-id="4d0ce-114">Olay işleyicisi olaydan kaldırın.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-114">Remove the event handler from the event.</span></span> <span data-ttu-id="4d0ce-115">İçinde [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], kullanın [RemoveHandler deyimi](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) anahtar sözcüğü; [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], kullanın [-= işleci (C# Başvurusu)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="4d0ce-115">In [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2.  <span data-ttu-id="4d0ce-116">Kullanım `Remove` istenen Denetim Masası'ndan 's silmek için yöntemi `Controls` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3.  <span data-ttu-id="4d0ce-117">Çağrı <xref:System.Windows.Forms.Control.Dispose%2A> denetimi tarafından kullanılan tüm kaynakları serbest bırakmak için yöntem.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4d0ce-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4d0ce-118">See Also</span></span>  
 <xref:System.Windows.Forms.Panel>  
 [<span data-ttu-id="4d0ce-119">Panel denetimi</span><span class="sxs-lookup"><span data-stu-id="4d0ce-119">Panel Control</span></span>](../../../../docs/framework/winforms/controls/panel-control-windows-forms.md)