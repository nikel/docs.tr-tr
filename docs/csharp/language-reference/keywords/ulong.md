---
title: "ulong (C# Başvurusu)"
ms.date: 03/14/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ulong_CSharpKeyword
- ulong
helpviewer_keywords: ulong keyword [C#]
ms.assetid: f2ece624-837a-40cf-92c5-343e7f33397c
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2058d9f6a228b13938fe08d7e2fb11e3b9f4600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ulong-c-reference"></a><span data-ttu-id="7bc69-102">ulong (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="7bc69-102">ulong (C# Reference)</span></span>

<span data-ttu-id="7bc69-103">`ulong` Anahtar sözcüğü değerleri aşağıdaki tabloda gösterilen aralığı ve boyutu göre depolayan bir tam sayı türünü gösterir.</span><span class="sxs-lookup"><span data-stu-id="7bc69-103">The `ulong` keyword denotes an integral type that stores values according to the size and range shown in the following table.</span></span>  
  
|<span data-ttu-id="7bc69-104">Tür</span><span class="sxs-lookup"><span data-stu-id="7bc69-104">Type</span></span>|<span data-ttu-id="7bc69-105">Aralık</span><span class="sxs-lookup"><span data-stu-id="7bc69-105">Range</span></span>|<span data-ttu-id="7bc69-106">Boyut</span><span class="sxs-lookup"><span data-stu-id="7bc69-106">Size</span></span>|<span data-ttu-id="7bc69-107">.NET Framework türü</span><span class="sxs-lookup"><span data-stu-id="7bc69-107">.NET Framework type</span></span>|  
|----------|-----------|----------|-------------------------|  
|`ulong`|<span data-ttu-id="7bc69-108">0 için 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="7bc69-108">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="7bc69-109">İmzasız 64 bit tam sayı</span><span class="sxs-lookup"><span data-stu-id="7bc69-109">Unsigned 64-bit integer</span></span>|<xref:System.UInt64?displayProperty=nameWithType>|  
  
## <a name="literals"></a><span data-ttu-id="7bc69-110">Sabit değerler</span><span class="sxs-lookup"><span data-stu-id="7bc69-110">Literals</span></span>  

<span data-ttu-id="7bc69-111">Bildirme ve başlatma bir `ulong` değişken ondalık değişmez değer, onaltılık bir hazır değer atama veya (C# 7 için değişmez değer bir ikili başlayarak).</span><span class="sxs-lookup"><span data-stu-id="7bc69-111">You can declare and initialize a `ulong` variable by assigning a decimal literal, a hexadecimal literal, or (starting with C# 7) a binary literal to it.</span></span>  <span data-ttu-id="7bc69-112">Değişmez değer tamsayı aralığı dışında ise `ulong` (diğer bir deyişle, bu ise değerinden <xref:System.UInt64.MinValue?displayProperty=nameWithType> veya daha büyük <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), bir derleme hatası oluşur.</span><span class="sxs-lookup"><span data-stu-id="7bc69-112">If the integer literal is outside the range of `ulong` (that is, if it is less than <xref:System.UInt64.MinValue?displayProperty=nameWithType> or greater than <xref:System.UInt64.MaxValue?displayProperty=nameWithType>), a compilation error occurs.</span></span> 

<span data-ttu-id="7bc69-113">Aşağıdaki örnekte, ondalık sayı olarak, onaltılık temsil 7,934,076,125 tamsayılar eşit ve ikili değişmez değerler atanır `ulong` değerleri.</span><span class="sxs-lookup"><span data-stu-id="7bc69-113">In the following example, integers equal to 7,934,076,125 that are represented as decimal, hexadecimal, and binary literals are assigned to `ulong` values.</span></span>  
  
[!code-csharp[ulong](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#ULong)]  

> [!NOTE] 
> <span data-ttu-id="7bc69-114">Önek kullanması `0x` veya `0X` onaltılık değişmez değeri ve öneki belirtmek için `0b` veya `0B` ikili bir hazır değer belirtmek için.</span><span class="sxs-lookup"><span data-stu-id="7bc69-114">You use the prefix `0x` or `0X` to denote a hexadecimal literal and the prefix `0b` or `0B` to denote a binary literal.</span></span> <span data-ttu-id="7bc69-115">Ondalık değişmez değerler, önek vardır.</span><span class="sxs-lookup"><span data-stu-id="7bc69-115">Decimal literals have no prefix.</span></span> 

<span data-ttu-id="7bc69-116">C# 7 ile okunabilirliği artırmak birkaç özellik eklenmiştir başlatılıyor.</span><span class="sxs-lookup"><span data-stu-id="7bc69-116">Starting with C# 7, a couple of features have been added to enhance readability.</span></span> 
 - <span data-ttu-id="7bc69-117">C# 7.0 sağlar alt çizgi karakteri kullanımını `_`, basamak ayırıcı olarak.</span><span class="sxs-lookup"><span data-stu-id="7bc69-117">C# 7.0 allows the usage of the underscore character, `_`, as a digit separator.</span></span>
 - <span data-ttu-id="7bc69-118">C# 7.2 verir `_` önekten sonra bir ikili ya da onaltılık değişmez değeri basamak ayırıcısı olarak kullanılacak.</span><span class="sxs-lookup"><span data-stu-id="7bc69-118">C# 7.2 allows `_` to be used as a digit separator for a binary or hexadecimal literal, after the prefix.</span></span> <span data-ttu-id="7bc69-119">Ondalık bir hazır değer önde gelen bir alt çizgi olan izin verilen değil.</span><span class="sxs-lookup"><span data-stu-id="7bc69-119">A decimal literal isn't permitted to have a leading underscore.</span></span>

<span data-ttu-id="7bc69-120">Aşağıda bazı örnekler gösterilmektedir.</span><span class="sxs-lookup"><span data-stu-id="7bc69-120">Some examples are shown below.</span></span>

[!code-csharp[long](../../../../samples/snippets/csharp/language-reference/keywords/numeric-literals.cs#LongS)]  
 
 <span data-ttu-id="7bc69-121">Tamsayı değişmez değerleri türü gösterir bir sonek de içerir.</span><span class="sxs-lookup"><span data-stu-id="7bc69-121">Integer literals can also include a suffix that denotes the type.</span></span> <span data-ttu-id="7bc69-122">Sonek `UL` veya `ul` belirsizliğe sayısal sabit değer olarak tanımlayan bir `ulong` değeri.</span><span class="sxs-lookup"><span data-stu-id="7bc69-122">The suffix `UL` or `ul` unambiguously identifies a numeric literal as a `ulong` value.</span></span> <span data-ttu-id="7bc69-123">`L` Soneki gösterir bir `ulong` hazır değeri aşarsa <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bc69-123">The `L` suffix denotes a `ulong` if the literal value exceeds <xref:System.Int64.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7bc69-124">Ve `U` veya `u` soneki gösterir bir `ulong` hazır değeri aşarsa <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7bc69-124">And the `U` or `u` suffix denotes a `ulong` if the literal value exceeds <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7bc69-125">Aşağıdaki örnek kullanır `ul` uzun tamsayı belirtmek için soneki:</span><span class="sxs-lookup"><span data-stu-id="7bc69-125">The following example uses the `ul` suffix to denote a long integer:</span></span>
 
[!code-csharp[ulsuffix](../../../../samples/snippets/csharp/language-reference/keywords/numeric-suffixes.cs#2)]

<span data-ttu-id="7bc69-126">Değişmez değer bir tamsayı sonek türünü ilk değerini gösterilebilir aşağıdaki türlerde ise:</span><span class="sxs-lookup"><span data-stu-id="7bc69-126">If an integer literal has no suffix, its type is the first of the following types in which its value can be represented:</span></span> 

1. [<span data-ttu-id="7bc69-127">int</span><span class="sxs-lookup"><span data-stu-id="7bc69-127">int</span></span>](int.md)
2. [<span data-ttu-id="7bc69-128">uint</span><span class="sxs-lookup"><span data-stu-id="7bc69-128">uint</span></span>](../../../csharp/language-reference/keywords/uint.md)
3. [<span data-ttu-id="7bc69-129">uzun</span><span class="sxs-lookup"><span data-stu-id="7bc69-129">long</span></span>](long.md)
4. `ulong`

## <a name="compiler-overload-resolution"></a><span data-ttu-id="7bc69-130">Derleyici aşırı yükleme çözümü</span><span class="sxs-lookup"><span data-stu-id="7bc69-130">Compiler overload resolution</span></span>
  
 <span data-ttu-id="7bc69-131">Bir ortak soneki aşırı yüklenmiş yöntemleri çağırma ile kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7bc69-131">A common use of the suffix is with calling overloaded methods.</span></span> <span data-ttu-id="7bc69-132">Örneğin, aşağıdaki aşırı kullanan yöntemleri düşünün `ulong` ve [int](../../../csharp/language-reference/keywords/int.md) Parametreler:</span><span class="sxs-lookup"><span data-stu-id="7bc69-132">Consider, for example, the following overloaded methods that use `ulong` and [int](../../../csharp/language-reference/keywords/int.md) parameters:</span></span>  
  
```csharp  
public static void SampleMethod(int i) {}  
public static void SampleMethod(ulong l) {}  
```  
  
 <span data-ttu-id="7bc69-133">Bir sonek ile kullanarak `ulong` parametresi doğru türde, örneğin çağrıldığından emin güvence altına alır:</span><span class="sxs-lookup"><span data-stu-id="7bc69-133">Using a suffix with the `ulong` parameter guarantees that the correct type is called, for example:</span></span>  
  
```csharp  
SampleMethod(5);    // Calling the method with the int parameter  
SampleMethod(5UL);  // Calling the method with the ulong parameter  
```  
  
## <a name="conversions"></a><span data-ttu-id="7bc69-134">Dönüşümler</span><span class="sxs-lookup"><span data-stu-id="7bc69-134">Conversions</span></span>  
 <span data-ttu-id="7bc69-135">Önceden tanımlanmış bir örtük dönüştürme `ulong` için [float](../../../csharp/language-reference/keywords/float.md), [çift](../../../csharp/language-reference/keywords/double.md), veya [ondalık](../../../csharp/language-reference/keywords/decimal.md).</span><span class="sxs-lookup"><span data-stu-id="7bc69-135">There is a predefined implicit conversion from `ulong` to [float](../../../csharp/language-reference/keywords/float.md), [double](../../../csharp/language-reference/keywords/double.md), or [decimal](../../../csharp/language-reference/keywords/decimal.md).</span></span>  
  
 <span data-ttu-id="7bc69-136">Örtük dönüştürme yok `ulong` herhangi bir tam sayı türüne.</span><span class="sxs-lookup"><span data-stu-id="7bc69-136">There is no implicit conversion from `ulong` to any integral type.</span></span> <span data-ttu-id="7bc69-137">Örneğin, aşağıdaki deyim derleme hatası açık atama olmadan üretir:</span><span class="sxs-lookup"><span data-stu-id="7bc69-137">For example, the following statement will produce a compilation error without an explicit cast:</span></span>  
  
```csharp  
long long1 = 8UL;   // Error: no implicit conversion from ulong  
```  
  
 <span data-ttu-id="7bc69-138">Önceden tanımlanmış bir örtük dönüştürme [bayt](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), veya [char](../../../csharp/language-reference/keywords/char.md) için `ulong`.</span><span class="sxs-lookup"><span data-stu-id="7bc69-138">There is a predefined implicit conversion from [byte](../../../csharp/language-reference/keywords/byte.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [uint](../../../csharp/language-reference/keywords/uint.md), or [char](../../../csharp/language-reference/keywords/char.md) to `ulong`.</span></span>  
  
 <span data-ttu-id="7bc69-139">Ayrıca, kayan nokta türleri için örtük dönüştürme yok yok `ulong`.</span><span class="sxs-lookup"><span data-stu-id="7bc69-139">Also, there is no implicit conversion from floating-point types to `ulong`.</span></span> <span data-ttu-id="7bc69-140">Örneğin, bir açık atama kullanılmadığı sürece aşağıdaki ifadeyi derleyici hatası oluşturur:</span><span class="sxs-lookup"><span data-stu-id="7bc69-140">For example, the following statement generates a compiler error unless an explicit cast is used:</span></span>  
  
```csharp  
// Error -- no implicit conversion from double:  
ulong x = 3.0;  
// OK -- explicit conversion:  
ulong y = (ulong)3.0;    
```  
  
 <span data-ttu-id="7bc69-141">Karma kayan nokta türleri ve tam sayı türleri ile aritmetik ifadeler hakkında daha fazla bilgi için bkz: [float](../../../csharp/language-reference/keywords/float.md) ve [çift](../../../csharp/language-reference/keywords/double.md).</span><span class="sxs-lookup"><span data-stu-id="7bc69-141">For information on arithmetic expressions with mixed floating-point types and integral types, see [float](../../../csharp/language-reference/keywords/float.md) and [double](../../../csharp/language-reference/keywords/double.md).</span></span>  
  
 <span data-ttu-id="7bc69-142">Örtük sayısal dönüştürme kuralları hakkında daha fazla bilgi için bkz: [örtük sayısal dönüşümler tablosu](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="7bc69-142">For more information on implicit numeric conversion rules, see the [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="7bc69-143">C# Dil Belirtimi</span><span class="sxs-lookup"><span data-stu-id="7bc69-143">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7bc69-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7bc69-144">See Also</span></span>  
 <xref:System.UInt64>  
 [<span data-ttu-id="7bc69-145">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="7bc69-145">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="7bc69-146">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="7bc69-146">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="7bc69-147">C# anahtar sözcükleri</span><span class="sxs-lookup"><span data-stu-id="7bc69-147">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="7bc69-148">Tam sayı türleri tablosu</span><span class="sxs-lookup"><span data-stu-id="7bc69-148">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="7bc69-149">Yerleşik türler tablosu</span><span class="sxs-lookup"><span data-stu-id="7bc69-149">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="7bc69-150">Örtük sayısal dönüşümler tablosu</span><span class="sxs-lookup"><span data-stu-id="7bc69-150">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="7bc69-151">Açık sayısal dönüşümler tablosu</span><span class="sxs-lookup"><span data-stu-id="7bc69-151">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)