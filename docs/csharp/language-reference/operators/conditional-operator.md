---
title: "?: İşleci (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9abfe4ca6be29b54edd591b503069c15e02c3532
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="24195-102">?: İşleci (C# Başvurusu)</span><span class="sxs-lookup"><span data-stu-id="24195-102">?: Operator (C# Reference)</span></span>
<span data-ttu-id="24195-103">Koşullu işleç (`?:`) Boole ifadesi değerine bağlı olarak iki değerden birini döndürür.</span><span class="sxs-lookup"><span data-stu-id="24195-103">The conditional operator (`?:`) returns one of two values depending on the value of a Boolean expression.</span></span> <span data-ttu-id="24195-104">Aşağıda, koşullu işlecin sözdizimi belirtilmiştir.</span><span class="sxs-lookup"><span data-stu-id="24195-104">Following is the syntax for the conditional operator.</span></span>  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a><span data-ttu-id="24195-105">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="24195-105">Remarks</span></span>  
 <span data-ttu-id="24195-106">`condition` Değerlendirilmelidir `true` veya `false`.</span><span class="sxs-lookup"><span data-stu-id="24195-106">The `condition` must evaluate to `true` or `false`.</span></span> <span data-ttu-id="24195-107">Varsa `condition` olan `true`, `first_expression` değerlendirilir ve sonucu olur.</span><span class="sxs-lookup"><span data-stu-id="24195-107">If `condition` is `true`, `first_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="24195-108">Varsa `condition` olan `false`, `second_expression` değerlendirilir ve sonucu olur.</span><span class="sxs-lookup"><span data-stu-id="24195-108">If `condition` is `false`, `second_expression` is evaluated and becomes the result.</span></span> <span data-ttu-id="24195-109">İki ifadeden yalnızca biri değerlendirilir.</span><span class="sxs-lookup"><span data-stu-id="24195-109">Only one of the two expressions is evaluated.</span></span>  
  
 <span data-ttu-id="24195-110">İki tür `first_expression` ve `second_expression` aynı olmalı ya da örtük bir dönüştürme bir türden diğerine bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="24195-110">Either the type of `first_expression` and `second_expression` must be the same, or an implicit conversion must exist from one type to the other.</span></span>  
  
 <span data-ttu-id="24195-111">Aksi takdirde gerektirebilir hesaplamalar express bir `if-else` koşullu işleç kullanarak daha az ama öz oluşturma.</span><span class="sxs-lookup"><span data-stu-id="24195-111">You can express calculations that might otherwise require an `if-else` construction more concisely by using the conditional operator.</span></span> <span data-ttu-id="24195-112">Örneğin, aşağıdaki kodu ilk kullanan bir `if` deyimi ve tamsayı olumlu veya olumsuz olarak sınıflandırmak için koşullu bir işleç.</span><span class="sxs-lookup"><span data-stu-id="24195-112">For example, the following code uses first an `if` statement and then a conditional operator to classify an integer as positive or negative.</span></span>  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 <span data-ttu-id="24195-113">Koşullu işleç, sağa ilişkilendirilir.</span><span class="sxs-lookup"><span data-stu-id="24195-113">The conditional operator is right-associative.</span></span> <span data-ttu-id="24195-114">İfade `a ? b : c ? d : e` olarak değerlendirilir `a ? b : (c ? d : e)`, olarak değil `(a ? b : c) ? d : e`.</span><span class="sxs-lookup"><span data-stu-id="24195-114">The expression `a ? b : c ? d : e` is evaluated as `a ? b : (c ? d : e)`, not as `(a ? b : c) ? d : e`.</span></span>  
  
 <span data-ttu-id="24195-115">Koşullu işleç aşırı yüklenemez.</span><span class="sxs-lookup"><span data-stu-id="24195-115">The conditional operator cannot be overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24195-116">Örnek</span><span class="sxs-lookup"><span data-stu-id="24195-116">Example</span></span>  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="24195-117">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="24195-117">See Also</span></span>  
 [<span data-ttu-id="24195-118">C# başvurusu</span><span class="sxs-lookup"><span data-stu-id="24195-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="24195-119">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="24195-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="24195-120">C# işleçleri</span><span class="sxs-lookup"><span data-stu-id="24195-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="24195-121">if-else</span><span class="sxs-lookup"><span data-stu-id="24195-121">if-else</span></span>](../../../csharp/language-reference/keywords/if-else.md)  
 [<span data-ttu-id="24195-122">?. ve? İşleçler</span><span class="sxs-lookup"><span data-stu-id="24195-122">?. and ?Operators</span></span>](../../../csharp/language-reference/operators/null-conditional-operators.md)  
 [<span data-ttu-id="24195-123">?? İşleci</span><span class="sxs-lookup"><span data-stu-id="24195-123">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)