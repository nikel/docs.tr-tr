---
title: "Nesne İfadeleri (F#)"
description: "Ek kod ve yeni, oluşturmak için gerekli ek yükünü engellemek istediğinizde F # nesne ifadeleri kullanmayı türü adlı öğrenin."
keywords: "Visual f #, f # işlevsel programlama"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c6dcf4c9-e7fd-4eee-9e4e-1176f4c27f57
ms.openlocfilehash: 28660d430473de02a8a55e37a26609827b364012
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="object-expressions"></a>Nesne İfadeleri

Bir *nesne ifadesi* dinamik olarak oluşturulan, anonim nesne türü yeni bir örneğini oluşturan bir ifade bir varolan temel türü, arabirim veya arabirim kümesine dayalıdır.


## <a name="syntax"></a>Sözdizimi

```fsharp
// When typename is a class:
{ new typename [type-params]arguments with
    member-definitions
    [ additional-interface-definitions ]
}
// When typename is not a class:
{ new typename [generic-type-args] with
    member-definitions
    [ additional-interface-definitions ]
}
```

## <a name="remarks"></a>Açıklamalar
Önceki sözdiziminde *typename* varolan bir sınıf veya arabirim türü temsil eder. *Tür parametreleri* isteğe bağlı genel tür parametreleri açıklar. *Bağımsız değişkenleri* Oluşturucu parametreleri gerektiren yalnızca sınıf türleri için kullanılır. *Üye tanımları* taban sınıf yöntemlerini, geçersiz kılmalar ya da bir taban sınıf veya arabirim soyut yöntemler uygulamaları.

Aşağıdaki örnek, birkaç farklı türde nesne ifadeleri gösterilmektedir.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4301.fs)]

## <a name="using-object-expressions"></a>Nesne ifadeleri kullanma
Türü adlı gerekli yeni bir oluşturmak için ek yükü ve ek kod engellemek istediğinizde nesne ifadeleri kullanın. Nesne ifadeleri bir programda oluşturulan türleri sayısını en aza indirmek için kullanırsanız, kod satırı sayısını azaltın ve türleri gereksiz artışı engelleyebilirsiniz. Yalnızca özel durumları işlemek için birçok türleri oluşturmak yerine, mevcut bir türle özelleştirir veya elinizdeki belirli çalışması için uygun bir uygulaması, bir arabirim sağlayan bir nesne ifadesi kullanabilirsiniz.


## <a name="see-also"></a>Ayrıca Bkz.
[F # dili başvurusu](index.md)
