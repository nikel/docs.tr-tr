---
title: "WCF Web HTTP Hizmetleri için Önbelleğe Alma Desteği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f8078e0-00d9-415c-b8ba-c1b6d5c31799
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b951c77e522180fa615a9b6853bfc195a3e5bcb2
ms.sourcegitcommit: 5d0e069655439984862a835f400058b7e8bbadc6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2017
---
# <a name="caching-support-for-wcf-web-http-services"></a><span data-ttu-id="a8ef3-102">WCF Web HTTP Hizmetleri için Önbelleğe Alma Desteği</span><span class="sxs-lookup"><span data-stu-id="a8ef3-102">Caching Support for WCF Web HTTP Services</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]<span data-ttu-id="a8ef3-103">WCF Web HTTP hizmetlerinizi ASP.NET zaten mevcut bir bildirim temelli önbelleğe alma mekanizması kullanmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-103"> enables you to use the declarative caching mechanism already available in ASP.NET in your WCF Web HTTP services.</span></span> <span data-ttu-id="a8ef3-104">Bu, önbelleği yanıtlarını WCF Web HTTP hizmeti işlemlerinden sağlar.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-104">This allows you to cache responses from your WCF Web HTTP service operations.</span></span> <span data-ttu-id="a8ef3-105">Bir kullanıcı bir HTTP GET hizmetinize önbelleğe alma işlemi için yapılandırılmış gönderdiğinde, ASP.NET önbelleğe alınmış bir yanıtı geri gönderir ve hizmet yöntemi çağrılmaz.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-105">When a user sends an HTTP GET to your service that is configured for caching, ASP.NET sends back the cached response and the service method is not called.</span></span> <span data-ttu-id="a8ef3-106">Önbellek, bir kullanıcı bir HTTP GET gönderir sonraki süresi dolduğunda, hizmeti yöntemi olarak adlandırılır ve yanıt yine önbelleğe alınır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-106">When the cache expires, the next time a user sends an HTTP GET, your service method is called and the response is once again cached.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a8ef3-107">Bkz: ASP.NET önbelleğe alma, [ASP.NET önbelleğe alma genel bakış](http://go.microsoft.com/fwlink/?LinkId=152534)</span><span class="sxs-lookup"><span data-stu-id="a8ef3-107"> ASP.NET caching, see [ASP.NET Caching Overview](http://go.microsoft.com/fwlink/?LinkId=152534)</span></span>  
  
## <a name="basic-web-http-service-caching"></a><span data-ttu-id="a8ef3-108">Temel Web HTTP hizmeti önbelleğe alma</span><span class="sxs-lookup"><span data-stu-id="a8ef3-108">Basic Web HTTP Service Caching</span></span>  
 <span data-ttu-id="a8ef3-109">WEB HTTP etkinleştirmek için önbelleğe alma hizmeti ilk ASP.NET uyumluluğu uygulayarak etkinleştirmelisiniz <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> hizmet ayarına <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> için <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> veya <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-109">To enable WEB HTTP service caching you must first enable ASP.NET compatibility by applying the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to the service setting <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute.RequirementsMode%2A> to <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Allowed> or <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsMode.Required>.</span></span>  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="a8ef3-110">adlı yeni bir öznitelik tanıtır <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> önbellek profili adını belirtmenize olanak verir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-110"> introduces a new attribute called <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> that allows you to specify a cache profile name.</span></span> <span data-ttu-id="a8ef3-111">Bu öznitelik, bir hizmet işlemi uygulanır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-111">This attribute is applied to a service operation.</span></span> <span data-ttu-id="a8ef3-112">Aşağıdaki örnek uygular <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> ASP.NET uyumluluğu sağlamak için bir hizmet ve yapılandırır `GetCustomer` önbelleğe alma işlemi.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-112">The following example applies the <xref:System.ServiceModel.Activation.AspNetCompatibilityRequirementsAttribute> to a service to enable ASP.NET compatibility and configures the `GetCustomer` operation for caching.</span></span> <span data-ttu-id="a8ef3-113"><!--zz<xref:System.ServiceModel.Activation.AspNetCacheProfileAttribute>--> `System.ServiceModel.Activation.AspNetCacheProfileAttribute` Özniteliği kullanılacak önbellek ayarları içeren bir önbellek profili belirtir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-113">The <!--zz<xref:System.ServiceModel.Activation.AspNetCacheProfileAttribute>--> `System.ServiceModel.Activation.AspNetCacheProfileAttribute` attribute specifies a cache profile that contains the cache settings to be used.</span></span>  
  
