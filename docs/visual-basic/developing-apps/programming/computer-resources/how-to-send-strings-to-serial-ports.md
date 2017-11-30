---
title: "Nasıl Yapılır: Visual Basic'te Seri Bağlantı Noktalarına Dizeler Gönderme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ports, sending strings to
- strings [Visual Basic], sending to serial ports
- My.Computer.Ports object
- serial ports, sending strings to
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 95c67b344572d21f418cbc14d350e6ff28611bd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-send-strings-to-serial-ports-in-visual-basic"></a><span data-ttu-id="6abf0-102">Nasıl Yapılır: Visual Basic'te Seri Bağlantı Noktalarına Dizeler Gönderme</span><span class="sxs-lookup"><span data-stu-id="6abf0-102">How to: Send Strings to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="6abf0-103">Bu konuda nasıl kullanılacağını açıklar `My.Computer.Ports` bilgisayarın seri bağlantı noktalarına dizeler gönderme için [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6abf0-103">This topic describes how to use `My.Computer.Ports` to send strings to the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="example"></a><span data-ttu-id="6abf0-104">Örnek</span><span class="sxs-lookup"><span data-stu-id="6abf0-104">Example</span></span>  
 <span data-ttu-id="6abf0-105">Bu örnek, bir dize COM1 seri bağlantı noktasına gönderir.</span><span class="sxs-lookup"><span data-stu-id="6abf0-105">This example sends a string to the COM1 serial port.</span></span> <span data-ttu-id="6abf0-106">Bilgisayarınızda farklı bir seri bağlantı noktası kullanmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="6abf0-106">You may need to use a different serial port on your computer.</span></span>  
  
 <span data-ttu-id="6abf0-107">Kullanım `My.Computer.Ports.OpenSerialPort` bir başvuru noktasına elde etmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="6abf0-107">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="6abf0-108">Daha fazla bilgi için bkz. <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="6abf0-108">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
 <span data-ttu-id="6abf0-109">`Using` Bloğu bir özel durum oluşturursa bile seri bağlantı noktasını kapatmak uygulama izin verir.</span><span class="sxs-lookup"><span data-stu-id="6abf0-109">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="6abf0-110">Seri bağlantı noktası yöneten tüm kod bu bloğu içinde veya içinde görünmesi gereken bir `Try...Catch...Finally` bloğu.</span><span class="sxs-lookup"><span data-stu-id="6abf0-110">All code that manipulates the serial port should appear within this block or within a `Try...Catch...Finally` block.</span></span>  
  
 <span data-ttu-id="6abf0-111"><xref:System.IO.Ports.SerialPort.WriteLine%2A> Yöntemi verileri seri bağlantı noktasına gönderir.</span><span class="sxs-lookup"><span data-stu-id="6abf0-111">The <xref:System.IO.Ports.SerialPort.WriteLine%2A> method sends the data to the serial port.</span></span>  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-send-strings-to-serial-ports_1.vb)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6abf0-112">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="6abf0-112">Compiling the Code</span></span>  
  
-   <span data-ttu-id="6abf0-113">Bu örnek kullandığınızı varsayar `COM1`.</span><span class="sxs-lookup"><span data-stu-id="6abf0-113">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6abf0-114">Güçlü Programlama</span><span class="sxs-lookup"><span data-stu-id="6abf0-114">Robust Programming</span></span>  
 <span data-ttu-id="6abf0-115">Bu örnek kullandığınızı varsayar `COM1`; daha fazla esneklik için kod istenilen seri bağlantı noktası kullanılabilir bağlantı noktaları listesinden seçmek kullanıcı sağlamalıdır.</span><span class="sxs-lookup"><span data-stu-id="6abf0-115">This example assumes the computer is using `COM1`; for more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="6abf0-116">Daha fazla bilgi için bkz: [nasıl yapılır: kullanılabilir seri bağlantı noktalarını göster](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="6abf0-116">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="6abf0-117">Bu örnekte bir `Using` bloğu bir özel durum oluşturursa bile uygulama bağlantı noktasını kapatır emin olun.</span><span class="sxs-lookup"><span data-stu-id="6abf0-117">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="6abf0-118">Daha fazla bilgi için bkz: [kullanarak deyimi](../../../../visual-basic/language-reference/statements/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6abf0-118">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6abf0-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6abf0-119">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>  
 [<span data-ttu-id="6abf0-120">Nasıl yapılır: seri bağlantı noktalarına ekli modemleri çevirme</span><span class="sxs-lookup"><span data-stu-id="6abf0-120">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)  
 [<span data-ttu-id="6abf0-121">Nasıl yapılır: kullanılabilir seri bağlantı noktalarını gösterme</span><span class="sxs-lookup"><span data-stu-id="6abf0-121">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)