---
title: "Düğme Stilleri ve Şablonları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- states [WPF], Button
- parts [WPF], Button
- styles [WPF], Button
- Button [WPF], styles and templates
- templates [WPF], Button
- ControlTemplate [WPF], Button
ms.assetid: e223c759-f8c4-4717-acfb-b1e40bdf5f3b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d783b3141463ca2c74ddd649848ea49e154415b6
ms.sourcegitcommit: 96cc82cac4650adfb65ba351506d8a8fbcd17b5c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/19/2018
---
# <a name="button-styles-and-templates"></a>Düğme Stilleri ve Şablonları
Stilleri ve şablonları için bu konuda açıklanmaktadır <xref:System.Windows.Controls.Button> denetim. Varsayılan değiştirebileceğiniz <xref:System.Windows.Controls.ControlTemplate> denetimi benzersiz bir görünüm vermek için. Daha fazla bilgi için bkz: [ControlTemplate oluşturarak varolan denetiminin görünümünü özelleştirme](../../../../docs/framework/wpf/controls/customizing-the-appearance-of-an-existing-control.md).  
  
## <a name="button-parts"></a>Düğme bölümleri  
 <xref:System.Windows.Controls.Button> Denetim adlandırılmış tüm bölümler sahip değil.  
  
## <a name="button-states"></a>Düğme durumları  
 Aşağıdaki tablo için görsel durumlarını listeler <xref:System.Windows.Controls.Button> denetim.  
  
|VisualState adı|VisualStateGroup adı|Açıklama|  
|-|-|-|  
|Normal|CommonStates|Varsayılan durumu.|  
|Fare üzerinde|CommonStates|Fare işaretçisini üzerinde denetim konumlandırıldı.|  
|Basılı|CommonStates|Denetim basıldığında.|  
|Devre dışı|CommonStates|Denetim devre dışı bırakıldı.|  
|Odaklanmış|FocusStates|Denetimi odağa sahip.|  
|Odaksız|FocusStates|Denetim odağı yok.|  
|Geçerli|ValidationStates|Denetim kullanan <xref:System.Windows.Controls.Validation> sınıfı ve <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> iliştirilmiş özelliği `false`.|  
|InvalidFocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` ve denetimi odağa sahip.|  
|InvalidUnfocused|ValidationStates|<xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> Ekli özellik `true` ve denetimi odağa sahip değil.|  
  
## <a name="button-controltemplate-example"></a>Düğme ControlTemplate Örneği  
 Aşağıdaki örnekte nasıl tanımlanacağı gösterilmektedir bir <xref:System.Windows.Controls.ControlTemplate> için <xref:System.Windows.Controls.Button> denetim.  
  
 [!code-xaml[ControlTemplateExamples#Button](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/button.xaml#button)]  
  
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
