---
title: 'Nasıl yapılır: Bir Metin Dosyasına Yazma (C# Programlama Kılavuzu)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
caps.latest.revision: ''
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: fa6de76e3981e0f05b5b192045043422a8a912aa
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Nasıl yapılır: Bir Metin Dosyasına Yazma (C# Programlama Kılavuzu)
Bu örnekler bir metin dosyasına yazmanın çeşitli yollarını göstermektedir. İlk iki örnek statik kullanışlı yöntemler kullanın <xref:System.IO.File?displayProperty=nameWithType> herhangi her öğeye yazmak için sınıf `IEnumerable<string>` ve bir metin dosyasına bir dize. Örnek 3 veya dosyaya yazmak gibi her satır ayrı ayrı işlemek varsa bir dosyaya metin eklemek nasıl gösterir. Örnek 1-3 dosyasındaki tüm var olan içeriğin üzerine ancak örnek 4 varolan bir dosyaya metin ekleneceği gösterilmiştir.  
  
 Tüm bu örneklerde dize değişmez değerleri dosyalara yazma. Bir dosyaya yazılır Metin biçimlendirmek istediğiniz kullanırsanız <xref:System.String.Format%2A> yöntemi veya C# [dize ilişkilendirme](../../../csharp/language-reference/tokens/interpolated.md) özelliği.  
  
## <a name="example"></a>Örnek  
 [!code-csharp[csFilesandFolders#3](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-write-to-a-text-file_1.cs)]  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Aşağıdaki koşullar özel bir duruma neden olabilir:  
  
-   Dosya mevcut ve salt okunur.  
  
-   Yol adı çok uzun olabilir.  
  
-   Disk dolu olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# Programlama Kılavuzu](../../../csharp/programming-guide/index.md)  
 [Dosya sistemi ve kayıt defteri (C# programlama Kılavuzu)](../../../csharp/programming-guide/file-system/index.md)  
 [Örnek: bir koleksiyon uygulama depoya kaydedin.](http://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
