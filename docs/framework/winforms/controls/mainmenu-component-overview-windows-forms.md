---
title: "MainMenu Bileşenine Genel Bakış (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c8681635f2f97e74893704513f57313106168e52
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="mainmenu-component-overview-windows-forms"></a>MainMenu Bileşenine Genel Bakış (Windows Forms)
> [!IMPORTANT]
>  Ancak <xref:System.Windows.Forms.MenuStrip> ve <xref:System.Windows.Forms.ContextMenuStrip> değiştirin ve işlevsellik eklemek <xref:System.Windows.Forms.MainMenu> ve <xref:System.Windows.Forms.ContextMenu> önceki sürümlerinin denetimleri <xref:System.Windows.Forms.MainMenu> ve <xref:System.Windows.Forms.ContextMenu> seçerseniz geriye dönük uyumluluk ve gelecekte kullanım için korunur.  
  
 Windows Forms <xref:System.Windows.Forms.MainMenu> bileşen çalışma zamanında bir menü görüntüler. Ana menü ayrı öğeleri ve tüm alt menüler olan <xref:System.Windows.Forms.MenuItem> nesneleri.  
  
## <a name="key-properties"></a>Anahtar Özellikler  
 Menü öğesi ayarlayarak varsayılan öğesi olarak belirlenebilir <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> özelliğine `true`. Menü tıklatıldığında varsayılan öğe kalın metin olarak görünür. Menü öğesinin <xref:System.Windows.Forms.MenuItem.Checked%2A> özelliktir ya da `true` veya `false`ve menü öğesi seçili olup olmadığını gösterir. Menü öğesi'nin <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> özelliği seçili öğenin görünümünü özelleştiren: varsa <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> ayarlanır `true`, varsa öğenin yanında; radyo düğmesi görünür <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> ayarlanır `false`, öğenin yanında bir onay işareti görünür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.MainMenu>  
 <xref:System.Windows.Forms.Menu>  
 <xref:System.Windows.Forms.MenuItem>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 [MenuStrip Denetimine Genel Bakış](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
