---
title: .NET Framework 4.5 için Windows Communication Foundation Sözlüğü
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], glossary
- WCF [WCF], glossary
ms.assetid: 39cd36f4-8a28-4d0b-a830-98d55c9d30ae
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 76cc8f456701d65b675ce7b89436da5213ea9430
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/26/2018
---
# <a name="windows-communication-foundation-glossary-for-net-framework-45"></a>.NET Framework 4.5 için Windows Communication Foundation Sözlüğü
Aşağıdaki terimler Windows Communication Foundation belgelerine tanımlanır.  
  
## <a name="terms"></a>Koşulları  
  
|Terim|Tanım|  
|----------|----------------|  
|adres|Burada iletileri alınan konumunu belirtir. Bir Tekdüzen Kaynak Tanımlayıcısı (URI) olarak belirtilir. URI şeması bölümü HTTP ve TCP gibi adresine erişmek için kullanılacak aktarım mekanizması adları. URI hiyerarşik parçası biçimini bir aktarım mekanizması bağımlı benzersiz bir konuma içerir.|  
|Uygulama uç noktası|Uygulama ve, tarafından kullanıma sunulan bir uç nokta uygulaması tarafından uygulanan bir hizmet sözleşmesini karşılık gelir.|  
|davranış|Bir hizmeti, bir uç nokta, belirli bir işlem veya bir istemci çeşitli çalışma zamanı yönlerini denetleyen bir bileşen bir davranıştır. Davranışları kapsam göre gruplandırılır: ortak davranışları etkileyen tüm uç noktaları genel olarak, hizmet davranışları etkiler yalnızca hizmeti ile ilgili konuları, uç nokta davranışları etkileyen yalnızca uç noktası ile ilgili özellikler ve işlem düzeyi davranışları etkileyen belirli işlemler.|  
|bağlama|Hangi iletişim protokolleri WCF hizmetleri ile iletişim kurmak için kullanılacağını tanımlar. Bir iletişim altyapısı oluşturmak için diğer üstünde yığın bağlama öğeleri adlı bileşenler kümesinin oluşturulur.  Uç nokta bakın.|  
|Kanal|Bir bağlama öğesi somut bir uygulamasıdır. Bağlama yapılandırmasını temsil eder ve kanal bu yapılandırmasıyla ilişkili uygulamasıdır. Bu nedenle her bağlama öğesi ile ilişkili bir kanalı yok. Kanal bağlama somut uygulaması oluşturmak için birbirinin yığın: kanal yığını.|  
|Talep tabanlı güvenlik|Yetkili talepleri temelinde korumalı kaynaklara erişmesini sağlar.|  
|istemci uygulaması|Bir istemci uygulaması, bir veya daha fazla uç noktaları iletileri alış verişleri bir programdır. İstemci uygulaması, WCF istemcisi örneği oluşturma ve WCF istemcisini yöntemleri çağırma başlar. Tek bir uygulama hem istemci hem de bir hizmet olabilir dikkate almak önemlidir.|  
|kodlama|Hizmet veya istemci bileşenlerinin tümünü üzerinde tam denetimi korumak Geliştirici sağlar ve yapılandırma aracılığıyla yapılan herhangi bir ayarı Denetlenmekte ve gerekirse kod tarafından geçersiz kılındı. Denetim bir uygulama ya da aracılığıyla, yapılandırma, veya ikisinin birleşimi yoluyla kodlama yapılabilir.|  
|yapılandırma|Yapılandırma birisi kodu yazıldıktan sonra istemci ve hizmet parametrelerini ayarlamak için (örneğin, bir ağ yöneticisi) Geliştirici dışındaki ve yeniden derleyin gerek kalmadan izin vererek avantajına sahiptir. Yapılandırma yalnızca, uç nokta adresleri gibi değerlerini ayarlamak sağlar, ancak aynı zamanda uç noktaları, bağlamaları ve davranışları eklemenize olanak sağlayarak daha fazla denetim sağlar. Bir uygulama denetim aracılığıyla ya da yapılandırma, kodlama aracılığıyla veya her ikisinin birleşimini aracılığıyla yapılabilir.|  
|Sözleşme|Bir sözleşme belirli tür bu sözleşme için destek belirtimidir. Bir hizmet sözleşmesi, örneğin, işlemlerinin bir grup için bir özelliğidir. WCF'de, sözleşmeleri System.ServiceModel.Description ad alanında bulunan tanım nesnelerindeki yansıtılmış bir hiyerarşiye sahip. Hizmet sözleşmesi en büyük WCF sözleşmesi kapsamında ' dir. Her hizmet işlemi bir hizmet sözleşmesinde işlemi alışverişi iletileri--dahil olmak üzere hata iletileri--belirtir, bir işlem sözleşmesi sahiptir ve hangi yönde. Her ileti bir işlemde belirtimi SOAP iletisi Zarf yapısı için bir ileti sözleşmesi ve her ileti sözleşmesi iletilerinde yer alan veri yapılarını belirten bir veri sözleşmesi sahiptir.|  
|veri sözleşmesi|Veri kullanan diğer hizmet ile birlikte çalışmak üzere etkinleştirmek için meta veri açıklanan hizmet türleri. Veri türlerinin açıklamaları veri sözleşmesi bilinir ve türleri dönüş türleri veya herhangi bir kısmını bir ileti Örneğin, parametre olarak kullanılabilir. Yalnızca basit türler hizmeti kullanıyorsanız, veri sözleşmeleri açıkça kullanmaya gerek yoktur.|  
|bildirim temelli uygulama|Çalışma zamanında kesinlik temelli yönergeleri çalıştırmadan oluşturulması için yeterince açıklanan uygulama.|  
|uç noktası|Bir adresi, bağlama ve bir WCF Hizmeti ile iletişim kurmak için kullanılan bir sözleşme oluşur.|  
|uç noktası adresi|Bir hizmet olarak her uç noktası için benzersiz bir uç nokta adresleri oluşturmak veya belirli koşullar altında bir adresi uç noktalar arasında paylaşmak etkinleştirir.|  
|hatalı sözleşme|Hatalı sözleşme çağırana döndürülen hatalar belirtmek için bir hizmet işlemi ile ilişkili olabilir. Bir işlem, kendisiyle ilişkilendirilmiş sıfır veya daha fazla hataları olabilir. Bu hatalar programlama modeli, özel durumlar olarak Modellenen SOAP hatalarıdır. Özel durum ardından istemciye gönderilen bir SOAP hatası dönüştürülür.|  
|barındırma|Bir hizmet bazı işleminde barındırılması gerekir. Bir ana bilgisayar hizmeti ömrü denetleyen bir uygulamadır. Hizmetleri otomatik olarak barındırılan veya varolan bir barındırma işlemi tarafından yönetiliyor.|  
|barındırma işlemi|Barındırma işlemi hizmetlerini barındırmak için tasarlanmış bir uygulamadır. Bu, Internet Information Services (IIS), Windows Etkinleştirme Hizmetleri (WAS) ve Windows Hizmetleri içerir. Barındırılan bu senaryolarda, ana bilgisayar hizmeti ömrü denetler. Örneğin, IIS kullanarak hizmet ve yapılandırma dosyasını içeren bir sanal dizin ayarlayabilirsiniz. Bir ileti alındığında, IIS hizmetini başlatır ve yaşam süresi denetler.|  
|işlemi başlatılıyor|Yeni bir oturum ilk işlem olarak adlı bir işlem. Olmayan başlatma işlemlerini en az bir başlatma işlemi yalnızca çağrıldıktan sonra çağrılabilir.|  
|Model örnek oluşturma|Bir hizmet bir örneklemesini modeli vardır. Üç örneklemesini modeli vardır: &quot;tek&quot; tek bir CLR nesnesi tüm istemciler için; Hizmetleri &quot;çağrı başına&quot; içinde her istemci çağrısını; işlemek için yeni bir CLR nesnesi oluşturulur ve &quot;oturumu başına&quot; CLR kümesi oluşturulur, ayrı her oturum için bir tane nesneleri içinde. Uygulama gereksinimleri ve beklediğiniz kullanım modelini hizmetinin örneklemesini model seçimi bağlıdır.|  
|iletisi|İleti gövde ve üstbilgileri dahil çeşitli bölümlerini oluşabilir veri kendi içinde bulunan bir birimdir.|  
|ileti sözleşmesi|İleti sözleşmesi bir ileti biçimi açıklar. Örneğin, ileti öğeleri gövdesi karşı üstbilgilerindeki gitmesi gereken olup olmadığını hangi güvenlik düzeyini ileti ve benzeri hangi öğelerine uygulanan bildirir.|  
|ileti güvenlik modu|Bir veya daha fazla güvenlik belirtimleri uygulayarak, güvenlik sağladığınız ileti güvenlik modunu belirtir. Her ileti, aktarım sırasında güvenliği sağlamak için ve izinsiz algılamak ve iletilerin şifresini çözmek için alıcıları etkinleştirmek için gerekli mekanizmalar içerir. Bu anlamda güvenlik birden çok atlama arasında uçtan uca güvenlik sağlayan her ileti içinde kapsüllenir. Güvenlik bilgileri iletinin bir parçası haline gelir olduğundan, ayrıca kimlik bilgileri (bunlar talepler olarak adlandırılır) ve ileti birden çok türde dahil etmek mümkündür. Bu yaklaşım, ayrıca kaynak ve hedef arasındaki birden çok aktarımı dahil olmak üzere herhangi bir aktarım üzerinden güvenli bir şekilde hareket etmek ileti etkinleştirme avantajına sahiptir. Bu yaklaşımın bir dezavantajı performans etkileri kaynaklanan işe, şifreleme mekanizmaları karmaşıklığını ' dir.|  
|meta veriler|Bir hizmeti meta verilerini bir dış varlık hizmetiyle iletişim kurmak için anlamanız gereken hizmet özelliklerini açıklar. Meta veri ServiceModel meta veri yardımcı Programracı (Svcutil.exe bir WCF istemcisi ve bir istemci uygulaması hizmetiyle etkileşim kurmak için kullanabileceğiniz eşlik eden yapılandırma oluşturmak için) tarafından kullanılabilecek.  Hizmet tarafından kullanıma sunulan meta veri hizmetinin veri sözleşmesi tanımlayın, XML Şeması belgeleri ve hizmet yöntemleri açıklayan WSDL belgelerini içerir.  Etkinleştirildiğinde, hizmet için meta verileri otomatik olarak WCF tarafından hizmet ve kendi uç noktaları inceleyerek oluşturulur. Bir hizmeti meta verilerini yayımlamak için meta veri davranışı açıkça etkinleştirmelisiniz.|  
|işlem Sözleşmesi|Bir işlem sözleşmesi parametreler ve dönüş türü bir işlemi tanımlar. Hizmet sözleşmesini tanımlayan bir arabirim oluştururken, bir işlem sözleşmesi sözleşmesinin bir parçası olan her yöntem tanımını T:System.ServiceModel.OperationContractAttribute özniteliği uygulayarak türünü belirtir. İşlemler, tek bir ileti alma ve tek bir ileti döndürerek veya türleri kümesi alma ve bir tür döndüren olarak modellenebilir. İkinci durumda, sistem, bu işlem için alınıp verilen iletileri biçimini belirler.|  
|Yansıtma|Kablo verileri gösterimi. Örneğin, bir SOAP projeksiyon SOAP Zarflar iletileri gönderir ve bir Web projeksiyonu JSON biçiminde iletileri gönderir.|  
|güvenlik|WCF güvenliğinde gizliliği (şifreleme gizlice Dinlemenin önlenmesi iletilerinin), bütünlük (anlamına gelir iletiyle oynama algılanamadı için), kimlik doğrulama (anlamına gelir sunucularını ve istemcilerini doğrulanması için) ve yetkilendirme (denetimi içerir kaynaklara erişim). Bu işlevler ya da yararlanmayı mevcut güvenlik mekanizmaları, HTTP (HTTPS olarak da bilinir) üzerinden TLS gibi veya bir veya daha fazlasını çeşitli WS - uygulama tarafından sağlanan * güvenlik özellikleri.|  
|kendini barındıran hizmet|Kendini barındıran hizmet Geliştirici oluşturulan işlem uygulama içinde çalışan biridir. Geliştirici yaşam denetimleri, hizmet özelliklerini ayarlar, (dinleme moduna ayarlar) hizmetini açar ve hizmet kapatır.|  
|hizmet|Bir program veya bir ya da daha fazla işlem gösterme her uç noktası ile bir veya daha fazla uç sunan işlemi.|  
|service contract|Hizmet sözleşmesi birden fazla ilgili işlemlerini tek bir işlev birime birbirine bağlar. Sözleşme ad alanı hizmeti, karşılık gelen bir geri çağırma sözleşme ve diğer tür ayarları gibi hizmet düzeyi ayarlarını tanımlayabilirsiniz. Çoğu durumda, sözleşmenin tercih ettiğiniz programlama dilinde bir arabirim oluşturma ve T:System.ServiceModel.ServiceContractAttribute özniteliği arabirimine uygulama tarafından tanımlanır. Arabirimi uygulama tarafından gerçek hizmet kod sonuçları.|  
|hizmet işlemi|Bir hizmet işlemi, bir işlem işlevselliğini hayata geçiren bir hizmetin kodda tanımlanan bir yordamdır. Bu işlem, istemcilere bir WCF istemcisi yöntemi olarak sunulur. Yöntemi bir değer döndürmesi isteğe bağlı bir bağımsız değişken sayısı alın veya bağımsız değişkenler almayan ve bir yanıt döndürür. Örneğin, olarak işlev bir işlem bir &quot;Hello&quot; bildirim bir istemcinin varlık ve işlemleri, bir dizi başlamaya olarak kullanılabilir.|  
|sistem tarafından sağlanan bağlamalar|WCF sistem tarafından sağlanan bağlamalar sayısını içerir. Bu bağlama belirli senaryolar için iyileştirilen öğelerinin koleksiyonlarıdır. Örneğin, T:System.ServiceModel.WSHttpBinding çeşitli WS - uygulama hizmetleri ile birlikte çalışabilirlik için tasarlanmış * belirtimleri. Bu bağlamaları, yalnızca belirli bir senaryoyu doğru uygulanabilir seçenekleri sunarak zaman kazandırır. Bu bağlamaların bir tanesini gereksinimlerinizi karşılamıyorsa, kendi özel bağlama oluşturabilirsiniz.|  
|işlem sonlandırma|En son iletinin varolan bir oturumda adlı bir işlem. Hizmet ilişkili oturum kapatıldıktan sonra varsayılan durumda, WCF Hizmeti nesnesi ve onun bağlamı geri dönüştürür.|  
|Aktarım güvenlik modu|Üç modlarından birini güvenliği sağlanabilir: aktarım modu, ileti güvenlik modu ve ileti kimlik bilgisi modu ile aktarma. Gizlilik, bütünlük ve kimlik doğrulaması için Aktarım katmanı mekanizmaları (Örneğin HTTPS) tarafından sağlanan transport güvenlik modunu belirtir. HTTPS gibi bir aktarım kullanırken bu modda kendi yaygınlığını Internet'te nedeniyle verimli, performans ve iyi anlaşılan olma avantajına sahiptir. Bu tür bir güvenlik iletişim açıktır. yapmadan iletişim yolundaki her atlama üzerinde ayrı olarak uygulandığını olumsuz olduğu bir &quot;ortadaki adam&quot; saldırı.|  
|ileti kimlik bilgileri güvenlik moduyla taşıma|Bu mod Aktarım katmanı her iletileri ileti alıcı tarafından birden çok kimlik bilgileri gerekli (talep) içerebilir ancak gizlilik, kimlik doğrulama ve iletileri bütünlüğünü sağlamak için kullanır.|  
|tür dönüştürücü|Veya daha fazla System.ComponentModel.TypeConverter için ve diğer türleri örneklerini CLR türünün dönüştürme örnekleri sağlayan türler türetilmiş bir CLR türü ile ilişkili olabilir. Tür converterr System.ComponentModel.TypeConverterAttribute özniteliğini kullanarak bir CLR türü ile ilişkilidir.  Bir TypeConverterAttribute doğrudan CLR türü veya bir özellik belirtilebilir. Bir özellik her zaman belirtilen tür dönüştürücüsünü özelliğin CLR türü üzerinde belirtilen tür dönüştürücüsünü daha önceliklidir.|  
|WCF istemcisi|Bir WCF istemcisi hizmet işlemleri yöntemleri (Visual Basic veya Visual C# gibi tercih ettiğiniz .NET Framework programlama dili) olarak kullanıma sunan bir istemci uygulaması yapıdır. Herhangi bir uygulama, bir hizmeti barındıran bir uygulama da dahil olmak üzere bir WCF istemcisi barındırabilir. Bu nedenle, diğer hizmetlerin WCF istemcileri içeren bir hizmet oluşturmak mümkündür.  Bir WCF istemcisi ServiceModel meta veri yardımcı Programracı (Svcutil.exe) kullanarak ve meta verilerini yayımlayan bir çalışan hizmetine işaret eden otomatik olarak oluşturulabilir.|  
|İş akışı Hizmetleri|İş akışı olarak uygulanan bir WCF hizmeti bir iş akışı hizmetidir. İş akışı gönderebilir ve/veya WCF iletilerini Mesajlaşma etkinlikleri içerir.|  
|WS-*|WCF'de uygulanan Web hizmeti (WS) özellikleri, WS-Security, WS-ReliableMessaging ve vb. gibi büyüyen kümesi için toplu özelliktir.|  
|XAML|Genişletilebilir uygulama biçimlendirme dili|  
|XAML şema|XAML'de custome türlerini tanımlamak için kullanılan biçimlendirme bir şema.|
