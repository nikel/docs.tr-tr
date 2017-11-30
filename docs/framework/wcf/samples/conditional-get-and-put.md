---
title: "Şartlı Alma ve Yerleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d22067f-57b8-4e0f-a571-a694512187ae
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e4ab4d0a97cbbaa2e5aaee25e0154e1cc94a82f8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="conditional-get-and-put"></a><span data-ttu-id="672d5-102">Şartlı Alma ve Yerleştirme</span><span class="sxs-lookup"><span data-stu-id="672d5-102">Conditional Get and Put</span></span>
<span data-ttu-id="672d5-103">Bu örnek yeni koşullu almak ve API'ler için WCF REST programlama modeli güncelleştirmek nasıl kullanılacağı gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="672d5-103">This sample demonstrates how to use the new conditional retrieve and update APIs for the WCF REST programming model.</span></span> <span data-ttu-id="672d5-104">Koşullu alın ve güncelleştirme için en uygun olduğundan kaynak odaklı ve REST Hizmetleri, bu örnek genişletir [temel kaynak hizmeti](../../../../docs/framework/wcf/samples/basic-resource-service.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="672d5-104">Because conditional retrieve and update are most appropriate for resource-oriented and REST services, this sample extends the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample.</span></span> <span data-ttu-id="672d5-105">Koşullu almak ve güncelleştirme desteği eklemek için bu örnek odaklanır [temel kaynak hizmeti](../../../../docs/framework/wcf/samples/basic-resource-service.md) sunulan yeni API'leri kullanarak örnek [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="672d5-105">This sample focuses on adding support for conditional retrieve and update to the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample using the new APIs introduced in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="672d5-106">Gösteriler</span><span class="sxs-lookup"><span data-stu-id="672d5-106">Demonstrates</span></span>  
 <span data-ttu-id="672d5-107">Koşullu alın ve güncelleştirme</span><span class="sxs-lookup"><span data-stu-id="672d5-107">Conditional Retrieve and Update</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="672d5-108">Tartışma</span><span class="sxs-lookup"><span data-stu-id="672d5-108">Discussion</span></span>  
 <span data-ttu-id="672d5-109">WCF hizmeti bu örnek, bir kaynak odaklı müşteriler koleksiyonunu ve REST şekilde gösterir.</span><span class="sxs-lookup"><span data-stu-id="672d5-109">The WCF service in this sample exposes a collection of customers in a resource-oriented and REST manner.</span></span> <span data-ttu-id="672d5-110">Hizmet uygulaması ayrıntılı bir açıklaması için lütfen bkz [temel kaynak hizmeti](../../../../docs/framework/wcf/samples/basic-resource-service.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="672d5-110">For a detailed description of the service implementation, please see the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample.</span></span>  
  
 <span data-ttu-id="672d5-111">Bu örnek koşullu alın ve güncelleştirme olanağı ekler [temel kaynak hizmeti](../../../../docs/framework/wcf/samples/basic-resource-service.md) örnek.</span><span class="sxs-lookup"><span data-stu-id="672d5-111">This sample adds conditional retrieve and update capabilities to the [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) sample.</span></span> <span data-ttu-id="672d5-112">Koşullu almak ve kullanım HTTP varlık etiketleri ve istemcilerin sahip veya belirli bir kaynak için en güncel varlık yok doğrulamak için HTTP If-None-Match ve IF-Match üst bilgileri güncelleştirin.</span><span class="sxs-lookup"><span data-stu-id="672d5-112">Conditional retrieve and update use HTTP entity tags and the HTTP If-None-Match and If-Match headers to validate that clients either have or do not have the most current entity for a given resource.</span></span> <span data-ttu-id="672d5-113">Ancak, doğru HTTP If-None-Match ve IF-Match üst bilgileri ayrıştırmak için kod uygulama yorucu ve hataya yatkın olabilir.</span><span class="sxs-lookup"><span data-stu-id="672d5-113">However, implementing the code to correctly parse the HTTP If-None-Match and If-Match headers can be tedious and error-prone.</span></span> <span data-ttu-id="672d5-114">Bu nedenle, <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> ve <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> yöntemler eklenmiştir <xref:System.ServiceModel.Web.IncomingWebRequestContext>, hangi erişilebilir geçerli örneği kullanarak <xref:System.ServiceModel.Web.WebOperationContext>.</span><span class="sxs-lookup"><span data-stu-id="672d5-114">Therefore, the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> and <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> methods have been added to the <xref:System.ServiceModel.Web.IncomingWebRequestContext>, which can be accessed using the current instance of the <xref:System.ServiceModel.Web.WebOperationContext>.</span></span> <span data-ttu-id="672d5-115">Ayrıca, `SetETag` yöntemi eklenmiştir <xref:System.ServiceModel.Web.OutgoingWebRequestContext>, geçerli bir varlık etiketleri döndürülecek kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="672d5-115">In addition, the `SetETag` method has been added to the <xref:System.ServiceModel.Web.OutgoingWebRequestContext>, making it easier to return valid entity tags.</span></span>  
  
 <span data-ttu-id="672d5-116"><xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> Yöntemi [WebGet] işlemleri ile kullanılmak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="672d5-116">The <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method is intended to be used with [WebGet] operations.</span></span> <span data-ttu-id="672d5-117">Belirtilen kaynak olarak geçerli varlık etiketi alır `entityTag` olabilir parametresi bir `string`, `int`, `long` veya `Guid`.</span><span class="sxs-lookup"><span data-stu-id="672d5-117">It takes the current entity tag for the given resource as the `entityTag` parameter, which can be a `string`, `int`, `long` or `Guid`.</span></span> <span data-ttu-id="672d5-118"><xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> Yöntemi varlık etiketi isteğin HTTP If-None-Match üstbilgisi karşı denetler.</span><span class="sxs-lookup"><span data-stu-id="672d5-118">The <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method checks the entity tag against the HTTP If-None-Match header of the request.</span></span> <span data-ttu-id="672d5-119">Varlık etiketi HTTP If-None-Match üst bilgisi varsa, sonra bir <xref:System.ServiceModel.Web.WebFaultException> (304) değişiklik kodunu bir durum ile oluşturulur; Aksi takdirde yöntemi döndürür.</span><span class="sxs-lookup"><span data-stu-id="672d5-119">If the entity tag is present in the HTTP If-None-Match header, then a <xref:System.ServiceModel.Web.WebFaultException> with a status code of Not Modified (304) is thrown; otherwise the method returns.</span></span> <span data-ttu-id="672d5-120">Koşullu alma mekanizması sunucusuna bu varlık olduğunu bildirir ve bunu istemci zaten yoksa, yalnızca geçerli varlık göndermek için istemcinin verir.</span><span class="sxs-lookup"><span data-stu-id="672d5-120">The conditional retrieve mechanism allows the client to tell the server that it has this entity and to only send the current entity if the client does not already have it.</span></span> <span data-ttu-id="672d5-121">Kullanım örneği <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> yöntemi içinde görülme `GetCustomer` ve `GetCustomers` hizmetinin operations.</span><span class="sxs-lookup"><span data-stu-id="672d5-121">Example usage of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method can be seen in the `GetCustomer` and `GetCustomers` operations of the service.</span></span> <span data-ttu-id="672d5-122">Bu çağrılar dikkate almak önemlidir <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> değil döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="672d5-122">It is important to note that calls to <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> may not return.</span></span> <span data-ttu-id="672d5-123">Böylece istek çağırmadan önce başarılı olması için zaten biliniyor, geliştiricilerin işlemi uygulamanız gerekir <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> yürütülen ise böyle olması durumunda çağrısı <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> edildi yok, hizmet başarılı durum koduyla bir yanıt gönderir.</span><span class="sxs-lookup"><span data-stu-id="672d5-123">Developers should implement the operation so that the request is already known to be successful before the call to <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> is executed, such that if the call to <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> was not present, the service would send a response with a successful status code.</span></span>  
  
 <span data-ttu-id="672d5-124"><xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> Yöntemi benzer <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="672d5-124">The <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> method is similar to the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A> method.</span></span> <span data-ttu-id="672d5-125">Ayrıca, söz konusu kaynağın geçerli varlık etiketi alır.</span><span class="sxs-lookup"><span data-stu-id="672d5-125">It also takes the current entity tag for the given resource.</span></span> <span data-ttu-id="672d5-126">Ancak, yöntem "PUT" veya "DELETE" olarak ayarlanırsa [Webınvoke] işlemleri ile kullanılmak üzere tasarlanmıştır.</span><span class="sxs-lookup"><span data-stu-id="672d5-126">However, it is intended to be used with [WebInvoke] operations in which the method is set to "PUT" or "DELETE".</span></span> <span data-ttu-id="672d5-127"><xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> Yöntemi varlık etiketi isteğin HTTP IF-Match üstbilgisi karşı denetler.</span><span class="sxs-lookup"><span data-stu-id="672d5-127">The <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> method checks the entity tag against the HTTP If-Match header of the request.</span></span> <span data-ttu-id="672d5-128">Varlık etiketi HTTP IF-Match üst bilgisinde mevcut değilse sonra bir <xref:System.ServiceModel.Web.WebFaultException> bir durum ile önkoşul başarısız oldu (412) kodunu atılır.</span><span class="sxs-lookup"><span data-stu-id="672d5-128">If the entity tag is not present in the HTTP If-Match header, then a <xref:System.ServiceModel.Web.WebFaultException> with a status code of Precondition Failed (412) is thrown.</span></span> <span data-ttu-id="672d5-129">Koşullu güncelleştirme mekanizması sunucusuna bu varlık için kaynak olduğunu bildirir ve yalnızca kaynak değiştirmek istemcinin sağlamak için istemcinin verir; varlık varsa geçerli olur.</span><span class="sxs-lookup"><span data-stu-id="672d5-129">The conditional update mechanism allows the client to tell the server that it has this entity for the resource and to only allow the client to alter the resource; if the entity it has is current.</span></span> <span data-ttu-id="672d5-130">Kullanım örneği <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> yöntemi içinde görülme `UpdateCustomer` ve `DeleteCustomer` hizmetinin operations.</span><span class="sxs-lookup"><span data-stu-id="672d5-130">Example usage of the <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> method can be seen in the `UpdateCustomer` and `DeleteCustomer` operations of the service.</span></span> <span data-ttu-id="672d5-131">İle olarak yalnızca <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, bu çağrılar dikkate almak önemlidir <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> değil döndürebilir.</span><span class="sxs-lookup"><span data-stu-id="672d5-131">Just as with <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalRetrieve%2A>, it is important to note that calls to <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> may not return.</span></span> <span data-ttu-id="672d5-132">Geliştiriciler sağlayacak şekilde istek çağırmadan önce başarılı olması için zaten biliniyor işlemi uygulamanız gerekir <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> yürütülen ise böyle olması durumunda çağrısı <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> hizmet başarılı durum koduyla yanıt, yoktu.</span><span class="sxs-lookup"><span data-stu-id="672d5-132">Developers should implement the operation such that the request is already known to be successful before the call to <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> is executed, such that if the call to <xref:System.ServiceModel.Web.IncomingWebRequestContext.CheckConditionalUpdate%2A> was not present, the service would respond with a successful status code.</span></span>  
  
 <span data-ttu-id="672d5-133">Kendini barındıran hizmet ve bir konsol uygulaması içinde çalıştırılan bir istemciyi, örnek oluşur.</span><span class="sxs-lookup"><span data-stu-id="672d5-133">The sample consists of a self-hosted service and a client that runs within a console application.</span></span> <span data-ttu-id="672d5-134">Konsol uygulaması çalışırken, istemci hizmete istek yaptığında ve konsol penceresine yanıtlardan bilgileri yazar.</span><span class="sxs-lookup"><span data-stu-id="672d5-134">As the console application runs, the client makes requests to the service and writes the pertinent information from the responses to the console window.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="672d5-135">Örnek çalıştırmak için</span><span class="sxs-lookup"><span data-stu-id="672d5-135">To run the sample</span></span>  
  
1.  <span data-ttu-id="672d5-136">Koşullu Get ve Put örnek çözümü açın.</span><span class="sxs-lookup"><span data-stu-id="672d5-136">Open the solution for the Conditional Get and Put sample.</span></span> <span data-ttu-id="672d5-137">Başlatılırken [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], örnek başarılı bir şekilde çalıştırmak için yönetici olarak çalıştırmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="672d5-137">When launching [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], you must run as an administrator to execute the sample successfully.</span></span> <span data-ttu-id="672d5-138">Sağ tıklayarak bunu [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] simgesi ve seçme **yönetici olarak çalıştır** ve bağlam menüsünden.</span><span class="sxs-lookup"><span data-stu-id="672d5-138">Do this by right-clicking the [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] icon and choosing **Run as Administrator** from the context menu.</span></span>  
  
2.  <span data-ttu-id="672d5-139">Çözümü derlemek ve konsol uygulama projesi çalıştırmak için CTRL + F5 tuşuna basın CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="672d5-139">Press CTRL+SHIFT+B to build the solution and then press CTRL+F5 to run the console application project.</span></span> <span data-ttu-id="672d5-140">Bu proje (CTRL + F5 yerine F5 tuşuna basarak) etkin hata ayıklama ile çalışıyorsa göre koşullu bir özel durum oluştuğunda hata ayıklayıcı durakları almak ve denetimi yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="672d5-140">If running this project with debugging enabled (by pressing F5 instead of CTRL+F5), the debugger stops when an exception is thrown by the conditional GET and PUT checking.</span></span> <span data-ttu-id="672d5-141">Bu gerçekleştiğinde, örnek yürütme devam etmek için F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="672d5-141">When this happens, press F5 to continue executing the sample.</span></span>  
  
3.  <span data-ttu-id="672d5-142">Konsol penceresinde görünür kum çalışan hizmeti için çalışan hizmetin URI ve HTML Yardım sayfası URI'sini sağlar.</span><span class="sxs-lookup"><span data-stu-id="672d5-142">The console window appear sand provides the URI of the running service and the URI of the HTML help page for the running service.</span></span>  
  
4.  <span data-ttu-id="672d5-143">Örnek çalışırken, istemci istekleri hizmetine gönderir ve yanıtları konsol penceresine yazar.</span><span class="sxs-lookup"><span data-stu-id="672d5-143">As the sample runs, the client sends requests to the service and writes the responses to the console window.</span></span>  
  
5.  <span data-ttu-id="672d5-144">Örnek sonlandırmak için herhangi bir tuşa basın.</span><span class="sxs-lookup"><span data-stu-id="672d5-144">Press any key to terminate the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="672d5-145">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="672d5-145">The samples may already be installed on your machine.</span></span> <span data-ttu-id="672d5-146">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="672d5-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="672d5-147">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="672d5-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="672d5-148">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="672d5-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\ConditionalGetAndPut`