---
title: DotNet depolama komutu
description: "'Dotnet depo' komutu çalışma zamanı paketi deposunda belirtilen derlemelerini depolar."
author: bleroy
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 80ea40dfbedba3dca0e767b66e14f5de22374d4f
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2018
---
# <a name="dotnet-store"></a>DotNet deposu

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]

## <a name="name"></a>Ad

`dotnet store` -Belirtilen derlemelerde depolar [çalışma zamanı Paket Deposu](../deploying/runtime-store.md).

## <a name="synopsis"></a>Özet

`dotnet store -m|--manifest -f|--framework -r|--runtime  [--framework-version] [-h|--help] [--output] [--skip-optimization] [--skip-symbols] [-v|--verbosity] [--working-dir]`

## <a name="description"></a>Açıklama

`dotnet store` Belirtilen derlemelerde depolar [çalışma zamanı Paket Deposu](../deploying/runtime-store.md). Varsayılan olarak, derlemeleri hedef çalışma zamanı ve framework için getirilmiştir. Daha fazla bilgi için bkz: [çalışma zamanı Paket Deposu](../deploying/runtime-store.md) konu.

## <a name="required-options"></a>Gerekli seçenekler

`-f|--framework <FRAMEWORK>`

Belirtir [hedef framework](../../standard/frameworks.md).

`-m|--manifest <PATH_TO_MANIFEST_FILE>`

*Paket Deposu bildirim dosyası* depolamak için paketlerin listesini içeren bir XML dosyasıdır. Bildirim dosyasının biçimi ile uyumlu *csproj* biçimi. Bu nedenle, bir *csproj* istediğiniz paketleri başvuran proje dosyası ile kullanılabilir `-m|--manifest` derlemeleri çalışma zamanı paketi deposunda depolamak için seçeneği. Birden çok bildirim dosyası belirtmek için her dosya için yolu ve seçeneği yineleyin: `--manifest packages1.csproj --manifest packages2.csproj`.

`-r|--runtime <RUNTIME_IDENTIFIER>`

[Çalışma zamanı tanımlayıcı](../rid-catalog.md) hedef.

## <a name="optional-options"></a>İsteğe bağlı seçenekleri

`--framework-version <FRAMEWORK_VERSION>`

.NET Core SDK sürümünü belirtir. Bu seçeneği tarafından belirtilen framework ötesinde belirli framework sürümünü seçmenize olanak sağlar `-f|--framework` seçeneği.

`-h|--help`

Yardım bilgisi gösterir.

`-o|--output <OUTPUT_DIRECTORY>`

Çalışma zamanı paketi deposunun yolunu belirtir. Belirtilmezse, varsayılan olarak *depolamak* kullanıcı profili .NET Core yükleme dizininin alt.

`--skip-optimization`

İyileştirme aşamasından atlar.

`--skip-symbols`

Atlar nesil simge. Şu anda yalnızca Windows ve Linux üzerindeki simgelerin oluşturabilir.

`-v|--verbosity <LEVEL>`

Komutun ayrıntı düzeyi ayarlar. İzin verilen değerler `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, ve `diag[nostic]`.

`-w|--working-dir <INTERMEDIATE_WORKING_DIRECTORY>`

Komutu tarafından kullanılan çalışma dizini. Belirtilmezse, kullanan *obj* geçerli dizinin alt dizini.

## <a name="examples"></a>Örnekler

Belirtilen paketleri depolamak *packages.csproj* .NET Core 2.0.0 için proje dosyası:

`dotnet store --manifest packages.csproj --framework-version 2.0.0`

Belirtilen paketleri depolamak *packages.csproj* en iyi duruma getirme olmadan:

`dotnet store --manifest packages.csproj --skip-optimization`

## <a name="see-also"></a>Ayrıca bkz.

[Çalışma zamanı paket deposu](../deploying/runtime-store.md)   
