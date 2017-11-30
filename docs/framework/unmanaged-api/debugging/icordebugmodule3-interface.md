---
title: ICorDebugModule3 Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule3
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugModule3
helpviewer_keywords: ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f6ef8314329aba60d8c23c6f00725192d83961ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="c29a2-102">ICorDebugModule3 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="c29a2-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="c29a2-103">Dinamik modül için simge okuyucu oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c29a2-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29a2-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="c29a2-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c29a2-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="c29a2-105">Methods</span></span>  
  
|<span data-ttu-id="c29a2-106">Yöntem</span><span class="sxs-lookup"><span data-stu-id="c29a2-106">Method</span></span>|<span data-ttu-id="c29a2-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c29a2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c29a2-108">Icordebugmodule3::createreaderforınmemorysymbols yöntemi</span><span class="sxs-lookup"><span data-stu-id="c29a2-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="c29a2-109">Bir simge okuyucu oluşturur (genellikle [Isymunmanagedreader arabirimi](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) dinamik modülü için.</span><span class="sxs-lookup"><span data-stu-id="c29a2-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c29a2-110">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="c29a2-110">Remarks</span></span>  
 <span data-ttu-id="c29a2-111">Bu arabirim, mantıksal olarak "ICorDebugModule" ve "ICorDebugModule2" arabirimleri genişletir.</span><span class="sxs-lookup"><span data-stu-id="c29a2-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c29a2-112">Bu arabirim, makineler arası veya çapraz işlem uzaktan çağrılan desteklemez.</span><span class="sxs-lookup"><span data-stu-id="c29a2-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c29a2-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="c29a2-113">Requirements</span></span>  
 <span data-ttu-id="c29a2-114">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c29a2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c29a2-115">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c29a2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c29a2-116">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c29a2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c29a2-117">**.NET framework sürümleri:**4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c29a2-117">**.NET Framework Versions:**4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c29a2-118">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c29a2-118">See Also</span></span>  
 [<span data-ttu-id="c29a2-119">Icordebugremotetarget arabirimi</span><span class="sxs-lookup"><span data-stu-id="c29a2-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="c29a2-120">Icordebug arabirimi</span><span class="sxs-lookup"><span data-stu-id="c29a2-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
    
 [<span data-ttu-id="c29a2-121">Hata ayıklama arabirimleri</span><span class="sxs-lookup"><span data-stu-id="c29a2-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)