---
title: '&lt;dataContractSerializer&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dataContractSerializer element
- <dataContractSerializer> element
- DataContractSerializer
- KnownTypes
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27b80c831fdc66bd3b022645c3de9c0c31ee575a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdatacontractserializergt"></a>&lt;dataContractSerializer&gt;
Yapılandırma verilerini içeren <xref:System.Runtime.Serialization.DataContractSerializer>. Bu öğe, iki farklı hiyerarşilere oluşur. Bir listelenir aşağıdaki şema hiyerarşisini bölümü ve diğer açıklamalar bölümünde listelenir.  
  
 \<Sistem. ServiceModel >  
\<davranışları >  
\<serviceBehaviors >  
\<davranışı >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|ignoreExtensionDataObject|Yüklenmekte olan zaman bitiş noktası tarafından sağlanan verileri yoksayacak şekilde belirten bir Boole değeri serileştirilecek veya serisi. Bu öznitelik yalnızca ayarlanabilir `<dataContractSerializer>` altında `<behavior>` öğesi.|  
|MaxItemsInObjectGraph|Tamsayı serileştirmek veya seri durumdan öğe sayısını belirtir. Bu öznitelik 65536'dır.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<davranışı >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Bir hizmet davranışını için ayarlar koleksiyonu.|  
|[\<System.Runtime.Serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Kök öğe için temsil eden <xref:System.Runtime.Serialization> ad alanı bölüm ve seçenekleri ayarlamak için öğeleri içeren <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu konuda girişte belirtildiği gibi bu ikinci hiyerarşisinde olan \<X509Extension > öğesi oluşur.  
  
 [\<System.Runtime.Serialization >](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Bilinen türleri hakkında daha fazla bilgi için bkz: <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [Veri Anlaşması Bilinen Türler](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [Veri Aktarma ve Seri Hale Getirme](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
