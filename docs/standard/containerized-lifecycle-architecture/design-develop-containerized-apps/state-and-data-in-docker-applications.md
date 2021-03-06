---
title: Durum ve Docker uygulamalarda verileri
description: Microsoft Platformu ve araçları ile kapsayıcılı Docker uygulama yaşam döngüsü
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 83094cd9a13d77f489df639096bb42b23ce152e7
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="state-and-data-in-docker-applications"></a>Durum ve Docker uygulamalarda verileri

Kapsayıcıların bir temel girişi olur. Bir VM'ye karşılaştırıldığında kapsayıcılar sık karşılaştıkları kayboluyor yok. VM aşırı yüklenmiş CPU veya tam ya da başarısız disk ölü işlemler çeşitli formlardan başarısız olabilir. Henüz kullanılabilir olması için VM bekliyoruz ve sürücü hataları verileri tutmak güvence altına almak için sıradan bir hale RAID sürücülerdir.

İşlem örneklerinin olmasını kapsayıcıları zorlayıcı ancak. Bir işlem dayanıklı durum bilgisini korumaz. Yerel depolama alanı için bir kapsayıcı yazabilirsiniz olsa bile, o örneği çevresinde süresiz olarak olacağını varsayılarak tek kopyası bellek dayanıklı olduğu varsayılarak için eşdeğer olacaktır. Sonlandırıldı, işlemleri gibi kapsayıcıları yinelenir veya bir kapsayıcı orchestrator ile yönetilen, bunlar taşınmış olabilir varsayalım.

Docker olarak bilinen bir özelliği kullanan bir *kaplama dosya sistemi* herhangi depolar yazarken kopyalama işlemi uygulamak için temel özgün görüntüsüne karşılaştırıldığında, bir kapsayıcı kök dosya sistemi bilgiler güncelleştirilmiştir. Kapsayıcı sonradan sistemden silinirse, bu değişiklikler kaybolur. Kapsayıcı, bu nedenle, varsayılan olarak kalıcı depolama yok. Bir kapsayıcı durumunu kaydetmek mümkün olsa da, bu geçici bir sistemi tasarladığınız kapsayıcı mimarisi ilkesini çakışıyor olabilir.

Docker uygulamaları kalıcı verileri yönetmek için yaygın çözümleri vardır:

-   [**Veri birimleri**](https://docs.docker.com/engine/tutorials/dockervolumes/) bunlar yalnızca belirtilen ana bilgisayara bağlayın.

-   [**Veri birim kapsayıcıları**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) bunlar gezinebilirsiniz dış bir kapsayıcı kullanılarak kapsayıcıları arasında paylaşılan depolama alanı sağlar.

-   [**Birim eklentileri**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) bu uzun vadeli Kalıcılık sağlayan uzak konumlara birimlerini bağlayın.

-   **Uzak Veri kaynaklarını** örnekler SQL ve Hayır SQL veritabanları dahil etmek veya önbelleğe Redis gibi hizmetler.

-   [**Azure depolama**](https://docs.microsoft.com/azure/storage/) bu kadar uzun vadeli Kalıcılık kapsayıcıların en iyi sağlayan bir hizmet (PaaS) depolama coğrafi dağıtılabilir platform sağlar.

Veri birimleri özel dizinleri atlama bir veya daha fazla kapsayıcı içinde belirtilen [birleşim dosya sistemi](https://docs.docker.com/v1.8/reference/glossary#union-file-system). Veri birimleri, verileri, kapsayıcının yaşam döngüsünü bağımsız korumak için tasarlanmıştır. Bir kapsayıcı kaldırın ya da artık kapsayıcı tarafından başvurulan "Çöp toplama" birimleri olur, docker bu nedenle hiçbir zaman otomatik olarak birimleri siler. Konak işletim sistemi göz atın ve veri birimlerini tutumlu kullanmak için başka bir neden olduğu herhangi bir birimdeki veriler serbestçe, Düzenle.

A [veri birim kapsayıcısı](https://docs.docker.com/v1.8/userguide/dockervolumes/) bir geliştirme normal veri birimleri üzerinde değil. İçinde oluşturulan (daha önce açıklandığı gibi) bir veya daha fazla veri birimleri sahip temelde bir etkinliği olmayan kapsayıcıdır. Veri birim kapsayıcısı, bir merkezi bağlama noktası kapsayıcılara erişim sağlar. Bu yöntem erişim avantajı veri kapsayıcısı mantıksal bağlama noktası yapma özgün verilerin konumu soyutlar ' dir. Ayrıca, "uygulama" kapsayıcıları veri kapsayıcısı birimlerinin oluşturulabilir ve verileri ayrılmış bir kapsayıcıda kalıcı tutarken yok erişim sağlar.

Şekil 4-5, normal Docker birimleri depolama kapsayıcıları kendilerini dışında ancak ana bilgisayar sunucusu/VM fiziksel sınırları içinde yerleştirilebilir gösterir. *Docker birimler bir konak sunucu/VM biriminden diğerine kullanma yeteneğini sahip değilseniz*.

![](./media/image5.png)

Şekil 4-5: veri birimlerini ve kapsayıcıları apps/kapsayıcıları için dış veri kaynakları

Doğrulanamadığından ayrı fiziksel ana bilgisayarda çalıştırılan kapsayıcıları arasında paylaşılan verileri yönetmek için sabit konak/VM, Docker ana bilgisayar olmadığı sürece, birimleri iş verilerini çünkü kullanmamasını önerilir Docker kapsayıcıları bir orchestrator'da kullanırken kapsayıcı, bir küme tarafından gerçekleştirilmek üzere en iyi duruma getirme bağlı olarak başka bir konağa taşınıp beklenir.

Bu nedenle, normal veri birimleri izleme dosyaları, zamana bağlı dosyaları ya da iş veri tutarlılığını varsa veya birden çok konak genelinde kapsayıcılarınızı taşındıklarında etkilemez benzer kavram çalışmak için iyi bir mekanizma altındadır.

Birim eklentileri ister [Flocker](https://clusterhq.com/flocker/) bir kümedeki tüm ana bilgisayarlar arasında veri sağlar. Tüm birim eklentileri eşit olarak oluşturulur ancak birim eklentileri genellikle değişmez kapsayıcılarla externalized kalıcı güvenilir depolama sağlar.

Uzak Veri kaynaklarını ve SQL Database, DocumentDB veya Redis gibi uzak bir önbellek gibi önbellekleri kapsayıcıları geliştirme ile aynı olacaktır. Bu, iş uygulama verilerini depolamak için tercih edilen ve kanıtlanmış, yolları biridir.


>[!div class="step-by-step"]
[Önceki] (tek yapılı-applications.md) [sonraki] (soa-applications.md)
