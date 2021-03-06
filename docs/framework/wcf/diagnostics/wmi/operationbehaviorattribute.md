---
title: OperationBehaviorAttribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 63824ae2171053bee2af204e748a6fa811f2ba82
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="operationbehaviorattribute"></a>OperationBehaviorAttribute
OperationBehaviorAttribute  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a>Yöntemler  
 OperationBehaviorAttribute sınıfı herhangi bir yöntem tanımlamıyor.  
  
## <a name="properties"></a>Özellikler  
 OperationBehaviorAttribute sınıfı aşağıdaki özelliklere sahiptir:  
  
### <a name="autodisposeparameters"></a>AutoDisposeParameters  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 Parametreler için otomatik dispose özellik durumu.  
  
### <a name="impersonation"></a>Kimliğe bürünme  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 İşlemin desteklediği arayan kimliğe bürünme düzeyini gösterir.  
  
### <a name="releaseinstancemode"></a>OperationBehaviorAttribute üstündeki ReleaseInstanceMode  
 Veri türü: dize  
  
 Erişim türüne: salt okunur  
  
 Nesne geri dönüştürmek için bir işlemi başlatılması sırasında gösterir.  
  
### <a name="transactionautocomplete"></a>TransactionAutoComplete  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 İşlenmeyen özel durumlar oluşursa geçerli işlem otomatik olarak gerçekleştirmeyi gösterir.  
  
### <a name="transactionscoperequired"></a>TransactionScopeRequired  
 Veri türü: boolean  
  
 Erişim türüne: salt okunur  
  
 İşlemi bir işlem gerekli olup olmadığını gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
  
|MOF|Bildirilen Servicemodel.mof.|  
|---------|-----------------------------------|  
|Ad Alanı|İçinde tanımlanan root\ServiceModel|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
