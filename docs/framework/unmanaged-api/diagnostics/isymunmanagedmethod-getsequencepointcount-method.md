---
title: ISymUnmanagedMethod::GetSequencePointCount Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetSequencePointCount
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetSequencePointCount
helpviewer_keywords:
- ISymUnmanagedMethod::GetSequencePointCount method [.NET Framework debugging]
- GetSequencePointCount method [.NET Framework debugging]
ms.assetid: 836133e8-6108-4b9b-b0a9-bce4e08dccda
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1666eacd8756209c126171ad8ecae56afa802892
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetsequencepointcount-method"></a><span data-ttu-id="e51b5-102">ISymUnmanagedMethod::GetSequencePointCount Metodu</span><span class="sxs-lookup"><span data-stu-id="e51b5-102">ISymUnmanagedMethod::GetSequencePointCount Method</span></span>
<span data-ttu-id="e51b5-103">Bu yöntem içinde sıralama noktaları sayısını alır.</span><span class="sxs-lookup"><span data-stu-id="e51b5-103">Gets the count of sequence points within this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e51b5-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="e51b5-104">Syntax</span></span>  
  
```  
HRESULT GetSequencePointCount(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e51b5-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="e51b5-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="e51b5-106">[out] Bir işaretçi bir `ULONG32` sıralama noktaları içermesi gerekir arabellek boyutunu alır.</span><span class="sxs-lookup"><span data-stu-id="e51b5-106">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the sequence points.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e51b5-107">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="e51b5-107">Return Value</span></span>  
 <span data-ttu-id="e51b5-108">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="e51b5-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e51b5-109">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="e51b5-109">Requirements</span></span>  
 <span data-ttu-id="e51b5-110">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e51b5-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e51b5-111">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="e51b5-111">See Also</span></span>  
 [<span data-ttu-id="e51b5-112">Isymunmanagedmethod arabirimi</span><span class="sxs-lookup"><span data-stu-id="e51b5-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)