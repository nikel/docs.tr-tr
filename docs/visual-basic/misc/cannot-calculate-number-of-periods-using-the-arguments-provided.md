---
title: "Sağlanan bağımsız değişkenler kullanılarak dönem sayısı hesaplayamıyor"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrFinancial_CannotCalculateNPer
ms.assetid: a96fed1c-73e6-4a2b-9906-0190bc3d4c3c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b915fec69e757cb9aa69a83b5c92c1af2988ac4
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cannot-calculate-number-of-periods-using-the-arguments-provided"></a>Sağlanan bağımsız değişkenler kullanılarak dönem sayısı hesaplayamıyor
Çağrı `NPer` işlevi tüm gerekli bağımsız değişkenleri içermiyor.  
  
## <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
-   Emin `Rate`, `Prnt` ve `PV` değer işlev çağrısında dahil edilir.