```csharp
[ServiceContract] AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]
public class Service
{
    [WebGet(UriTemplate = "{id}")]
    [AspNetCacheProfile("CacheFor60Seconds")]
    public Customer GetCustomer(string id)
    {
        // ...
    }
}
```  
  
 <span data-ttu-id="a8ef3-114">Aşağıdaki örnekte gösterildiği gibi Web.config dosyasında ASP.NET uyumluluğu modunu etkinleştirmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-114">You must also turn on ASP.NET compatibility mode in the Web.config file as shown in the following example.</span></span>  
  
```xml
<system.serviceModel>
  <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />
</system.serviceModel>
```
  
> [!WARNING]
>  <span data-ttu-id="a8ef3-115">ASP.NET uyumluluğu modu açık değilse ve <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> kullanılan bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-115">If ASP.NET compatibility mode is not turned on and the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> is used an exception is thrown.</span></span>  
  
 <span data-ttu-id="a8ef3-116">Belirtilen önbellek profili adı <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> Web.config yapılandırma dosyasına eklenen bir önbellek profili tanımlar.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-116">The cache profile name specified by the <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute> identifies a cache profile that is added to your Web.config configuration file.</span></span> <span data-ttu-id="a8ef3-117">Önbellek profili ile tanımlanan bir <`outputCacheSetting`> aşağıdaki yapılandırma örnekte gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-117">The cache profile is defined with in a <`outputCacheSetting`> element as shown in the following configuration example.</span></span>  
  
```xml
<!-- ...  -->
<system.web>  
   <caching>  
      <outputCacheSettings>  
         <outputCacheProfiles>  
            <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable"/>  
         </outputCacheProfiles>  
      </outputCacheSettings>  
   </caching>  
   <!-- ... -->  
</system.web>  
```  
  
 <span data-ttu-id="a8ef3-118">ASP.NET uygulamaları için kullanılabilir aynı yapılandırma öğesi budur.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-118">This is the same configuration element that is available to ASP.NET applications.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a8ef3-119">Bkz: ASP.NET önbellek profilleri <xref:System.Web.Configuration.OutputCacheProfile>.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-119"> ASP.NET cache profiles, see <xref:System.Web.Configuration.OutputCacheProfile>.</span></span> <span data-ttu-id="a8ef3-120">Web HTTP Hizmetleri için önbellek profili en önemli öznitelikleri şunlardır: `cacheDuration` ve `varyByParam`.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-120">For Web HTTP services, the most important attributes in the cache profile are: `cacheDuration` and `varyByParam`.</span></span> <span data-ttu-id="a8ef3-121">Bu öznitelikler her ikisi de gereklidir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-121">Both of these attributes are required.</span></span> <span data-ttu-id="a8ef3-122">`cacheDuration`saniye cinsinden bir yanıt önbelleğe alınması gereken süre miktarını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-122">`cacheDuration` sets the amount of time a response should be cached in seconds.</span></span> <span data-ttu-id="a8ef3-123">`varyByParam`Önbellek yanıtlar için kullanılan sorgu dizesi parametresi belirtmenize olanak tanır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-123">`varyByParam` allows you to specify a query string parameter that is used to cache responses.</span></span> <span data-ttu-id="a8ef3-124">Farklı sorgu dizesi parametre değerleri ile yapılan tüm istekleri ayrı ayrı önbelleğe alınır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-124">All requests made with different query string parameter values are cached separately.</span></span> <span data-ttu-id="a8ef3-125">Http://MyServer/MyHttpService/MyOperation?param=10 için ilk istek yapıldığında (önbellek süresi değil geçti sürece) Örneğin, aynı URI ile yapılan tüm sonraki istekleri önbelleğe alınan yanıtın döndürülür.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-125">For example, once an initial request is made to http://MyServer/MyHttpService/MyOperation?param=10 all subsequent requests made with the same URI would be returned the cached response (so long as the cache duration has not elapsed).</span></span> <span data-ttu-id="a8ef3-126">Yanıtlar aynıdır, ancak parametre sorgu dizesi parametresi için farklı bir değere sahip benzer bir istek için ayrı olarak önbelleğe alınır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-126">Responses for a similar request that is the same but has a different value for the parameter query string parameter are cached separately.</span></span> <span data-ttu-id="a8ef3-127">Bu ayrı önbelleğe alma davranışını istemiyorsanız ayarlamak `varyByParam` "none".</span><span class="sxs-lookup"><span data-stu-id="a8ef3-127">If you do not want this separate caching behavior, set `varyByParam` to "none".</span></span>  
  
