---
title: "Nasıl yapılır: Belirtilen Bir Kimlik Doğrulama Modu için SecurityBindingElement Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a7c7747a-5b8c-463f-8493-7266dac75066
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 658eaf3469e0be179c78d9963687e6de9cb7fc00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-securitybindingelement-for-a-specified-authentication-mode"></a><span data-ttu-id="19804-102">Nasıl yapılır: Belirtilen Bir Kimlik Doğrulama Modu için SecurityBindingElement Oluşturma</span><span class="sxs-lookup"><span data-stu-id="19804-102">How to: Create a SecurityBindingElement for a Specified Authentication Mode</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="19804-103">birkaç modu olarak istemciler ve hizmetler birbirine kimlik doğrulaması sağlar.</span><span class="sxs-lookup"><span data-stu-id="19804-103"> provides several modes by which clients and services authenticate to one another.</span></span> <span data-ttu-id="19804-104">Güvenlik bağlama öğeleri bu kimlik doğrulama modları için statik yöntemler kullanarak oluşturabileceğiniz <xref:System.ServiceModel.Channels.SecurityBindingElement> sınıfı veya yapılandırma ve aşağıdaki örnekte gösterildiği gibi.</span><span class="sxs-lookup"><span data-stu-id="19804-104">You can create security binding elements for these authentication modes by using static methods on the <xref:System.ServiceModel.Channels.SecurityBindingElement> class or through configuration, as shown in the following example.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="19804-105">bkz: 18 kimlik doğrulama modları [SecurityBindingElement kimlik doğrulama modları](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span><span class="sxs-lookup"><span data-stu-id="19804-105"> the 18 authentication modes, see [SecurityBindingElement Authentication Modes](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="19804-106">Örnek</span><span class="sxs-lookup"><span data-stu-id="19804-106">Example</span></span>  
 <span data-ttu-id="19804-107">Aşağıdaki kod örneği, çeşitli kimlik doğrulama modları için bağlamaları oluşturmak için yöntemleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="19804-107">The following code example shows methods for creating bindings for the various authentication modes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="19804-108">Bir kez örneği <xref:System.ServiceModel.Channels.SecurityBindingElement> nesnesi oluşturulur, bir dizi değişmez gibi <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> ve <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span><span class="sxs-lookup"><span data-stu-id="19804-108">Once an instance of the <xref:System.ServiceModel.Channels.SecurityBindingElement> object is created, a number of properties are immutable, such as <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.KeyType%2A> and <xref:System.ServiceModel.Channels.SecurityBindingElement.MessageSecurityVersion%2A>.</span></span> <span data-ttu-id="19804-109">Çağırma `set` gibi özellikleri bunları değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="19804-109">Calling `set` on such properties does not change them.</span></span>  
  
 [!code-csharp[c_CustomBindingsAuthMode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#2)]
 [!code-vb[c_CustomBindingsAuthMode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="19804-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="19804-110">See Also</span></span>  
 [<span data-ttu-id="19804-111">SecurityBindingElement kimlik doğrulama modları</span><span class="sxs-lookup"><span data-stu-id="19804-111">SecurityBindingElement Authentication Modes</span></span>](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 [<span data-ttu-id="19804-112">Nasıl yapılır: SecurityBindingElement kullanarak özel bağlama oluşturma</span><span class="sxs-lookup"><span data-stu-id="19804-112">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)