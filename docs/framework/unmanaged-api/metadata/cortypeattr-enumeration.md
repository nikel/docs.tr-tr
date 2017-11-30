---
title: "CorTypeAttr Numaralandırması"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorTypeAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorTypeAttr
helpviewer_keywords: CorTypeAttr enumeration [.NET Framework metadata]
ms.assetid: 9bede0ec-5fdf-42a2-b5b7-bee64056acb6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ab9ce555406dfeb16f99601e6b88af2395c91ae0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="cortypeattr-enumeration"></a><span data-ttu-id="411a4-102">CorTypeAttr Numaralandırması</span><span class="sxs-lookup"><span data-stu-id="411a4-102">CorTypeAttr Enumeration</span></span>
<span data-ttu-id="411a4-103">Tür meta veri gösteren değerler içeriyor.</span><span class="sxs-lookup"><span data-stu-id="411a4-103">Contains values that indicate type metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="411a4-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="411a4-104">Syntax</span></span>  
  
```  
typedef enum CorTypeAttr {  
  
    tdVisibilityMask        =   0x00000007,  
    tdNotPublic             =   0x00000000,  
    tdPublic                =   0x00000001,  
    tdNestedPublic          =   0x00000002,  
    tdNestedPrivate         =   0x00000003,  
    tdNestedFamily          =   0x00000004,  
    tdNestedAssembly        =   0x00000005,  
    tdNestedFamANDAssem     =   0x00000006,  
    tdNestedFamORAssem      =   0x00000007,  
  
    tdLayoutMask            =   0x00000018,  
    tdAutoLayout            =   0x00000000,  
    tdSequentialLayout      =   0x00000008,  
    tdExplicitLayout        =   0x00000010,  
  
    tdClassSemanticsMask    =   0x00000020,  
    tdClass                 =   0x00000000,  
    tdInterface             =   0x00000020,  
  
    tdAbstract              =   0x00000080,  
    tdSealed                =   0x00000100,  
    tdSpecialName           =   0x00000400,  
  
    tdImport                =   0x00001000,  
    tdSerializable          =   0x00002000,  
    tdWindowsRuntime        =   0x00004000,  
  
    tdStringFormatMask      =   0x00030000,  
    tdAnsiClass             =   0x00000000,  
    tdUnicodeClass          =   0x00010000,  
    tdAutoClass             =   0x00020000,  
    tdCustomFormatClass     =   0x00030000,  
    tdCustomFormatMask      =   0x00C00000,  
  
    tdBeforeFieldInit       =   0x00100000,  
    tdForwarder             =   0x00200000,  
  
    tdReservedMask          =   0x00040800,  
    tdRTSpecialName         =   0x00000800,  
    tdHasSecurity           =   0x00040000,  
  
} CorTypeAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="411a4-105">Üyeler</span><span class="sxs-lookup"><span data-stu-id="411a4-105">Members</span></span>  
  
|<span data-ttu-id="411a4-106">Üye</span><span class="sxs-lookup"><span data-stu-id="411a4-106">Member</span></span>|<span data-ttu-id="411a4-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="411a4-107">Description</span></span>|  
|------------|-----------------|  
|`tdVisibilityMask`|<span data-ttu-id="411a4-108">Tür görünürlüğü bilgileri kullanılır.</span><span class="sxs-lookup"><span data-stu-id="411a4-108">Used for type visibility information.</span></span>|  
|`tdNotPublic`|<span data-ttu-id="411a4-109">Tür genel kapsamda değil belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-109">Specifies that the type is not in public scope.</span></span>|  
|`tdPublic`|<span data-ttu-id="411a4-110">Türünün ortak kapsamında olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-110">Specifies that the type is in public scope.</span></span>|  
|`tdNestedPublic`|<span data-ttu-id="411a4-111">Ortak bir görünürlük türü iç içe yerleştirilmiş belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-111">Specifies that the type is nested with public visibility.</span></span>|  
|`tdNestedPrivate`|<span data-ttu-id="411a4-112">Özel bir görünürlük türü iç içe yerleştirilmiş belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-112">Specifies that the type is nested with private visibility.</span></span>|  
|`tdNestedFamily`|<span data-ttu-id="411a4-113">Türü ile ailesi görünürlük iç içe yerleştirilmiş belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-113">Specifies that the type is nested with family visibility.</span></span>|  
|`tdNestedAssembly`|<span data-ttu-id="411a4-114">Derleme bir görünürlük türü iç içe yerleştirilmiş belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-114">Specifies that the type is nested with assembly visibility.</span></span>|  
|`tdNestedFamANDAssem`|<span data-ttu-id="411a4-115">Aile ve derleme bir görünürlük türü iç içe yerleştirilmiş belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-115">Specifies that the type is nested with family and assembly visibility.</span></span>|  
|`tdNestedFamORAssem`|<span data-ttu-id="411a4-116">Aile veya derleme bir görünürlük türü iç içe yerleştirilmiş belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-116">Specifies that the type is nested with family or assembly visibility.</span></span>|  
|`tdLayoutMask`|<span data-ttu-id="411a4-117">Türü için Düzen bilgileri alır.</span><span class="sxs-lookup"><span data-stu-id="411a4-117">Gets layout information for the type.</span></span>|  
|`tdAutoLayout`|<span data-ttu-id="411a4-118">Bu tür alanları otomatik olarak düzenlenmiştir belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-118">Specifies that the fields of this type are laid out automatically.</span></span>|  
|`tdSequentialLayout`|<span data-ttu-id="411a4-119">Bu tür alanları sırayla düzenlenmiştir belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-119">Specifies that the fields of this type are laid out sequentially.</span></span>|  
|`tdExplicitLayout`|<span data-ttu-id="411a4-120">Bu alan düzeni açıkça sağlanan belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-120">Specifies that field layout is supplied explicitly.</span></span>|  
|`tdClassSemanticsMask`|<span data-ttu-id="411a4-121">Türü anlamsal bilgilerini alır.</span><span class="sxs-lookup"><span data-stu-id="411a4-121">Gets semantic information about the type.</span></span>|  
|`tdClass`|<span data-ttu-id="411a4-122">Türün bir sınıf olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-122">Specifies that the type is a class.</span></span>|  
|`tdInterface`|<span data-ttu-id="411a4-123">Türün bir arabirim olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-123">Specifies that the type is an interface.</span></span>|  
|`tdAbstract`|<span data-ttu-id="411a4-124">Türün Özet olup olmadığını belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-124">Specifies that the type is abstract.</span></span>|  
|`tdSealed`|<span data-ttu-id="411a4-125">Türü genişletilemez belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-125">Specifies that the type cannot be extended.</span></span>|  
|`tdSpecialName`|<span data-ttu-id="411a4-126">Sınıf adı özel olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-126">Specifies that the class name is special.</span></span> <span data-ttu-id="411a4-127">Adını açıklar nasıl.</span><span class="sxs-lookup"><span data-stu-id="411a4-127">Its name describes how.</span></span>|  
|`tdImport`|<span data-ttu-id="411a4-128">Türü alınır belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-128">Specifies that the type is imported.</span></span>|  
|`tdSerializable`|<span data-ttu-id="411a4-129">Türü seri hale getirilebilir olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-129">Specifies that the type is serializable.</span></span>|  
|`tdWindowsRuntime`|<span data-ttu-id="411a4-130">Bu tür gerektiğini belirten bir [!INCLUDE[wrt](../../../../includes/wrt-md.md)] türü.</span><span class="sxs-lookup"><span data-stu-id="411a4-130">Specifies that this type is a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`tdStringFormatMask`|<span data-ttu-id="411a4-131">Dizeleri nasıl kodlanmış ve biçimlendirilmiş hakkında bilgi alır.</span><span class="sxs-lookup"><span data-stu-id="411a4-131">Gets information about how strings are encoded and formatted.</span></span>|  
|`tdAnsiClass`|<span data-ttu-id="411a4-132">Bu tür bir LPTSTR ANSI olarak yorumlar belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-132">Specifies that this type interprets an LPTSTR as ANSI.</span></span>|  
|`tdUnicodeClass`|<span data-ttu-id="411a4-133">Bu tür bir LPTSTR Unicode olarak yorumlar belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-133">Specifies that this type interprets an LPTSTR as Unicode.</span></span>|  
|`tdAutoClass`|<span data-ttu-id="411a4-134">Bu tür bir LPTSTR otomatik olarak yorumlar belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-134">Specifies that this type interprets an LPTSTR automatically.</span></span>|  
|`tdCustomFormatClass`|<span data-ttu-id="411a4-135">Türü bir standart kodlama, olduğunu belirtir belirtildiği gibi `CustomFormatMask`.</span><span class="sxs-lookup"><span data-stu-id="411a4-135">Specifies that the type has a non-standard encoding, as specified by `CustomFormatMask`.</span></span>|  
|`tdCustomFormatMask`|<span data-ttu-id="411a4-136">Yerel birlikte çalışabilirliği için standart olmayan kodlama bilgilerini almak için bu maskesi kullanın.</span><span class="sxs-lookup"><span data-stu-id="411a4-136">Use this mask to get non-standard encoding information for native interop.</span></span> <span data-ttu-id="411a4-137">Bu iki BITS değerlerin anlamı, belirtilmedi.</span><span class="sxs-lookup"><span data-stu-id="411a4-137">The meaning of the values of these two bits is unspecified.</span></span>|  
|`tdBeforeFieldInit`|<span data-ttu-id="411a4-138">Türü statik bir alana erişmek için ilk deneme önce başlatılmalıdır belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-138">Specifies that the type must be initialized before the first attempt to access a static field.</span></span>|  
|`tdForwarder`|<span data-ttu-id="411a4-139">Türü dışarı belirtir ve bir tür iletici.</span><span class="sxs-lookup"><span data-stu-id="411a4-139">Specifies that the type is exported, and a type forwarder.</span></span>|  
|`tdReservedMask`|<span data-ttu-id="411a4-140">Bu bayrak ve bayrakları ortak dil çalışma zamanı tarafından dahili olarak kullanılır.</span><span class="sxs-lookup"><span data-stu-id="411a4-140">This flag and the flags below are used internally by the common language runtime.</span></span>|  
|`tdRTSpecialName`|<span data-ttu-id="411a4-141">Ortak dil çalışma zamanı adı kodlama denetleyeceğini belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-141">Specifies that the common language runtime should check the name encoding.</span></span>|  
|`tdHasSecurity`|<span data-ttu-id="411a4-142">Türü, kendisiyle ilişkilendirilmiş güvenlik olduğunu belirtir.</span><span class="sxs-lookup"><span data-stu-id="411a4-142">Specifies that the type has security associated with it.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="411a4-143">Gereksinimler</span><span class="sxs-lookup"><span data-stu-id="411a4-143">Requirements</span></span>  
 <span data-ttu-id="411a4-144">**Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="411a4-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411a4-145">**Başlık:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="411a4-145">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="411a4-146">**.NET framework sürümleri:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411a4-146">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411a4-147">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="411a4-147">See Also</span></span>  
 [<span data-ttu-id="411a4-148">Meta veri numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="411a4-148">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)