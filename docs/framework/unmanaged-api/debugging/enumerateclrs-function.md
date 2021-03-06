---
title: "EnumerateCLRs İşlevi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- EnumerateCLRs
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6539b471d6a3075bb4cec69b382cf7702a439d5a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="enumerateclrs-function"></a>EnumerateCLRs İşlevi
Bir işlemde CLRs numaralandırma için bir mekanizma sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `debuggeePID`  
 [in] Yüklenen CLRs Numaralandırılacak işleminin işlem tanıtıcısı.  
  
 `ppHandleArrayOut`  
 [out] Bir CLR başlatma devam etmek için kullanılan olay tanıtıcıları içeren bir dizi işaretçi. Dizideki her tanıtıcı geçerli olması garanti edilmez. Geçerli işleme devam başlangıç olayı olarak aynı dizinde bulunan karşılık gelen çalışma zamanı için kullanılmak üzere olup olmadığını `ppStringArrayOut`.  
  
 `ppStringArrayOut`  
 [out] CLRs tam yollarını belirtin bir dizeler dizisi işaretçisine işlemde yüklü.  
  
 `pdwArrayLengthOut`  
 [out] İşaretçi eşit boyutta uzunluğunu içeren DWORD `ppHandleArrayOut` ve `pdwArrayLengthOut`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 S_OK  
 İşlem CLRs sayısında başarıyla belirlendi ve karşılık gelen tanıtıcısı ve yol dizileri düzgün doldurulmuş.  
  
 E_INVALIDARG  
 Ya da `ppHandleArrayOut` veya `ppStringArrayOut` null, veya `pdwArrayLengthOut` null.  
  
 E_OUTOFMEMORY  
 İşlev işleyici ve yol diziler için yeterli bellek ayıramıyor.  
  
 E_FAIL (veya diğer E_ dönüş kodları)  
 Yüklenen CLRs numaralandırılamadı.  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından tanımlanan bir hedef işleminin `debuggeePID`, işlevi yolları, bir dizi döndürür `ppStringArrayOut`, işlemde yüklü CLRs; bir dizi olay işleyicilerini `ppHandleArrayOut`, hangi içerebilir devam startup olayı aynı dizinde; CLR için ve diziler boyutunu `pdwArrayLengthOut`, yüklenen CLRs sayısını belirtir.  
  
 Windows işletim sisteminde `debuggeePID` eşlemeleri bir işletim sistemi için işlem tanıtıcısı.  
  
 Bellek için `ppHandleArrayOut` ve `ppStringArrayOut` bu işlev tarafından ayrılır. Ayrılan bellek boşaltmak için çağırmalısınız [CloseCLREnumeration işlevi](../../../../docs/framework/unmanaged-api/debugging/closeclrenumeration-function.md).  
  
 Bu işlev hedef işleminde CLRs sayısını döndürmek için sıfıra ayarlayın dizi parametrelerinin her ikisini de ile çağrılabilir. Bu sayı çağıran oluşturulacak arabellek boyutu çıkarımını: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Platformlar:** bkz [sistem gereksinimleri](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Başlık:** dbgshim.h  
  
 **Kitaplığı:** dbgshim.dll  
  
 **.NET framework sürümleri:** 3.5 SP1
