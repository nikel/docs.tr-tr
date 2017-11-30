---
title: "Nesne Başvuruları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a93d260-91c3-4448-8f7a-a66fb562fc23
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 643cdf80900a02f269887aa6c95832429060fc8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="object-references"></a><span data-ttu-id="6c21e-102">Nesne Başvuruları</span><span class="sxs-lookup"><span data-stu-id="6c21e-102">Object References</span></span>
<span data-ttu-id="6c21e-103">Bu örnek, sunucu ve istemci arasında başvurular nesneleri geçirmek gösterilmiştir.</span><span class="sxs-lookup"><span data-stu-id="6c21e-103">This sample demonstrates how to pass objects by references between server and client.</span></span> <span data-ttu-id="6c21e-104">Örnek kullandığı benzetimli *sosyal ağlar*.</span><span class="sxs-lookup"><span data-stu-id="6c21e-104">The sample uses simulated *social networks*.</span></span> <span data-ttu-id="6c21e-105">Sosyal ağ oluşan bir `Person` her arkadaş örneği olan arkadaş listesi içeren sınıf `Person` sınıfıyla arkadaş kendi listesi.</span><span class="sxs-lookup"><span data-stu-id="6c21e-105">A social network consists of a `Person` class that contains a list of friends in which each friend is an instance of the `Person` class, with its own list of friends.</span></span> <span data-ttu-id="6c21e-106">Bu nesne bir grafik oluşturur.</span><span class="sxs-lookup"><span data-stu-id="6c21e-106">This creates a graph of objects.</span></span> <span data-ttu-id="6c21e-107">Hizmet bu sosyal ağlarda işlemini kullanıma sunar.</span><span class="sxs-lookup"><span data-stu-id="6c21e-107">The service exposes operations on these social networks.</span></span>  
  
 <span data-ttu-id="6c21e-108">Bu örnekte, Internet Information Services (IIS) tarafından barındırılan hizmetindeki ve istemcinin bir konsol uygulaması (.exe).</span><span class="sxs-lookup"><span data-stu-id="6c21e-108">In this sample, the service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c21e-109">Kurulum yordamı ve yapı yönergeleri Bu örnek için bu konunun sonunda yer alır.</span><span class="sxs-lookup"><span data-stu-id="6c21e-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="service"></a><span data-ttu-id="6c21e-110">Hizmet</span><span class="sxs-lookup"><span data-stu-id="6c21e-110">Service</span></span>  
 <span data-ttu-id="6c21e-111">`Person` Sınıfına sahip <xref:System.Runtime.Serialization.DataContractAttribute> uygulanan özniteliği ile <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> alan kümesi'ne `true` gibi bir başvuru türü bildirmek için.</span><span class="sxs-lookup"><span data-stu-id="6c21e-111">The `Person` class has the <xref:System.Runtime.Serialization.DataContractAttribute> attribute applied, with the <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A> field set to `true` to declare it as a reference type.</span></span> <span data-ttu-id="6c21e-112">Tüm özelliklere sahip <xref:System.Runtime.Serialization.DataMemberAttribute> özniteliği uygulanmıştır.</span><span class="sxs-lookup"><span data-stu-id="6c21e-112">All properties have the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute applied.</span></span>  
  
```  
[DataContract(IsReference=true)]  
public class Person  
{  
    string name;  
    string location;  
    string gender;  
    int age;  
    List<Person> friends;  
    [DataMember()]  
    public string Name  
    {  
        get { return name; }  
        set { name = value; }  
    }  
    [DataMember()]  
    public string Location  
    {  
        get { return location; }  
        set { location = value; }  
    }  
    [DataMember()]  
    public string Gender  
    {  
        get { return gender; }  
        set { gender = value; }  
    }  
…  
}  
```  
  
 <span data-ttu-id="6c21e-113">`GetPeopleInNetwork` İşlemi türünde bir parametre alır `Person` ve tüm kişilerin ağda; döndürür diğer bir deyişle, tüm kişiler `friends` listesi, arkadaşınızın arkadaşlarınız ve yinelemeleri olmadan belirli bir benzeri.</span><span class="sxs-lookup"><span data-stu-id="6c21e-113">The `GetPeopleInNetwork` operation takes a parameter of type `Person` and returns all the people in the network; that is, all the people in the `friends` list, the friend's friends, and so on, without duplicates.</span></span>  
  
