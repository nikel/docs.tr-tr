---
title: "PNRP uygulama geliştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 265615d6-4423-4b5d-8626-752e456f4f4e
caps.latest.revision: "6"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d11f1b284ebb4e4a44d1dad442f727692fa26ffa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="pnrp-in-application-development"></a>PNRP uygulama geliştirme
Windows Vista'da ağ uygulamaları ad yayını ve çözümleme işlevleri bir Basitleştirilmiş PNRP uygulama programlama arabirimi (API) erişebilir.  
  
## <a name="implementing-the-peer-name-resolution-protocol"></a>Eş Adı Çözümleme Protokolü'nü uygulama  
 Basitleştirilmiş PNRP API ile bulut açıkça adı ve adreslerini kaydetmek için belirtilmeyen; PNRP bileşen otomatik olarak uygun bulut birleştirme ve Bulutlar içinde yayımlamak için adresleri belirler.  
  
 Yüksek oranda Basitleştirilmiş PNRP ad çözümlemesi için Windows Vista'da, PNRP adlarını artık Windows yuvaları işlevi getaddrinfo() tümleşiktir. Bir IPv6 adresi için bir adı çözümlemek için PNRP kullanmak için uygulamaları getaddrinfo() işlevi tam etki alanı adı (FQDN) name.prnp.net çözmek için kullanabilir hangi adının çözümlendiği eş adıdır. Windows Vista'da ayrılmış olarak etki alanı PNRP ad çözümlemesi için pnrp.net etki alanıdır.  
  
 İleti PeerToPeer uygulamalar arasında geçirme PeerChannel'a ve WCF gibi temel mimarileri tarafından işlenen hala [büyük veriler ve akış](http://go.microsoft.com/fwlink/?LinkID=179652).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Net.PeerToPeer>
