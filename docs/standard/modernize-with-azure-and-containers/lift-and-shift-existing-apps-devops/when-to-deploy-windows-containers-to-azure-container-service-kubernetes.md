---
title: "Azure kapsayıcı hizmeti (diğer bir deyişle, Kubernetes) Windows kapsayıcıları dağıtma zamanı"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Azure kapsayıcı hizmeti (diğer bir deyişle, Kubernetes) Windows kapsayıcıları dağıtma zamanı"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: f0a096712e14e506403961f0b9283ca4b707cbda
ms.sourcegitcommit: d3cfda0943364aaf6ccd574f55f584576c8a4fee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Azure kapsayıcı hizmeti (diğer bir deyişle, Kubernetes) Windows kapsayıcıları dağıtma zamanı

Azure kapsayıcı hizmeti popüler açık kaynak Araçlar ve teknolojiler yapılandırmasını özellikle Azure için en iyi duruma getirir. Taşınabilirlik kapsayıcılarınızı hem uygulama yapılandırmanızı sağlayan açık olan çözüm alın. Boyut, ana bilgisayar sayısı ve orchestrator araçları seçin. Azure kapsayıcı hizmeti altyapı işler.

Zaten açık kaynak orchestrators Kubernetes, Docker Swarm veya DC/OS gibi çalışıyorsanız kapsayıcı iş yüklerinin buluta taşımak için var olan Yönetim uygulamalarınızı değiştirmeniz gerekmez. Zaten aşina ve tercih ettiğiniz orchestrator için standart API uç noktaları bağlanma uygulama yönetim araçlarını kullanın.

Bu orchestrators Linux Docker kapsayıcılar, ancak bunlar da destek Windows kapsayıcıları 2017 gibi (bazıları daha önce bazıları daha yakın zamanda üzerinde orchestrator bağlı olarak), kullanmakta olduğunuz olgun ortamları demektir.

Kapsayıcıları için Kubernetes Örneğin, destek Windows kapsayıcıları üzerinde Kubernetes bunu kullanarak yerel (birinci sınıf citizen), ayrıca çok etkili ve güvenilir (kadar önizlemede erken 2017 kalan).

>[!div class="step-by-step"]
[Önceki](when-to-deploy-windows-containers-to-service-fabric.md)
[sonraki](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
