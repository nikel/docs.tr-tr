---
title: "ProgressBar Stilleri ve Şablonları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parts [WPF], ProgressBar
- ProgressBar [WPF], styles and templates
- styles [WPF], ProgressBar
- ControlTemplate [WPF], ProgressBar
- templates [WPF], ProgressBar
- states [WPF], ProgressBar
ms.assetid: 935aa600-16e6-4947-a905-37a189a583dd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6809ce2f51af8a1baf535afa8fe80f4e5b5f53e9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="progressbar-styles-and-templates"></a>ProgressBar Stilleri ve Şablonları
Stilleri ve şablonları için bu konuda açıklanmaktadır <xref:System.Windows.Controls.ProgressBar> denetim. Varsayılan değiştirebileceğiniz <xref:System.Windows.Controls.ControlTemplate> denetimi benzersiz bir görünüm vermek için. Daha fazla bilgi için bkz: [ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="progressbar-parts"></a>ProgressBar bölümleri  
 Adlandırılmış bölümleri için aşağıdaki tabloda listelenmektedir <xref:System.Windows.Controls.ProgressBar> denetim.  
  
|Bölümü|Tür|Açıklama|  
|-|-|-|  
|PART_Indicator|<xref:System.Windows.FrameworkElement>|İlerleme durumunu gösteren nesne.|  
|PART_Track|<xref:System.Windows.FrameworkElement>|İlerleme göstergesi yolunu tanımlayan nesnesi.|  
|PART_GlowRect|<xref:System.Windows.FrameworkElement>|İlerleme çubuğu embellishes bir nesne.|  
  
## <a name="progressbar-states"></a>ProgressBar durumları  
 Aşağıdaki tablo için görsel durumlarını listeler <xref:System.Windows.Controls.ProgressBar> denetim.  
  
|VisualState adı|VisualStateGroup adı|Açıklama|  
|----------------------|---------------------------|-----------------|  
|Belirli|CommonStates|<xref:System.Windows.Controls.ProgressBar>temel ilerleme raporları <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> özelliği.|  
|Belirsiz|CommonStates|<xref:System.Windows.Controls.ProgressBar>Yinelenen bir desen ile genel ilerleme durumunu raporlar.|  
|Geçerli|ValidationStates|Denetim kullanan <xref:System.Windows.Controls.Validation> sınıfı ve <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> iliştirilmiş özelliği `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` sahip denetimi odağa sahip değil.|  
  
## <a name="progressbar-controltemplate-example"></a>ProgressBar ControlTemplate Örneği  
 Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir bir <xref:System.Windows.Controls.ControlTemplate> için <xref:System.Windows.Controls.ProgressBar> denetim.  
  
 [!code-xaml[ControlTemplateExamples#ProgressBar](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/progressbar.xaml#progressbar)]  
  
 Önceki örnekte, bir veya daha fazla aşağıdaki kaynakları kullanır.  
  
 [!code-xaml[ControlTemplateExamples#Resources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]  
  
 Tam bir örnek için bkz: [ControlTemplates örneği ile stil oluşturma](http://go.microsoft.com/fwlink/?LinkID=160041).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.FrameworkElement.Style%2A>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Denetim Stilleri ve Şablonları](../../../../docs/framework/wpf/controls/control-styles-and-templates.md)  
 [Denetim Özelleştirme](../../../../docs/framework/wpf/controls/control-customization.md)  
 [Stil ve Şablon Oluşturma](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [ControlTemplate Oluşturarak Varolan Denetimin Görünümünü Özelleştirme](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md)