## <a name="sql-cache-dependency"></a><span data-ttu-id="a8ef3-128">SQL önbellek bağımlılığı</span><span class="sxs-lookup"><span data-stu-id="a8ef3-128">SQL Cache Dependency</span></span>  
 <span data-ttu-id="a8ef3-129">Web HTTP hizmeti yanıtlar ile SQL önbellek bağımlılığı önbelleğe alınabilir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-129">Web HTTP service responses can also be cached with a SQL cache dependency.</span></span> <span data-ttu-id="a8ef3-130">Bir SQL veritabanında depolanan veriler, WCF Web HTTP hizmeti bağlıdır, hizmetin yanıt önbelleğe alma ve verileri SQL veritabanı tablosu değişiklikleri zaman önbelleğe alınan yanıtın geçersiz kılmak isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-130">If your WCF Web HTTP service depends on data stored in a SQL database, you may want to cache the service's response and invalidate the cached response when data in the SQL database table changes.</span></span> <span data-ttu-id="a8ef3-131">Bu davranış, Web.config dosyasında tamamen yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-131">This behavior is configured completely within the Web.config file.</span></span> <span data-ttu-id="a8ef3-132">Bir bağlantı dizesi ilk tanımlamanız gerekir <`connectionStrings`> öğesi.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-132">You must first define a connection string in the <`connectionStrings`> element.</span></span>  
  
```xml
<connectionStrings>
  <add name="connectString"
       connectionString="Data Source=MyService;Initial Catalog=MyTestDatabase;Integrated Security=True"
       providerName="System.Data.SqlClient" />
</connectionStrings>
```  
  
 <span data-ttu-id="a8ef3-133">SQL önbellek bağımlılığı içinde etkinleştirmelisiniz sonra bir <`caching`> öğesi içinde <`system.web`> aşağıdaki yapılandırma örnekte gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-133">Then you must enable SQL cache dependency within a <`caching`> element within the <`system.web`> element as shown in the following config example.</span></span>  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>
    </sqlCacheDependency>
    <!-- ... -->
  </caching>
  <!-- ... -->
