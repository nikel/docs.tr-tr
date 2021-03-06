---
title: "&lt;netMsmqBinding&gt; &lt;güvenliği&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: fb381d6970d72cc1ff88ed1238d8d8541c40a40d
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="ltsecuritygt-of-ltnetmsmqbindinggt"></a>&lt;netMsmqBinding&gt; &lt;güvenliği&gt;
MSMQ bağlama için güvenlik ayarlarını tanımlar. Taşıma veya SOAP Güvenliği etkinleştirilmiş ve varsa, hangi kimlik doğrulama modu ve koruma düzeyleri kullanımda olup olmadığını belirtir.  
  
 \<system.ServiceModel>  
\<bağlamaları >  
\<netMsmqBinding>  
\<bağlama >  
\<Güvenlik >  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<security mode="None/Transport/Message/Both">  
   <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"  
      msmqEncryptionAlgorithm="RC4Stream/AES"  
      msmqProtectionLevel="None/Sign/EncryptAndSign"  
      msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />  
      <message  
      algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="None/Windows/UserName/Certificate/CardSpace"/>  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|mod|Bütünlük, gizlilik ve kimlik doğrulama denetimleri güvenlik türünü belirtir. Geçerli değerler şunlardır:<br /><br /> -Hiçbiri: Bu güvenlik devre dışı bırakır.<br />-Taşıma: Koruma ve kimlik aktarım tarafından sunulur. Bu iki sıra yöneticileri arasında ileti güvenliği için geçerlidir. Sıra yöneticisini ve uygulama arasında sunulan güvenlik yoktur. Varolan Msmq uygulamalarının güvenlik modu bu tür işlevsel olarak eşdeğerdir.<br />-İleti: sona uygulama güvenliği belirtir. Aktarım katmanında sunulan güvenlik yoktur. Bu, diğer standart bağlamaları tarafından sunulan güvenlik benzer.<br />-Her ikisi: taşıma ve katman Mesajlaşma SOAP güvenlik sunar. Aynı kimlik bilgisini iki düzeyde gereklidir.<br /><br /> Aktarım varsayılan değerdir. Bu öznitelik türünde <xref:System.ServiceModel.NetMsmqSecurityMode>.|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[\<İleti >](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-netmsmqbinding.md)|SOAP iletisi güvenlik ayarlarını tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.|  
|[\<taşıma >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-netmsmqbinding.md)|MSMQ taşıma için güvenlik ayarlarını tanımlar. Bu öğe türünde <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|bağlama|Bağlama öğesi [ \<netMsmqBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>  
 <xref:System.ServiceModel.NetMsmqBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>  
 <xref:System.ServiceModel.NetMsmqSecurity>  
 [Hizmet ve İstemcileri Güvenli Hale Getirme](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bağlamalar](../../../../../docs/framework/wcf/bindings.md)  
 [Sistem Tarafından Sağlanan Bağlamaları Yapılandırma](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Windows Communication Foundation Hizmetleri ve istemcileri yapılandırmak için bağlamaları kullanma](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<bağlama >](../../../../../docs/framework/misc/binding.md)  
 [WCF'de Kuyruklar](../../../../../docs/framework/wcf/feature-details/queues-in-wcf.md)
