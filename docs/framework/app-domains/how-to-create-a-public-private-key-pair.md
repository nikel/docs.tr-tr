---
title: "Nasıl yapılır: bir genel-özel anahtar çifti oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- key pairs for strong-named assemblies
- signing assemblies
- assemblies [.NET Framework], signing
- cryptographic key pairs
- snk files (key pair files)
- public-private key pairs
- .snk files
- strong-named assemblies, key pairs
ms.assetid: 05026813-f3bd-4d7c-9e0b-fc588eb3d114
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b8076f5ed713c88f8f538959855408a8c542705a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-public-private-key-pair"></a>Nasıl yapılır: bir genel-özel anahtar çifti oluşturma
Derlemeyi tanımlayıcı adla imzalamak için ortak/özel anahtar çifti olmalıdır. Bu ortak ve özel şifreleme anahtar çiftinin derleme sırasında kesin adlandırılmış bir derleme oluşturmak için kullanılır. Kullanarak bir anahtar çifti oluşturma [tanımlayıcı ad Aracı (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md). Anahtar çifti dosyaları genellikle .snk uzantısına sahiptir.  
  
> [!NOTE]
>  İçinde [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], C# ve Visual Basic proje özellik sayfalarını içeren bir **imzalama** , var olan anahtar dosyaları seçmek veya Sn.exe kullanmadan yeni anahtar dosyaları oluşturmak için sağlar sekmesi. Visual C++'da, var olan bir anahtar dosyasının konumunu belirtebilirsiniz **Gelişmiş** özellik sayfasında **bağlayıcı** bölümünü **yapılandırma özellikleri** bölümü **Özellik sayfaları** penceresi. Kullanımını <xref:System.Reflection.AssemblyKeyFileAttribute> anahtar dosyası çiftleri tanımlamak için öznitelik eski başlayarak sağlandıktan [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)].  
  
### <a name="to-create-a-key-pair"></a>Bir anahtar çifti oluşturmak için  
  
1.  Komut satırında, aşağıdaki komutu yazın:  
  
     **sn – k** \< *dosya adı*>  
  
     Bu komutta *dosya adı* anahtar çiftini içeren çıkış dosyasının adıdır.  
  
 Aşağıdaki örnek adlı bir anahtar çifti oluşturur `sgKey.snk`.  
  
```  
sn -k sgKey.snk  
```  
  
 Bir anahtar çifti oluşturmak ve sonra ortak anahtarı buradan ayrı bir dosyaya ayıklamak için oturum bütünleştirilmiş gecikme istiyorsanız ve (hangi test senaryoları olası değil) tüm anahtar çifti denetlemek, kullanabileceğiniz aşağıdaki komutları. İlk olarak, anahtar çifti oluşturun:  
  
```  
sn -k keypair.snk  
```  
  
 Ardından, ortak anahtarın anahtar çifti ayıklamak ve ayrı bir dosyaya kopyalayın:  
  
```  
sn -p keypair.snk public.snk  
```  
  
 Anahtar çiftini oluşturduktan sonra Araçlar imzalama güçlü ad bulabileceğiniz bir yerde dosya konulmalıdır.  
  
 Güçlü bir ada sahip bir derleme imzalarken [derleme bağlayıcı (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) geçerli dizin ve çıktı dizinine göreli dosya anahtarı arar. Komut satırı derleyicileri kullanırken, yalnızca kod modülleri içeren geçerli dizin anahtarı kopyalayabilirsiniz.  
  
 Önceki bir sürümünü kullanıyorsanız, [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] , yok bir **imzalama** sekmesi proje özelliklerinde önerilen anahtar dosyası konumu proje gibi belirtilen dosya özniteliği ile dizindir:  
  
 [!code-cpp[AssemblyName_KeyPair#21](../../../samples/snippets/cpp/VS_Snippets_CLR/AssemblyName_KeyPair/CPP/keyfileattrib.cpp#21)]
 [!code-csharp[AssemblyName_KeyPair#21](../../../samples/snippets/csharp/VS_Snippets_CLR/AssemblyName_KeyPair/CS/keyfileattrib.cs#21)]
 [!code-vb[AssemblyName_KeyPair#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AssemblyName_KeyPair/VB/keyfileattrib.vb#21)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kesin Adlandırılmış Bütünleştirilmiş Kodlar Oluşturma ve Kullanma](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
