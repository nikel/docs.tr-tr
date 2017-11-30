---
title: IEnumIDENTITY_ATTRIBUTE Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IEnumIDENTITY_ATTRIBUTE
api_location: fusion.dll
api_type: COM
f1_keywords: IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords: IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f88e400556421e0908e0a0b115f66ec3221124c2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="d3bb6-102">IEnumIDENTITY_ATTRIBUTE Arabirimi</span><span class="sxs-lookup"><span data-stu-id="d3bb6-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="d3bb6-103">Geçerli kapsamdaki kod nesnesinin öznitelikleri için bir numaralandırıcı olarak görev yapar.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3bb6-104">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="d3bb6-104">Methods</span></span>  
  
|<span data-ttu-id="d3bb6-105">Yöntem</span><span class="sxs-lookup"><span data-stu-id="d3bb6-105">Method</span></span>|<span data-ttu-id="d3bb6-106">Açıklama</span><span class="sxs-lookup"><span data-stu-id="d3bb6-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="d3bb6-107">Arabirim işaretçisi yeni bir alır `IEnumIDENTITY_ATTRIBUTE` bu aynı üyeleri içeren `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="d3bb6-108">Bu öğeleri bulunan verileri Yazar `IEnumIDENTITY_ATTRIBUTE` için belirtilen veri arabelleği.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="d3bb6-109">Belirtilen öznitelikler, geçerli konumdan başlayarak sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="d3bb6-110">Yönerge işaretçisi başlangıcına bu taşır `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="d3bb6-111">Öğeler, geçerli konumdan başlayarak belirtilen sayıda tarafından yönerge işaretçisi İleri taşınır.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3bb6-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="d3bb6-112">Requirements</span></span>  
 <span data-ttu-id="d3bb6-113">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3bb6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3bb6-114">**Başlık:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d3bb6-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d3bb6-115">**.NET framework sürümleri:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3bb6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3bb6-116">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d3bb6-116">See Also</span></span>  
 [<span data-ttu-id="d3bb6-117">Fusion arabirimleri</span><span class="sxs-lookup"><span data-stu-id="d3bb6-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)