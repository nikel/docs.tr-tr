---
title: "İleti Kimlik Bilgileri ile WS Aktarma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d092f3a-b309-439b-920b-66d8f46a0e3c
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 517bf7684f6219248ade1f2c8e88879e94b2f1c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ws-transport-with-message-credential"></a><span data-ttu-id="9dc90-102">İleti Kimlik Bilgileri ile WS Aktarma</span><span class="sxs-lookup"><span data-stu-id="9dc90-102">WS Transport With Message Credential</span></span>
<span data-ttu-id="9dc90-103">Bu örnek, iletide taşınmasına istemci kimlik bilgileri ile birlikte SSL taşıma güvenliği kullanımını göstermektedir.</span><span class="sxs-lookup"><span data-stu-id="9dc90-103">This sample demonstrates the use of SSL transport security in combination with client credential being carried in the message.</span></span> <span data-ttu-id="9dc90-104">Bu örnekte `wsHttpBinding` bağlama.</span><span class="sxs-lookup"><span data-stu-id="9dc90-104">This sample uses the `wsHttpBinding` binding.</span></span>  
  
 <span data-ttu-id="9dc90-105">Varsayılan olarak, `wsHttpBinding` bağlama HTTP iletişim sağlar.</span><span class="sxs-lookup"><span data-stu-id="9dc90-105">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="9dc90-106">Taşıma güvenliği için yapılandırıldığında, bağlama HTTPS iletişimi destekler.</span><span class="sxs-lookup"><span data-stu-id="9dc90-106">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="9dc90-107">HTTPS gizliliği ve bütünlük koruması kablo üzerinden gönderilen iletiler için sağlar.</span><span class="sxs-lookup"><span data-stu-id="9dc90-107">HTTPS provides confidentiality and integrity protection for the messages that are transmitted over the wire.</span></span> <span data-ttu-id="9dc90-108">Ancak istemci hizmeti için kimlik doğrulaması için kullanılan kimlik doğrulama mekanizmaları HTTPS taşıma desteklediği için sınırlı kümesidir.</span><span class="sxs-lookup"><span data-stu-id="9dc90-108">However the set of authentication mechanisms that can be used to authenticate the client to the service is limited to what the HTTPS transport supports.</span></span> [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="9dc90-109">sunan bir `TransportWithMessageCredential` bu sınırlamanın üstesinden gelmek için tasarlanmış güvenlik modu.</span><span class="sxs-lookup"><span data-stu-id="9dc90-109"> offers a `TransportWithMessageCredential` security mode that is designed to overcome this limitation.</span></span> <span data-ttu-id="9dc90-110">Bu güvenlik modu yapılandırıldığında, taşıma güvenliği için iletilen iletileri gizliliği ve bütünlük sağlamak ve hizmet kimlik doğrulaması yapmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9dc90-110">When this security mode is configured, the transport security is used to provide confidentiality and integrity for the transmitted messages and to perform the service authentication.</span></span> <span data-ttu-id="9dc90-111">Ancak, istemci kimlik doğrulama ileti doğrudan istemci kimlik bilgileri koyarak gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="9dc90-111">However, the client authentication is performed by putting the client credential directly in the message.</span></span> <span data-ttu-id="9dc90-112">Bu ileti güvenlik modu aktarım güvenlik modu performans avantajı korurken istemci kimlik doğrulaması için tarafından desteklenen herhangi bir kimlik bilgisi türü kullanmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="9dc90-112">This allows you to use any credential type that is supported by the message security mode for the client authentication while keeping the performance benefit of transport security mode.</span></span>  
  
 <span data-ttu-id="9dc90-113">Bu örnekte, bir `UserName` kimlik bilgisi türü hizmeti için istemci kimlik doğrulaması için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="9dc90-113">In this sample, a `UserName` credential type is used to authenticate the client to the service.</span></span>  
  
 <span data-ttu-id="9dc90-114">Bu örnek dayanır [Başlarken](../../../../docs/framework/wcf/samples/getting-started-sample.md) hesap makinesi hizmetinin uygular.</span><span class="sxs-lookup"><span data-stu-id="9dc90-114">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="9dc90-115">`wsHttpBinding` Bağlama belirtilen ve uygulama yapılandırma dosyaları istemci ve hizmet için yapılandırılır.</span><span class="sxs-lookup"><span data-stu-id="9dc90-115">The `wsHttpBinding` binding is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9dc90-116">Kurulum yordamı ve yapı yönergeleri Bu örnek için bu konunun sonunda yer alır.</span><span class="sxs-lookup"><span data-stu-id="9dc90-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="9dc90-117">Örnek program kodunda olarak neredeyse aynıdır [Başlarken](../../../../docs/framework/wcf/samples/getting-started-sample.md) hizmet.</span><span class="sxs-lookup"><span data-stu-id="9dc90-117">The program code in the sample is almost identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="9dc90-118">Bir başka işlem tarafından hizmet sözleşmesini - sağlanan `GetCallerIdentity`.</span><span class="sxs-lookup"><span data-stu-id="9dc90-118">There is one additional operation provided by the service contract - `GetCallerIdentity`.</span></span> <span data-ttu-id="9dc90-119">Bu işlem çağırana çağıranının kimliğini adını döndürür.</span><span class="sxs-lookup"><span data-stu-id="9dc90-119">This operation returns the name of the caller's identity to the caller.</span></span>  
  
```  
public string GetCallerIdentity()  
{  
    // Use ServiceSecurityContext.WindowsIdentity to get the name of the caller.  
    return ServiceSecurityContext.Current.WindowsIdentity.Name;  
}  
```  
  
 <span data-ttu-id="9dc90-120">Bir sertifika oluşturun ve oluşturmaya ve örnek çalıştırmaya önce Web Sunucusu Sertifika Sihirbazı'nı kullanarak atamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="9dc90-120">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="9dc90-121">Uç nokta tanımı ve bağlama tanımı dosyası ayarlarını etkinleştir `TransportWithMessageCredential` istemci için aşağıdaki örnek yapılandırma gösterildiği gibi güvenlik modu.</span><span class="sxs-lookup"><span data-stu-id="9dc90-121">The endpoint definition and binding definition in the configuration file settings enable `TransportWithMessageCredential` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  <client>  
    <endpoint name=""  
              address="https://localhost/servicemodelsamples/service.svc"   
              binding="wsHttpBinding"   
              bindingConfiguration="Binding1"   
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  </client>  
  
  <bindings>  
    <wsHttpBinding>  
      <!--   
        This configuration defines the security mode as TransportWithMessageCredential.  
        and the clientCredentialType as UserName.  
        -->  
      <binding name="Binding1">  
        <security mode ="TransportWithMessageCredential">  
          <message clientCredentialType="UserName" />  
        </security>  
      </binding>  
    </wsHttpBinding>  
  </bindings>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="9dc90-122">Belirtilen adres https:// düzenini kullanır.</span><span class="sxs-lookup"><span data-stu-id="9dc90-122">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="9dc90-123">Güvenlik modu bağlama yapılandırması ayarlar `TransportWithMessageCredential`.</span><span class="sxs-lookup"><span data-stu-id="9dc90-123">The binding configuration sets the security mode to `TransportWithMessageCredential`.</span></span> <span data-ttu-id="9dc90-124">Aynı güvenlik modu hizmetin Web.config dosyasında belirtilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="9dc90-124">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="9dc90-125">Bu örnekte kullanılan sertifikanın Makecert.exe ile oluşturulan bir test sertifikası olduğundan, bir https erişmeye çalıştığınızda bir güvenlik uyarısı görünür: tarayıcınızdan https://localhost/servicemodelsamples/service.svc gibi adresi.</span><span class="sxs-lookup"><span data-stu-id="9dc90-125">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="9dc90-126">İzin vermek için [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] istemci, yerinde bir test sertifikası ile çalışmak için bazı ek kod güvenlik uyarıyı gizlemek için istemciye eklendi.</span><span class="sxs-lookup"><span data-stu-id="9dc90-126">To allow the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="9dc90-127">Bu kod, eşlik eden sınıfı değil ve gerekli üretim sertifikalar kullanıldığında.</span><span class="sxs-lookup"><span data-stu-id="9dc90-127">This code, and the accompanying class, is not required when using production certificates.</span></span>  
  
```  
// WARNING: This code is only needed for test certificates such as those created by makecert. It is   
// not recommended for production code.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
 <span data-ttu-id="9dc90-128">Örneği çalıştırdığınızda, işlem isteklerini ve yanıtlarını istemci konsol penceresinde görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="9dc90-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="9dc90-129">İstemcisi penceresinde istemciyi aşağı kapatmak için ENTER tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="9dc90-129">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Username authentication required.  
Provide a valid machine or domain account. [domain\\user]  
   Enter username:   
YourDomainName\YourAccountName  
   Enter password:   
********  
YourDomainName\YourAccountName  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9dc90-130">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="9dc90-130">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="9dc90-131">Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9dc90-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="9dc90-132">Gerçekleştirmiş emin olun [Internet Information Services (IIS) sunucu sertifikası yükleme yönergeleri](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="9dc90-132">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
3.  <span data-ttu-id="9dc90-133">Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9dc90-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="9dc90-134">Tek veya çapraz makine yapılandırmada örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="9dc90-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc90-135">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9dc90-135">See Also</span></span>