```  
public List<Person> GetPeopleInNetwork(Person p)  
{  
    List<Person> people = new List<Person>();  
    ListPeopleInNetwork(p, people);  
    return people;  
  
}  
```  
  
 <span data-ttu-id="6c21e-114">`GetMutualFriends` İşlemi türünde bir parametre alır `Person` ve ayrıca bu kişinin sahip listesindeki tüm arkadaş verir, bunların `friends` listesi.</span><span class="sxs-lookup"><span data-stu-id="6c21e-114">The `GetMutualFriends` operation takes a parameter of type `Person` and returns all the friends in the list who also have this person in their `friends` list.</span></span>  
  
```  
public List<Person> GetMutualFriends(Person p)  
{  
    List<Person> mutual = new List<Person>();  
    foreach (Person friend in p.Friends)  
    {  
        if (friend.Friends.Contains(p))  
            mutual.Add(friend);  
    }  
    return mutual;  
}  
```  
  
 <span data-ttu-id="6c21e-115">`GetCommonFriends` İşlemi türü listesini alır `Person`.</span><span class="sxs-lookup"><span data-stu-id="6c21e-115">The `GetCommonFriends` operation takes a list of type `Person`.</span></span> <span data-ttu-id="6c21e-116">Liste iki olması beklenir `Person` içindeki nesneleri.</span><span class="sxs-lookup"><span data-stu-id="6c21e-116">The list is expected to have two `Person` objects in it.</span></span> <span data-ttu-id="6c21e-117">İşlemi bir listesini döndürür `Person` nesnelerine `friends` listeleri hem `Person` giriş listesi nesneleri.</span><span class="sxs-lookup"><span data-stu-id="6c21e-117">The operation returns a list of `Person` objects that are in the `friends` lists of both `Person` objects in the input list.</span></span>  
  
```  
public List<Person> GetCommonFriends(List<Person> people)  
{  
    List<Person> common = new List<Person>();  
    foreach (Person friend in people[0].Friends)  
        if (people[1].Friends.Contains(friend))  
            common.Add(friend);  
    return common;  
}  
```  
  
## <a name="client"></a><span data-ttu-id="6c21e-118">İstemci</span><span class="sxs-lookup"><span data-stu-id="6c21e-118">Client</span></span>  
 <span data-ttu-id="6c21e-119">İstemci proxy kullanılarak oluşturulan **hizmet Başvurusu Ekle** özelliği [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6c21e-119">The client proxy is created using the **Add Service Reference** feature of [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].</span></span>  
  
 <span data-ttu-id="6c21e-120">Beş oluşan bir sosyal ağda `Person` nesneleri oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="6c21e-120">A social network that consists of five `Person` objects is created.</span></span> <span data-ttu-id="6c21e-121">İstemci hizmeti her üç yöntemi çağırır.</span><span class="sxs-lookup"><span data-stu-id="6c21e-121">The client calls each of the three methods in the service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6c21e-122">Ayarlamak için derleme ve örnek çalıştırın</span><span class="sxs-lookup"><span data-stu-id="6c21e-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6c21e-123">Gerçekleştirmiş emin olun [kerelik Kurulum prosedürü Windows Communication Foundation örnekleri için](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6c21e-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6c21e-124">Çözüm C# veya Visual Basic .NET sürümünü oluşturmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örnekleri derleme](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6c21e-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6c21e-125">Tek veya çapraz makine yapılandırmada örneği çalıştırmak için'ndaki yönergeleri izleyin [Windows Communication Foundation örneklerini çalıştırma](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6c21e-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c21e-126">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="6c21e-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6c21e-127">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="6c21e-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6c21e-128">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="6c21e-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6c21e-129">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="6c21e-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\ObjectReferences`  
  
## <a name="see-also"></a><span data-ttu-id="6c21e-130">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6c21e-130">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractAttribute.IsReference%2A>  
 [<span data-ttu-id="6c21e-131">Birlikte çalışabilir nesne başvuruları</span><span class="sxs-lookup"><span data-stu-id="6c21e-131">Interoperable Object References</span></span>](../../../../docs/framework/wcf/feature-details/interoperable-object-references.md)