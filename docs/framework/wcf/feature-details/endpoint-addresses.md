---
title: "Uç Noktası Adresleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- addresses [WCF]
- Windows Communication Foundation [WCF], addresses
- WCF [WCF], addresses
ms.assetid: 13f269e3-ebb1-433c-86cf-54fbd866a627
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 52c5dfd84a55e727e465e2bd6214462fd57c334f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="endpoint-addresses"></a><span data-ttu-id="fc210-102">Uç Noktası Adresleri</span><span class="sxs-lookup"><span data-stu-id="fc210-102">Endpoint Addresses</span></span>
<span data-ttu-id="fc210-103">Tüm uç bulun ve uç noktayı tanımlamak için kullanılan ilişkili bir adresi vardır.</span><span class="sxs-lookup"><span data-stu-id="fc210-103">Every endpoint has an address associated with it, which is used to locate and identify the endpoint.</span></span> <span data-ttu-id="fc210-104">Bu adres, öncelikle bir Tekdüzen Kaynak Tanımlayıcısı (uç nokta konumunu belirten URI), oluşur.</span><span class="sxs-lookup"><span data-stu-id="fc210-104">This address consists primarily of a Uniform Resource Identifier (URI), which specifies the location of the endpoint.</span></span> <span data-ttu-id="fc210-105">Uç nokta adresi temsil edilen [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] programlama modeli tarafından <xref:System.ServiceModel.EndpointAddress> isteğe bağlı bir içeren sınıf <xref:System.ServiceModel.EndpointAddress.Identity%2A> bitiş noktası ile ileti değiş tokuşu diğer uç noktaları tarafından kimlik doğrulamasını etkinleştirir özelliği ve İsteğe bağlı kümesi <xref:System.ServiceModel.EndpointAddress.Headers%2A> hizmete erişmek için gerekli diğer SOAP üstbilgileri tanımlayan özellikleri.</span><span class="sxs-lookup"><span data-stu-id="fc210-105">The endpoint address is represented in the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] programming model by the <xref:System.ServiceModel.EndpointAddress> class, which contains an optional <xref:System.ServiceModel.EndpointAddress.Identity%2A> property that enables the authentication of the endpoint by other endpoints that exchange messages with it, and a set of optional <xref:System.ServiceModel.EndpointAddress.Headers%2A> properties, which define any other SOAP headers required to reach the service.</span></span> <span data-ttu-id="fc210-106">İsteğe bağlı üstbilgi ek sağlar ve daha ayrıntılı tanımlamak veya hizmet uç noktası ile etkileşim kurmak için adresleme bilgi.</span><span class="sxs-lookup"><span data-stu-id="fc210-106">The optional headers provide additional and more detailed addressing information to identify or interact with the service endpoint.</span></span> <span data-ttu-id="fc210-107">Bir uç nokta adresi kablo WS adresleme uç noktası başvuru olarak (EPR) gösterilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-107">The address of an endpoint is represented on the wire as a WS-Addressing endpoint reference (EPR).</span></span>  
  
## <a name="uri-structure-of-an-address"></a><span data-ttu-id="fc210-108">Bir adresi URI yapısı</span><span class="sxs-lookup"><span data-stu-id="fc210-108">URI Structure of an Address</span></span>  
 <span data-ttu-id="fc210-109">Çoğu taşıma için URI adresi dört bölümden oluşur.</span><span class="sxs-lookup"><span data-stu-id="fc210-109">The address URI for most transports has four parts.</span></span> <span data-ttu-id="fc210-110">Örneğin, dört URI'SİNİN bölümlerini http://www.fabrikam.com:322/mathservice.svc/secureEndpoint gibi dökümü:</span><span class="sxs-lookup"><span data-stu-id="fc210-110">For example, the four parts of the URI http://www.fabrikam.com:322/mathservice.svc/secureEndpoint can be itemized as follows:</span></span>  
  
-   <span data-ttu-id="fc210-111">Düzen: http:</span><span class="sxs-lookup"><span data-stu-id="fc210-111">Scheme: http:</span></span>  
  
-   <span data-ttu-id="fc210-112">Makine: www.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="fc210-112">Machine: www.fabrikam.com</span></span>  
  
-   <span data-ttu-id="fc210-113">(isteğe bağlı) Bağlantı noktası: 322</span><span class="sxs-lookup"><span data-stu-id="fc210-113">(optional) Port: 322</span></span>  
  
