---
title: "Nasıl yapılır: COM Birlikte Çalışma Programlamada Dizin Oluşturulmuş Özellikleri Kullanma (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2538dae8f02b17a77cc1eb2798b8b38a7f1d7db2
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a>Nasıl yapılır: COM Birlikte Çalışma Programlamada Dizin Oluşturulmuş Özellikleri Kullanma (C# Programlama Kılavuzu)
*Dizin oluşturulmuş özellikleri* COM parametrelere sahip özellikleri tüketilen şeklini geliştirmek C# programlama içinde. Diğer özellikler Visual C# ' ta, birlikte özellikleri iş gibi dizine [adlandırılmış ve isteğe bağlı bağımsız değişkenler](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), yeni bir tür ([dinamik](../../../csharp/language-reference/keywords/dynamic.md)), ve [katıştırılmış türde bilgi](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), Microsoft Office programlama geliştirin.  
  
 Önceki sürümlerde, C#, yöntemleri özellikleri yalnızca Eğer erişilebilir `get` yöntemi sahip herhangi bir parametre ve `set` yöntemi tek bir değer parametresine sahip. Ancak, tüm COM özellikleri bu kısıtlamaları karşılar. Örneğin, Excel [aralığı](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.range.aspx) özelliğine sahip bir `get` aralığın adı için bir parametre gerektiren erişimcisi. Geçmişte, değil erişebilir çünkü `Range` özelliği doğrudan, sahip olduğunuz kullanmak `get_Range` yöntemi bunun yerine, aşağıdaki örnekte gösterildiği gibi.  
  
 [!code-csharp[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]  
  
 Dizinli Özellikler, bunun yerine aşağıdaki yazma olanak sağlar:  
  
 [!code-csharp[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]  
  
> [!NOTE]
>  Önceki örnekte de kullanır [isteğe bağlı bağımsız değişkenler](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) atlayın olanak tanıyan özellik `Type.Missing`.  
  
 Benzer şekilde değerini ayarlamak için `Value` özelliği bir [aralığı](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) nesne Visual C# 2008 ve daha önceki sürümlerde, iki bağımsız değişkenleri gereklidir. Bir aralık değeri türünü belirtir. isteğe bağlı bir parametre için bir bağımsız değişken sağlar. Diğer için değer sağlıyor `Value` özelliği. Aşağıdaki örnekler, bu teknikleri gösterir. Her ikisi de A1 hücrenin değerini `Name`.
  
 [!code-csharp[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]  
  
 Dizinli Özellikler, bunun yerine aşağıdaki kod yazmanıza olanak sağlar.  
  
 [!code-csharp[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]  
  
 Dizinli Özellikler kendi oluşturulamıyor. Özelliği, yalnızca mevcut Dizinli Özellikler kullanımını destekler.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod, tam bir örnek gösterilir. Office API erişen bir projeyi ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual C# özellikleri kullanarak erişim Office birlikte çalışma nesneleriyle](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).  
  
 [!code-csharp[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Adlandırılmış ve İsteğe Bağlı Bağımsız Değişkenler](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)  
 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)  
 [Tür dinamiği kullanma](../../../csharp/programming-guide/types/using-type-dynamic.md)  
 [Nasıl yapılır: Office Programlamada Adlandırılmış ve İsteğe Bağlı Bağımsız Değişkenleri Kullanma](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md)  
 [Nasıl yapılır: Visual C# Özelliklerini Kullanarak Office Birlikte Çalışma Nesnelerine Erişim](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)  
 [İzlenecek yol: Office programlama](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)
