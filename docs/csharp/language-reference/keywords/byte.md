---
title: "byte (C# Başvurusu)"
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- byte
- byte_CSharpKeyword
helpviewer_keywords: byte keyword [C#]
ms.assetid: 111f1db9-ca32-4f0e-b497-4783517eda47
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 231a491914071b1d43b5a8938e677be531726e75
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="byte-c-reference"></a><span data-ttu-id="622fc-102">byte (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="622fc-102">byte (C# Reference)</span></span>

<span data-ttu-id="622fc-103">`byte`değerleri aşağıdaki tabloda gösterildiği gibi depolayan bir tam sayı türünü gösterir.</span><span class="sxs-lookup"><span data-stu-id="622fc-103">`byte` denotes an integral type that stores values as indicated in the following table.</span></span>  
  
|<span data-ttu-id="622fc-104">Tür</span><span class="sxs-lookup"><span data-stu-id="622fc-104">Type</span></span>|<span data-ttu-id="622fc-105">Aralık</span><span class="sxs-lookup"><span data-stu-id="622fc-105">Range</span></span>|<span data-ttu-id="622fc-106">Boyut</span><span class="sxs-lookup"><span data-stu-id="622fc-106">Size</span></span>|<span data-ttu-id="622fc-107">.NET Framework türü</span><span class="sxs-lookup"><span data-stu-id="622fc-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`byte`|<span data-ttu-id="622fc-108">0-255</span><span class="sxs-lookup"><span data-stu-id="622fc-108">0 to 255</span></span>|<span data-ttu-id="622fc-109">İmzasız 8 bit tam sayı</span><span class="sxs-lookup"><span data-stu-id="622fc-109">Unsigned 8-bit integer</span></span>|<xref:System.Byte?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="622fc-110">Sabit değerler</span><span class="sxs-lookup"><span data-stu-id="622fc-110">Literals</span></span>  

 <span data-ttu-id="622fc-111">Bildirme ve başlatma bir `byte` değişken ondalık değişmez değer, onaltılık bir hazır değer atama veya (C# 7 için değişmez değer bir ikili başlayarak).</span><span class="sxs-lookup"><span data-stu-id="622fc-111">You can declare and initialize a `byte` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span> <span data-ttu-id="622fc-112">Değişmez değer tamsayı aralığı dışında ise `byte` (diğer bir deyişle, bu ise değerinden <xref:System.Byte.MinValue?displayProperty=nameWithType> veya daha büyük <xref:System.Byte.MaxValue?displayProperty=nameWithType>), bir derleme hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="622fc-112">If the integer literal is outside the range of `byte` (that is, if it is less than <xref:System.Byte.MinValue?displayProperty=nameWithType> or greater than <xref:System.Byte.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span>

<span data-ttu-id="622fc-113">Aşağıdaki örnekte, ondalık sayı olarak, onaltılık temsil 201 tamsayılar eşit ve ikili değişmez değerleri gelen örtük olarak dönüştürülür [int](../../../csharp/language-reference/keywords/int.md) için `byte` değerleri.</span><span class="sxs-lookup"><span data-stu-id="622fc-113">In the following example, integers equal to 201 that are represented as decimal, hexadecimal, and binary literals are implicitly converted from [int](../../../csharp/language-reference/keywords/int.md) to `byte` values.</span></span>    
  
[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#Byte)]  

> [!NOTE] 
> <span data-ttu-id="622fc-114">Önek kullanması `0x` veya `0X` onaltılık değişmez değeri ve öneki belirtmek için `0b` veya `0B` ikili bir hazır değer belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="622fc-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="622fc-115">Ondalık değişmez değerler, önek vardır.</span><span class="sxs-lookup"><span data-stu-id="622fc-115">Decimal literals have no prefix.</span></span>

<span data-ttu-id="622fc-116">C# 7 ile okunabilirliği artırmak birkaç özellik eklenmiştir başlatılıyor.</span><span class="sxs-lookup"><span data-stu-id="622fc-116">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="622fc-117">C# 7.0 sağlar alt çizgi karakteri kullanımını `_`, basamak ayırıcı olarak.</span><span class="sxs-lookup"><span data-stu-id="622fc-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="622fc-118">C# 7.2 verir `_` önekten sonra bir ikili ya da onaltılık değişmez değeri basamak ayırıcısı olarak kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="622fc-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="622fc-119">Ondalık bir hazır değer önde gelen bir alt çizgi olan izin verilen değil.</span><span class="sxs-lookup"><span data-stu-id="622fc-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="622fc-120">Aşağıda bazı örnekler gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="622fc-120">Some examples are shown below.</span></span>

[!code-csharp[Byte](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ByteS)]  
 
## <a name="conversions"></a><span data-ttu-id="622fc-121">Dönüşümler</span><span class="sxs-lookup"><span data-stu-id="622fc-121">Conversions</span></span>  
 <span data-ttu-id="622fc-122">Önceden tanımlanmış bir örtük dönüştürme `byte` için [kısa](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [uzun ](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [çift](../../../csharp/language-reference/keywords/double.md), veya [ondalık](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="622fc-122">There is a predefined implicit conversion from `byte` to [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), [ulong](../../../csharp/language-reference/keywords/ulong.md), [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="622fc-123">Örtük olarak sabit olmayan sayısal türler için daha büyük depolama boyutunu dönüştürülemiyor `byte`.</span><span class="sxs-lookup"><span data-stu-id="622fc-123">You cannot implicitly convert non-literal numeric types of larger storage size to `byte`.</span></span> <span data-ttu-id="622fc-124">Tam sayı türleri depolama boyutları hakkında daha fazla bilgi için bkz: [tam sayı türleri tablosu](../../../csharp/language-reference/keywords/integral-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="622fc-124">For more information on the storage sizes of integral types, see [Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md).</span></span> <span data-ttu-id="622fc-125">Örneğin, aşağıdaki iki göz önünde bulundurun `byte` değişkenleri `x` ve `y`:</span><span class="sxs-lookup"><span data-stu-id="622fc-125">Consider, for example, the following two `byte` variables `x` and `y`:</span></span>  
  
```  
byte x = 10, y = 20;  
```  
  
 <span data-ttu-id="622fc-126">Atama işlecinin sağ taraftaki aritmetik ifade değerlendiren çünkü aşağıdaki atama deyimi bir derleme hatası üretecektir `int` varsayılan olarak.</span><span class="sxs-lookup"><span data-stu-id="622fc-126">The following assignment statement will produce a compilation error, because the arithmetic expression on the right-hand side of the assignment operator evaluates to `int` by default.</span></span>  
  
```  
// Error: conversion from int to byte:  
byte z = x + y;  
```  
  
 <span data-ttu-id="622fc-127">Bu sorunu gidermek için bir atama kullanın:</span><span class="sxs-lookup"><span data-stu-id="622fc-127">To fix this problem, use a cast:</span></span>  
  
```  
// OK: explicit conversion:  
byte z = (byte)(x + y);  
```  
  
 <span data-ttu-id="622fc-128">Ancak, hedef değişkeni depolama boyutu ile aynı veya daha büyük bir depolama boyutu sahip olduğu aşağıdaki deyimleri kullanmak için mümkündür:</span><span class="sxs-lookup"><span data-stu-id="622fc-128">It is possible though, to use the following statements where the destination variable has the same storage size or a larger storage size:</span></span>  
  
```  
int x = 10, y = 20;  
int m = x + y;  
long n = x + y;  
```  
  
 <span data-ttu-id="622fc-129">Ayrıca, kayan nokta türleri için örtük dönüştürme yok yok `byte`.</span><span class="sxs-lookup"><span data-stu-id="622fc-129">Also, there is no implicit conversion from floating-point types to `byte`.</span></span> <span data-ttu-id="622fc-130">Örneğin, bir açık atama kullanılmadığı sürece aşağıdaki ifadeyi derleyici hatası oluşturur:</span><span class="sxs-lookup"><span data-stu-id="622fc-130">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```  
// Error: no implicit conversion from double:  
byte x = 3.0;   
// OK: explicit conversion:  
byte y = (byte)3.0;  
```  
  
 <span data-ttu-id="622fc-131">Aşırı yüklenmiş yöntemleri çağrılırken bir cast kullanılması gerekir.</span><span class="sxs-lookup"><span data-stu-id="622fc-131">When calling overloaded methods, a cast must be used.</span></span> <span data-ttu-id="622fc-132">Örneğin, aşağıdaki aşırı kullanan yöntemleri düşünün `byte` ve [int](../../../csharp/language-reference/keywords/int.md) Parametreler:</span><span class="sxs-lookup"><span data-stu-id="622fc-132">Consider, for example, the following overloaded methods that use `byte` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```  
public static void SampleMethod(int i) {}  
public static void SampleMethod(byte b) {}  
```  
  
 <span data-ttu-id="622fc-133">Kullanarak `byte` cast garanti doğru türde, örneğin çağrıldığından emin:</span><span class="sxs-lookup"><span data-stu-id="622fc-133">Using the `byte` cast guarantees that the correct type is called, for example:</span></span>  
  
```  
// Calling the method with the int parameter:  
SampleMethod(5);  
// Calling the method with the byte parameter:  
SampleMethod((byte)5);  
```  
  
 <span data-ttu-id="622fc-134">Karma kayan nokta türleri ve tam sayı türleri ile aritmetik ifadeler hakkında daha fazla bilgi için bkz: [float](../../../csharp/language-reference/keywords/float.md) ve [çift](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="622fc-134">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="622fc-135">Örtük sayısal dönüştürme kuralları hakkında daha fazla bilgi için bkz: [örtük sayısal dönüşümler tablosu](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="622fc-135">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="622fc-136">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="622fc-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="622fc-137">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="622fc-137">See Also</span></span>  
 <xref:System.Byte>  
 [<span data-ttu-id="622fc-138">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="622fc-138">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="622fc-139">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="622fc-139">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="622fc-140">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="622fc-140">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="622fc-141">Tam sayı türleri tablosu</span><span class="sxs-lookup"><span data-stu-id="622fc-141">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="622fc-142">Yerleşik türler tablosu</span><span class="sxs-lookup"><span data-stu-id="622fc-142">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="622fc-143">Örtük sayısal dönüşümler tablosu</span><span class="sxs-lookup"><span data-stu-id="622fc-143">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="622fc-144">Açık sayısal dönüşümler tablosu</span><span class="sxs-lookup"><span data-stu-id="622fc-144">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)