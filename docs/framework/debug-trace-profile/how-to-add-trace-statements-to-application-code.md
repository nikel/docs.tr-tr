---
title: "Nasıl yapılır: Uygulama Koduna İzleme Deyimleri Ekleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tracing [.NET Framework], conditional writes based on switches
- trace statements
- WriteLineIf method
- tracing [.NET Framework], adding trace statements
- Assert method, tracing code
- trace switches, conditional writes based on switches
- WriteIf method
ms.assetid: f3a93fa7-1717-467d-aaff-393e5c9828b4
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5dd46da24c379a7900dff0dc482577195f5f4c23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-trace-statements-to-application-code"></a><span data-ttu-id="4307b-102">Nasıl yapılır: Uygulama Koduna İzleme Deyimleri Ekleme</span><span class="sxs-lookup"><span data-stu-id="4307b-102">How to: Add Trace Statements to Application Code</span></span>
<span data-ttu-id="4307b-103">İzleme için en sık kullanılan yöntemler dinleyici çıktı yazmak için yöntemler şunlardır: **yazma**, **Writeıf**, **WriteLine**, **Writelineıf**, **Assert**, ve **başarısız**.</span><span class="sxs-lookup"><span data-stu-id="4307b-103">The methods used most often for tracing are the methods for writing output to listeners: **Write**, **WriteIf**, **WriteLine**, **WriteLineIf**, **Assert**, and **Fail**.</span></span> <span data-ttu-id="4307b-104">Bu yöntemleri iki kategoriye ayrılabilir: **yazma**, **WriteLine**, ve **başarısız** tüm çıktı koşulsuz, ancak yayma **Writeıf**, **Writelineıf**, ve **Assert** Boolean koşulu test ve yazma ya da koşul değerine göre yazma.</span><span class="sxs-lookup"><span data-stu-id="4307b-104">These methods can be divided into two categories: **Write**, **WriteLine**, and **Fail** all emit output unconditionally, whereas **WriteIf**, **WriteLineIf**, and **Assert** test a Boolean condition, and write or do not write based on the value of the condition.</span></span> <span data-ttu-id="4307b-105">**Writeıf** ve **Writelineıf** koşul ise, çıktı yayma `true`, ve **Assert** koşul ise çıktıyı yayar `false`.</span><span class="sxs-lookup"><span data-stu-id="4307b-105">**WriteIf** and **WriteLineIf** emit output if the condition is `true`, and **Assert** emits output if the condition is `false`.</span></span>  
  
 <span data-ttu-id="4307b-106">İzleme ve hata ayıklama stratejisi tasarlarken, aramak için çıktı nasıl istediğinizi hakkında düşünmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="4307b-106">When designing your tracing and debugging strategy, you should think about how you want the output to look.</span></span> <span data-ttu-id="4307b-107">Birden çok **yazma** ilgisiz bilgilerle doldurulmuş deyimleri okunması zor bir günlük oluşturur.</span><span class="sxs-lookup"><span data-stu-id="4307b-107">Multiple **Write** statements filled with unrelated information will create a log that is difficult to read.</span></span> <span data-ttu-id="4307b-108">Diğer taraftan, kullanarak **WriteLine** ilişkili ifadeleri koymak için ayrı satırlara hangi bilgilerin birlikte ait ayırt etmek zorlaştıran.</span><span class="sxs-lookup"><span data-stu-id="4307b-108">On the other hand, using **WriteLine** to put related statements on separate lines may make it difficult to distinguish what information belongs together.</span></span> <span data-ttu-id="4307b-109">Genel olarak, çoklu kullanmak **yazma** tek bir bilgilendirici ileti oluşturmak ve kullanmak için birden fazla kaynaktan bilgileri birleştirmek istediğinizde deyimleri **WriteLine** oluşturmak istediğinizde deyimi bir tek, tam iletisi.</span><span class="sxs-lookup"><span data-stu-id="4307b-109">In general, use multiple **Write** statements when you want to combine information from multiple sources to create a single informative message, and use the **WriteLine** statement when you want to create a single, complete message.</span></span>  
  
### <a name="to-write-a-complete-line"></a><span data-ttu-id="4307b-110">Tam bir satır yazmak için</span><span class="sxs-lookup"><span data-stu-id="4307b-110">To write a complete line</span></span>  
  
