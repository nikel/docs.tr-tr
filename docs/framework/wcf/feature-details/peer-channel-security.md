---
title: "Eş Kanalı Güvenliği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c59b164-3729-44f0-a967-f247c42de662
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: afe4252a56802ff2796f947afa31a5871f29223e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="peer-channel-security"></a><span data-ttu-id="deba0-102">Eş Kanalı Güvenliği</span><span class="sxs-lookup"><span data-stu-id="deba0-102">Peer Channel Security</span></span>
<span data-ttu-id="deba0-103">Eş kanal çeşitli taraflı mesajlaşmayı bağımlı dağıtılmış uygulama türlerini sağlar.</span><span class="sxs-lookup"><span data-stu-id="deba0-103">Peer Channel enables a variety of distributed application types that depend on multiparty messaging.</span></span> <span data-ttu-id="deba0-104">Burada güvenilen bir kaynak (örneğin, medya veya yazılım güncelleştirmeleri) içerik dağıtır, Internet ölçeğinde içerik dağıtımı bazı örnekler bir arkadaş grubuyla exchange müzik ve fotoğraf veya iş arkadaşlarınızı ekibi birliğine dayalı olarak bir belgeyi Düzenle.</span><span class="sxs-lookup"><span data-stu-id="deba0-104">Some examples include Internet-scale content distribution, where a trusted source distributes content (such as media or software updates), a group of friends exchange music and photos, or a team of colleagues collaboratively edit a document.</span></span> <span data-ttu-id="deba0-105">Bu senaryoların her biri benzersiz güvenlik modelini gerektirir.</span><span class="sxs-lookup"><span data-stu-id="deba0-105">Each of these scenarios requires a unique security model.</span></span> <span data-ttu-id="deba0-106">Eş kanal güvenlik modeli bu senaryosu için tasarlanmıştır ve farklı kimlik, kimlik doğrulama ve yetkilendirme modelleri ilgili gereksinimleriniz için bir güvenlik modeli sağlar.</span><span class="sxs-lookup"><span data-stu-id="deba0-106">The Peer Channel security model is designed to address these scenarios and provides a sound security model for the respective needs of different identity, authentication, and authorization models.</span></span>  
  
## <a name="security-scenarios"></a><span data-ttu-id="deba0-107">Güvenlik senaryoları</span><span class="sxs-lookup"><span data-stu-id="deba0-107">Security Scenarios</span></span>  
 <span data-ttu-id="deba0-108">İçerik dağıtım senaryosu, içerik her alıcı içerik kaynağı tanımlamak gerektirir.</span><span class="sxs-lookup"><span data-stu-id="deba0-108">A content-distribution scenario requires that each content recipient identify the content source.</span></span> <span data-ttu-id="deba0-109">Senaryo dağıtılmış yapısı nedeniyle, her zaman bilmek ve bu işlem veya ıntercept iletileri aracıların güven mümkün değildir.</span><span class="sxs-lookup"><span data-stu-id="deba0-109">Due to the distributed nature of the scenario, it is not always possible to know and trust the intermediaries that process or intercept messages.</span></span> <span data-ttu-id="deba0-110">Uygulamaları etkili bir şekilde güvenilmeyen bir aracı iletilerle değiştirmesine tehdidi azaltmak için böylece değiştirme girişimleri kolayca algılanan Gönderenin iletiyi güvenliğini sağlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deba0-110">To effectively mitigate the threat that an untrusted intermediary might tamper with the messages, applications can secure the message at the sender so that any tampering attempts are easily detected.</span></span> <span data-ttu-id="deba0-111">Bu durumda, içerik gizliliğini bağlı olarak, şifreleme gerekli olabilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-111">In this case, depending on the confidentiality of the content, encryption can be necessary.</span></span>  
  
 <span data-ttu-id="deba0-112">İşbirliği senaryoları genellikle Grup belge işbirliği gibi oturumda katılan her üye ayrı ayrı tanımlanan kimlik doğrulaması ve gerektirir.</span><span class="sxs-lookup"><span data-stu-id="deba0-112">Collaboration scenarios like group document collaboration often require that each member participating in the session be individually identified and authenticated.</span></span> <span data-ttu-id="deba0-113">Bu, kullanıcı gruplarını tanımlar ve bu gruplara karşı kimlik doğrulaması için bir mekanizma güvenli bir oturum gerekli olduğu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="deba0-113">This means that a mechanism to define user groups and authenticate against those groups is necessary to have a secured session.</span></span> <span data-ttu-id="deba0-114">Ayrıca, uygulamalar her ileti kimlik doğrulama ileti düzeyinde tarafından izleme gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-114">Moreover, applications might require tracing each message by authentication at the message level.</span></span> <span data-ttu-id="deba0-115">Bu tür uygulamalar için daha güçlü güvenlik şeması performans feda.</span><span class="sxs-lookup"><span data-stu-id="deba0-115">In these types of applications, performance can be sacrificed for a stronger security scheme.</span></span>  
  
 <span data-ttu-id="deba0-116">Bir kullanıcı grubuna sıradan arasında iletişim oturumu grubu arasında ortak bir gizlilik bilgisi gibi resmi olmayan güvenlik modelleri gerektirebilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-116">A communication session among a group of casual users can require informal security models, like knowledge of a common secret among the group.</span></span> <span data-ttu-id="deba0-117">Bu tür uygulamalar oluşturmak ve yapılandırmak uygun bir güvenlik modeli sahip kimlik doğrulaması güçlü biçiminde olması veya kabullenme ölçüleri sağlayarak daha daha önemlidir.</span><span class="sxs-lookup"><span data-stu-id="deba0-117">For these types of applications, having a security model that is convenient to establish and configure is more important than having the strongest form of authentication or providing nonrepudiation measures.</span></span> <span data-ttu-id="deba0-118">Bu senaryolarda, ileti kimlik doğrulaması için hala verirken güvenli iletişim katmanı için bir parola tabanlı kimlik doğrulama mekanizması yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="deba0-118">For these scenarios, a password-based authentication mechanism helps to secure the communication layer while still allowing for message authentication.</span></span> <span data-ttu-id="deba0-119">Parola tabanlı güvenlik eş kanalı için varsayılan ayardır.</span><span class="sxs-lookup"><span data-stu-id="deba0-119">Password-based security is the default setting for Peer Channel.</span></span>  
  
