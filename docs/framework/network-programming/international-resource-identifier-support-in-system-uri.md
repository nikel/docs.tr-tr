---
title: "System.Uri uluslararası kaynak tanımlayıcısı desteği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5e994c3-3535-4aff-8e1b-b69be22e9a22
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: e11e6a6746c555db9b51d76da3554ce75c1f6ee8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="international-resource-identifier-support-in-systemuri"></a><span data-ttu-id="85e85-102">System.Uri uluslararası kaynak tanımlayıcısı desteği</span><span class="sxs-lookup"><span data-stu-id="85e85-102">International Resource Identifier Support in System.Uri</span></span>
<span data-ttu-id="85e85-103"><xref:System.Uri?displayProperty=nameWithType> Sınıfı genişletilmişse uluslararası kaynak tanımlayıcısı (IRI) ve Uluslararası yapılan etki alanı adları (IDN) desteği.</span><span class="sxs-lookup"><span data-stu-id="85e85-103">The <xref:System.Uri?displayProperty=nameWithType> class has been extended with International Resource Identifier (IRI) and Internationalized Domain Names (IDN) support.</span></span> <span data-ttu-id="85e85-104">Bu geliştirmeler, .NET Framework 3.5, 3.0 SP1 ve 2.0 SP1'de kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="85e85-104">These enhancements are available in .NET Framework 3.5, 3.0 SP1, and 2.0 SP1.</span></span>  
  
## <a name="iri-and-idn-support"></a><span data-ttu-id="85e85-105">IRI ve IDN desteği</span><span class="sxs-lookup"><span data-stu-id="85e85-105">IRI and IDN Support</span></span>  
 <span data-ttu-id="85e85-106">Web adresleri genellikle Tekdüzen Kaynak Tanımlayıcıları (çok kısıtlı bir karakter kümesi oluşur URI) kullanarak belirtilmiştir:</span><span class="sxs-lookup"><span data-stu-id="85e85-106">Web addresses are typically expressed using Uniform Resource Identifiers (URI) that consist of a very restricted set of characters:</span></span>  
  
-   <span data-ttu-id="85e85-107">Büyük ve küçük ASCII harf İngilizce alfabesinde.</span><span class="sxs-lookup"><span data-stu-id="85e85-107">Upper and lower case ASCII letters from the English alphabet.</span></span>  
  
-   <span data-ttu-id="85e85-108">9 basamak 0.</span><span class="sxs-lookup"><span data-stu-id="85e85-108">Digits from 0 to 9.</span></span>  
  