1.  <span data-ttu-id="4307b-111">Arama <xref:System.Diagnostics.Trace.WriteLine%2A> veya <xref:System.Diagnostics.Trace.WriteLineIf%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4307b-111">Call the <xref:System.Diagnostics.Trace.WriteLine%2A> or <xref:System.Diagnostics.Trace.WriteLineIf%2A> method.</span></span>  
  
     <span data-ttu-id="4307b-112">Böylece sonraki iletiyi tarafından döndürülen satır başı bu yöntem, ileti sonuna eklenir **yazma**, **Writeıf**, **WriteLine**, veya  **Writelineıf** aşağıdaki satırda başlar:</span><span class="sxs-lookup"><span data-stu-id="4307b-112">A carriage return is appended to the end of the message this method returns, so that the next message returned by **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the following line:</span></span>  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteLine("Error in AppendData procedure.")  
    Trace.WriteLineIf(errorFlag, "Error in AppendData procedure.")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteLine ("Error in AppendData procedure.");  
    System.Diagnostics.Trace.WriteLineIf(errorFlag,   
       "Error in AppendData procedure.");  
    ```  
  
### <a name="to-write-a-partial-line"></a><span data-ttu-id="4307b-113">Kısmi bir satır yazmak için</span><span class="sxs-lookup"><span data-stu-id="4307b-113">To write a partial line</span></span>  
  
1.  <span data-ttu-id="4307b-114">Arama <xref:System.Diagnostics.Trace.Write%2A> veya <xref:System.Diagnostics.Trace.WriteIf%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4307b-114">Call the <xref:System.Diagnostics.Trace.Write%2A> or <xref:System.Diagnostics.Trace.WriteIf%2A> method.</span></span>  
  
     <span data-ttu-id="4307b-115">Sonraki iletiyi put bir **yazma**, **Writeıf**, **WriteLine**, veya **Writelineıf** tarafından put ileti aynı satırda başlar **yazma** veya **Writeıf** deyimi:</span><span class="sxs-lookup"><span data-stu-id="4307b-115">The next message put out by a **Write**, **WriteIf**, **WriteLine**, or **WriteLineIf** will begin on the same line as the message put out by the **Write** or **WriteIf** statement:</span></span>  
  
    ```vb  
    Dim errorFlag As Boolean = False  
    Trace.WriteIf(errorFlag, "Error in AppendData procedure.")  
    Debug.WriteIf(errorFlag, "Transaction abandoned.")  
    Trace.Write("Invalid value for data request")  
    ```  
  
    ```csharp  
    bool errorFlag = false;  
    System.Diagnostics.Trace.WriteIf(errorFlag,   
       "Error in AppendData procedure.");  
    System.Diagnostics.Debug.WriteIf(errorFlag, "Transaction abandoned.");  
    Trace.Write("Invalid value for data request");  
    ```  
  
### <a name="to-verify-that-certain-conditions-exist-either-before-or-after-you-execute-a-method"></a><span data-ttu-id="4307b-116">Doğrulamak için bu belirli koşullar, önce veya sonra bir yöntem yürütülmeye mevcut</span><span class="sxs-lookup"><span data-stu-id="4307b-116">To verify that certain conditions exist either before or after you execute a method</span></span>  
  
1.  <span data-ttu-id="4307b-117">Çağrı <xref:System.Diagnostics.Trace.Assert%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="4307b-117">Call the <xref:System.Diagnostics.Trace.Assert%2A> method.</span></span>  
  
    ```vb  
    Dim i As Integer = 4  
    Trace.Assert(i = 5, "i is not equal to 5.")  
    ```  
  
    ```csharp  
    int i = 4;  
    System.Diagnostics.Trace.Assert(i == 5, "i is not equal to 5.");  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4307b-118">Kullanabileceğiniz **Assert** izleme ve hata ayıklama ile.</span><span class="sxs-lookup"><span data-stu-id="4307b-118">You can use **Assert** with both tracing and debugging.</span></span> <span data-ttu-id="4307b-119">Bu örnekte tüm dinleyici için çağrı yığını çıkarır **dinleyicileri** koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="4307b-119">This example outputs the call stack to any listener in the **Listeners** collection.</span></span> <span data-ttu-id="4307b-120">Daha fazla bilgi için bkz: [yönetilen koddaki onaylar](/visualstudio/debugger/assertions-in-managed-code) ve <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4307b-120">For more information, see [Assertions in Managed Code](/visualstudio/debugger/assertions-in-managed-code) and <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4307b-121">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="4307b-121">See Also</span></span>  
 <xref:System.Diagnostics.Debug.WriteIf%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.Debug.WriteLineIf%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.Trace.WriteIf%2A?displayProperty=nameWithType>  
 <xref:System.Diagnostics.Trace.WriteLineIf%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="4307b-122">İzleme ve uygulamaları</span><span class="sxs-lookup"><span data-stu-id="4307b-122">Tracing and Instrumenting Applications</span></span>](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)  
 [<span data-ttu-id="4307b-123">Nasıl yapılır: oluşturma ve başlatma izleme anahtarları</span><span class="sxs-lookup"><span data-stu-id="4307b-123">How to: Create, Initialize and Configure Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/how-to-create-initialize-and-configure-trace-switches.md)  
 [<span data-ttu-id="4307b-124">İzleme anahtarları</span><span class="sxs-lookup"><span data-stu-id="4307b-124">Trace Switches</span></span>](../../../docs/framework/debug-trace-profile/trace-switches.md)  
 [<span data-ttu-id="4307b-125">İzleme dinleyicileri</span><span class="sxs-lookup"><span data-stu-id="4307b-125">Trace Listeners</span></span>](../../../docs/framework/debug-trace-profile/trace-listeners.md)