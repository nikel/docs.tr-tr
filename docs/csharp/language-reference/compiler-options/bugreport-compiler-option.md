---
title: "-bugreport (C# Derleyici Seçenekleri)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d2a6c27454cc8f95b9662d6ae688471849c5cee0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="-bugreport-c-compiler-options"></a>-bugreport (C# Derleyici Seçenekleri)
Hata ayıklama bilgileri daha sonra çözümlemek için bir dosya yerleştirilmesi gerektiğini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a>Arguments  
 `file`  
 Hata raporu içeren istediğiniz dosyanın adı.  
  
## <a name="remarks"></a>Açıklamalar  
 **- Bugreport** seçeneği belirtir, aşağıdaki bilgileri yerleştirilmelidir `file`:  
  
-   Derlemedeki tüm kaynak kodu dosyaları bir kopyası.  
  
-   Derlemede kullanılan derleyici seçeneklerinin listesi.  
  
-   Derleyici, çalıştırma ve işletim sistemi hakkında sürüm bilgisi.  
  
-   Başvurulan derlemeler ve modüller, .NET Framework ve SDK ile birlikte gönderilen derlemeler dışında onaltılık basamak olarak kaydedilir.  
  
-   Derleyici çıkışı, varsa.  
  
-   İçin istenir sorunun açıklaması.  
  
-   Sorunu nasıl düşündüğünüz bir açıklama için istenir sabit.  
  
 Bu seçenek ile kullanıldığında **- errorreport: istemi** veya **- errorreport: gönderme**, Microsoft Corporation'a dosyasındaki bilgiler gönderilir.  
  
 Tüm kaynak kodu dosyaları bir kopyasını yerleştirilecek çünkü `file`, kısa olası programı şüpheli kod hatası yeniden oluşturmak isteyebilirsiniz.  
  
 Bu derleyici seçeneği Visual Studio'da kullanılamıyor ve programlı olarak değiştirilemez.  
  
 Oluşturulan dosyanın içeriğini bilgilerin yanlışlıkla açığa çıkmasına neden kaynak kodu kullanıma dikkat edin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# Derleyici Seçenekleri](../../../csharp/language-reference/compiler-options/index.md)  
 [-errorreport (C# Derleyici Seçenekleri)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)  
 [Proje ve Çözüm Özelliklerini Yönetme](/visualstudio/ide/managing-project-and-solution-properties)