-   <span data-ttu-id="85e85-109">Diğer ASCII simgelerini küçük sayısı.</span><span class="sxs-lookup"><span data-stu-id="85e85-109">A small number of other ASCII symbols.</span></span>  
  
 <span data-ttu-id="85e85-110">RFC 2396 ve RFC 3986 Internet Engineering Task Force (IETF) tarafından yayımlanan URI'ler belirtimleri belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="85e85-110">The specifications for URIs are documented in RFC 2396 and RFC 3986 published by the Internet Engineering Task Force (IETF).</span></span>  
  
 <span data-ttu-id="85e85-111">Internet büyümesi ile İngilizce dışındaki dilleri kullanarak kaynakları tanımlamak için büyüyen bir gereksinimi yoktur.</span><span class="sxs-lookup"><span data-stu-id="85e85-111">With the growth of the Internet, there is a growing need to identify resources using languages other than English.</span></span> <span data-ttu-id="85e85-112">Bu gereksinim kolaylaştırmak ve ASCII olmayan karakterler (karakter Unicode/ISO 10646 karakter kümesinde) izin tanımlayıcılarını uluslararası kaynak tanımlayıcıları (IRIS) bilinir.</span><span class="sxs-lookup"><span data-stu-id="85e85-112">Identifiers which facilitate this need and allow non-ASCII characters (characters in the Unicode/ISO 10646 character set) are known as International Resource Identifiers (IRIs).</span></span> <span data-ttu-id="85e85-113">IRIs belirtimleri RFC IETF tarafından yayımlanan 3987 belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="85e85-113">The specifications for IRIs are documented in RFC 3987 published by IETF.</span></span> <span data-ttu-id="85e85-114">IRIs kullanarak Unicode karakterler içeren bir URL sağlar.</span><span class="sxs-lookup"><span data-stu-id="85e85-114">Using IRIs allows a URL to contain Unicode characters.</span></span>  
  
 <span data-ttu-id="85e85-115">Varolan <xref:System.Uri?displayProperty=nameWithType> sınıfı genişletilmişse RFC 3987 üzerinde IRI desteği sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="85e85-115">The existing <xref:System.Uri?displayProperty=nameWithType> class has been extended to provide IRI support based on RFC 3987.</span></span> <span data-ttu-id="85e85-116">Bunlar IRI özellikle etkinleştirmediğiniz sürece geçerli kullanıcılar .NET Framework 2.0 davranış herhangi bir değişiklik görmez.</span><span class="sxs-lookup"><span data-stu-id="85e85-116">Current users will not see any change from the .NET Framework 2.0 behavior unless they specifically enable IRI.</span></span> <span data-ttu-id="85e85-117">Bu, .NET Framework'ün önceki sürümler ile uygulama uyumluluğunu sağlar.</span><span class="sxs-lookup"><span data-stu-id="85e85-117">This ensures application compatibility with prior versions of the .NET Framework.</span></span>  
  
 <span data-ttu-id="85e85-118">Uygulama etki alanı adlarına uygulanan Uluslararası yapılan etki alanı adı (IDN) ayrıştırma kullanılıp kullanılmayacağını ve kuralları ayrıştırma IRI uygulanıp belirtebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="85e85-118">An application can specify whether to use Internationalized Domain Name (IDN) parsing applied to domain names and whether IRI parsing rules should be applied.</span></span> <span data-ttu-id="85e85-119">Machine.config veya app.config dosyasında yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="85e85-119">This can be done in the machine.config or in the app.config file.</span></span>  
  
 <span data-ttu-id="85e85-120">Bir etki alanı adındaki tüm Unicode etiketleri IDN etkinleştirme Punycode eşdeğerlerine dönüştürür.</span><span class="sxs-lookup"><span data-stu-id="85e85-120">Enabling IDN will convert all Unicode labels in a domain name to their Punycode equivalents.</span></span> <span data-ttu-id="85e85-121">Zayıf kod adları yalnızca ASCII karakterler içeren ve her zaman xn--önekiyle başlatın.</span><span class="sxs-lookup"><span data-stu-id="85e85-121">Punycode names contain only ASCII characters and always start with the xn-- prefix.</span></span> <span data-ttu-id="85e85-122">Bunun nedeni çoğu DNS sunucuları, yalnızca ASCII karakterleri (RFC 3940 bakın) destekler beri Internet'te var olan DNS sunucuları desteklemektir.</span><span class="sxs-lookup"><span data-stu-id="85e85-122">The reason for this is to support existing DNS servers on the Internet, since most DNS servers only support ASCII characters (see RFC 3940).</span></span>  
  
 <span data-ttu-id="85e85-123">IRI ve IDN etkinleştirilmesi etkiler değerini <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType> özelliği.</span><span class="sxs-lookup"><span data-stu-id="85e85-123">Enabling IRI and IDN affects the value of the <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="85e85-124">IRI ve IDN etkinleştirme davranışını da değiştirebilir <xref:System.Uri.Equals%2A?displayProperty=nameWithType>, <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType>, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType>, ve <xref:System.Uri.IsWellFormedOriginalString%2A> yöntemleri.</span><span class="sxs-lookup"><span data-stu-id="85e85-124">Enabling IRI and IDN can also change the behavior of the <xref:System.Uri.Equals%2A?displayProperty=nameWithType>, <xref:System.Uri.OriginalString%2A?displayProperty=nameWithType>, <xref:System.Uri.GetComponents%2A?displayProperty=nameWithType>, and <xref:System.Uri.IsWellFormedOriginalString%2A> methods.</span></span>  
  
 <span data-ttu-id="85e85-125"><xref:System.GenericUriParser?displayProperty=nameWithType> Sınıfı ayrıca genişletilmişse IRI ve IDN destekleyen özelleştirilebilir ayrıştırıcı oluşturma izin vermek için.</span><span class="sxs-lookup"><span data-stu-id="85e85-125">The <xref:System.GenericUriParser?displayProperty=nameWithType> class has also been extended to allow creating a customizable parser that supports IRI and IDN.</span></span> <span data-ttu-id="85e85-126">Davranışını bir <xref:System.GenericUriParser?displayProperty=nameWithType> nesne bulunan değerlerin Bitsel bir birleşimi geçirerek belirtilen <xref:System.GenericUriParserOptions?displayProperty=nameWithType> numaralandırma <xref:System.GenericUriParser?displayProperty=nameWithType> Oluşturucusu.</span><span class="sxs-lookup"><span data-stu-id="85e85-126">The behavior of a <xref:System.GenericUriParser?displayProperty=nameWithType> object is specified by passing a bitwise combination of the values available in the <xref:System.GenericUriParserOptions?displayProperty=nameWithType> enumeration to the <xref:System.GenericUriParser?displayProperty=nameWithType> constructor.</span></span> <span data-ttu-id="85e85-127"><xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType> Türünü gösteren ayrıştırıcı RFC 3987 uluslararası kaynak tanımlayıcıları (IRI) için belirtilen ayrıştırma kuralları destekler.</span><span class="sxs-lookup"><span data-stu-id="85e85-127">The <xref:System.GenericUriParserOptions.IriParsing?displayProperty=nameWithType> type indicates the parser supports the parsing rules specified in RFC 3987 for International Resource Identifiers (IRI).</span></span> <span data-ttu-id="85e85-128">IRI gerçekten kullanılıp kullanılmadığını IRI etkin olup olmadığını bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="85e85-128">Whether IRI is actually used depends on if IRI is enabled.</span></span>  
  
 <span data-ttu-id="85e85-129"><xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType> Türünü gösteren ayrıştırıcı Uluslararası yapılan etki alanı adı (IDN) ana bilgisayar adlarını (IDN) ayrıştırma destekler.</span><span class="sxs-lookup"><span data-stu-id="85e85-129">The <xref:System.GenericUriParserOptions.Idn?displayProperty=nameWithType> type indicates the parser supports Internationalized Domain Name (IDN) parsing (IDN) of host names.</span></span> <span data-ttu-id="85e85-130">IDN gerçekte kullanılıp kullanılmadığını IDN etkin olup olmadığını bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="85e85-130">Whether IDN is actually used depends on if IDN is enabled.</span></span>  
  
 <span data-ttu-id="85e85-131">IRI etkinleştirme ayrıştırma normalleştirme ne yapacağını ve RFC 3987 göre en son IRI denetimi karakter kuralları.</span><span class="sxs-lookup"><span data-stu-id="85e85-131">Enabling IRI parsing will do normalization and character checking according to the latest IRI rules in RFC 3987.</span></span> <span data-ttu-id="85e85-132">Normalleştirme ve karakter denetimi RFC 2396 ve RFC 3986 göre yapılan şekilde devre dışı bırakılması ayrıştırma IRI için varsayılan değerdir.</span><span class="sxs-lookup"><span data-stu-id="85e85-132">The default value is for IRI parsing to be disabled so normalization and character checking are done according to RFC 2396 and RFC 3986.</span></span>  
  
 <span data-ttu-id="85e85-133">IRI ve içinde işleme IDN <xref:System.Uri?displayProperty=nameWithType> sınıfı da denetlenebilir kullanarak <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> ve <xref:System.Configuration.IdnElement?displayProperty=nameWithType> yapılandırma ayarı sınıflarını.</span><span class="sxs-lookup"><span data-stu-id="85e85-133">IRI and IDN processing in the <xref:System.Uri?displayProperty=nameWithType> class can also be controlled using the <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> and <xref:System.Configuration.IdnElement?displayProperty=nameWithType> configuration setting classes.</span></span> <span data-ttu-id="85e85-134"><xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> Ayarını etkinleştirir veya içinde işleme IRI devre dışı bırakır <xref:System.Uri?displayProperty=nameWithType> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="85e85-134">The <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> setting enables or disables IRI processing in the <xref:System.Uri?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="85e85-135"><xref:System.Configuration.IdnElement?displayProperty=nameWithType> Ayarını etkinleştirir veya içinde işleme IDN devre dışı bırakır <xref:System.Uri> sınıfı.</span><span class="sxs-lookup"><span data-stu-id="85e85-135">The <xref:System.Configuration.IdnElement?displayProperty=nameWithType> setting enables or disables IDN processing in the <xref:System.Uri> class.</span></span> <span data-ttu-id="85e85-136"><xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> Da dolaylı olarak ayarlama IDN denetler.</span><span class="sxs-lookup"><span data-stu-id="85e85-136">The <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> setting also indirectly controls IDN.</span></span> <span data-ttu-id="85e85-137">IRI işleme olabilmesi için işleme IDN için etkinleştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="85e85-137">IRI processing must be enabled for IDN processing to be possible.</span></span> <span data-ttu-id="85e85-138">IRI işleme devre dışıysa, IDN işleme burada .NET Framework 2.0 davranışı uyumluluk için kullanılır ve IDN adları kullanılmayan varsayılan ayar olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="85e85-138">If IRI processing is disabled, then IDN processing will be set to the default setting where the .NET Framework 2.0 behavior is used for compatibility and IDN names are not used.</span></span>  
  
 <span data-ttu-id="85e85-139">İçin yapılandırma ayarı <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> ve <xref:System.Configuration.IdnElement?displayProperty=nameWithType> yapılandırma sınıfları okunabilir bir kez zaman ilk <xref:System.Uri?displayProperty=nameWithType> sınıfı yapılandırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="85e85-139">The configuration setting for the <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType> and <xref:System.Configuration.IdnElement?displayProperty=nameWithType> configuration classes will be read once when the first <xref:System.Uri?displayProperty=nameWithType> class is constructed.</span></span> <span data-ttu-id="85e85-140">Bu süre sonunda yapılandırma ayarlarında yapılan değişiklikler göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="85e85-140">Changes to configuration settings after that time are ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85e85-141">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="85e85-141">See Also</span></span>  
 <xref:System.Configuration.IdnElement?displayProperty=nameWithType>  
 <xref:System.Configuration.IriParsingElement?displayProperty=nameWithType>  
 <xref:System.Uri?displayProperty=nameWithType>  
 <xref:System.Uri.DnsSafeHost%2A?displayProperty=nameWithType>