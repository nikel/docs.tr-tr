---
title: ICorDebugProcess::GetHelperThreadID Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHelperThreadID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 092e99cb1d5534cee56db08b5a2eedaaa2fc4724
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="cdf18-102">ICorDebugProcess::GetHelperThreadID Metodu</span><span class="sxs-lookup"><span data-stu-id="cdf18-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="cdf18-103">Hata Ayıklayıcı'nın iç yardımcı iş parçacığı işletim sistemi (OS) iş parçacığı kimliği alır.</span><span class="sxs-lookup"><span data-stu-id="cdf18-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdf18-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="cdf18-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cdf18-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="cdf18-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="cdf18-106">[out] İşletim sistemi için bir işaretçi iş parçacığı Hata Ayıklayıcı'nın iç yardımcı iş parçacığı kimliği.</span><span class="sxs-lookup"><span data-stu-id="cdf18-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cdf18-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="cdf18-107">Remarks</span></span>  
 <span data-ttu-id="cdf18-108">Yönetilen ve yönetilmeyen hata ayıklama sırasında hata ayıklayıcı tarafından yerleştirilen bir kesme noktası değerse, iş parçacığı belirtilen kimliği ile çalışan kaldığından emin olmak için hata ayıklayıcı'nın sorumluluğundadır.</span><span class="sxs-lookup"><span data-stu-id="cdf18-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="cdf18-109">Bir hata ayıklayıcısı da kullanıcının bu iş parçacığından Gizle isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="cdf18-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="cdf18-110">Hiçbir Yardımcısı iş parçacığı işleminde henüz varsa `GetHelperThreadID` yöntemi döndürür sıfır *`pThreadID`.</span><span class="sxs-lookup"><span data-stu-id="cdf18-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in *`pThreadID`.</span></span>  
  
 <span data-ttu-id="cdf18-111">Zaman içinde değişebilir olduğundan Yardımcısı iş parçacığı, iş parçacığı kimliği önbelleğe alamıyor.</span><span class="sxs-lookup"><span data-stu-id="cdf18-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="cdf18-112">İş parçacığı kimliği her durdurma olay yeniden sorgulaması gerekir.</span><span class="sxs-lookup"><span data-stu-id="cdf18-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="cdf18-113">Hata Ayıklayıcı'nın Yardımcısı iş parçacığı iş parçacığı kimliği üzerinde doğru her yönetilmeyen [Icordebugmanagedcallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) olay, böylece kendi Yardımcısı iş parçacığı iş parçacığı Kimliğini belirlemek ve kullanıcıdan gizlemek bir hata ayıklayıcısı sağlar.</span><span class="sxs-lookup"><span data-stu-id="cdf18-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="cdf18-114">Bir yardımcı iş parçacığı yönetilmeyen sırasında tanımlanan bir iş parçacığı `ICorDebugManagedCallback::CreateThread` olay asla yönetilen kullanıcı kodu çalışmaz.</span><span class="sxs-lookup"><span data-stu-id="cdf18-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdf18-115">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="cdf18-115">Requirements</span></span>  
 <span data-ttu-id="cdf18-116">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdf18-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdf18-117">**Başlık:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="cdf18-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="cdf18-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdf18-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="cdf18-119">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdf18-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdf18-120">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdf18-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>