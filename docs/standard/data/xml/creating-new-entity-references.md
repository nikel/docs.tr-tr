---
title: "Yeni varlık başvuruları oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a42f81b3-0403-4e34-b346-7d2129804e54
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 76093fbe7095c2aae7caa69147f6181c292ca734
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="creating-new-entity-references"></a>Yeni varlık başvuruları oluşturma
**CreateEntityReference** yöntemi yeni bir oluşturur **XmlEntityReference** düğümü. Başvurulan varlık adı zaten bildirilmiş olmadığını görmek için XML belge nesne modeli (DOM) arar. Varsa, alt düğümleri **XmlEntityReference** düğümü varlık bildirimi düğümden kopyalanır. Eşleşen hiçbir varlık bildirimi ise, boş metin düğümü yalnızca düğümün alt öğesi varlık başvuru eklendi. Çünkü alt düğümlerin **XmlEntityReference** düğümü diğer düğümlere kopyalarını, bu alt düğümlerin salt okunurdur ve değiştirilemez.  
  
 Düğümleri kopyalandığında, olabilir. bir ad alanı varlık başvurusu noktasında kapsamı. Bu ad alanı oluşturulan herhangi bir öğe veya öznitelik düğümünün yapılandırmasını etkiler.  
  
> [!NOTE]
>  DOM alt düğüm ekler **EntityReference** eklediğinizde yalnızca **EntityReference** belge düğümü. Yeni oluşturulan **EntityReference** düğümünüz alt düğüm yok.  
  
 Olsa bile **XmlDataDocument** türetilmiş bir sınıf **XmlDocument**, **XmlDataDocument** varlık başvuruları oluşturulmasını desteklemiyor. Bunun nedeni, **EntityReference** alt salt okunur. Alt öğelerinin bir **EntityReference** düğümü birden fazla bölge yayılabilir. Bu durumda, bir satır parçası ilişkili bir parçasını içeren bölgesiyle bir **EntityReference** salt okunur olacaktır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belge Nesne Modeli (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
