---
title: "Oluşturma ve bir iş akışı örneği çalıştırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3d6dd2f27a6db9770231a5c947c98614d4f6f175
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-and-running-a-workflow-instance"></a>Oluşturma ve bir iş akışı örneği çalıştırma
Bu örnek, bir iş akışı örneği çalıştırmak gösterilmiştir. Zaman uyumlu ve zaman uyumsuz olarak yürütülecek nasıl gösterir.  
  
## <a name="demonstrates"></a>Gösteriler  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>Tartışma  
 İlk bölümü örneğinin kullandığı <xref:System.Activities.WorkflowInvoker.Invoke%2A>. Bir iş akışını yürütmek için en temel yolu budur. İş akışları ile yürütülen <xref:System.Activities.WorkflowInvoker.Invoke%2A> zaman uyumlu olarak yürütülür.  
  
 İkinci bölümü örneğinin kullandığı <xref:System.Activities.WorkflowApplication> sınıfı. <xref:System.Activities.WorkflowApplication>çalışan bir iş akışı ile etkileşim kurmak için ve iş akışını zaman uyumsuz olarak çalıştırmak için yeteneği dahil olmak üzere her örneği üzerinde daha fazla denetime sahip olmasını sağlar.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse, Git [Windows Communication Foundation (WCF) ve .NET Framework 4 için Windows Workflow Foundation (WF) örnek](http://go.microsoft.com/fwlink/?LinkId=150780) tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WorkflowInvoker ve WorkflowApplication Kullanma](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
