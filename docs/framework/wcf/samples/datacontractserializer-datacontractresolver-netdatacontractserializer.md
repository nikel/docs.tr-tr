---
title: "NetDataContractSerializer İşlevselliğini Sağlamak için DataContractSerializer ve DataContractResolver Kullanma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d189b68cc8321dace0418a3c1e4b1b3c21cfd3ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="e3b57-102">NetDataContractSerializer İşlevselliğini Sağlamak için DataContractSerializer ve DataContractResolver Kullanma</span><span class="sxs-lookup"><span data-stu-id="e3b57-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="e3b57-103">Bu örnek gösterilmektedir nasıl kullanımını <xref:System.Runtime.Serialization.DataContractSerializer> uygun bir <xref:System.Runtime.Serialization.DataContractResolver> aynı işlevselliği sunar <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e3b57-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="e3b57-104">Bu örnek uygun oluşturulacağını gösterir <xref:System.Runtime.Serialization.DataContractResolver> ve eklemek nasıl <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e3b57-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="e3b57-105">Örnek Ayrıntıları</span><span class="sxs-lookup"><span data-stu-id="e3b57-105">Sample details</span></span>  
 <span data-ttu-id="e3b57-106"><xref:System.Runtime.Serialization.NetDataContractSerializer>farklı <xref:System.Runtime.Serialization.DataContractSerializer> önemli bir şekilde: <xref:System.Runtime.Serialization.NetDataContractSerializer> CLR türü bilgileri serileştirilmiş XML'de içerir <xref:System.Runtime.Serialization.DataContractSerializer> desteklemez.</span><span class="sxs-lookup"><span data-stu-id="e3b57-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="e3b57-107">Bu nedenle, <xref:System.Runtime.Serialization.NetDataContractSerializer> yalnızca hem seri hale getirme ve uçları seri durumdan aynı CLR Türleri paylaşıyorsa kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="e3b57-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="e3b57-108">Ancak, kullanmak için önerilir <xref:System.Runtime.Serialization.DataContractSerializer> performansını daha iyi olduğundan <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="e3b57-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="e3b57-109">İçinde serileştirilmiş bilgileri değiştirebilirsiniz <xref:System.Runtime.Serialization.DataContractSerializer> ekleyerek bir <xref:System.Runtime.Serialization.DataContractResolver> kendisine.</span><span class="sxs-lookup"><span data-stu-id="e3b57-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>  
  
 <span data-ttu-id="e3b57-110">Bu örnek iki projeden oluşan.</span><span class="sxs-lookup"><span data-stu-id="e3b57-110">This sample consists of two projects.</span></span> <span data-ttu-id="e3b57-111">İlk proje kullanan <xref:System.Runtime.Serialization.NetDataContractSerializer> bir nesneyi serileştirme.</span><span class="sxs-lookup"><span data-stu-id="e3b57-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="e3b57-112">İkinci projenin kullandığı <xref:System.Runtime.Serialization.DataContractSerializer> ile bir <xref:System.Runtime.Serialization.DataContractResolver> ilk proje ile aynı işlevselliği sağlamak için.</span><span class="sxs-lookup"><span data-stu-id="e3b57-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>  
  
 <span data-ttu-id="e3b57-113">Aşağıdaki kod örneğinde özel bir gösterir <xref:System.Runtime.Serialization.DataContractResolver> adlı `MyDataContractResolver` için eklenen <xref:System.Runtime.Serialization.DataContractSerializer> DCSwithDCR projesinde.</span><span class="sxs-lookup"><span data-stu-id="e3b57-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>  
  
```  
class MyDataContractResolver : DataContractResolver  
{  
    private XmlDictionary dictionary = new XmlDictionary();  
  
    public MyDataContractResolver()  
    {  
    }  
  
    // Used at deserialization  
    // Allows users to map xsi:type name to any Type   
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)  
    {  
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);  
        if (type == null)  
        {  
            type = Type.GetType(typeName + ", " + typeNamespace);  
        }  
        return type;  
    }  
  
    // Used at serialization  
    // Maps any Type to a new xsi:type representation  
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)  
    {  
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);  
        if (typeName == null || typeNamespace == null)  
        {  
            XmlDictionary dictionary = new XmlDictionary();  
            typeName = dictionary.Add(dataContractType.FullName);  
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);  
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="e3b57-114">Bu örneği kullanmak için</span><span class="sxs-lookup"><span data-stu-id="e3b57-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="e3b57-115">Kullanarak [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], DCRSample.sln çözüm dosyasını açın.</span><span class="sxs-lookup"><span data-stu-id="e3b57-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the DCRSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="e3b57-116">Çözüm dosyasını sağ tıklatın ve seçin **özellikleri**.</span><span class="sxs-lookup"><span data-stu-id="e3b57-116">Right-click the solution file and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="e3b57-117">İçinde **çözüm özellik sayfaları** iletişim altında **ortak özellikleri**, **başlangıç projesi**seçin **birden fazla başlangıç projesi:**.</span><span class="sxs-lookup"><span data-stu-id="e3b57-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>  
  
4.  <span data-ttu-id="e3b57-118">Yanına **DCSwithDCR** proje, select **Başlat** gelen **eylem** açılır.</span><span class="sxs-lookup"><span data-stu-id="e3b57-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>  
  
5.  <span data-ttu-id="e3b57-119">Yanına **NetDCS** proje, select **Başlat** gelen **eylem** açılır.</span><span class="sxs-lookup"><span data-stu-id="e3b57-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>  
  
6.  <span data-ttu-id="e3b57-120">Tıklatın **Tamam** iletişim kutusunu kapatmak için.</span><span class="sxs-lookup"><span data-stu-id="e3b57-120">Click **OK** to close the dialog.</span></span>  
  
7.  <span data-ttu-id="e3b57-121">Çözümü derlemek için CTRL + SHIFT + B tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e3b57-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
8.  <span data-ttu-id="e3b57-122">Çözümü çalıştırmak için CTRL + F5 tuşuna basın.</span><span class="sxs-lookup"><span data-stu-id="e3b57-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e3b57-123">Örnekler, makinenizde zaten yüklü olabilir.</span><span class="sxs-lookup"><span data-stu-id="e3b57-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e3b57-124">Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.</span><span class="sxs-lookup"><span data-stu-id="e3b57-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="e3b57-125">Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri.</span><span class="sxs-lookup"><span data-stu-id="e3b57-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e3b57-126">Bu örnek aşağıdaki dizinde bulunur.</span><span class="sxs-lookup"><span data-stu-id="e3b57-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## <a name="see-also"></a><span data-ttu-id="e3b57-127">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e3b57-127">See Also</span></span>