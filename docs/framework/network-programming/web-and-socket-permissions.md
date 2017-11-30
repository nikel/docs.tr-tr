---
title: Web ve yuva izinleri
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Networking
- positions [.NET Framework], accepting
- sockets, permissions
- network, permissions
- Internet, permissions
- Network Resources
- SocketPermission class, about SocketPermission class
- positions [.NET Framework], connecting
- WebPermission class, about WebPermission class
- permissions [.NET Framework], sockets
- security [.NET Framework], Internet
- positions [.NET Framework], granting
ms.assetid: d51ad8cb-03ae-4a51-bfcd-cfcf6b98afa9
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 102d7d92384d77b5fbb56cd8c3eb859ec64bcca0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="web-and-socket-permissions"></a><span data-ttu-id="b4919-102">Web ve yuva izinleri</span><span class="sxs-lookup"><span data-stu-id="b4919-102">Web and Socket Permissions</span></span>
<span data-ttu-id="b4919-103">Internet güvenliği kullanan uygulamalar için <xref:System.Net> ad alanı tarafından sağlanan <xref:System.Net.WebPermission> ve <xref:System.Net.SocketPermission> sınıfları.</span><span class="sxs-lookup"><span data-stu-id="b4919-103">Internet security for applications using the <xref:System.Net> namespace is provided by the <xref:System.Net.WebPermission> and <xref:System.Net.SocketPermission> classes.</span></span> <span data-ttu-id="b4919-104">**WebPermission** sınıfı, bir uygulamanın sağ istek verileri için bir URI veya Internet'e bir URI sunmak için denetler.</span><span class="sxs-lookup"><span data-stu-id="b4919-104">The **WebPermission** class controls an application's right to request data from a URI or to serve a URI to the Internet.</span></span> <span data-ttu-id="b4919-105">**SocketPermission** sınıfı bir uygulamayı kullanmak doğru denetimleri bir <xref:System.Net.Sockets.Socket> yerel bağlantı noktası verileri kabul etmek veya başka bir adresinde konak, bağlantı noktası numarası, temel bir aktarım protokolünü kullanarak uzak aygıtlar iletişim kurmak için ve Soket Aktarım Protokolü.</span><span class="sxs-lookup"><span data-stu-id="b4919-105">The **SocketPermission** class controls an application's right to use a <xref:System.Net.Sockets.Socket> to accept data on a local port or to contact remote devices using a transport protocol at another address, based on the host, port number, and transport protocol of the socket.</span></span>  
  
 <span data-ttu-id="b4919-106">Kullandığınız hangi izni sınıfı, uygulama türüne bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="b4919-106">Which permission class you use depends on your application type.</span></span> <span data-ttu-id="b4919-107">Kullanan uygulamalar <xref:System.Net.WebRequest> ve alt öğeleri kullanması gereken **WebPermission** izinleri yönetmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="b4919-107">Applications that use <xref:System.Net.WebRequest> and its descendants should use the **WebPermission** class to manage permissions.</span></span> <span data-ttu-id="b4919-108">Yuva düzeyinde erişim kullanan uygulamaları kullanması gereken **SocketPermission** izinleri yönetmek için sınıf.</span><span class="sxs-lookup"><span data-stu-id="b4919-108">Applications that use socket-level access should use the **SocketPermission** class to manage permissions.</span></span>  
  
 <span data-ttu-id="b4919-109">**WebPermission** ve **SocketPermission** iki izinlerini tanımlamak: kabul etmek ve bağlanın.</span><span class="sxs-lookup"><span data-stu-id="b4919-109">**WebPermission** and **SocketPermission** define two permissions: accept and connect.</span></span> <span data-ttu-id="b4919-110">Kabul uygulama başka bir tarafa gelen bir bağlantıdan yanıt hakkı verir.</span><span class="sxs-lookup"><span data-stu-id="b4919-110">Accept grants the application the right to answer an incoming connection from another party.</span></span> <span data-ttu-id="b4919-111">Bağlantı uygulama başka bir tarafa bir bağlantı başlatmak hakkı verir.</span><span class="sxs-lookup"><span data-stu-id="b4919-111">Connect grants the application the right to initiate a connection to another party.</span></span>  
  
 <span data-ttu-id="b4919-112">İçin **SocketPermission** örnekleri, bir uygulamanın yerel gelen bağlantıları kabul edebilir anlamına gelir kabul aktarım adres; Bağlan uygulamanın bazı Uzak (veya yerel) aktarım adresine bağlanabilir anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="b4919-112">For **SocketPermission** instances, accept means that an application can accept incoming connections on a local transport address; connect means that an application can connect to some remote (or local) transport address.</span></span>  
  
 <span data-ttu-id="b4919-113">İçin **WebPermission** örnekleri, bir uygulama tarafından denetlenen URI verebilirsiniz anlamına gelir kabul **WebPermission** dünyasına; bir uygulama (olup bu URI erişebileceği anlamına gelir Bağlan Uzak veya yerel).</span><span class="sxs-lookup"><span data-stu-id="b4919-113">For **WebPermission** instances, accept means that an application can export the URI controlled by the **WebPermission** to the world; connect means that an application can access that URI (whether it is remote or local).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4919-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b4919-114">See Also</span></span>  
 [<span data-ttu-id="b4919-115">Güvenlik</span><span class="sxs-lookup"><span data-stu-id="b4919-115">Security</span></span>](../../../docs/standard/security/index.md)  
 [<span data-ttu-id="b4919-116">Güvenlik ağ programlama</span><span class="sxs-lookup"><span data-stu-id="b4919-116">Security in Network Programming</span></span>](../../../docs/framework/network-programming/security-in-network-programming.md)