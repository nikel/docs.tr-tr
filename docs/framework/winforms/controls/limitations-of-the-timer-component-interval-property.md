---
title: Windows Forms süreölçer bileşeni sınırlamaları&#39;s aralık özelliği
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e9c42a0946cf29415f7bb12345da6784e0c276d5
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/23/2018
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a>Windows Forms süreölçer bileşeni sınırlamaları&#39;s aralık özelliği
Windows Forms <xref:System.Windows.Forms.Timer> bileşen bir <xref:System.Windows.Forms.Timer.Interval%2A> özelliği yalnızca bir süreölçer olayı ve sonraki arasında geçen süreyi milisaniye olarak belirtir. Bileşen devre dışı bırakılmadığı sürece bir süreölçer almaya devam eder <xref:System.Windows.Forms.Timer.Tick> süre kabaca eşit aralıklarla olay.  
  
 Bu bileşen, bir Windows Forms ortamı için tasarlanmıştır. Bir sunucu ortamı için uygun bir süreölçer gerekirse bkz [sunucu tabanlı zamanlayıcılar giriş](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).  
  
## <a name="the-interval-property"></a>Aralık özelliği  
 <xref:System.Windows.Forms.Timer.Interval%2A> Özelliği, ne zaman programlama dikkate alınması gereken birkaç sınırlamalara sahiptir bir <xref:System.Windows.Forms.Timer> bileşen:  
  
-   Uygulamanızı veya başka bir uygulama sistem üzerinde ağır taleplerini değiştirirken, — uzun döngüler, yoğun hesaplamalar veya sürücü, ağ veya bağlantı noktası erişim gibi — uygulamanızı Süreölçer olayları kadar sık olarak alamayabilirsiniz <xref:System.Windows.Forms.Timer.Interval%2A> özelliği belirtir.  
  
-   Aralık tam zamanında geçmesi garanti edilmez. Doğruluk emin olmak için Zamanlayıcı gerektiği gibi sistem saatini denetleyin yerine biriken zaman dahili olarak izlemek deneyin.  
  
-   Kesinliğini <xref:System.Windows.Forms.Timer.Interval%2A> milisaniye cinsinden bir özelliktir. Bazı bilgisayarlarda milisaniye yüksek çözünürlüğe olan yüksek çözünürlüklü bir sayaç sağlar. Bu tür bir sayaç kullanılabilirliği bilgisayarınızı işlemci donanımda bağlıdır. Makale 172338, "Nasıl için kullanım QueryPerformanceCounter için zamanı kodu," adresindeki Microsoft Bilgi Bankası'nda daha fazla bilgi için bkz: http://support.microsoft.com.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Windows.Forms.Timer>  
 [Süreölçer Bileşeni](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Süreölçer Bileşenine Genel Bakış](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