-   <span data-ttu-id="fc210-114">Yol: /mathservice.svc/secureEndpoint</span><span class="sxs-lookup"><span data-stu-id="fc210-114">Path: /mathservice.svc/secureEndpoint</span></span>  
  
## <a name="defining-an-address-for-a-service"></a><span data-ttu-id="fc210-115">Bir hizmet için bir adres tanımlama</span><span class="sxs-lookup"><span data-stu-id="fc210-115">Defining an Address for a Service</span></span>  
 <span data-ttu-id="fc210-116">Bir hizmet uç noktası adresi ya da imperatively kodu veya bildirimli olarak ile yapılandırma kullanılarak belirtilebilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-116">The endpoint address for a service can be specified either imperatively using code or declaratively through configuration.</span></span> <span data-ttu-id="fc210-117">Bağlamalar ve dağıtılmış bir hizmet için adresleri hizmet geliştirildiği sırada kullanılan olanlardan genellikle farklı olduğu için uç noktalar kodda tanımlama genellikle pratik değildir.</span><span class="sxs-lookup"><span data-stu-id="fc210-117">Defining endpoints in code is usually not practical because the bindings and addresses for a deployed service are typically different from those used while the service is being developed.</span></span> <span data-ttu-id="fc210-118">Genellikle, kod yerine Yapılandırması kullanılarak hizmet uç noktaları tanımlamak daha pratik olur.</span><span class="sxs-lookup"><span data-stu-id="fc210-118">Generally, it is more practical to define service endpoints using configuration rather than code.</span></span> <span data-ttu-id="fc210-119">Bağlama tutulması ve adresleme bilgilerini kodu dışında yeniden derleyin veya uygulamayı yeniden dağıtmak zorunda kalmadan değiştirmek için bunları sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc210-119">Keeping the binding and addressing information out of the code allows them to change without having to recompile or redeploy the application.</span></span>  
  
