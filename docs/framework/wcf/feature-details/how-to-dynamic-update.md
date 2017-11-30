---
title: "Nasıl yapılır: Dinamik Güncelleme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
caps.latest.revision: "4"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 70f9bb374405496c62650ee3fb715f059e91cd7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-dynamic-update"></a><span data-ttu-id="26de9-102">Nasıl yapılır: Dinamik Güncelleme</span><span class="sxs-lookup"><span data-stu-id="26de9-102">How To: Dynamic Update</span></span>
<span data-ttu-id="26de9-103">Bu konuda oluşturmak ve dinamik yönlendirme yapılandırmasını güncelleştirmek için gereken temel adımlar verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="26de9-103">This topic outlines the basic steps required to create and dynamically update the routing configuration.</span></span> <span data-ttu-id="26de9-104">Bu örnekte, ilk yönlendirme yapılandırması yapılandırma dosyasından alınır ve tüm iletileri regularCalc hesaplayıcı hizmete yönlendirir; Ancak, daha sonra program aracılığıyla hedef uç nokta roundingCalc hizmet değiştirmek için güncelleştirilir.</span><span class="sxs-lookup"><span data-stu-id="26de9-104">In this example, the initial routing configuration is obtained from the configuration file and routes all messages to the regularCalc calculator service; however, it is subsequently updated programmatically in order to change the destination endpoint the roundingCalc service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26de9-105">Birçok uygulamalarında yapılandırma tam olarak dinamik olacaktır ve bir varsayılan yapılandırmasını kullanan değil; Ancak, hizmeti başladığında varsayılan yapılandırma durumu etmesi olduğu Bu konu, bir gibi bazı senaryolar vardır.</span><span class="sxs-lookup"><span data-stu-id="26de9-105">In many implementations, configuration will be fully dynamic and will not rely on a default configuration; however, there are some scenarios, such as the one in this topic, where it is desirable to have a default configuration state when the service starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="26de9-106">Dinamik güncelleştirmeleri yalnızca bellekte oluşur ve yapılandırma dosyaları değişiklik neden değil.</span><span class="sxs-lookup"><span data-stu-id="26de9-106">Dynamic updates occur only in memory, and do not result in the modification of configuration files.</span></span>  
  
 <span data-ttu-id="26de9-107">RegularCalc ve roundingCalc Ekle aynı işlemlerini destekleyen, çıkarma, çarpma ve bölme; Ancak, roundingCalc döndürmeden önce hesaplamalarının yakın tamsayı değere yuvarlar.</span><span class="sxs-lookup"><span data-stu-id="26de9-107">Both regularCalc and roundingCalc support the same operations of add, subtract, multiply and divide; however, roundingCalc rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="26de9-108">Bir yapılandırma dosyası, tüm iletileri regularCalc hizmete yönlendirmek için bu hizmeti yapılandırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="26de9-108">A configuration file is used to configure the service to route all messages to the regularCalc service.</span></span> <span data-ttu-id="26de9-109">Yönlendirme hizmeti başlatıldıktan sonra <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> roundingCalc hizmet iletileri yönlendirmek için hizmeti yeniden için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="26de9-109">After the Routing Service has been started, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> is used to reconfigure the service to route messages to the roundingCalc service.</span></span>  
  
### <a name="implement-initial-configuration"></a><span data-ttu-id="26de9-110">Uygulama başlangıç yapılandırması</span><span class="sxs-lookup"><span data-stu-id="26de9-110">Implement Initial Configuration</span></span>  
  
