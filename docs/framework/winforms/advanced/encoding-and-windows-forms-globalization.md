---
title: "Kodlama ve Windows Forms Genelleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbac07e92d892913f2d2a342b2fa5b3d5fe2f40c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="13e35-102">Kodlama ve Windows Forms Genelleştirme</span><span class="sxs-lookup"><span data-stu-id="13e35-102">Encoding and Windows Forms Globalization</span></span>
<span data-ttu-id="13e35-103">Windows Forms uygulamaları tamamen Unicode her karakter hangi platformu, program veya dil olsun benzersiz bir numara tarafından temsil edilen anlamına gelir, etkinleştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="13e35-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="13e35-104">Unicode hakkında daha fazla bilgi için bkz: [Unicode Web sitesine](http://www.unicode.org).</span><span class="sxs-lookup"><span data-stu-id="13e35-104">For more information about Unicode, see the [Unicode consortium Web site](http://www.unicode.org).</span></span>  
  
## <a name="benefits-of-unicode"></a><span data-ttu-id="13e35-105">Unicode yararları</span><span class="sxs-lookup"><span data-stu-id="13e35-105">Benefits of Unicode</span></span>  
 <span data-ttu-id="13e35-106">Unicode etkin formlar avantajları olan komut dosyaları ile çalışma olanağını şunlardır yalnızca Unicode, Hintçe gibi.</span><span class="sxs-lookup"><span data-stu-id="13e35-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="13e35-107">Ayrıca, tek bir form üzerinde birden çok dil kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="13e35-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="13e35-108">Unicode olarak tüm karakterleri iki bayt uzun olduğundan hiçbir özel çaba çift baytlık karakterler temsil etmek için gereklidir.</span><span class="sxs-lookup"><span data-stu-id="13e35-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="13e35-109">Ayrıca, tüm platformlarda çalışır kod tek bir dizi yazabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="13e35-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="13e35-110">Bu önceki sürümlerden farklıdır [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], Windows NT gibi farklı platformları için farklı bir kod yazmak zorunda içinde ve [!INCLUDE[win98](../../../../includes/win98-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13e35-110">This is a change from previous versions of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], in which you had to write different code for different platforms, such as Windows NT and [!INCLUDE[win98](../../../../includes/win98-md.md)].</span></span>  
  
 <span data-ttu-id="13e35-111">Ancak, bazı denetimler Unicode desteklemeyen [!INCLUDE[win98](../../../../includes/win98-md.md)] ve Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="13e35-111">However, certain controls do not support Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] and Windows Millennium Edition.</span></span> <span data-ttu-id="13e35-112">Her biri ortak denetiminden devral, bu denetimleri olarak Windows kod sayfaları ile veri işleyecek [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="13e35-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span></span> <span data-ttu-id="13e35-113">Bu denetimler: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, ve <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="13e35-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="13e35-114">Sonuç olarak, bu denetimlerindeki listelenen platformlar Unicode verilerini görüntüleyemezsiniz.</span><span class="sxs-lookup"><span data-stu-id="13e35-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="13e35-115">Örneğin, Japonca karakterler İngilizce görüntüleyemiyor [!INCLUDE[win98](../../../../includes/win98-md.md)] işletim sistemi.</span><span class="sxs-lookup"><span data-stu-id="13e35-115">For example, you cannot display Japanese characters on an English [!INCLUDE[win98](../../../../includes/win98-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="13e35-116">Unicode uyumlu alternatifleri için <xref:System.Windows.Forms.ToolBar> ve <xref:System.Windows.Forms.StatusBar> denetimleri kullanın <xref:System.Windows.Forms.ToolStrip> ve <xref:System.Windows.Forms.StatusStrip> bu eski denetimleri Değiştir kontrol eder.</span><span class="sxs-lookup"><span data-stu-id="13e35-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="13e35-117">Benzer bir görünüm ve kullanımında uygulamanızda görsel öğeleri arasında korumak için kullanmak <xref:System.Windows.Forms.MenuStrip> denetim işleme menüleri yerine için <xref:System.Windows.Forms.MainMenu>.</span><span class="sxs-lookup"><span data-stu-id="13e35-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="13e35-118">Gibi <xref:System.Windows.Forms.ToolStrip> ve <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> ayrıca işlemek ve Unicode karakterler görüntüleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="13e35-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13e35-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="13e35-119">See Also</span></span>  
 [<span data-ttu-id="13e35-120">Windows Forms Genelleştirme</span><span class="sxs-lookup"><span data-stu-id="13e35-120">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)