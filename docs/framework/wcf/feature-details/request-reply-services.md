---
title: "İstek-Yanıt Hizmetleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], request-reply services
- contracts [WCF], request-reply services
- WCF [WCF], request-reply services
- request-reply contracts [WCF]
ms.assetid: 2fa710f1-47f4-4598-b063-3ab3bd22ebba
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a38a90d4e9ec249f91e8bfda88c646c006890d8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="request-reply-services"></a><span data-ttu-id="d971d-102">İstek-Yanıt Hizmetleri</span><span class="sxs-lookup"><span data-stu-id="d971d-102">Request-Reply Services</span></span>
<span data-ttu-id="d971d-103">İstek-yanıt Hizmetleri işlemi sözleşmede varsayılan türündedir [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d971d-103">Request-reply services are the default type of operation contract in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="d971d-104">İstemcileri hizmet işlemleri çağrı yapmak ve hizmetinden bir yanıt bekleyin.</span><span class="sxs-lookup"><span data-stu-id="d971d-104">Clients make calls to service operations and wait for a response from the service.</span></span> <span data-ttu-id="d971d-105">Bir hizmet işlemi çağrıları ya da zaman uyumlu olarak gerçekleştirebileceğiniz, kadar istemci engeller burada bu hizmetin veya çağrı süreleri bir yanıt alır veya zaman uyumsuz olarak, istemci hizmet işlemi için bir çağrı yapar burada çalışmaya devam eder ve alır başka bir iş parçacığında hizmetinden gelen yanıt.</span><span class="sxs-lookup"><span data-stu-id="d971d-105">You can perform calls to a service operation either synchronously, where the client blocks until it receives a response from the service or the call times, or asynchronously, where the client makes a call to the service operation, continues working, and receives the response from the service on another thread.</span></span>  
  
 <span data-ttu-id="d971d-106">İstek-yanıt hizmeti sözleşme oluşturmak için hizmet sözleşmesini tanımlama ve uygulama <xref:System.ServiceModel.OperationContractAttribute> aşağıdaki örnek kodda gösterildiği gibi her işlem için sınıf.</span><span class="sxs-lookup"><span data-stu-id="d971d-106">To create a request-reply service contract, define your service contract, and apply the <xref:System.ServiceModel.OperationContractAttribute> class to each operation, as shown in the following sample code.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IRequestReplyCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="d971d-107">Ayarlama gerekmez <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> özelliğine `false` bu varsayılan davranış olduğu için.</span><span class="sxs-lookup"><span data-stu-id="d971d-107">You do not have to set the  <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A> property to `false` because this is the default behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d971d-108">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d971d-108">See Also</span></span>  
 [<span data-ttu-id="d971d-109">Tek yönlü hizmetler</span><span class="sxs-lookup"><span data-stu-id="d971d-109">One-Way Services</span></span>](../../../../docs/framework/wcf/feature-details/one-way-services.md)  
 [<span data-ttu-id="d971d-110">Çift yönlü hizmetler</span><span class="sxs-lookup"><span data-stu-id="d971d-110">Duplex Services</span></span>](../../../../docs/framework/wcf/feature-details/duplex-services.md)