---
title: "Nasıl yapılır: Windows API'larını Çağırma (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- API calls [Visual Basic]
- Windows API, calling
- API calls [Visual Basic], platform invoke
- calls [Visual Basic], stored procedures
ms.assetid: 27d75f0a-54ab-4ee1-b91d-43513a19b12d
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a219e031cdd36c713db8dcee6cc1da3849c9cf93
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-windows-apis-visual-basic"></a><span data-ttu-id="c08ca-102">Nasıl yapılır: Windows API'larını Çağırma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c08ca-102">How to: Call Windows APIs (Visual Basic)</span></span>
<span data-ttu-id="c08ca-103">Bu örnek tanımlar ve çağırır `MessageBox` user32.dll işlevinde ve bir dize geçirir.</span><span class="sxs-lookup"><span data-stu-id="c08ca-103">This example defines and calls the `MessageBox` function in user32.dll and then passes a string to it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c08ca-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="c08ca-104">Example</span></span>  
 [!code-vb[VbVbalrInterop#1](../../../visual-basic/programming-guide/com-interop/codesnippet/VisualBasic/how-to-call-windows-apis_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c08ca-105">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="c08ca-105">Compiling the Code</span></span>  
 <span data-ttu-id="c08ca-106">Bu örnek gerektirir:</span><span class="sxs-lookup"><span data-stu-id="c08ca-106">This example requires:</span></span>  
  
-   <span data-ttu-id="c08ca-107">Bir başvuru <xref:System> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="c08ca-107">A reference to the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c08ca-108">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="c08ca-108">Robust Programming</span></span>  
 <span data-ttu-id="c08ca-109">Aşağıdaki koşullar özel bir duruma neden olabilir:</span><span class="sxs-lookup"><span data-stu-id="c08ca-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="c08ca-110">Yöntemi statik değil, Özet veya önceden tanımlanmış.</span><span class="sxs-lookup"><span data-stu-id="c08ca-110">The method is not static, is abstract, or has been previously defined.</span></span> <span data-ttu-id="c08ca-111">Bir arabirim ya da uzunluğu üst türüdür *adı* veya *dll* sıfırdır.</span><span class="sxs-lookup"><span data-stu-id="c08ca-111">The parent type is an interface, or the length of *name* or *dllName* is zero.</span></span> <span data-ttu-id="c08ca-112">(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="c08ca-112">(<xref:System.ArgumentException>)</span></span>  
  
-   <span data-ttu-id="c08ca-113">*Adı* veya *dll* olan `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="c08ca-113">The *name* or *dllName* is `Nothing`.</span></span> <span data-ttu-id="c08ca-114">(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="c08ca-114">(<xref:System.ArgumentNullException>)</span></span>  
  
-   <span data-ttu-id="c08ca-115">İçeren türü kullanılarak önceden oluşturuldu `CreateType`.</span><span class="sxs-lookup"><span data-stu-id="c08ca-115">The containing type has been previously created using `CreateType`.</span></span> <span data-ttu-id="c08ca-116">(<xref:System.InvalidOperationException>)</span><span class="sxs-lookup"><span data-stu-id="c08ca-116">(<xref:System.InvalidOperationException>)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08ca-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c08ca-117">See Also</span></span>  
 [<span data-ttu-id="c08ca-118">Yakından Platform çağırma</span><span class="sxs-lookup"><span data-stu-id="c08ca-118">A Closer Look at Platform Invoke</span></span>](http://msdn.microsoft.com/en-us/ba9dd55b-2eaa-45cd-8afd-75cb8d64d243)  
 [<span data-ttu-id="c08ca-119">Platform çağırma örnekleri</span><span class="sxs-lookup"><span data-stu-id="c08ca-119">Platform Invoke Examples</span></span>](../../../framework/interop/platform-invoke-examples.md)  
 [<span data-ttu-id="c08ca-120">Yönetilmeyen DLL işlevlerini kullanma</span><span class="sxs-lookup"><span data-stu-id="c08ca-120">Consuming Unmanaged DLL Functions</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md)  
 [<span data-ttu-id="c08ca-121">Yansıma ile bir yöntem tanımlama yayma</span><span class="sxs-lookup"><span data-stu-id="c08ca-121">Defining a Method with Reflection Emit</span></span>](http://msdn.microsoft.com/en-us/84fd3bf6-628f-41aa-83d9-b990cf926e81)  
 [<span data-ttu-id="c08ca-122">İzlenecek yol: Windows API'larını çağırma</span><span class="sxs-lookup"><span data-stu-id="c08ca-122">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)  
 [<span data-ttu-id="c08ca-123">COM birlikte çalışma</span><span class="sxs-lookup"><span data-stu-id="c08ca-123">COM Interop</span></span>](../../../visual-basic/programming-guide/com-interop/index.md)