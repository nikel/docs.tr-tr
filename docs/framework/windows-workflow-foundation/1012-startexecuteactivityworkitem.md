---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc60af91088fd61910dc0301b93844f4771177af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="73339-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="73339-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="73339-103">Özellikler</span><span class="sxs-lookup"><span data-stu-id="73339-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="73339-104">Kimlik</span><span class="sxs-lookup"><span data-stu-id="73339-104">ID</span></span>|<span data-ttu-id="73339-105">1012</span><span class="sxs-lookup"><span data-stu-id="73339-105">1012</span></span>|  
|<span data-ttu-id="73339-106">Anahtar Sözcükler</span><span class="sxs-lookup"><span data-stu-id="73339-106">Keywords</span></span>|<span data-ttu-id="73339-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="73339-107">WFRuntime</span></span>|  
|<span data-ttu-id="73339-108">Düzey</span><span class="sxs-lookup"><span data-stu-id="73339-108">Level</span></span>|<span data-ttu-id="73339-109">Ayrıntılı</span><span class="sxs-lookup"><span data-stu-id="73339-109">Verbose</span></span>|  
|<span data-ttu-id="73339-110">Kanal</span><span class="sxs-lookup"><span data-stu-id="73339-110">Channel</span></span>|<span data-ttu-id="73339-111">Microsoft Windows uygulaması sunucu-uygulamalar/hata ayıklama</span><span class="sxs-lookup"><span data-stu-id="73339-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="73339-112">Açıklama</span><span class="sxs-lookup"><span data-stu-id="73339-112">Description</span></span>  
 <span data-ttu-id="73339-113">Bir ExecuteActivityWorkItem yürütme başlanacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="73339-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="73339-114">İleti</span><span class="sxs-lookup"><span data-stu-id="73339-114">Message</span></span>  
 <span data-ttu-id="73339-115">'%1', DisplayName etkinliği için bir ExecuteActivityWorkItem yürütülmesi başlatılıyor: '%2', örnek kimliği: '%3'.</span><span class="sxs-lookup"><span data-stu-id="73339-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="73339-116">Ayrıntılar</span><span class="sxs-lookup"><span data-stu-id="73339-116">Details</span></span>  
  
|<span data-ttu-id="73339-117">Veri öğesi adı</span><span class="sxs-lookup"><span data-stu-id="73339-117">Data Item Name</span></span>|<span data-ttu-id="73339-118">Veri öğesi türü</span><span class="sxs-lookup"><span data-stu-id="73339-118">Data Item Type</span></span>|<span data-ttu-id="73339-119">Açıklama</span><span class="sxs-lookup"><span data-stu-id="73339-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="73339-120">Etkinlik</span><span class="sxs-lookup"><span data-stu-id="73339-120">Activity</span></span>|<span data-ttu-id="73339-121">xs: String</span><span class="sxs-lookup"><span data-stu-id="73339-121">xs:string</span></span>|<span data-ttu-id="73339-122">Etkinlik türü adı.</span><span class="sxs-lookup"><span data-stu-id="73339-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="73339-123">Görünen adı</span><span class="sxs-lookup"><span data-stu-id="73339-123">DisplayName</span></span>|<span data-ttu-id="73339-124">xs: String</span><span class="sxs-lookup"><span data-stu-id="73339-124">xs:string</span></span>|<span data-ttu-id="73339-125">Etkinliğin görünen adı.</span><span class="sxs-lookup"><span data-stu-id="73339-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="73339-126">örnek kimliği</span><span class="sxs-lookup"><span data-stu-id="73339-126">InstanceId</span></span>|<span data-ttu-id="73339-127">xs: String</span><span class="sxs-lookup"><span data-stu-id="73339-127">xs:string</span></span>|<span data-ttu-id="73339-128">Etkinlik örnek kimliği.</span><span class="sxs-lookup"><span data-stu-id="73339-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="73339-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="73339-129">AppDomain</span></span>|<span data-ttu-id="73339-130">xs: String</span><span class="sxs-lookup"><span data-stu-id="73339-130">xs:string</span></span>|<span data-ttu-id="73339-131">AppDomain.CurrentDomain.FriendlyName tarafından döndürülen dize.</span><span class="sxs-lookup"><span data-stu-id="73339-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|