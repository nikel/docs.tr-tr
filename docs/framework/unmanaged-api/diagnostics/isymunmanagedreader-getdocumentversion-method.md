---
title: ISymUnmanagedReader::GetDocumentVersion Metodu
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetDocumentVersion
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetDocumentVersion
helpviewer_keywords:
- GetDocumentVersion method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocumentVersion method [.NET Framework debugging]
ms.assetid: a51f1f64-e084-44c5-830c-2222da5a6bbf
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 377457fa852e1a4ae140f72d2dd83731490b81d9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetdocumentversion-method"></a><span data-ttu-id="a3aed-102">ISymUnmanagedReader::GetDocumentVersion Metodu</span><span class="sxs-lookup"><span data-stu-id="a3aed-102">ISymUnmanagedReader::GetDocumentVersion Method</span></span>
<span data-ttu-id="a3aed-103">Belirtilen belge belirtilen sürümünü alır.</span><span class="sxs-lookup"><span data-stu-id="a3aed-103">Gets the specified version of the specified document.</span></span> <span data-ttu-id="a3aed-104">Belge sürüm 1'den başlar ve belgenin kullanarak güncelleştirilir her zaman artırılır [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) yöntemi.</span><span class="sxs-lookup"><span data-stu-id="a3aed-104">The document version starts at 1 and is incremented each time the document is updated using the [UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) method.</span></span> <span data-ttu-id="a3aed-105">Varsa `pbCurrent` parametresi `true`, bu belgenin en son sürümüdür.</span><span class="sxs-lookup"><span data-stu-id="a3aed-105">If the `pbCurrent` parameter is `true`, this is the latest version of the document.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3aed-106">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="a3aed-106">Syntax</span></span>  
  
```  
HRESULT GetDocumentVersion (  
    [in]  ISymUnmanagedDocument *pDoc,  
    [out] int* version,  
    [out] BOOL* pbCurrent);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3aed-107">Parametreler</span><span class="sxs-lookup"><span data-stu-id="a3aed-107">Parameters</span></span>  
 `pDoc`  
 <span data-ttu-id="a3aed-108">[in] Belirtilen belge.</span><span class="sxs-lookup"><span data-stu-id="a3aed-108">[in] The specified document.</span></span>  
  
 `version`  
 <span data-ttu-id="a3aed-109">[out] Bir işaretçi bir değişkene belirtilen belge sürümünü alır.</span><span class="sxs-lookup"><span data-stu-id="a3aed-109">[out] A pointer to a variable that receives the version of the specified document.</span></span>  
  
 `pbCurrent`  
 <span data-ttu-id="a3aed-110">[out] Alan bir değişken için bir işaretçi `true` bu belgenin en son sürüm ise veya `false` en son sürümü değilse.</span><span class="sxs-lookup"><span data-stu-id="a3aed-110">[out] A pointer to a variable that receives `true` if this is the latest version of the document, or `false` if it isn't the latest version.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3aed-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="a3aed-111">Return Value</span></span>  
 <span data-ttu-id="a3aed-112">Yöntem başarılı olursa S_OK; Aksi takdirde E_FAIL veya başka bir hata kodu.</span><span class="sxs-lookup"><span data-stu-id="a3aed-112">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3aed-113">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="a3aed-113">Requirements</span></span>  
 <span data-ttu-id="a3aed-114">**Başlık:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a3aed-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3aed-115">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a3aed-115">See Also</span></span>  
 [<span data-ttu-id="a3aed-116">Isymunmanagedreader arabirimi</span><span class="sxs-lookup"><span data-stu-id="a3aed-116">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)