</system.web>
```  
  
 <span data-ttu-id="a8ef3-134">SQL önbellek bağımlılığı burada etkinleştirildikten ve yoklama zaman 1000 milisaniye olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-134">Here SQL cache dependency is enabled and a polling time of 1000 milliseconds is set.</span></span> <span data-ttu-id="a8ef3-135">Veritabanı tablosunun yoklama süresi sona erdiğinde her zaman güncelleştirmeleri denetlenir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-135">Each time the polling time elapses the database table is checked for updates.</span></span> <span data-ttu-id="a8ef3-136">Değişiklikleri önbelleğinin içeriğini kaldırılır ve yeni bir yanıt hizmet işlemi başlatıldığında çağrılan algılanırsa, önbelleğe alınır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-136">If changes are detected the contents of the cache are removed and the next time the service operation is invoked a new response is cached.</span></span> <span data-ttu-id="a8ef3-137">İçinde <`sqlCacheDependency`> öğesi veritabanlarını ekleyin ve bağlantı dizeleri içinde reference <`databases`> Aşağıdaki örnekte gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-137">Within the <`sqlCacheDependency`> element add the databases and reference the connection strings within the <`databases`> element as shown in the following example.</span></span>  
  
```xml  
<system.web>
  <caching>
    <sqlCacheDependency enabled="true" pollTime="1000">
      <databases>
        <add name="MyTestDatabase" connectionStringName="connectString" />
      </databases>  
    </sqlCacheDependency>  
    <!-- ... -->  
  </caching>  
  <!-- ... -->  
</system.web>  
```  
  
 <span data-ttu-id="a8ef3-138">Sonraki içinde çıktı önbellek ayarlarını yapılandırmanız gerekir <`caching`> Aşağıdaki örnekte gösterildiği gibi öğesi.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-138">Next you must configure the output cache settings within the <`caching`> element as shown in the following example.</span></span>  
  
```xml
<system.web>
  <caching>  
    <!-- ...  -->
    <outputCacheSettings>
      <outputCacheProfiles>
        <add name="CacheFor60Seconds" duration="60" varyByParam="none" sqlDependency="MyTestDatabase:MyTable" />
      </outputCacheProfiles>
    </outputCacheSettings>
  </caching>
  <!-- ... -->
