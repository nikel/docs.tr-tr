---
title: ISymUnmanagedScope2 Arabirimi
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedScope2
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedScope2
helpviewer_keywords: ISymUnmanagedScope2 interface [.NET Framework debugging]
ms.assetid: 2ed6a387-ba45-483e-9a1e-b0c69f67998b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5eed6061c8108fcf91f8ac1ac9ff139da426f0e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedscope2-interface"></a><span data-ttu-id="9def8-102">ISymUnmanagedScope2 Arabirimi</span><span class="sxs-lookup"><span data-stu-id="9def8-102">ISymUnmanagedScope2 Interface</span></span>
<span data-ttu-id="9def8-103">Bir yöntem sözcük kapsamında temsil eder.</span><span class="sxs-lookup"><span data-stu-id="9def8-103">Represents a lexical scope within a method.</span></span> <span data-ttu-id="9def8-104">Bu arabirim genişletir [Isymunmanagedscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) kapsamı içinde tanımlanan sabitleri hakkında bilgi alma yöntemleriyle arabirimi.</span><span class="sxs-lookup"><span data-stu-id="9def8-104">This interface extends the [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface with methods that get information about constants defined within the scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9def8-105">Yöntemler</span><span class="sxs-lookup"><span data-stu-id="9def8-105">Methods</span></span>  
  
|<span data-ttu-id="9def8-106">Yöntem</span><span class="sxs-lookup"><span data-stu-id="9def8-106">Method</span></span>|<span data-ttu-id="9def8-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="9def8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9def8-108">GetConstantCount yöntemi</span><span class="sxs-lookup"><span data-stu-id="9def8-108">GetConstantCount Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstantcount-method.md)|<span data-ttu-id="9def8-109">Bu kapsam içinde tanımlanan sabitleri sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="9def8-109">Gets a count of the constants defined within this scope.</span></span>|  
|[<span data-ttu-id="9def8-110">GetConstants yöntemi</span><span class="sxs-lookup"><span data-stu-id="9def8-110">GetConstants Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-getconstants-method.md)|<span data-ttu-id="9def8-111">Bu kapsam içinde tanımlanan yerel sabitleri alır.</span><span class="sxs-lookup"><span data-stu-id="9def8-111">Gets the local constants defined within this scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9def8-112">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="9def8-112">Requirements</span></span>  
 <span data-ttu-id="9def8-113">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9def8-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9def8-114">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="9def8-114">See Also</span></span>  
 [<span data-ttu-id="9def8-115">Tanılama sembol deposu arabirimleri</span><span class="sxs-lookup"><span data-stu-id="9def8-115">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="9def8-116">Isymunmanagedscope arabirimi</span><span class="sxs-lookup"><span data-stu-id="9def8-116">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)