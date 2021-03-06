---
title: '&lt;authorizationPolicies&gt; &lt;ekleme&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 613a03d8-4384-4556-bce2-8c23286c0bb0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72af0529cea2e6810bdb7a518874a313e3ceab40
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltauthorizationpoliciesgt"></a>&lt;authorizationPolicies&gt; &lt;ekleme&gt;
Talep dönüştürme için bir yetkilendirme ilkesi belirtir.  
  
 \<Sistem. ServiceModel >  
\<davranışları >  
\<davranışı >  
\<serviceAuthorization >  
\<authorizationPolicies >  
\<ekleme >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<authorizationPolicies>  
   <add policyType="String" />  
</authorizationPolicies>  
```  
  
## <a name="type"></a>Tür  
 `Type`  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`policyType`|Gerekli bir dize özniteliği.<br /><br /> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Erişim denetimi modelini destekleyen türler olarak yetkilendirme ilkeleri kümesini sağlama. Bu öznitelik, bir giriş talep kümesini bir dönüştürme talep başka bir dizi içine sağlayan bir yetkilendirme ilkesi belirtir. Erişim denetimi verilen veya reddedilen oturum tabanlı.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<authorizationPolicies >](../../../../../docs/framework/configure-apps/file-schema/wcf/authorizationpolicies.md)|Yetkilendirme İlkesi türleri koleksiyonunu belirtir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Her bir yetkilendirme ilkesi gereken tek bir içeren `policyType` bir dize özniteliği. Öznitelik, bir giriş talep kümesini bir dönüştürme talep başka bir dizi içine sağlayan bir yetkilendirme ilkesi belirtir. Erişim denetimi verilen veya reddedilen oturum tabanlı. Bir yetkilendirme ilkesi nasıl çalıştığı hakkında daha fazla bilgi için bkz: <xref:System.IdentityModel.Policy.IAuthorizationPolicy> ve [yetkilendirme ilkesi](../../../../../docs/framework/wcf/samples/authorization-policy.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.ExternalAuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElement>  
 <xref:System.ServiceModel.Configuration.ServiceAuthorizationElement.AuthorizationPolicies%2A>  
 <xref:System.ServiceModel.Configuration.AuthorizationPolicyTypeElementCollection>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 [Hizmet İşlemlerine Erişimi Yetkilendirme](../../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 [Nasıl yapılır: Bir Hizmet için Özel Yetkilendirme Yöneticisi Oluşturma](../../../../../docs/framework/wcf/extending/how-to-create-a-custom-authorization-manager-for-a-service.md)  
 [\<ekleme >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-authorizationpolicies.md)  
 [Yetkilendirme İlkesi](../../../../../docs/framework/wcf/samples/authorization-policy.md)
