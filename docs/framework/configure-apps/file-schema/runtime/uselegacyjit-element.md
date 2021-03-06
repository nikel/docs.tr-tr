---
title: "&lt;useLegacyJit&gt; öğesi"
ms.custom: 
ms.date: 04/26/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9d2a71e44db2d6e85ae730f4603bf191f54525c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltuselegacyjitgt-element"></a>&lt;useLegacyJit&gt; öğesi

Ortak dil çalışma zamanı için tam zamanında derleme eski 64-bit JIT Derleyici kullanıp kullanmadığını belirler.  
  
\<Yapılandırma >  
\<çalışma zamanı >  
\<useLegacyJit >
  
## <a name="syntax"></a>Sözdizimi  
  
```xml
<useLegacyJit enabled=0|1 />
```

Öğe adı `useLegacyJit` küçük harfe duyarlıdır.
  
## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler

Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
| Öznitelik | Açıklama                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | Gerekli öznitelik.<br><br>Çalışma zamanı eski 64-bit JIT Derleyici kullanıp kullanmadığını belirtir. |  
  
### <a name="enabled-attribute"></a>Etkin özniteliği  
  
| Değer | Açıklama                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | Ortak dil çalışma zamanı .NET Framework 4.6 ve sonraki sürümlerinde bulunan yeni 64-bit JIT Derleyici kullanır. |  
| 1.     | Ortak dil çalışma zamanı eski 64-bit JIT Derleyici kullanır.                                                     |  
  
### <a name="child-elements"></a>Alt öğeleri

Yok.
  
### <a name="parent-elements"></a>Üst öğeler  
  
| Öğe         | Açıklama                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | Her yapılandırma dosyasında yer alan ve ortak dil çalışma zamanı ve .NET Framework uygulamaları tarafından kullanılan kök öğe. |  
| `runtime`       | Çalışma zamanı başlatma seçenekleri hakkında bilgi içerir.                                                        |  
  
## <a name="remarks"></a>Açıklamalar  

.NET Framework 4.6 ile başlayarak, ortak dil çalışma zamanı yeni bir 64 bit derleyici Just-In-Time (JIT) derleme için varsayılan olarak kullanır. Bazı durumlarda, bu davranışı fark JIT derlenmiş önceki sürümü 64-bit JIT Derleyici tarafından uygulama kodu neden olabilir. Ayarlayarak `enabled` özniteliği `<useLegacyJit>` öğesine `1`, yeni 64-bit JIT Derleyici devre dışı bırakabilir ve bunun yerine eski 64-bit JIT Derleyici kullanarak uygulamanızı derleyin.  
  
> [!NOTE]
> `<useLegacyJit>` Öğesi yalnızca 64-bit JIT derleme etkiler. 32-bit JIT derleyicisi ile derleme etkilenmez.  
  
Bir yapılandırma dosyası ayarı kullanmak yerine, diğer iki yolla eski 64-bit JIT Derleyici etkinleştirebilirsiniz:  
  
- Bir ortam değişkeni ayarlama

  Ayarlama `COMPLUS_useLegacyJit` ya da ortam değişkeni `0` (yeni 64-bit JIT Derleyici kullanın) veya `1` (eski 64-bit JIT Derleyici kullanın):
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  Ortam değişkeni sahip *genel kapsam*, etkilediği anlamına tüm uygulamaları makinede çalıştırın. Ayarlama, bu uygulama yapılandırma dosyası ayarı tarafından geçersiz kılınabilir durumunda. Ortam değişkeni adı büyük küçük harfe duyarlı değil.
  
- Bir kayıt defteri anahtarı ekleme

  Eski 64-bit JIT Derleyici ekleyerek etkinleştirebilirsiniz bir `REG_DWORD` değeri ya da `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` veya `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` kayıt defterinde anahtar. Adlı değer `useLegacyJit`. Değer 0 ise, yeni derleyici kullanılır. Değer 1 ise, eski 64-bit JIT Derleyici etkinleştirilir. Kayıt defteri değerinin adını büyük küçük harfe duyarlı değil.
  
  Değer ekleme `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` anahtar makine üzerinde çalışan tüm uygulamaları etkiler. Değer ekleme `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` anahtar geçerli kullanıcı tarafından çalıştırılan tüm uygulamaları etkiler. Bir makine birden çok kullanıcı hesabı ile yapılandırılmışsa, değer de diğer kullanıcılar için kayıt defteri anahtarları için eklenene kadar yalnızca geçerli kullanıcı tarafından çalıştırılan uygulamalar etkilenmez. Ekleme `<useLegacyJit>` öğesi bir yapılandırma dosyasına mevcut değilse kayıt defteri ayarları geçersiz kılar.  
  
## <a name="example"></a>Örnek  

Aşağıdaki yapılandırma dosyası derleme yeni 64-bit JIT derleyicisi ile devre dışı bırakır ve bunun yerine eski 64-bit JIT Derleyici kullanır.  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Ayrıca bkz.

[\<çalışma zamanı > öğesi](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
[\<Yapılandırma > öğesi](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
[Azaltma: Yeni 64-bit JIT derleme](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
