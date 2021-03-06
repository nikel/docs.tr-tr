---
title: "Nasıl yapılır: Özel Güvenlik Belirteci Sağlayıcı Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 37e7f9541457c475bfe187485520df63a84f7555
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-create-a-custom-security-token-provider"></a>Nasıl yapılır: Özel Güvenlik Belirteci Sağlayıcı Oluşturma
Bu konu, yeni belirteç türleri sahip bir özel güvenlik belirteci sağlayıcı oluşturma ve sağlayıcı özel güvenlik belirteci yöneticisi ile tümleştirmek nasıl gösterir.  
  
> [!NOTE]
>  Sistem tarafından sağlanan belirteçleri bulunan özel bir belirteç sağlayıcısı oluşturun <xref:System.IdentityModel.Tokens> ad alanı gereksinimlerinizi eşleşmiyor.  
  
 Güvenlik belirteci sağlayıcısı istemci veya hizmet kimlik bilgileri temel alarak bir güvenlik belirteci temsilini oluşturur. Özel güvenlik belirteci sağlayıcı kullanacak şekilde [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] güvenlik, özel kimlik bilgileri ve güvenlik belirteci Yöneticisi uygulamaları oluşturmalısınız.  
  
 Özel kimlik bilgileri ve güvenlik belirteci Yöneticisi hakkında daha fazla bilgi için bkz: [izlenecek yol: özel istemci oluşturma ve hizmet kimlik bilgilerini](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
 Kimlik bilgileri hakkında daha fazla bilgi için bkz: güvenlik belirteci yöneticisi, sağlayıcı ve Doğrulayıcı sınıfları [güvenlik mimarisi](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f).  
  
### <a name="to-create-a-custom-security-token-provider"></a>Bir özel güvenlik belirteci sağlayıcısı oluşturmak için  
  
1.  Türetilen yeni bir sınıf tanımlama <xref:System.IdentityModel.Selectors.SecurityTokenProvider> sınıfı.  
  
2.  Uygulama <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> yöntemi. Yöntemi, oluşturma ve güvenlik belirteci örneğini döndüren sorumludur. Aşağıdaki örnek adlı bir sınıf oluşturur `MySecurityTokenProvider`ve geçersiz kılmalar <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> örneği döndürülecek yöntemi <xref:System.IdentityModel.Tokens.X509SecurityToken> sınıfı. Sınıf oluşturucu örneği gerektirir <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> sınıfı.  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a>Özel güvenlik belirteci sağlayıcı özel güvenlik belirteci yöneticisi ile tümleştirmek için  
  
1.  Türetilen yeni bir sınıf tanımlama <xref:System.IdentityModel.Selectors.SecurityTokenManager> sınıfı. (Aşağıdaki örnekte türetilen <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> türeyen sınıf <xref:System.IdentityModel.Selectors.SecurityTokenManager> sınıfı.)  
  
2.  Geçersiz kılma <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> değil zaten geçersiz kılınırsa yöntemi.  
  
     <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> Yöntemi örneği döndürmek için sorumlu <xref:System.IdentityModel.Selectors.SecurityTokenProvider> sınıfı için uygun <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> yöntemi tarafından geçirilen parametre [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security çerçevesi. (Önceki yordamda oluşturduğunuz) özel bir güvenlik belirteci sağlayıcı uygulaması döndürmek için yöntemini değiştirme zaman yöntemi çağrıldığında bir uygun güvenlik belirteci parametresiyle. Güvenlik belirteci Yöneticisi hakkında daha fazla bilgi için bkz: [izlenecek yol: özel istemci oluşturma ve hizmet kimlik bilgilerini](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).  
  
3.  Temel, özel güvenlik belirteci sağlayıcı döndürülecek etkinleştirmek için yöntemi Özel mantık ekleme <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parametresi. Aşağıdaki örnek, belirteç gereksinimlerin karşılanması durumunda özel güvenlik belirteci sağlayıcı döndürür. Gereksinimleri, bir X.509 güvenlik belirteci ve (belirteç ileti çıktı için kullanıldığını) ileti yönü içerir. Tüm diğer durumlarda, diğer güvenlik belirteci gereksinimleri için sistem tarafından sağlanan davranışı sağlamak için temel sınıf kod çağırır.  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki tam gösterir <xref:System.IdentityModel.Selectors.SecurityTokenProvider> karşılık gelen yanı sıra uygulama <xref:System.IdentityModel.Selectors.SecurityTokenManager> uygulaması.  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [İzlenecek Yol: Özel İstemci ve Hizmet Kimlik Bilgileri Oluşturma](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [Nasıl yapılır: Özel Güvenlik Belirteci Kimlik Doğrulayıcı Oluşturma](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [Güvenlik mimarisi](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)