1.  <span data-ttu-id="26de9-111">Temel yönlendirme hizmeti yapılandırma hizmeti tarafından sunulan hizmet uç noktalarına belirterek oluşturun.</span><span class="sxs-lookup"><span data-stu-id="26de9-111">Create the basic Routing Service Configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="26de9-112">Aşağıdaki örnek, iletileri almak için kullanılan bir tek hizmet uç noktası tanımlar.</span><span class="sxs-lookup"><span data-stu-id="26de9-112">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="26de9-113">Ayrıca, regularCalc iletileri göndermek için kullanılan bir istemci uç noktası tanımlar.</span><span class="sxs-lookup"><span data-stu-id="26de9-113">It also defines a client endpoint that will be used to send messages to the regularCalc.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <client>  
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2.  <span data-ttu-id="26de9-114">Hedef Uç noktalara iletileri yönlendirmek için kullanılan filtre tanımlar.</span><span class="sxs-lookup"><span data-stu-id="26de9-114">Define the filter used to route messages to the destination endpoints.</span></span> <span data-ttu-id="26de9-115">Bu örnekte, MatchAll filtre önceden tanımlanmış regularCalcEndpoint tüm iletileri yönlendirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="26de9-115">For this example, the MatchAll filter is used to route all messages to the regularCalcEndpoint defined previously.</span></span> <span data-ttu-id="26de9-116">Aşağıdaki örnek, filtre tablosu ve filtre tanımlar.</span><span class="sxs-lookup"><span data-stu-id="26de9-116">The following example defines the filter and filter table.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3.  <span data-ttu-id="26de9-117">Filtre tablosunda bulunan filtreleriyle gelen iletileri değerlendirmek için yönlendirme davranışı kullanarak hizmet uç noktaları ile Filtresi tablosu ilişkilendirmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="26de9-117">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="26de9-118">Aşağıdaki örnek, hizmet uç noktası ile özellikle görüntüyle "filterTable1" gösterir.</span><span class="sxs-lookup"><span data-stu-id="26de9-118">The following example demonstrates associating "filterTable1" with the service endpoint.</span></span>  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="implement-dynamic-configuration"></a><span data-ttu-id="26de9-119">Uygulama dinamik yapılandırma</span><span class="sxs-lookup"><span data-stu-id="26de9-119">Implement Dynamic Configuration</span></span>  
 <span data-ttu-id="26de9-120">Yönlendirme hizmeti, dinamik olarak yapılandırılmasını yalnızca yapılabilir kodda yeni oluşturarak <xref:System.ServiceModel.Routing.RoutingConfiguration> ve kullanarak <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> geçerli yapılandırmayı değiştirmek için.</span><span class="sxs-lookup"><span data-stu-id="26de9-120">Dynamic configuration of the Routing Service can only be performed in code by creating a new <xref:System.ServiceModel.Routing.RoutingConfiguration> and using <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> to replace the current configuration.</span></span>  <span data-ttu-id="26de9-121">Bu örnekte, yönlendirme hizmeti bir konsol uygulaması içinde kendi kendine büyük/küçük harf barındırılır.</span><span class="sxs-lookup"><span data-stu-id="26de9-121">For this example, the Routing Service is self-hosted within a console application.</span></span> <span data-ttu-id="26de9-122">Uygulama başlatıldıktan sonra konsol penceresinden iletileri yönlendirilir hedef uç noktası yapılandırmak için 'Normal' veya 'yuvarlama' girerek yönlendirme yapılandırmasını değiştirebilirsiniz; 'Normal zaman' regularCalc girilen, aksi takdirde 'yuvarlarken' roundingCalc girilir.</span><span class="sxs-lookup"><span data-stu-id="26de9-122">After the application has started, you can modify the routing configuration by entering ‘regular’ or ‘rounding’ at the console window to configure the destination endpoint that messages are routed to; regularCalc when ‘regular’ is entered, otherwise roundingCalc when ‘rounding’ is entered.</span></span>  
  