### <a name="defining-an-address-in-configuration"></a><span data-ttu-id="fc210-120">Yapılandırmada bir adresi tanımlama</span><span class="sxs-lookup"><span data-stu-id="fc210-120">Defining an Address in Configuration</span></span>  
 <span data-ttu-id="fc210-121">Bir yapılandırma dosyasında bir uç nokta tanımlamak için [ \<uç noktası >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) öğesi.</span><span class="sxs-lookup"><span data-stu-id="fc210-121">To define an endpoint in a configuration file, use the [\<endpoint>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span> <span data-ttu-id="fc210-122">Ayrıntılar ve bir örnek için bkz: [bir uç noktası adresi belirtme](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="fc210-122">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
### <a name="defining-an-address-in-code"></a><span data-ttu-id="fc210-123">Bir adresi kodda tanımlama</span><span class="sxs-lookup"><span data-stu-id="fc210-123">Defining an Address in Code</span></span>  
 <span data-ttu-id="fc210-124">Bir uç nokta adresi koduyla oluşturulabilir <xref:System.ServiceModel.EndpointAddress> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fc210-124">An endpoint address can be created in code with the <xref:System.ServiceModel.EndpointAddress> class.</span></span> <span data-ttu-id="fc210-125">Ayrıntılar ve bir örnek için bkz: [bir uç noktası adresi belirtme](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="fc210-125">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
### <a name="endpoints-in-wsdl"></a><span data-ttu-id="fc210-126">WSDL içindeki uç noktaları</span><span class="sxs-lookup"><span data-stu-id="fc210-126">Endpoints in WSDL</span></span>  
 <span data-ttu-id="fc210-127">Bir uç nokta adresi de WSDL içinde karşılık gelen uç noktanın içinde WS adresleme EPR öğe olarak temsil edilebilir `wsdl:port` öğesi.</span><span class="sxs-lookup"><span data-stu-id="fc210-127">An endpoint address can also be represented in WSDL as a WS-Addressing EPR element inside the corresponding endpoint's `wsdl:port` element.</span></span> <span data-ttu-id="fc210-128">EPR, uç noktanın adresi herhangi bir adres özelliği içerir.</span><span class="sxs-lookup"><span data-stu-id="fc210-128">The EPR contains the endpoint's address as well as any address properties.</span></span> <span data-ttu-id="fc210-129">Ayrıntılar ve bir örnek için bkz: [bir uç noktası adresi belirtme](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span><span class="sxs-lookup"><span data-stu-id="fc210-129">For details and an example, see [Specifying an Endpoint Address](../../../../docs/framework/wcf/specifying-an-endpoint-address.md).</span></span>  
  
## <a name="multiple-iis-binding-support-in-net-framework-35"></a><span data-ttu-id="fc210-130">Birden çok IIS .NET Framework 3.5 destek bağlama</span><span class="sxs-lookup"><span data-stu-id="fc210-130">Multiple IIS Binding Support in .NET Framework 3.5</span></span>  
 <span data-ttu-id="fc210-131">Internet hizmet sağlayıcıları, genellikle site yoğunluğu ve düşük toplam sahip olma maliyetini artırmak için birçok uygulama aynı sunucu ve site üzerinde barındırır.</span><span class="sxs-lookup"><span data-stu-id="fc210-131">Internet service providers often host many applications on the same server and site to increase the site density and lower total cost of ownership.</span></span> <span data-ttu-id="fc210-132">Bu uygulamalar genellikle farklı temel adreslerine bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="fc210-132">These applications are typically bound to different base addresses.</span></span> <span data-ttu-id="fc210-133">Internet Information Services (IIS) Web sitesini birden çok uygulama içerebilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-133">An Internet Information Services (IIS) Web site can contain multiple applications.</span></span> <span data-ttu-id="fc210-134">Bir sitedeki uygulamaları bir veya daha fazla IIS bağlamaları erişilebilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-134">The applications in a site can be accessed through one or more IIS bindings.</span></span>  
  
 <span data-ttu-id="fc210-135">IIS bağlamaları iki parça bilgi sağlar: bir bağlama protokolü ve bağlama bilgileri.</span><span class="sxs-lookup"><span data-stu-id="fc210-135">IIS bindings provide two pieces of information: a binding protocol, and binding information.</span></span> <span data-ttu-id="fc210-136">Bağlama protokolü üzerinden iletişimin şeması tanımlar ve bağlama bilgileri siteye erişmek için kullanılan bilgilerdir.</span><span class="sxs-lookup"><span data-stu-id="fc210-136">The binding protocol defines the scheme over which communication occurs, and binding information is the information used to access the site.</span></span>  
  
 <span data-ttu-id="fc210-137">Aşağıdaki örnek, bir IIS bağlaması mevcut olabilecek bileşenleri gösterir:</span><span class="sxs-lookup"><span data-stu-id="fc210-137">The following example shows the components that can be present in an IIS binding:</span></span>  
  
-   <span data-ttu-id="fc210-138">Bağlama iletişim kuralı: HTTP</span><span class="sxs-lookup"><span data-stu-id="fc210-138">Binding protocol: HTTP</span></span>  
  
-   <span data-ttu-id="fc210-139">Bağlama bilgileri: IP adresi, bağlantı noktası, ana bilgisayar üstbilgisi</span><span class="sxs-lookup"><span data-stu-id="fc210-139">Binding Information: IP Address, Port, Host header</span></span>  
  
 <span data-ttu-id="fc210-140">IIS her şeması için birden çok taban adresi sonuçlanan her site için birden fazla bağlama belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc210-140">IIS can specify multiple bindings for each site, which results in multiple base addresses for each scheme.</span></span> <span data-ttu-id="fc210-141">Öncesinde [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] birden çok adresi için bir şema desteklemiyor ve belirtilmiş olması durumunda belirtti bir <xref:System.ArgumentException> etkinleştirme sırasında.</span><span class="sxs-lookup"><span data-stu-id="fc210-141">Prior to [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] did not support multiple addresses for a schema and, if they were specified, threw a <xref:System.ArgumentException> during activation.</span></span>  
  
 <span data-ttu-id="fc210-142">[!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] Birden çok uygulama aynı sitedeki aynı düzeni için farklı temel adresleriyle barındırmak Internet hizmet sağlayıcıları sağlar.</span><span class="sxs-lookup"><span data-stu-id="fc210-142">The [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] enables Internet service providers to host multiple applications with different base addresses for the same scheme on the same site.</span></span>  
  
 <span data-ttu-id="fc210-143">Örneğin, bir site aşağıdaki temel adresler içerebilir:</span><span class="sxs-lookup"><span data-stu-id="fc210-143">For example, a site could contain the following base addresses:</span></span>  
  
-   <span data-ttu-id="fc210-144">http://Payroll.myOrg.com/Service.svc</span><span class="sxs-lookup"><span data-stu-id="fc210-144">http://payroll.myorg.com/Service.svc</span></span>  
  
-   <span data-ttu-id="fc210-145">http://shipping.myOrg.com/Service.svc</span><span class="sxs-lookup"><span data-stu-id="fc210-145">http://shipping.myorg.com/Service.svc</span></span>  
  
 <span data-ttu-id="fc210-146">İle [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], yapılandırma dosyasında bir önek filtre AppDomain düzeyinde belirtin.</span><span class="sxs-lookup"><span data-stu-id="fc210-146">With [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], you specify a prefix filter at the AppDomain level in the configuration file.</span></span> <span data-ttu-id="fc210-147">Bunu ile [ \<baseAddressPrefixFilters >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) öneklerinin bir listesini içeren öğe.</span><span class="sxs-lookup"><span data-stu-id="fc210-147">You do this with the [\<baseAddressPrefixFilters>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddressprefixfilters.md) element, which contains a list of prefixes.</span></span> <span data-ttu-id="fc210-148">IIS tarafından sağlanan gelen temel adresler, isteğe bağlı önek listesi göre filtrelenir.</span><span class="sxs-lookup"><span data-stu-id="fc210-148">The incoming base addresses, supplied by IIS, are filtered based on the optional prefix list.</span></span> <span data-ttu-id="fc210-149">Bir önek belirtilmediğinde, varsayılan olarak, tüm adresleri üzerinden geçirilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-149">By default, when a prefix is not specified, all addresses are passed through.</span></span> <span data-ttu-id="fc210-150">Önek sonuçları yalnızca eşleşen taban adresi üzerinden iletilecek bu düzeni için belirterek.</span><span class="sxs-lookup"><span data-stu-id="fc210-150">Specifying the prefix results in only the matching base address for that scheme to be passed through.</span></span>  
  
 <span data-ttu-id="fc210-151">Önek filtreleri kullanan yapılandırma kodu örneği verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="fc210-151">The following is an example of configuration code that uses the prefix filters.</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment>  
     <baseAddressPrefixFilters>  
        <add prefix="net.tcp://payroll.myorg.com:8000"/>  
        <add prefix="http://shipping.myorg.com:8000"/>  
    </baseAddressPrefixFilters>  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="fc210-152">Önceki örnekte, net.tcp://payroll.myorg.com: 8000 ve http://shipping.myorg.com:8000 geçirilecek kendi ilgili şemaları için yalnızca temel adres.</span><span class="sxs-lookup"><span data-stu-id="fc210-152">In the preceding example, net.tcp://payroll.myorg.com:8000 and http://shipping.myorg.com:8000 are the only base addresses, for their respective schemes, which are passed through.</span></span>  
  
 <span data-ttu-id="fc210-153">`baseAddressPrefixFilter` Joker karakterleri desteklemez.</span><span class="sxs-lookup"><span data-stu-id="fc210-153">The `baseAddressPrefixFilter` does not support wildcards.</span></span>  
  
 <span data-ttu-id="fc210-154">IIS tarafından sağlanan temel adresler adresleri değil diğer düzenleri bağlı olabilir `baseAddressPrefixFilters` listesi.</span><span class="sxs-lookup"><span data-stu-id="fc210-154">The base addresses supplied by IIS may have addresses bound to other schemes not present in `baseAddressPrefixFilters` list.</span></span> <span data-ttu-id="fc210-155">Bu adresler filtrelendi değil.</span><span class="sxs-lookup"><span data-stu-id="fc210-155">These addresses are not filtered out.</span></span>  
  
## <a name="multiple-iis-binding-support-in-net-framework-4-and-later"></a><span data-ttu-id="fc210-156">Birden çok IIS bağlama desteği .NET Framework 4 ve üzeri</span><span class="sxs-lookup"><span data-stu-id="fc210-156">Multiple IIS Binding Support in .NET Framework 4 and later</span></span>  
 <span data-ttu-id="fc210-157">.NET 4'ten başlayarak, birden fazla bağlama IIS'de desteği tek bir taban adresi ayarlayarak çekme gerek kalmadan etkinleştirebilirsiniz <xref:System.ServiceModel.ServiceHostingEnvironment>'s <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> ayarı TRUE.</span><span class="sxs-lookup"><span data-stu-id="fc210-157">Starting in .NET 4, you can enable support for multiple bindings in IIS without having to pick a single base address, by setting <xref:System.ServiceModel.ServiceHostingEnvironment>’s <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A> setting to true.</span></span> <span data-ttu-id="fc210-158">Bu destek, HTTP protokol düzenleri sınırlıdır.</span><span class="sxs-lookup"><span data-stu-id="fc210-158">This support is limited to HTTP protocol schemes.</span></span>  
  
 <span data-ttu-id="fc210-159">Aşağıdaki multipleSiteBindingsEnabled kullanır yapılandırma kodu örneğidir [ \<serviceHostingEnvironment >](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).</span><span class="sxs-lookup"><span data-stu-id="fc210-159">The following is an example of configuration code that uses multipleSiteBindingsEnabled on [\<serviceHostingEnvironment>](../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).</span></span>  
  
```xml  
<system.serviceModel>  
  <serviceHostingEnvironment multipleSiteBindingsEnabled="true" >  
  </serviceHostingEnvironment>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="fc210-160">Bu ayarı kullanarak birden çok site bağlamaları etkin olduğunda baseAddressPrefixFilters ayarları, hem HTTP hem de HTTP olmayan protokolleri için göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-160">Any baseAddressPrefixFilters settings are ignored, for both HTTP and non-HTTP protocols, when multiple site bindings are enabled using this setting.</span></span>  
  
 <span data-ttu-id="fc210-161">Ayrıntılı bilgi ve örnekler için bkz: [birden fazla IIS Site bağlamasını destekleme](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) ve <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="fc210-161">For details and examples, see [Supporting Multiple IIS Site Bindings](../../../../docs/framework/wcf/feature-details/supporting-multiple-iis-site-bindings.md) and <xref:System.ServiceModel.ServiceHostingEnvironment.MultipleSiteBindingsEnabled%2A>.</span></span>  
  
## <a name="extending-addressing-in-wcf-services"></a><span data-ttu-id="fc210-162">WCF hizmetlerinde adresleme genişletme</span><span class="sxs-lookup"><span data-stu-id="fc210-162">Extending Addressing in WCF Services</span></span>  
 <span data-ttu-id="fc210-163">Varsayılan adresleme modelini [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Hizmetleri uç noktası adresi URI aşağıdaki amaçlarla kullanır:</span><span class="sxs-lookup"><span data-stu-id="fc210-163">The default addressing model of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services uses the endpoint address URI for the following purposes:</span></span>  
  
-   <span data-ttu-id="fc210-164">Hizmet dinleme adresi, bitiş noktası için iletileri dinleyen konumu belirtmek için</span><span class="sxs-lookup"><span data-stu-id="fc210-164">To specify the service listening address, the location at which the endpoint listens for messages,</span></span>  
  
-   <span data-ttu-id="fc210-165">SOAP adresi filtresi belirtmek için adres SOAP üstbilgi olarak bir uç nokta bekler.</span><span class="sxs-lookup"><span data-stu-id="fc210-165">To specify the SOAP address filter, the address an endpoint expects as a SOAP header.</span></span>  
  
 <span data-ttu-id="fc210-166">Değerlerin her biri bu amaçlar için ayrı olarak, bu yararlı senaryoları adresleme birkaç uzantılarına olanak veren belirtilebilir:</span><span class="sxs-lookup"><span data-stu-id="fc210-166">The values for each of these purposes can be specified separately, allowing several extensions of addressing that cover useful scenarios:</span></span>  
  
-   <span data-ttu-id="fc210-167">SOAP aracılar: bir istemci tarafından gönderilen bir ileti son hedefine ulaşmadan önce iletiyi işleyen bir veya daha fazla ek hizmet erişir.</span><span class="sxs-lookup"><span data-stu-id="fc210-167">SOAP intermediaries: a message sent by a client traverses one or more additional services that process the message before it reaches its final destination.</span></span> <span data-ttu-id="fc210-168">SOAP aracılar önbelleğe alma, yönlendirme, Yük Dengeleme veya şema doğrulama iletileri gibi çeşitli görevleri gerçekleştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc210-168">SOAP intermediaries can perform various tasks, such as caching, routing, load-balancing, or schema validation on the messages.</span></span> <span data-ttu-id="fc210-169">Bu senaryo için ayrı bir fiziksel adresi iletileri göndererek yapıldığını (`via`) aracı yerine yalnızca bir mantıksal adresine hedefleyen (`wsa:To`) ultimate hedef hedefleyen.</span><span class="sxs-lookup"><span data-stu-id="fc210-169">This scenario is accomplished by sending messages to a separate physical address (`via`) that targets the intermediary rather than just to a logical address (`wsa:To`) that targets the ultimate destination.</span></span>  
  
-   <span data-ttu-id="fc210-170">Uç nokta dinleme adresini özel bir URI ve farklı bir değere ayarlamak, `listenURI` özelliği.</span><span class="sxs-lookup"><span data-stu-id="fc210-170">The listening address of the endpoint is a private URI and is set to a different value than its `listenURI` property.</span></span>  
  
 <span data-ttu-id="fc210-171">Taşıma adres `via` olduğu bir ileti başlangıçta gönderilmesi gerektiğini başka bir uzak adres yolu üzerindeki konumu tarafından belirtilir belirtir `to` hizmet bulunduğu parametresi.</span><span class="sxs-lookup"><span data-stu-id="fc210-171">The transport address that the `via` specifies is the location to which a message should initially be sent on its way to some other remote address specified by the `to` parameter at which the service is located.</span></span> <span data-ttu-id="fc210-172">Çoğu Internet senaryoda `via` URI aynıdır <xref:System.ServiceModel.EndpointAddress.Uri%2A> son özelliğinin `to` hizmetinin adresi.</span><span class="sxs-lookup"><span data-stu-id="fc210-172">In most Internet scenarios, the `via` URI is the same as the <xref:System.ServiceModel.EndpointAddress.Uri%2A> property of the final `to` address of the service.</span></span> <span data-ttu-id="fc210-173">Yalnızca el ile üretim yapmanız gerekir, bu iki adresler arasında ayrım yapmak.</span><span class="sxs-lookup"><span data-stu-id="fc210-173">You only distinguish between these two addresses when you must do manual routing.</span></span>  
  
### <a name="addressing-headers"></a><span data-ttu-id="fc210-174">Adres üstbilgileri</span><span class="sxs-lookup"><span data-stu-id="fc210-174">Addressing Headers</span></span>  
 <span data-ttu-id="fc210-175">Bir uç nokta temel URI'sini yanı sıra bir veya daha fazla SOAP üstbilgileri çözülebilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-175">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="fc210-176">Bu faydalı olduğu senaryolar bir dizi, burada bir uç nokta aracılar hedeflenen SOAP üstbilgileri dahil etmek Bu uç noktanın gerektirir. istemciler SOAP Ara senaryoları kümesidir.</span><span class="sxs-lookup"><span data-stu-id="fc210-176">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span>  
  
 <span data-ttu-id="fc210-177">İki yolla özel adres üstbilgileri tanımlayabilirsiniz — kod veya yapılandırma kullanarak:</span><span class="sxs-lookup"><span data-stu-id="fc210-177">You can define custom address headers in two ways—by using either code or configuration:</span></span>  
  
-   <span data-ttu-id="fc210-178">Kullanarak kod içinde özel adres üstbilgileri oluşturma <xref:System.ServiceModel.Channels.AddressHeader> sınıfı ve yapımı içinde kullanılan bir <xref:System.ServiceModel.EndpointAddress>.</span><span class="sxs-lookup"><span data-stu-id="fc210-178">In code, create custom address headers by using the <xref:System.ServiceModel.Channels.AddressHeader> class, and then used in the construction of an <xref:System.ServiceModel.EndpointAddress>.</span></span>  
  
-   <span data-ttu-id="fc210-179">Yapılandırmada, özel [ \<üstbilgiler >](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) alt olarak belirtilen [ \<uç noktası >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) öğesi.</span><span class="sxs-lookup"><span data-stu-id="fc210-179">In configuration, custom [\<headers>](../../../../docs/framework/configure-apps/file-schema/wcf/headers.md) are specified as children of the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
 <span data-ttu-id="fc210-180">Dağıtımdan sonra üstbilgileri değiştirmenize izin verdiğinden yapılandırma kod, genellikle tercih edilir.</span><span class="sxs-lookup"><span data-stu-id="fc210-180">Configuration is generally preferable to code, as it allows you to change the headers after deployment.</span></span>  
  
### <a name="custom-listening-addresses"></a><span data-ttu-id="fc210-181">Özel dinleme adresleri</span><span class="sxs-lookup"><span data-stu-id="fc210-181">Custom Listening Addresses</span></span>  
 <span data-ttu-id="fc210-182">Uç noktanın URI farklı bir değere dinleme adresini ayarlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="fc210-182">You can set the listening address to a different value than the endpoint’s URI.</span></span> <span data-ttu-id="fc210-183">Burada uç nokta gerçekte dinler adresi bir özel ağ adresi iken açığa çıkarılması SOAP adresi, aracı, bir ortak SOAP olduğu Ara senaryolarda kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="fc210-183">This is useful in intermediary scenarios where the SOAP address to be exposed is that of a public SOAP intermediary, whereas the address where the endpoint actually listens is a private network address.</span></span>  
  
 <span data-ttu-id="fc210-184">Kod veya yapılandırma kullanarak özel bir dinleme adresi belirtebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="fc210-184">You can specify a custom listening address by using either code or configuration:</span></span>  
  
-   <span data-ttu-id="fc210-185">Kodda ekleyerek özel dinleme adresi belirtin. bir <xref:System.ServiceModel.Description.ClientViaBehavior> uç noktanın davranış koleksiyonu sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fc210-185">In code, specify a custom listening address by adding a <xref:System.ServiceModel.Description.ClientViaBehavior> class to the endpoint’s behavior collection.</span></span>  
  
-   <span data-ttu-id="fc210-186">Özel bir dinleme adresiyle Yapılandırması'nda belirtin `ListenUri` özniteliği hizmetinin [ \<uç noktası >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) öğesi.</span><span class="sxs-lookup"><span data-stu-id="fc210-186">In configuration, specify a custom listening address with the `ListenUri` attribute of the service [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
### <a name="custom-soap-address-filter"></a><span data-ttu-id="fc210-187">Özel SOAP adresi filtresi</span><span class="sxs-lookup"><span data-stu-id="fc210-187">Custom SOAP Address Filter</span></span>  
 <span data-ttu-id="fc210-188"><xref:System.ServiceModel.EndpointAddress.Uri%2A> Herhangi ile birlikte kullanılan <xref:System.ServiceModel.EndpointAddress.Headers%2A> bir uç noktanın SOAP adresi filtresi tanımlamak için özelliği (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>).</span><span class="sxs-lookup"><span data-stu-id="fc210-188">The <xref:System.ServiceModel.EndpointAddress.Uri%2A> is used in conjunction with any <xref:System.ServiceModel.EndpointAddress.Headers%2A> property to define an endpoint’s SOAP address filter (<xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>).</span></span> <span data-ttu-id="fc210-189">Varsayılan olarak, bu filtre gelen iletiyi sahip olduğunu doğrular bir `To` uç noktayla eşleşen ileti üstbilgisi kullanıcının URI ve tüm gerekli uç nokta üstbilgilerinin iletide.</span><span class="sxs-lookup"><span data-stu-id="fc210-189">By default, this filter verifies that an incoming message has a `To` message header that matches the endpoint’s URI and that all of the required endpoint headers are present in the message.</span></span>  
  
 <span data-ttu-id="fc210-190">Bazı senaryolarda, bir uç nokta temel aktarımı ve uygun yalnızca olanlar gelen tüm iletileri alır `To` üstbilgi.</span><span class="sxs-lookup"><span data-stu-id="fc210-190">In some scenarios, an endpoint receives all messages that arrive on the underlying transport, and not just those with the appropriate `To` header.</span></span> <span data-ttu-id="fc210-191">Bunu etkinleştirmek için kullanıcı kullanabilir <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fc210-191">To enable this, the user can use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc210-192">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fc210-192">See Also</span></span>  
 [<span data-ttu-id="fc210-193">Bir uç noktası adresi belirtme</span><span class="sxs-lookup"><span data-stu-id="fc210-193">Specifying an Endpoint Address</span></span>](../../../../docs/framework/wcf/specifying-an-endpoint-address.md)  
 [<span data-ttu-id="fc210-194">Hizmet kimliği ve kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="fc210-194">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)