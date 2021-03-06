---
title: "Üye aşırı yüklemesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- default arguments
- members [.NET Framework], overloaded
- member design guidelines [.NET Framework], overloading
- overloaded members
- signatures, members
ms.assetid: 964ba19e-8b94-4b5b-b1e3-5a0b531a0bb1
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2c84d70fb8c05dc295fc807c9a59085c47d0f455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="member-overloading"></a>Üye aşırı yüklemesi
Üye aşırı yüklemesi, iki veya daha fazla üye, yalnızca sayısını veya parametre türünü farklılık gösterir ancak aynı ada sahip aynı türde oluşturmak anlamına gelir. Örneğin, aşağıdakileri de `WriteLine` yöntemi aşırı yüklenmiş:  
  
```  
public static class Console {  
    public void WriteLine();  
    public void WriteLine(string value);  
    public void WriteLine(bool value);  
    ...  
}  
```  
  
 Yalnızca yöntemleri oluşturucular ve Dizinli Özellikler parametreleri olabileceğinden, bu üyeler yalnızca aşırı yüklenmiş.  
  
 Aşırı yüklemesi, kullanılabilirlik, verimliliği ve yeniden kullanılabilir kitaplıkları okunabilirliğini artırmak için en önemli teknikler biridir. Parametrelerin sayısı aşırı oluşturucular ve yöntemleri daha basit sürümlerini sağlamak mümkün kılar. Parametre türü aşırı yüklemesi farklı türleri seçili kümesi üzerinde aynı işlemler üyeleri için aynı üye adı kullanmayı mümkün kılar.  
  
 **✓ YAPMAK** kısa aşırı yüklemeler tarafından kullanılan varsayılan belirtmek için açıklayıcı parametre adları kullanmayı deneyin.  
  
 **KAÇININ x** rasgele aşırı parametre adlarında değişen. Aynı giriş başka bir aşırı içindeki bir parametre olarak bir aşırı parametresinde temsil ediyorsa parametreleri aynı ada sahip.  
  
 **KAÇININ x** parametrelerinde sıralama içinde tutarsız olan aşırı yüklenmiş üyeler. Aynı adlı parametreleri, tüm aşırı aynı konumda görüntülenmelidir.  
  
 **✓ YAPMAK** (genişletilebilirlik gerekliyse) yalnızca en uzun aşırı sanal olun. Daha kısa aşırı yalnızca üzerinden uzun bir aşırı yüklemesine çağırmanız gerekir.  
  
 **X yok** kullanmak `ref` veya `out` üyeleri aşırı yüklemeyi değiştiricileri.  
  
 Bazı diller şöyle aşırı çağrıları çözümlenemiyor. Ayrıca, bu tür aşırı genellikle tamamen farklı semantiklerine sahip ve büyük olasılıkla aşırı ancak iki ayrı yöntem bunun yerine olmamalıdır.  
  
 **X yok** aşırı aynı konuma ve benzer türleri parametrelerle henüz farklı semantiği ile sahip.  
  
 **✓ YAPMAK** izin `null` isteğe bağlı bağımsız değişkenler için geçirilecek.  
  
 **✓ YAPMAK** varsayılan bağımsız değişkenler üyeleriyle tanımlama yerine aşırı üye kullanın.  
  
 Varsayılan bağımsız değişkenler, CLS uyumlu değildir.  
  
 *Bölümleri © 2005, 2009 Microsoft Corporation. Tüm hakları saklıdır.*  
  
 *Pearson eğitim, Inc. şirketinin izni tarafından yeniden yazdırılmaları [Framework tasarım yönergeleri: kuralları, deyimleri ve yeniden kullanılabilir .NET kitaplıkları, 2 sürümü için desenleri](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina ve Brad Abrams tarafından 22 Eki 2008 tarafından yayımlanan Microsoft Windows geliştirme serisi bir parçası olarak Addison-Wesley Professional.*  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye Tasarımı Yönergeleri](../../../docs/standard/design-guidelines/member.md)  
 [Çerçeve Tasarım Yönergeleri](../../../docs/standard/design-guidelines/index.md)
