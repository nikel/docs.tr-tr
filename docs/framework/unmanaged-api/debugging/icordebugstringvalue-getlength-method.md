---
title: ICorDebugStringValue::GetLength Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetLength
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c072e7420e400e6402c8697eefc62c658c590261
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="8a78d-102">ICorDebugStringValue::GetLength Metodu</span><span class="sxs-lookup"><span data-stu-id="8a78d-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="8a78d-103">Bu Icordebugstringvalue tarafından başvurulan dizedeki karakter sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="8a78d-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a78d-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="8a78d-104">Syntax</span></span>  
  
```  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a78d-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="8a78d-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="8a78d-106">[out] Bu tarafından başvurulan dize uzunluğu belirten bir değer için bir işaretçi `ICorDebugStringValue` nesnesi.</span><span class="sxs-lookup"><span data-stu-id="8a78d-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a78d-107">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="8a78d-107">Requirements</span></span>  
 <span data-ttu-id="8a78d-108">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a78d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a78d-109">**Başlık:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a78d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a78d-110">**Kitaplığı:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a78d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a78d-111">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a78d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>