1.  <span data-ttu-id="26de9-123">Aşağıdaki yönlendirme hizmeti desteklemek için using deyimleri eklenmelidir.</span><span class="sxs-lookup"><span data-stu-id="26de9-123">The following using statements must be added in order to support the Routing Service.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2.  <span data-ttu-id="26de9-124">Aşağıdaki kod yönlendirme hizmeti bir konsol uygulaması olarak kendi kendine barındırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="26de9-124">The following code is used to self-host the Routing Service as a console application.</span></span> <span data-ttu-id="26de9-125">Bu yönlendirme kullanılarak uygulama yapılandırma dosyasında yer alan önceki adımda açıklanan Yapılandırma hizmetini başlatır.</span><span class="sxs-lookup"><span data-stu-id="26de9-125">This initializes the Routing Service using the configuration described in the previous step, which is contained within the application configuration file.</span></span> <span data-ttu-id="26de9-126">While döngü yönlendirme yapılandırmasını değiştirmek için kullanılan kod içerir.</span><span class="sxs-lookup"><span data-stu-id="26de9-126">The while loop contains the code used to change the routing configuration.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners           
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="26de9-127">Dinamik yönlendirme yapılandırmasını güncelleştirmek için yeni bir yönlendirme yapılandırması oluşturulması gerekir.</span><span class="sxs-lookup"><span data-stu-id="26de9-127">To dynamically update the routing configuration, a new routing configuration must be created.</span></span> <span data-ttu-id="26de9-128">Varolan yönlendirme yapılandırmasını tamamen yerini alacak şekilde bu tüm uç noktaları, filtreleri ve yeni yönlendirme yapılandırması için gerekli olan filtre tablolara içermesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="26de9-128">This must contain all endpoints, filters and filter tables that are required for the new routing configuration, as it will completely replace the existing routing configuration.</span></span> <span data-ttu-id="26de9-129">Yeni yönlendirme yapılandırmasını kullanmak için çağırmalıdır <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> ve yeni yapılandırmayı geçirin.</span><span class="sxs-lookup"><span data-stu-id="26de9-129">In order to use the new routing configuration, you must invoke <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> and pass the new configuration.</span></span>  
  
     <span data-ttu-id="26de9-130">Aşağıdaki kodu ekleyin while Hizmeti'nin yapılandırılması izin vermek için önceden tanımlanmış döngü kullanıcı girişini temel alarak.</span><span class="sxs-lookup"><span data-stu-id="26de9-130">Add the following code to the while loop defined previously to allow the service to be reconfigured based on user input.</span></span>  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="26de9-131">Sağlama yöntemini itibaren yeni RoutingConfiguration nesneleri sağlanabilir herhangi bir yere ServiceHost başvuru elde edebilirsiniz veya WCF genişletilebilirlik modeli yeni RoutingConfiguration RoutingExtension hizmet uzantısı'nda bulunan veya ServiceExtensions (başka bir ServiceExtension olduğu gibi).</span><span class="sxs-lookup"><span data-stu-id="26de9-131">Since the method for providing a new RoutingConfiguration is contained in the RoutingExtension service extension, new RoutingConfiguration objects can be provided anywhere in the WCF extensibility model that has or can obtain a reference to the ServiceHost or ServiceExtensions (such as in another ServiceExtension).</span></span> <span data-ttu-id="26de9-132">Bu şekilde RoutingConfiguration dinamik güncelleştirme bir örnek için bkz: [dinamik yeniden yapılandırma](../../../../docs/framework/wcf/samples/dynamic-reconfiguration.md).</span><span class="sxs-lookup"><span data-stu-id="26de9-132">For an example of dynamically updating the RoutingConfiguration in this manner, see [Dynamic Reconfiguration](../../../../docs/framework/wcf/samples/dynamic-reconfiguration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="26de9-133">Örnek</span><span class="sxs-lookup"><span data-stu-id="26de9-133">Example</span></span>  
 <span data-ttu-id="26de9-134">Bu örnekte kullanılan konsol uygulaması tam bir listesi aşağıda verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="26de9-134">Following is a complete listing of the console application used in this example.</span></span>  
  
```  
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {             
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners           
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="26de9-135">Örnek</span><span class="sxs-lookup"><span data-stu-id="26de9-135">Example</span></span>  
 <span data-ttu-id="26de9-136">Aşağıdaki yapılandırma tam bir listesi verilmiştir Bu örnekte kullanılan dosya.</span><span class="sxs-lookup"><span data-stu-id="26de9-136">Following is a complete listing of the configuration file used in this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26de9-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="26de9-137">See Also</span></span>  
 [<span data-ttu-id="26de9-138">Yönlendirme Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="26de9-138">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)