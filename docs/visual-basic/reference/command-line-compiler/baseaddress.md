---
title: -baseaddress
ms.date: 08/09/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3abe566e7a32a0b350a4f483df5c77fa4d003367
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="-baseaddress"></a>-baseaddress
DLL oluştururken, varsayılan taban adresi belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
-baseaddress:address  
```  
  
## <a name="arguments"></a>Arguments  
  
|Terim|Tanım|  
|---|---|  
|`address`|Gerekli. DLL için temel adres. Bu adresi bir onaltılık sayı olarak belirtilmelidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir DLL için varsayılan taban adresi belirlediği [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].  
  
 Bu adres alt sıra Word'de yuvarlanır unutmayın. Örneğin, 0x11110001 belirtirseniz, 0x11110000 için yuvarlanır.  
  
 Bir DLL için imzalama işlemini tamamlamak için kullanmak `–R` seçeneği güçlü adlandırma aracının (Sn.exe).  
  
 Hedef DLL değilse, bu seçeneği göz ardı edilir.  
  
|-Baseaddress Visual Studio IDE'de ayarlamak için|  
|---|  
|1.  Seçili bir projeyi **Çözüm Gezgini**. Üzerinde **proje** menüsünde tıklatın **özellikleri**. <br />2.  Tıklatın **derleme** sekmesi.<br />3.  **Gelişmiş**'e tıklayın.<br />4.  Değer değiştirme **DLL temel adresi:** kutusu. **Not:** **DLL temel adresi:** kutusudur salt okunur hedef DLL değilse.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic komut satırı derleyicisi](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)  
 [Örnek Derleme Komut Satırları](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Sn.exe (tanımlayıcı ad aracı)] [Sn.exe (tanımlayıcı ad aracı)](../../../framework/tools/sn-exe-strong-name-tool.md))
