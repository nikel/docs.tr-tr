---
title: "Nasıl yapılır: Görsel Taslağı Başladıktan Sonra Denetlemek için Olay Tetikleyicilerini Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7d9e096969713cc4b9c42261b238691d51cb49d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="b1602-102">Nasıl yapılır: Görsel Taslağı Başladıktan Sonra Denetlemek için Olay Tetikleyicilerini Kullanma</span><span class="sxs-lookup"><span data-stu-id="b1602-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="b1602-103">Bu örnek nasıl denetleneceğini gösterir bir <xref:System.Windows.Media.Animation.Storyboard> başladıktan sonra.</span><span class="sxs-lookup"><span data-stu-id="b1602-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="b1602-104">Başlamak için bir <xref:System.Windows.Media.Animation.Storyboard> kullanarak [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], kullanmak <xref:System.Windows.Media.Animation.BeginStoryboard>, nesneleri ve özellikleri hale getirmeyi ve film şeridi başlar animasyonları dağıtır.</span><span class="sxs-lookup"><span data-stu-id="b1602-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="b1602-105">Size, <xref:System.Windows.Media.Animation.BeginStoryboard> belirterek bir isim kendi <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> özelliği, onu bir denetlenebilir film şeridi yapın.</span><span class="sxs-lookup"><span data-stu-id="b1602-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="b1602-106">Başladıktan sonra film şeridi etkileşimli olarak denetleyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b1602-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="b1602-107">İle birlikte aşağıdaki film şeridi eylemlerini kullanmak <xref:System.Windows.EventTrigger> film şeridi denetlemek için nesneleri.</span><span class="sxs-lookup"><span data-stu-id="b1602-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
-   <span data-ttu-id="b1602-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Film şeridi duraklatır.</span><span class="sxs-lookup"><span data-stu-id="b1602-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
-   <span data-ttu-id="b1602-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Duraklatılmış film şeridi sürdürür.</span><span class="sxs-lookup"><span data-stu-id="b1602-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
-   <span data-ttu-id="b1602-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Film şeridi hızını değiştirir.</span><span class="sxs-lookup"><span data-stu-id="b1602-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
-   <span data-ttu-id="b1602-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Varsa, film şeridi dolgu süresinin sonuna ilerletir.</span><span class="sxs-lookup"><span data-stu-id="b1602-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
-   <span data-ttu-id="b1602-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Film şeridi durdurur.</span><span class="sxs-lookup"><span data-stu-id="b1602-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
-   <span data-ttu-id="b1602-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Kaynakları serbest bırakma film şeridi kaldırır.</span><span class="sxs-lookup"><span data-stu-id="b1602-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1602-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="b1602-114">Example</span></span>  
 <span data-ttu-id="b1602-115">Aşağıdaki örnek, etkileşimli olarak film şeridi denetlemek için denetlenebilir film şeridi eylemleri kullanır.</span><span class="sxs-lookup"><span data-stu-id="b1602-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="b1602-116">**Not:** , kod kullanarak bir film şeridi denetleme bir örnek için bkz [bir film şeridi sonra onu başlatır ITS etkileşimli yöntemlerini kullanarak denetim](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="b1602-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="b1602-117">Ek örnekler için bkz: [animasyon örnek Galerisi](http://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="b1602-117">For additional examples, see the [Animation Example Gallery](http://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1602-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b1602-118">See Also</span></span>  
 <xref:System.Windows.Media.Animation.ResumeStoryboard>  
 <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>  
 <xref:System.Windows.Media.Animation.SkipStoryboardToFill>  
 <xref:System.Windows.Media.Animation.PauseStoryboard>  
 <xref:System.Windows.Media.Animation.StopStoryboard>  
 <xref:System.Windows.Media.Animation.SeekStoryboard>  
 [<span data-ttu-id="b1602-119">Etkileşimli yöntemlerini kullanarak başladıktan sonra film şeridi kontrol etme</span><span class="sxs-lookup"><span data-stu-id="b1602-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-storyboard-after-it-starts.md)  
 [<span data-ttu-id="b1602-120">Animasyon genel bakış</span><span class="sxs-lookup"><span data-stu-id="b1602-120">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="b1602-121">Film şeritleri genel bakış</span><span class="sxs-lookup"><span data-stu-id="b1602-121">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)