## <a name="token-types"></a><span data-ttu-id="deba0-120">Belirteç türleri</span><span class="sxs-lookup"><span data-stu-id="deba0-120">Token Types</span></span>  
 <span data-ttu-id="deba0-121">Eş kanal tek bir belirteç türü güçlü kimlik için kimlik doğrulama ve yetkilendirme uygulanabilir türüne göre bir güçlü kimlik modeli sağlar X.509 sertifikalarını tanır.</span><span class="sxs-lookup"><span data-stu-id="deba0-121">Peer Channel recognizes a single token type for strong identification, X.509 certificates, which provide a strong identity model based on the type of authentication and authorization that can be implemented.</span></span> <span data-ttu-id="deba0-122">Gizliliği ve bütünlük kolayca sertifikalar kullanılarak sağlanır.</span><span class="sxs-lookup"><span data-stu-id="deba0-122">Confidentiality and integrity are easily provided using certificates.</span></span> <span data-ttu-id="deba0-123">Ancak, X.509 sertifikalarını kullanın ve dağıtmak zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-123">However, X.509 certificates can be difficult to use and deploy.</span></span>  
  
 <span data-ttu-id="deba0-124">Eş kanal, parolaları ile basit uygulamalar için de destek sağlar.</span><span class="sxs-lookup"><span data-stu-id="deba0-124">Peer Channel also provides support for simple applications through the use of passwords.</span></span> <span data-ttu-id="deba0-125">Sağlanan parola tabanlı hızlı ve basit eş gruplarını ayarlamak uygulamaları seçebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deba0-125">Applications can choose to set up quick and simple peer groups based on a supplied password.</span></span> <span data-ttu-id="deba0-126">Bu durumda, bir grup sahibi karar verir ve parola üyelerine iletişim kurar.</span><span class="sxs-lookup"><span data-stu-id="deba0-126">In this case, a group owner decides and communicates the password to members.</span></span> <span data-ttu-id="deba0-127">Her üye oturum katılabilmesi için önce bu parola kullanarak oturum açmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="deba0-127">Each member must sign in using this password before they can join the session.</span></span> <span data-ttu-id="deba0-128">Parolalar, yalnızca oturum girişine izin vermek için kullanılabilir; ileti kimlik doğrulaması gerçekleştirmek için kullanılamaz.</span><span class="sxs-lookup"><span data-stu-id="deba0-128">Passwords can be used only to allow entry to the session; they cannot be used to perform message authentication.</span></span> <span data-ttu-id="deba0-129">Eşleri grubudur paylaşan simetrik belirteç zor ve kaynak kimlik doğrulaması için kullanılacak uygun olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="deba0-129">This is because a symmetric token that a group of peers share is difficult and inappropriate to use for source authentication.</span></span>  
  
