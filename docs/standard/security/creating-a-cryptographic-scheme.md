---
title: "Şifreleme Düzeni Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [.NET Framework], creating cryptographic schemes
- cryptography [.NET Framework], creating cryptographic schemes
ms.assetid: d40c509f-5a5e-46cc-94cb-a951e9ab6843
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3e3c4a832f70fae7808bf71016cb9f6648332f01
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="creating-a-cryptographic-scheme"></a><span data-ttu-id="31eb4-102">Şifreleme Düzeni Oluşturma</span><span class="sxs-lookup"><span data-stu-id="31eb4-102">Creating a Cryptographic Scheme</span></span>
<span data-ttu-id="31eb4-103">.NET Framework şifreleme bileşenlerinin şifrelemek ve verilerin şifresini çözmek için farklı düzenleri oluşturmak için birleştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="31eb4-103">The cryptographic components of the .NET Framework can be combined to create different schemes to encrypt and decrypt data.</span></span>  
  
 <span data-ttu-id="31eb4-104">Şifreleme ve verilerin şifresini çözmek için basit bir şifreleme şeması aşağıdakileri belirtebilir:</span><span class="sxs-lookup"><span data-stu-id="31eb4-104">A simple cryptographic scheme for encrypting and decrypting data might specify the following steps:</span></span>  
  
1.  <span data-ttu-id="31eb4-105">Her taraf ortak/özel anahtar çifti oluşturur.</span><span class="sxs-lookup"><span data-stu-id="31eb4-105">Each party generates a public/private key pair.</span></span>  
  
2.  <span data-ttu-id="31eb4-106">Tarafların sitelerin genel anahtarlarını exchange.</span><span class="sxs-lookup"><span data-stu-id="31eb4-106">The parties exchange their public keys.</span></span>  
  
3.  <span data-ttu-id="31eb4-107">Her taraf TripleDES şifreleme için gizli bir anahtar oluşturur örneğin ve diğer kişilerin ortak anahtar kullanarak yeni oluşturulan anahtarı şifreler.</span><span class="sxs-lookup"><span data-stu-id="31eb4-107">Each party generates a secret key for TripleDES encryption, for example, and encrypts the newly created key using the other's public key.</span></span>  
  
4.  <span data-ttu-id="31eb4-108">Her taraf diğer verileri gönderir ve diğer kişilerin gizli anahtarı yeni gizli bir anahtar oluşturmak için kendi belirli bir sıra ile birleştirir.</span><span class="sxs-lookup"><span data-stu-id="31eb4-108">Each party sends the data to the other and combines the other's secret key with its own, in a particular order, to create a new secret key.</span></span>  
  
5.  <span data-ttu-id="31eb4-109">Taraflar ardından simetrik şifreleme kullanarak bir konuşma başlatın.</span><span class="sxs-lookup"><span data-stu-id="31eb4-109">The parties then initiate a conversation using symmetric encryption.</span></span>  
  
 <span data-ttu-id="31eb4-110">Şifreleme düzeni oluşturma, karmaşık bir görev değil.</span><span class="sxs-lookup"><span data-stu-id="31eb4-110">Creating a cryptographic scheme is not a trivial task.</span></span> <span data-ttu-id="31eb4-111">Şifreleme kullanma hakkında daha fazla bilgi için Platform SDK belgelerine http://msdn.microsoft.com/library şifreleme konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="31eb4-111">For more information on using cryptography, see the Cryptography topic in the Platform SDK documentation at http://msdn.microsoft.com/library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31eb4-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="31eb4-112">See Also</span></span>  
 [<span data-ttu-id="31eb4-113">Şifreleme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="31eb4-113">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)