</system.web>
```  
  
 <span data-ttu-id="a8ef3-139">Önbellek süresi 60 saniye için burada ayarlanan `varyByParam` none olarak ayarlanmış ve `sqlDependency` noktalı virgülle ayrılmış listesini virgüllerle ayrılmış veritabanı adı/tablo çiftleri için ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-139">Here the cache duration is set to 60 seconds, `varyByParam` is set to none and `sqlDependency` is set to a semicolon delimited list of database name/table pairs separated by colons.</span></span> <span data-ttu-id="a8ef3-140">Zaman içinde veri `MyTable` önbelleğe alınan yanıtın hizmet işlemi kaldırılır ve işlem çağrıldığında yeni bir yanıt (hizmet işlemi çağırarak) oluşturulur, önbelleğe alınan ve istemciye döndürülen değiştirilir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-140">When data in `MyTable` is changed the cached response for the service operation is removed and when the operation is invoked a new response is generated (by calling the service operation), cached, and returned to the client.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a8ef3-141">Bir SQL veritabanına erişmek ASP.NET ile ilgili kullanmalısınız [ASP.NET SQL Server kayıt aracı](http://go.microsoft.com/fwlink/?LinkId=152536).</span><span class="sxs-lookup"><span data-stu-id="a8ef3-141">For ASP.NET to access a SQL database, you must use the [ASP.NET SQL Server Registration Tool](http://go.microsoft.com/fwlink/?LinkId=152536).</span></span> <span data-ttu-id="a8ef3-142">Ayrıca veritabanı ve tablo uygun kullanıcı hesabı erişimi izni vermelidir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-142">In addition you must allow the appropriate user account access to the database and table.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="a8ef3-143">[SQL Server'a bir Web uygulamasından erişmek](http://go.microsoft.com/fwlink/?LinkId=178988).</span><span class="sxs-lookup"><span data-stu-id="a8ef3-143"> [Accessing SQL Server from a Web Application](http://go.microsoft.com/fwlink/?LinkId=178988).</span></span>  
  
## <a name="conditional-http-get-based-caching"></a><span data-ttu-id="a8ef3-144">Koşullu HTTP tabanlı önbelleğe alma</span><span class="sxs-lookup"><span data-stu-id="a8ef3-144">Conditional HTTP GET Based Caching</span></span>  
 <span data-ttu-id="a8ef3-145">Web HTTP senaryolarda koşullu bir HTTP GET genellikle Hizmetleri tarafından akıllı HTTP önbelleğe alma açıklandığı gibi uygulamak için kullanılan [HTTP belirtimi](http://go.microsoft.com/fwlink/?LinkId=165800).</span><span class="sxs-lookup"><span data-stu-id="a8ef3-145">In Web HTTP scenarios a conditional HTTP GET is often used by services to implement intelligent HTTP caching as described in the [HTTP Specification](http://go.microsoft.com/fwlink/?LinkId=165800).</span></span> <span data-ttu-id="a8ef3-146">Bu hizmet yapmak için ETag üstbilgi değerini HTTP yanıt olarak ayarlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-146">To do this the service must set the value of the ETag header in the HTTP response.</span></span> <span data-ttu-id="a8ef3-147">If-None-Match üst bilgisinde belirtilen ETag hiçbirini eşleşip eşleşmediğini geçerli ETag görmek için HTTP isteği da işaretlemeleri gerekir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-147">It also must check the If-None-Match header in the HTTP request to see whether any of the ETag specified matches the current ETag.</span></span>  
  
 <span data-ttu-id="a8ef3-148">GET ve HEAD isteklerini <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> bir ETag değeri alır ve istek If-None-Match üstbilgisi karşı denetler.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-148">For GET and HEAD requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> takes an ETag value and checks it against the If-None-Match header of the request.</span></span> <span data-ttu-id="a8ef3-149">Üstbilgi bulunduğundan ve bir eşleşme varsa bir <xref:System.ServiceModel.Web.WebFaultException> ile bir HTTP durum kodu 304 (değişiklik) oluşturulur ve bir ETag üstbilgisi eşleşen ETag Yanıtla eklenir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-149">If the header is present and there is a match, a <xref:System.ServiceModel.Web.WebFaultException> with a HTTP status code 304 (Not Modified) is thrown and an ETag header is added to the response with the matching ETag.</span></span>  
  
 <span data-ttu-id="a8ef3-150">Bir aşırı yüklemesini <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> yöntemi son değiştirilme tarihini alır ve If-Modified-Since üstbilgisi isteği karşı denetler.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-150">One overload of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method takes a last modified date and checks it against the If-Modified-Since header of the request.</span></span> <span data-ttu-id="a8ef3-151">Üstbilgi varsa ve bu yana, kaynak değiştirilmemiş bir <xref:System.ServiceModel.Web.WebFaultException> ile bir HTTP durum kodu 304 (değişiklik) oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-151">If the header is present and the resource has not been modified since, a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 304 (Not Modified) is thrown.</span></span>  
  
 <span data-ttu-id="a8ef3-152">PUT, POST ve DELETE isteklerini <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> bir kaynağın geçerli ETag değeri alır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-152">For PUT, POST, and DELETE requests, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> takes the current ETag value of a resource.</span></span> <span data-ttu-id="a8ef3-153">Geçerli ETag değeri null ise, yöntem If-None-Match üst bilgisi değeri olup olmadığını denetler "*".</span><span class="sxs-lookup"><span data-stu-id="a8ef3-153">If the current ETag value is null, the method checks that the If-None- Match header has a value of "*".</span></span>  <span data-ttu-id="a8ef3-154">Geçerli ETag değeri varsayılan bir değer değil yöntemi geçerli ETag değeri istek IF - Match üstbilgisi karşı denetler.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-154">If the current ETag value is not a default value, then the method checks the current ETag value against the If- Match header of the request.</span></span> <span data-ttu-id="a8ef3-155">Her iki durumda da yöntemi atar bir <xref:System.ServiceModel.Web.WebFaultException> beklenen üstbilgisi istekte mevcut değilse veya değerini koşullu onay karşılamadığı ve yanıtın geçerli ETag için ETag üstbilgisini ayarlar 412 (önkoşul başarısız oldu) ile bir HTTP durum kodu değer.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-155">In either case, the method throws a <xref:System.ServiceModel.Web.WebFaultException> with an HTTP status code 412 (Precondition Failed) if the expected header is not present in the request or its value does not satisfy the conditional check and sets the ETag header of the response to the current ETag value.</span></span>  
  
 <span data-ttu-id="a8ef3-156">Her iki `CheckConditional` yöntemleri ve <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> yöntemi yanıt üstbilgisi ayarlamak ETag değeri geçerli bir ETag göre HTTP belirtiminin olmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-156">Both the `CheckConditional` methods and the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.SetETag%2A> method ensures that the ETag value set on the response header is a valid ETag according to the HTTP specification.</span></span> <span data-ttu-id="a8ef3-157">Bu, zaten yoksa, çift tırnak işareti ETag değeri çevreleyen ve düzgün şekilde herhangi bir iç çift tırnak karakteri kaçış içerir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-157">This includes surrounding the ETag value in double quotes if they are not already present and properly escaping any internal double quote characters.</span></span> <span data-ttu-id="a8ef3-158">Zayıf bir ETag karşılaştırma desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-158">Weak ETag comparison is not supported.</span></span>  
  
 <span data-ttu-id="a8ef3-159">Aşağıdaki örnek, bu yöntemleri kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-159">The following example shows how to use these methods.</span></span>  
  
```csharp
[WebGet(UriTemplate = "{id}"), Description("Returns the specified customer from customers collection. Returns NotFound if there is no such customer. Supports conditional GET.")]
public Customer GetCustomer(string id)
{
    lock (writeLock)
    {
        // return NotFound if there is no item with the specified id.
        object itemEtag = customerEtags[id];
        if (itemEtag == null)
        {
            throw new WebFaultException(HttpStatusCode.NotFound);
        }
  
        // return NotModified if the client did a conditional GET and the customer item has not changed
        // since when the client last retrieved it
        WebOperationContext.Current.IncomingRequest.CheckConditionalRetrieve((long)itemEtag);
        Customer result = this.customers[id] as Customer;
        
        // set the customer etag before returning the result
        WebOperationContext.Current.OutgoingResponse.SetETag((long)itemEtag);
        return result;
    }
}
```  
  
## <a name="security-considerations"></a><span data-ttu-id="a8ef3-160">Güvenlik Değerlendirmeleri</span><span class="sxs-lookup"><span data-stu-id="a8ef3-160">Security Considerations</span></span>  
 <span data-ttu-id="a8ef3-161">Yanıtı önbelleğinden sunulduğunda yetkilendirme yapılmaz çünkü yetkilendirme gerektiren isteklerinin yanıtlarını önbelleğe alınmış, olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-161">Requests that require authorization should not have their responses cached, because the authorization is not performed when the response is served from the cache.</span></span>  <span data-ttu-id="a8ef3-162">Bu tür yanıtlarını önbelleğe alma ciddi güvenlik açığı tanıtır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-162">Caching such responses would introduce a serious security vulnerability.</span></span>  <span data-ttu-id="a8ef3-163">Genellikle, kullanıcıya özgü verileri yetkilendirme gerektiren isteklerinin sağlayın ve bu nedenle sunucu tarafı önbelleğe alma bile yararlı değildir.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-163">Usually, requests that require authorization provide user-specific data and therefore server-side caching is not even beneficial.</span></span>  <span data-ttu-id="a8ef3-164">Böyle durumlarda, istemci tarafı önbelleğe alma veya yalnızca hiç önbelleğe alma değil daha uygun olacaktır.</span><span class="sxs-lookup"><span data-stu-id="a8ef3-164">In such situations, client-side caching or simply not caching at all will be more appropriate.</span></span>