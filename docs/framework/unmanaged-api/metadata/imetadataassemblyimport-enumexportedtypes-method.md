---
title: "IMetaDataAssemblyImport::EnumExportedTypes Yöntemi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumExportedTypes
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 76c73cc3d13089b4a38a47d523d8baa77f6eed12
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="fb785-102">IMetaDataAssemblyImport::EnumExportedTypes Yöntemi</span><span class="sxs-lookup"><span data-stu-id="fb785-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="fb785-103">Derleme bildirimi geçerli meta veri kapsamında başvurulan dışarı aktarılan türlerini numaralandırır.</span><span class="sxs-lookup"><span data-stu-id="fb785-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb785-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="fb785-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb785-105">Parametreler</span><span class="sxs-lookup"><span data-stu-id="fb785-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="fb785-106">[içinde out] Numaralayıcı gösteren bir işaretçi.</span><span class="sxs-lookup"><span data-stu-id="fb785-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="fb785-107">Bu bir null olmalıdır değeri `EnumExportedTypes` yöntemi ilk kez çağrılır.</span><span class="sxs-lookup"><span data-stu-id="fb785-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="fb785-108">[out] Numaralandırması `mdExportedType` meta veri belirteçleri.</span><span class="sxs-lookup"><span data-stu-id="fb785-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="fb785-109">[in] En fazla sayısını `mdExportedType` yerleştirilebilir belirteçleri `rExportedTypes` dizi.</span><span class="sxs-lookup"><span data-stu-id="fb785-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="fb785-110">[out] Sayısı `mdExportedType` belirteçleri gerçekten yerleştirilen `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="fb785-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb785-111">Dönüş Değeri</span><span class="sxs-lookup"><span data-stu-id="fb785-111">Return Value</span></span>  
  
|<span data-ttu-id="fb785-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fb785-112">HRESULT</span></span>|<span data-ttu-id="fb785-113">Açıklama</span><span class="sxs-lookup"><span data-stu-id="fb785-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="fb785-114">`EnumExportedTypes`başarıyla döndürüldü.</span><span class="sxs-lookup"><span data-stu-id="fb785-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="fb785-115">Numaralandırılacak hiçbir belirteçleri vardır.</span><span class="sxs-lookup"><span data-stu-id="fb785-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="fb785-116">Bu durumda, `pcTokens` sıfır olarak ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="fb785-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fb785-117">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="fb785-117">Requirements</span></span>  
 <span data-ttu-id="fb785-118">**Platform:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb785-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb785-119">**Başlık:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="fb785-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb785-120">**Kitaplığı:** MsCorEE.dll kaynak olarak kullanılır</span><span class="sxs-lookup"><span data-stu-id="fb785-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb785-121">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb785-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb785-122">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fb785-122">See Also</span></span>  
 [<span data-ttu-id="fb785-123">Imetadataassemblyımport arabirimi</span><span class="sxs-lookup"><span data-stu-id="fb785-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)