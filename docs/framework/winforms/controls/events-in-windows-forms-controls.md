---
title: Windows Forms Denetimlerindeki Olaylar
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- events [Windows Forms], custom controls (using code)
- custom controls [Windows Forms], events overview (using code)
ms.assetid: 7e3d1379-87aa-437c-afce-c99454eff30e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2dba74214fe439e09d1855f7ab248c075bd8257c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="events-in-windows-forms-controls"></a>Windows Forms Denetimlerindeki Olaylar
Bir Windows Forms denetimi birden fazla altmış olaylarından devralır <xref:System.Windows.Forms.Control?displayProperty=nameWithType>. Bunlar <xref:System.Windows.Forms.Control.Paint> çizilecek denetim neden olan olay, bir pencere gibi görüntüleme için ilgili olayları <xref:System.Windows.Forms.Control.Resize> ve <xref:System.Windows.Forms.Control.Layout> olayları ve alt düzey fare ve klavye olayları. Alt düzey bazı olaylar tarafından oluşturulan <xref:System.Windows.Forms.Control> anlamsal olayları gibi içine <xref:System.Windows.Forms.Control.Click> ve <xref:System.Windows.Forms.Control.DoubleClick>. Devralınan olaylar hakkında daha fazla ayrıntı için bkz: <xref:System.Windows.Forms.Control>.  
  
 Özel denetim devralınmış olay işlevi geçersiz kılması gerekiyorsa, devralınan geçersiz kılma `On` *EventName* temsilci ekleme yerine yöntemi. .NET Framework olay modelinde alışık değilseniz bkz [oluşturma olayları bir bileşenin](http://msdn.microsoft.com/library/9aebf605-a87d-470b-b7c8-f9abfc8360a0).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OnPaint Yöntemini Geçersiz Kılma](../../../../docs/framework/winforms/controls/overriding-the-onpaint-method.md)  
 [Kullanıcı Girişini İşleme](../../../../docs/framework/winforms/controls/handling-user-input.md)  
 [Olay Tanımlama](../../../../docs/framework/winforms/controls/defining-an-event-in-windows-forms-controls.md)  
 [Olaylar](../../../../docs/standard/events/index.md)
