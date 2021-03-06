---
title: "XAML etkinleştirme"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 486760e2-bb10-4ed5-8c02-fe7472498d2d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53665f39c6c0c7e5c7956912b05e3fd80659ddcb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="xaml-activation"></a>XAML etkinleştirme
Bu örnek, IIS'de bildirim temelli bir iş akışı barındırma gösterilmiştir. Örnek olarak adlandırılan bir temel iş akışıdır `EchoService` bir işleme sahip.  
  
> [!IMPORTANT]
>  Örnekler, makinenizde zaten yüklü olabilir. Devam etmeden önce aşağıdaki (varsayılan) dizin denetleyin.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Bu dizin mevcut değilse (indirme) gidin tüm indirmek için [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ve [!INCLUDE[wf1](../../../../includes/wf1-md.md)] örnekleri. Bu örnek aşağıdaki dizinde bulunur.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\XAMLActivation`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Ayarlamak için derleme ve örnek çalıştırın  
  
1.  XAMLActivation.sln çözümde açmak [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Tuşlarına basarak çözümü oluşturun **F5**.  
  
3.  WcfTestClient.exe çalıştırın. Bir komut isteminden aşağıdaki komutu yazın:  
  
    1.  CD %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE  
  
    2.  WcfTestClient.exe çalıştırın.  
  
4.  Hizmetinin adresini üzerinde WcfTestClient.exe CTRL + SHIFT + A basarak ve http://localhost:56133/Service.xamlx için hizmeti adresi ayarlayarak ayarlayın.  
  
5.  Hizmeti sınamak için Yankı işlemi gerçekleştirin.  
  
6.  Hizmeti IIS DeployToIIS.Bat yönetici ayrıcalıklarıyla bir komut istemi kullanarak dağıtın.  
  
7.  Http://localhost/XAMLActivation/Service.xamlx için istemci hizmeti adresi güncelleştirmek ve hizmeti yeniden WcfTestClient.exe kullanarak test edin.
