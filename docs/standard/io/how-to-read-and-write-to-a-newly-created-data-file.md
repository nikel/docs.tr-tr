---
title: "Nasıl yapılır: Yeni Oluşturulan bir Veri Dosyasını Okuma ve Dosyaya Yazma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 04ded71a23ba4cabab0a22e0d66c1084a726d8c8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a>Nasıl yapılır: Yeni Oluşturulan bir Veri Dosyasını Okuma ve Dosyaya Yazma
<xref:System.IO.BinaryWriter> ve <xref:System.IO.BinaryReader?displayProperty=nameWithType> sınıfları, karakter dizeleri yerine verileri yazmak ve okumak için kullanılır. Aşağıdaki örnek, `Test.data` adındaki yeni ve boş bir dosya akışına verilerin nasıl yazılacağını ve bu dosya akışındaki verilerin nasıl okunacağını gösterir. Veri dosyasını geçerli dizinde oluşturduktan sonra, ilişkili <xref:System.IO.BinaryWriter> ve <xref:System.IO.BinaryReader> nesneleri oluşturulur ve <xref:System.IO.BinaryWriter> nesnesi, 0 ile 10 arasındaki tamsayıları, dosya işaretçisini dosyanın sonunda bırakan  `Test.data`'a yazmak için kullanılır. Dosya işaretçisini başlangıç noktasına geri ayarladıktan sonra <xref:System.IO.BinaryReader> nesnesi belirtilen içeriği okur.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Eğer `Test.data` geçerli dizinde zaten bulunuyorsa, bir <xref:System.IO.IOException> özel durumu oluşturulur. Özel durum oluşturmadan her zaman yeni bir dosya oluşturmak için, dosya akışını başlatırken <xref:System.IO.FileMode.Create?displayProperty=nameWithType> dosya modu seçeneğini kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [Nasıl yapılır: Dizinleri ve Dosyaları Numaralandırma](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [Nasıl yapılır: Günlük Dosyasını Açma ve Sonuna Ekleme](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [Nasıl yapılır: Dosyadan Metin Okuma](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [Nasıl yapılır: Bir Dosyaya Metin Yazma](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [Nasıl yapılır: Dizeden Karakterleri Okuma](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [Nasıl yapılır: Bir Dizeye Karakter Yazma](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [Dosya ve akış t-O](../../../docs/standard/io/index.md)
