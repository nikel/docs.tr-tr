---
title: "Birlikte Çalışma ETW Olayları"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interop events [.NET Framework]
- ETW, interop events (CLR)
ms.assetid: eb6eac2e-45f4-4923-a32c-38f203da66df
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 55097e38161ea5c76f4e46584241344ec5a52cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="interop-etw-events"></a><span data-ttu-id="b30a4-102">Birlikte Çalışma ETW Olayları</span><span class="sxs-lookup"><span data-stu-id="b30a4-102">Interop ETW Events</span></span>
<span data-ttu-id="b30a4-103"><a name="top"></a>Birlikte çalışma olayları Microsoft Ara dili (MSIL) saplama oluşturma ve önbelleğe alma hakkında bilgi yakalar.</span><span class="sxs-lookup"><span data-stu-id="b30a4-103"><a name="top"></a> Interop events capture information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 <span data-ttu-id="b30a4-104">Bu kategori aşağıdaki olaylar oluşur:</span><span class="sxs-lookup"><span data-stu-id="b30a4-104">This category consists of the following events:</span></span>  
  
-   [<span data-ttu-id="b30a4-105">ILStubGenerated olayı</span><span class="sxs-lookup"><span data-stu-id="b30a4-105">ILStubGenerated Event</span></span>](#ilstubgenerated_event)  
  
-   [<span data-ttu-id="b30a4-106">ILStubCacheHit olayı</span><span class="sxs-lookup"><span data-stu-id="b30a4-106">ILStubCacheHit Event</span></span>](#ilstubcachehit_event)  
  
<a name="ilstubgenerated_event"></a>   
## <a name="ilstubgenerated-event"></a><span data-ttu-id="b30a4-107">ILStubGenerated olayı</span><span class="sxs-lookup"><span data-stu-id="b30a4-107">ILStubGenerated Event</span></span>  
 <span data-ttu-id="b30a4-108">Aşağıdaki tablo düzeyi ve anahtar sözcüğü gösterir.</span><span class="sxs-lookup"><span data-stu-id="b30a4-108">The following table shows the keyword and level.</span></span> <span data-ttu-id="b30a4-109">(Daha fazla bilgi için bkz: [CLR ETW anahtar sözcükleri ve Düzeyler](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="b30a4-109">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="b30a4-110">Olay oluşturma için anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="b30a4-110">Keyword for raising the event</span></span>|<span data-ttu-id="b30a4-111">Düzey</span><span class="sxs-lookup"><span data-stu-id="b30a4-111">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b30a4-112">`InteropKeyword`(0x2000)</span><span class="sxs-lookup"><span data-stu-id="b30a4-112">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="b30a4-113">Informational(4)</span><span class="sxs-lookup"><span data-stu-id="b30a4-113">Informational(4)</span></span>|  
  
 <span data-ttu-id="b30a4-114">Aşağıdaki tabloda olay bilgilerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="b30a4-114">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b30a4-115">Olay</span><span class="sxs-lookup"><span data-stu-id="b30a4-115">Event</span></span>|<span data-ttu-id="b30a4-116">Olay Kimliği</span><span class="sxs-lookup"><span data-stu-id="b30a4-116">Event ID</span></span>|<span data-ttu-id="b30a4-117">Ne zaman oluşturulur</span><span class="sxs-lookup"><span data-stu-id="b30a4-117">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubGenerated`|<span data-ttu-id="b30a4-118">88</span><span class="sxs-lookup"><span data-stu-id="b30a4-118">88</span></span>|<span data-ttu-id="b30a4-119">MSIL saplama oluşturuldu.</span><span class="sxs-lookup"><span data-stu-id="b30a4-119">The MSIL stub has been generated.</span></span>|  
  
 <span data-ttu-id="b30a4-120">Aşağıdaki tabloda olay verilerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="b30a4-120">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b30a4-121">Alan adı</span><span class="sxs-lookup"><span data-stu-id="b30a4-121">Field name</span></span>|<span data-ttu-id="b30a4-122">Veri türü</span><span class="sxs-lookup"><span data-stu-id="b30a4-122">Data type</span></span>|<span data-ttu-id="b30a4-123">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b30a4-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b30a4-124">Modül kimliği</span><span class="sxs-lookup"><span data-stu-id="b30a4-124">ModuleID</span></span>|<span data-ttu-id="b30a4-125">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="b30a4-125">win:UInt16</span></span>|<span data-ttu-id="b30a4-126">Modül tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-126">The module identifier.</span></span>|  
|<span data-ttu-id="b30a4-127">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="b30a4-127">StubMethodID</span></span>|<span data-ttu-id="b30a4-128">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="b30a4-128">win:UInt64</span></span>|<span data-ttu-id="b30a4-129">Saplama yöntem tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-129">The stub method identifier.</span></span>|  
|<span data-ttu-id="b30a4-130">StubFlags</span><span class="sxs-lookup"><span data-stu-id="b30a4-130">StubFlags</span></span>|<span data-ttu-id="b30a4-131">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="b30a4-131">win:UInt64</span></span>|<span data-ttu-id="b30a4-132">Saplama bayrakları:</span><span class="sxs-lookup"><span data-stu-id="b30a4-132">The flags for the stub:</span></span><br /><br /> <span data-ttu-id="b30a4-133">0x1 - ters birlikte çalışabilirlik.</span><span class="sxs-lookup"><span data-stu-id="b30a4-133">0x1 - Reverse interop.</span></span><br /><br /> <span data-ttu-id="b30a4-134">0x2 - COM birlikte çalışma.</span><span class="sxs-lookup"><span data-stu-id="b30a4-134">0x2 - COM interop.</span></span><br /><br /> <span data-ttu-id="b30a4-135">0x4 - NGen.exe tarafından oluşturulan saplama.</span><span class="sxs-lookup"><span data-stu-id="b30a4-135">0x4 - Stub generated by NGen.exe.</span></span><br /><br /> <span data-ttu-id="b30a4-136">0x8 - temsilci.</span><span class="sxs-lookup"><span data-stu-id="b30a4-136">0x8 - Delegate.</span></span><br /><br /> <span data-ttu-id="b30a4-137">0x10 - değişken arrgument.</span><span class="sxs-lookup"><span data-stu-id="b30a4-137">0x10 - Variable arrgument.</span></span><br /><br /> <span data-ttu-id="b30a4-138">0x20 - yönetilmeyen Aranan.</span><span class="sxs-lookup"><span data-stu-id="b30a4-138">0x20 - Unmanaged callee.</span></span>|  
|<span data-ttu-id="b30a4-139">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="b30a4-139">ManagedInteropMethodToken</span></span>|<span data-ttu-id="b30a4-140">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="b30a4-140">win:UInt32</span></span>|<span data-ttu-id="b30a4-141">Yönetilen birlikte çalışabilirlik yöntemi için belirteci.</span><span class="sxs-lookup"><span data-stu-id="b30a4-141">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-142">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="b30a4-142">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="b30a4-143">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-143">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-144">Yönetilen birlikte çalışabilirlik yöntemi ad alanı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-144">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-145">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="b30a4-145">ManagedInteropMethodName</span></span>|<span data-ttu-id="b30a4-146">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-146">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-147">Yönetilen birlikte çalışabilirlik yöntemin adı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-147">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-148">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="b30a4-148">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="b30a4-149">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-149">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-150">Yönetilen birlikte çalışabilirlik yöntemi imzası.</span><span class="sxs-lookup"><span data-stu-id="b30a4-150">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-151">NativeMethodSignature</span><span class="sxs-lookup"><span data-stu-id="b30a4-151">NativeMethodSignature</span></span>|<span data-ttu-id="b30a4-152">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-152">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-153">Yerel yöntemi imzası.</span><span class="sxs-lookup"><span data-stu-id="b30a4-153">The native method signature.</span></span>|  
|<span data-ttu-id="b30a4-154">StubMethodSignature</span><span class="sxs-lookup"><span data-stu-id="b30a4-154">StubMethodSignature</span></span>|<span data-ttu-id="b30a4-155">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-155">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-156">Saplama yöntemi imzası.</span><span class="sxs-lookup"><span data-stu-id="b30a4-156">The stub method signature.</span></span>|  
|<span data-ttu-id="b30a4-157">StubMethodILCode</span><span class="sxs-lookup"><span data-stu-id="b30a4-157">StubMethodILCode</span></span>|<span data-ttu-id="b30a4-158">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-158">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-159">Saplama yöntemi MSIL kodu.</span><span class="sxs-lookup"><span data-stu-id="b30a4-159">The MSIL code for the stub method.</span></span>|  
|<span data-ttu-id="b30a4-160">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b30a4-160">ClrInstanceID</span></span>|<span data-ttu-id="b30a4-161">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="b30a4-161">win:UInt16</span></span>|<span data-ttu-id="b30a4-162">CLR veya CoreCLR örneği için benzersiz kimlik.</span><span class="sxs-lookup"><span data-stu-id="b30a4-162">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b30a4-163">Başa dön</span><span class="sxs-lookup"><span data-stu-id="b30a4-163">Back to top</span></span>](#top)  
  
<a name="ilstubcachehit_event"></a>   
## <a name="ilstubcachehit-event"></a><span data-ttu-id="b30a4-164">ILStubCacheHit olayı</span><span class="sxs-lookup"><span data-stu-id="b30a4-164">ILStubCacheHit Event</span></span>  
 <span data-ttu-id="b30a4-165">Aşağıdaki tablo düzeyi ve anahtar sözcüğü gösterir.</span><span class="sxs-lookup"><span data-stu-id="b30a4-165">The following table shows the keyword and level.</span></span>  
  
|<span data-ttu-id="b30a4-166">Olay oluşturma için anahtar sözcüğü</span><span class="sxs-lookup"><span data-stu-id="b30a4-166">Keyword for raising the event</span></span>|<span data-ttu-id="b30a4-167">Düzey</span><span class="sxs-lookup"><span data-stu-id="b30a4-167">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="b30a4-168">`InteropKeyword`(0x2000)</span><span class="sxs-lookup"><span data-stu-id="b30a4-168">`InteropKeyword` (0x2000)</span></span>|<span data-ttu-id="b30a4-169">Informational(4)</span><span class="sxs-lookup"><span data-stu-id="b30a4-169">Informational(4)</span></span>|  
  
 <span data-ttu-id="b30a4-170">Aşağıdaki tabloda olay bilgilerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="b30a4-170">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="b30a4-171">Olay</span><span class="sxs-lookup"><span data-stu-id="b30a4-171">Event</span></span>|<span data-ttu-id="b30a4-172">Olay Kimliği</span><span class="sxs-lookup"><span data-stu-id="b30a4-172">Event ID</span></span>|<span data-ttu-id="b30a4-173">Ne zaman oluşturulur</span><span class="sxs-lookup"><span data-stu-id="b30a4-173">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ILStubCacheHit`|<span data-ttu-id="b30a4-174">89</span><span class="sxs-lookup"><span data-stu-id="b30a4-174">89</span></span>|<span data-ttu-id="b30a4-175">MSIL önbellek erişilmedi.</span><span class="sxs-lookup"><span data-stu-id="b30a4-175">The MSIL cache has been accessed.</span></span>|  
  
 <span data-ttu-id="b30a4-176">Aşağıdaki tabloda olay verilerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="b30a4-176">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="b30a4-177">Alan adı</span><span class="sxs-lookup"><span data-stu-id="b30a4-177">Field name</span></span>|<span data-ttu-id="b30a4-178">Veri türü</span><span class="sxs-lookup"><span data-stu-id="b30a4-178">Data type</span></span>|<span data-ttu-id="b30a4-179">Açıklama</span><span class="sxs-lookup"><span data-stu-id="b30a4-179">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="b30a4-180">Modül kimliği</span><span class="sxs-lookup"><span data-stu-id="b30a4-180">ModuleID</span></span>|<span data-ttu-id="b30a4-181">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="b30a4-181">win:UInt16</span></span>|<span data-ttu-id="b30a4-182">Modül tanıtıcısı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-182">The module identifier.</span></span>|  
|<span data-ttu-id="b30a4-183">StubMethodID</span><span class="sxs-lookup"><span data-stu-id="b30a4-183">StubMethodID</span></span>|<span data-ttu-id="b30a4-184">Win: UInt64</span><span class="sxs-lookup"><span data-stu-id="b30a4-184">win:UInt64</span></span>|<span data-ttu-id="b30a4-185">Saplama yöntem tanımlayıcısı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-185">The stub method identifier.</span></span>|  
|<span data-ttu-id="b30a4-186">ManagedInteropMethodToken</span><span class="sxs-lookup"><span data-stu-id="b30a4-186">ManagedInteropMethodToken</span></span>|<span data-ttu-id="b30a4-187">Win: UInt32</span><span class="sxs-lookup"><span data-stu-id="b30a4-187">win:UInt32</span></span>|<span data-ttu-id="b30a4-188">Yönetilen birlikte çalışabilirlik yöntemi için belirteci.</span><span class="sxs-lookup"><span data-stu-id="b30a4-188">The token for the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-189">ManagedInteropMethodNameSpace</span><span class="sxs-lookup"><span data-stu-id="b30a4-189">ManagedInteropMethodNameSpace</span></span>|<span data-ttu-id="b30a4-190">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-190">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-191">Yönetilen birlikte çalışabilirlik yöntemi ad alanı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-191">The namespace of the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-192">ManagedInteropMethodName</span><span class="sxs-lookup"><span data-stu-id="b30a4-192">ManagedInteropMethodName</span></span>|<span data-ttu-id="b30a4-193">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-193">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-194">Yönetilen birlikte çalışabilirlik yöntemin adı.</span><span class="sxs-lookup"><span data-stu-id="b30a4-194">The name of the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-195">ManagedInteropMethodSignature</span><span class="sxs-lookup"><span data-stu-id="b30a4-195">ManagedInteropMethodSignature</span></span>|<span data-ttu-id="b30a4-196">Win: UnicodeString</span><span class="sxs-lookup"><span data-stu-id="b30a4-196">win:UnicodeString</span></span>|<span data-ttu-id="b30a4-197">Yönetilen birlikte çalışabilirlik yöntemi imzası.</span><span class="sxs-lookup"><span data-stu-id="b30a4-197">The signature of the managed interop method.</span></span>|  
|<span data-ttu-id="b30a4-198">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="b30a4-198">ClrInstanceID</span></span>|<span data-ttu-id="b30a4-199">Win: UInt16</span><span class="sxs-lookup"><span data-stu-id="b30a4-199">win:UInt16</span></span>|<span data-ttu-id="b30a4-200">CLR veya CoreCLR örneği için benzersiz kimlik.</span><span class="sxs-lookup"><span data-stu-id="b30a4-200">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
 [<span data-ttu-id="b30a4-201">Başa dön</span><span class="sxs-lookup"><span data-stu-id="b30a4-201">Back to top</span></span>](#top)  
  
## <a name="see-also"></a><span data-ttu-id="b30a4-202">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="b30a4-202">See Also</span></span>  
 [<span data-ttu-id="b30a4-203">CLR ETW olayları</span><span class="sxs-lookup"><span data-stu-id="b30a4-203">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)