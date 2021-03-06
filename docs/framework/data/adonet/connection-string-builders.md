---
title: "Bağlantı dizesi oluşturucular"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: beec0aba34bc38ba310aa87dadeeaa4b41c82649
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/17/2018
---
# <a name="connection-string-builders"></a>Bağlantı dizesi oluşturucular
Önceki sürümlerinde [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)], derleme zamanı değerleri gerçekleşmediği, birleştirilmiş dizeyi içeren bağlantı dizeleri çalışma zamanında, yanlış bir anahtar sözcüğü oluşturulan böylece denetimi bir <xref:System.ArgumentException>. Her biri [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veri sağlayıcıları geçerli bağlantı dizeleri zor el ile yapıldığında oluşturma yapılan bağlantı dizesi anahtar için farklı bir sözdizimi desteklenir. Bu sorunu gidermek için [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] 2.0 sunulan her yeni bağlantı dizesi oluşturucular [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veri sağlayıcısı. Her bir veri sağlayıcısı devralan bir kesin türü belirtilmiş bağlantı dizesi Oluşturucu sınıf içerir <xref:System.Data.Common.DbConnectionStringBuilder>. Aşağıdaki tabloda [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] veri sağlayıcıları ve bunların ilişkili bir bağlantı dizesi Oluşturucu sınıfları.  
  
|Sağlayıcı|ConnectionStringBuilder sınıfı|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a>Bağlantı dizesi ekleme saldırıları  
 Dinamik dize birleştirme kullanıcı girişini temel alarak bağlantı dizelerini oluşturmak için kullanılan bağlantı dizesi ekleme saldırı ortaya çıkabilir. Dize doğrulanmış ve kötü amaçlı metin veya değil kaçış karakterleri değilse, bir saldırganın olası hassas verileri veya sunucudaki diğer kaynakları erişebilirsiniz. Örneğin, bir saldırganın bir noktalı virgül sağladığını ve ek bir değer ekleyerek saldırısı. Bağlantı dizesi "son bir WINS" algoritması kullanılarak ayrıştırılır ve tehlikeli giriş için meşru bir değer geçmesidir.  
  
 Bağlantı dizesi Oluşturucu sınıfları konusunda güvenilir bilgiler ortadan kaldırmak ve sözdizimi hataları ve güvenlik açıklarına karşı korumak için tasarlanmıştır. Bunlar, yöntemleri ve her veri sağlayıcısı tarafından izin verilen bilinen anahtar/değer çiftleri karşılık gelen özellikleri sağlar. Her sınıf eş anlamlıları sabit koleksiyonu tutar ve iyi bilinen bir karşılık gelen anahtar ad bir eş anlamlı çevirebilir. Denetimler için geçerli bir anahtar/değer çiftleri gerçekleştirilir ve geçersiz bir çiftinin bir özel durum oluşturur. Ayrıca, eklenen değerleri güvenli bir şekilde ele alınır.  
  
 Aşağıdaki örnekte gösterilmiştir nasıl <xref:System.Data.SqlClient.SqlConnectionStringBuilder> için eklenen ek değer işleme `Initial Catalog` ayarı.  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 Çıkış gösterir <xref:System.Data.SqlClient.SqlConnectionStringBuilder> bu doğru yeni bir anahtar/değer çifti olarak bağlantı dizesine ekleme yerine çift tırnak işaretleri ek değeri kaçış tarafından işlenen.  
  
```  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a>Yapı bağlantı dizeleri yapılandırma dosyaları  
 Belirli öğeleri, bir bağlantı dizesi önceden biliniyorsa, bunlar bir yapılandırma dosyasında depolanabilir ve tam bağlantı dizesi oluşturmak için çalışma zamanında alınan. Örneğin, veritabanının adı önceden bilinen, ancak sunucu adını değil olabilir. Veya diğer değerleri bağlantı dizesi Ekle mümkün olmaksızın çalışma zamanında bir adı ve parola sağlamak için bir kullanıcı isteyebilirsiniz.  
  
 Bir bağlantı dizesi oluşturucusu için aşırı yüklü oluşturucular birini alır bir <xref:System.String> bağımsız değişken olarak, hangi kullanıcı girişten sonra tamamlanabilir bir kısmi bağlantı dizesi sağlayabilirsiniz olanak sağlar. Kısmi bağlantı dizesini yapılandırma dosyasında depolanır ve çalışma zamanında alınır.  
  
> [!NOTE]
>  <xref:System.Configuration> Ad alanı kullanan yapılandırma dosyaları için programlı erişim sağlayan <xref:System.Web.Configuration.WebConfigurationManager> Web uygulamaları için ve <xref:System.Configuration.ConfigurationManager> Windows uygulamaları için. Bağlantı dizeleri ve yapılandırma dosyaları ile çalışma hakkında daha fazla bilgi için bkz: [bağlantı dizeleri ve yapılandırma dosyalarını](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).  
  
### <a name="example"></a>Örnek  
 Bu örnek bir yapılandırma dosyasından bir kısmi bağlantı dizesi alma ve ayarlayarak Tamamlanıyor gösterir <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A>, ve <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> özelliklerini <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Yapılandırma dosyası şu şekilde tanımlanır.  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
>  Bir başvuru ayarlamalısınız `System.Configuration.dll` projenizdeki çalıştırmak için kod.  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı Dizeleri](../../../../docs/framework/data/adonet/connection-strings.md)  
 [Gizlilik ve Veri Güvenliği](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 [ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkId=217917)
