---
title: "&lt;httpDigest&gt; Öğesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3da4f276-dfd9-4247-8c07-01d83618727c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 95e6a7d31949bd7a6badb029e3f768a63fbaf924
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="lthttpdigestgt-element"></a>&lt;httpDigest&gt; Öğesi
Bir Özet belirten bir hizmet için istemci kimlik doğrulaması yapılırken kullanılan kimlik bilgilerini yazın.  
  
 \<Sistem. ServiceModel >  
\<davranışları >  
\<endpointBehaviors >  
\<davranışı >  
\<clientCredentials >  
\<httpDigest >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<digest impersonationLevel="Identification/Impersonation/Delegation/Anonymous/None" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`impersonationLevel`|İstemci iletişim kuruyorsa kimliğe bürünme tercih sunucuya ayarlar. İstemcinin kimliğe bürünme modu sunucuda zorlanmaz. Geçerli değerler şunlardır:<br /><br /> -Kimliği: Sunucunun kimliğini ve istemci ayrıcalıkların alabilir, ancak istemci alınamıyor.<br />-Kimliğe bürünme: Sunucu istemcinin güvenlik bağlamı yerel sistemde kimliğine bürünebilir.<br />-Temsilci: Sunucu istemcinin güvenlik bağlamı uzak sistemlere kimliğine bürünebilir.<br />-Anonim: Sunucusu taklit veya istemci kimliği.<br />-Hiçbiri: Kimliğe bürünme düzeyi atanmadı.<br /><br /> Varsayılan kimliğidir. Bu öznitelik türünde <xref:System.Security.Principal.TokenImpersonationLevel>.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Bir hizmet için bir istemci kimlik doğrulaması için kullanılan kimlik bilgilerini belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir Özet bir karma algoritma ve girişleri kümesi kullanarak belirlenen var. Doğrulayıcı ve kimliği doğrulanmış bir algoritma kabul ediyorum ve girdi olarak kullanılan veri değişimi. İstemci, karmayı hesaplar ve hizmete gönderin. Hizmet ayrıca karmayı hesaplar ve değerlerini karşılaştırır. Bir eşleşme istemci doğrular.  
  
 Bu özellik, Windows ve Internet Information Services (IIS) üzerinde Active Directory ile etkinleştirilmelidir. [!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)][Özet kimlik doğrulaması IIS 6.0](http://go.microsoft.com/fwlink/?LinkId=88443).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.HttpDigest%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.HttpDigest%2A>  
 <xref:System.ServiceModel.Configuration.HttpDigestClientElement>  
 <xref:System.ServiceModel.Security.HttpDigestClientCredential>  
 [Güvenlik Davranışları](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/securing-clients.md)  
 [Sertifikalarla Çalışma](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
