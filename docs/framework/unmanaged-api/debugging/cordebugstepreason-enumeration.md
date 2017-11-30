---
title: "CorDebugStepReason Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugStepReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugStepReason
helpviewer_keywords: CorDebugStepReason enumeration [.NET Framework debugging]
ms.assetid: fe248069-b33c-48e1-a777-06ac9b239c54
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 32892a14de820e8add38654cef92aa44930aec62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugstepreason-enumeration"></a><span data-ttu-id="1816c-102">CorDebugStepReason Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="1816c-102">CorDebugStepReason Enumeration</span></span>
<span data-ttu-id="1816c-103">Tek bir adımı sonucunu gösterir.</span><span class="sxs-lookup"><span data-stu-id="1816c-103">Indicates the outcome of an individual step.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1816c-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="1816c-104">Syntax</span></span>  
  
```  
typedef enum CorDebugStepReason {  
    STEP_NORMAL,  
    STEP_RETURN,  
    STEP_CALL,  
    STEP_EXCEPTION_FILTER,  
    STEP_EXCEPTION_HANDLER,  
    STEP_INTERCEPT,  
    STEP_EXIT  
} CorDebugStepReason;  
```  
  
## <a name="members"></a><span data-ttu-id="1816c-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="1816c-105">Members</span></span>  
  
|<span data-ttu-id="1816c-106">Üye</span><span class="sxs-lookup"><span data-stu-id="1816c-106">Member</span></span>|<span data-ttu-id="1816c-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="1816c-107">Description</span></span>|  
|------------|-----------------|  
|`STEP_NORMAL`|<span data-ttu-id="1816c-108">Atlama normal olarak, aynı işlev içinde tamamlandı.</span><span class="sxs-lookup"><span data-stu-id="1816c-108">Stepping completed normally, within the same function.</span></span>|  
|`STEP_RETURN`|<span data-ttu-id="1816c-109">İşlev sonra atlama normal şekilde devam.</span><span class="sxs-lookup"><span data-stu-id="1816c-109">Stepping continued normally, after the function returned.</span></span>|  
|`STEP_CALL`|<span data-ttu-id="1816c-110">Atlama normal olarak, yeni çağrılan işlev başında devam eder.</span><span class="sxs-lookup"><span data-stu-id="1816c-110">Stepping continued normally, at the beginning of a newly called function.</span></span>|  
|`STEP_EXCEPTION_FILTER`|<span data-ttu-id="1816c-111">Bir özel durum oluşturuldu ve denetim için bir özel durum filtresi geçirildi.</span><span class="sxs-lookup"><span data-stu-id="1816c-111">An exception was generated and control was passed to an exception filter.</span></span>|  
|`STEP_EXCEPTION_HANDLER`|<span data-ttu-id="1816c-112">Bir özel durum oluşturuldu ve denetim için bir özel durum işleyici geçirildi.</span><span class="sxs-lookup"><span data-stu-id="1816c-112">An exception was generated and control was passed to an exception handler.</span></span>|  
|`STEP_INTERCEPT`|<span data-ttu-id="1816c-113">Denetim bir dinleyiciyi geçirildi.</span><span class="sxs-lookup"><span data-stu-id="1816c-113">Control was passed to an interceptor.</span></span>|  
|`STEP_EXIT`|<span data-ttu-id="1816c-114">Adım tamamlanmadan önce iş parçacığı çıkıldı.</span><span class="sxs-lookup"><span data-stu-id="1816c-114">The thread exited before the step was completed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1816c-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="1816c-115">Requirements</span></span>  
 <span data-ttu-id="1816c-116">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1816c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1816c-117">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1816c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1816c-118">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1816c-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1816c-119">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1816c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1816c-120">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="1816c-120">See Also</span></span>  
 [<span data-ttu-id="1816c-121">StepComplete yöntemi</span><span class="sxs-lookup"><span data-stu-id="1816c-121">StepComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)  
 [<span data-ttu-id="1816c-122">Hata ayıklama numaralandırmaları</span><span class="sxs-lookup"><span data-stu-id="1816c-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)