## <a name="security-model"></a><span data-ttu-id="deba0-130">Güvenlik modeli</span><span class="sxs-lookup"><span data-stu-id="deba0-130">Security Model</span></span>  
 <span data-ttu-id="deba0-131">Eş kanal tek bağlantılar eşler arasında güvenli olanağı sağlar.</span><span class="sxs-lookup"><span data-stu-id="deba0-131">Peer Channel provides the ability to secure the individual links between peers.</span></span> <span data-ttu-id="deba0-132">Bu, bir ileti hiçbir zaman güvenli bir bağlantı (uygulama açısından) üzerindeki akar olduğunu anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="deba0-132">This means that a message never flows on an unsecured link (from the application perspective).</span></span> <span data-ttu-id="deba0-133">Dahili olarak, her bir bağlantının (iki eş arasında taşıma kanal) Aktarım Katmanı Güvenliği (TLS) kullanarak güvenli hale getirilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-133">Internally, each link (a transport channel between two peers) is secured using Transport Layer Security (TLS).</span></span> <span data-ttu-id="deba0-134">Bir gönderici oluşturur ve bir ileti gönderir anlamına gelir, her bir iletinin erişmek ve sırayla kendi hemen eşlere güvenli bağlantıları üzerinden Gönder, ileti hemen eşlerine, onu güvenli aktarımı üzerinden gönderilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-134">This means that when a sender composes and sends a message, it is sent over secure transport to each of its immediate peers, who access the message, and in turn send the message to their immediate peers over secure connections.</span></span> <span data-ttu-id="deba0-135">Aktarım sırasında yalnızca works düzey ve ileti güvenlik modellerinin bağımsızdır bu güvenlik.</span><span class="sxs-lookup"><span data-stu-id="deba0-135">This security only works at the transport level and is independent of the message security models.</span></span>  
  
 <span data-ttu-id="deba0-136">Eş kanal ayrıca kullanılan taşıma güvenliği bağımsız olarak iletileri güvenli hale getirmek için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="deba0-136">Peer Channel also provides a way to secure messages independently of the transport security used.</span></span> <span data-ttu-id="deba0-137">Şu anda yalnızca X.509 sertifikaları desteklenir, ancak bu modelde, kaynağın güvenlik belirtecini kullanarak kaynakta ileti güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="deba0-137">In this model, the message is secured at the source using the source’s security token, although currently only X.509 certificates are supported.</span></span> <span data-ttu-id="deba0-138">Güvenli bir ileti sonra eş ağ üzerinden iletilir.</span><span class="sxs-lookup"><span data-stu-id="deba0-138">The secured message is then transmitted over the peer network.</span></span> <span data-ttu-id="deba0-139">Her alıcı eş kaynağı özgünlüğünü doğrulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deba0-139">Each receiving peer can verify the authenticity of the source.</span></span> <span data-ttu-id="deba0-140">İleti güvenliği ve böylece aracılar ile değiştirmesine unutmayın.</span><span class="sxs-lookup"><span data-stu-id="deba0-140">Note that the message is secured so that intermediaries cannot tamper with it.</span></span>  
  
 <span data-ttu-id="deba0-141">Gizliliği elde etmek için uygulamaları iletiye yetkisiz erişimi önlemek için güçlü grup üyeliği düzenleri ile taşıma güvenliği tercih edebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="deba0-141">To achieve confidentiality, applications can employ transport security with strong group membership schemes to prevent unauthorized access to the message.</span></span>  
  
 <span data-ttu-id="deba0-142">Eş kanal uygulama desteklenen belirteç türleri birini seçer sürece belirli bir kimlik modeli gerektirmez.</span><span class="sxs-lookup"><span data-stu-id="deba0-142">Peer Channel does not require a specific identity model as long as the application chooses one of the supported token types.</span></span> <span data-ttu-id="deba0-143">Uygulamalar, bu kimlikleri ve kimlik doğrulama kararları yaşam döngüsünü tamamen kendi.</span><span class="sxs-lookup"><span data-stu-id="deba0-143">Applications completely own the life cycle of these identities and authentication decisions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deba0-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="deba0-144">See Also</span></span>  
 [<span data-ttu-id="deba0-145">Eş kanalı uygulamalarını güvenli hale getirme</span><span class="sxs-lookup"><span data-stu-id="deba0-145">Securing Peer Channel Applications</span></span>](../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [<span data-ttu-id="deba0-146">Eş kanal kavramları</span><span class="sxs-lookup"><span data-stu-id="deba0-146">Peer Channel Concepts</span></span>](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)  
 [<span data-ttu-id="deba0-147">Eş kanal uygulaması oluşturma</span><span class="sxs-lookup"><span data-stu-id="deba0-147">Building a Peer Channel Application</span></span>](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)