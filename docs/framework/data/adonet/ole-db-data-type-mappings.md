---
title: OLE DB veri türü eşlemeleri
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-ado
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04bcb259-59d3-4fd7-894d-4f0dd0c68069
caps.latest.revision: ''
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload:
- dotnet
ms.openlocfilehash: 407f194a8530f9b9e4241a6bdb4d26a4b891aa46
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/26/2018
---
# <a name="ole-db-data-type-mappings"></a>OLE DB veri türü eşlemeleri
Aşağıdaki tabloda oluşturulursa gösterilmektedir [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ADO ve OLE DB için .NET Framework Veri Sağlayıcısı'ndan veri türleri için türü (<xref:System.Data.OleDb>). Yazılı erişimci yöntemleri <xref:System.Data.OleDb.OleDbDataReader> da listelenir.  
  
|ADO türü|OLE DB türü|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Türü|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] yazılı erişimcisi|  
|--------------|-----------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|adBigInt|DBTYPE_I8|Int64|GetInt64()|  
|adBinary|DBTYPE_BYTES|Byte]|GetBytes()|  
|adBoolean|DBTYPE_BOOL|Boole değeri|GetBoolean()|  
|adBSTR|DBTYPE_BSTR|Dize|GetString()|  
|adChapter|DBTYPE_HCHAPTER|Üzerinden desteklenen `DataReader`. Bkz: [DataReader kullanarak veri alma](../../../../docs/framework/data/adonet/retrieving-data-using-a-datareader.md).|GetValue()|  
|adChar|DBTYPE_STR|Dize|GetString()|  
|adCurrency|DBTYPE_CY|Ondalık|GetDecimal()|  
|adDate|DBTYPE_DATE|DateTime|GetDateTime()|  
|adDBDate|DBTYPE_DBDATE|DateTime|GetDateTime()|  
|adDBTime|DBTYPE_DBTIME|DateTime|GetDateTime()|  
|adDBTimeStamp|DBTYPE_DBTIMESTAMP|DateTime|GetDateTime()|  
|adDecimal|DBTYPE_DECIMAL|Ondalık|GetDecimal()|  
|adDouble|DBTYPE_R8|Çift|GetDouble()|  
|adError|DBTYPE_ERROR|ExternalException|GetValue()|  
|adFileTime|DBTYPE_FILETIME|DateTime|GetDateTime()|  
|adGUID|DBTYPE_GUID|Guid|GetGuid()|  
|adIDispatch|DBTYPE_IDISPATCH *|Nesne|GetValue()|  
|adInteger|DBTYPE_I4|Int32|GetInt32()|  
|adUnknown|DBTYPE_IUNKNOWN *|Nesne|GetValue()|  
|adNumeric|DBTYPE_NUMERIC|Ondalık|GetDecimal()|  
|adPropVariant|DBTYPE_PROPVARIANT|Nesne|GetValue()|  
|adSingle|DBTYPE_R4|Tek|GetFloat()|  
|adSmallInt|DBTYPE_I2|Int16|GetInt16()|  
|adTinyInt|DBTYPE_I1|Bayt|GetByte()|  
|adUnsignedBigInt|DBTYPE_UI8|UInt64|GetValue()|  
|adUnsignedInt|DBTYPE_UI4|UInt32|GetValue()|  
|adUnsignedSmallInt|DBTYPE_UI2|UInt16|GetValue()|  
|adUnsignedTinyInt|DBTYPE_UI1|Bayt|GetByte()|  
|adVariant|DBTYPE_VARIANT|Nesne|GetValue()|  
|adWChar|DBTYPE_WSTR|Dize|GetString()|  
|adUserDefined|DBTYPE_UDT|Desteklenmiyor||  
|adVarNumeric|DBTYPE_VARNUMERIC|Desteklenmiyor||  
  
 \* OLE DB türleri için `DBTYPE_IUNKNOWN` ve `DBTYPE_IDISPATCH`, nesne başvurusu bir sıralanmış işaretçiyi gösterimidir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ADO.NET’te Veri Alma ve Değiştirme](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
