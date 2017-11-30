---
title: "Nasıl yapılır: Bir Yordam Bağımsız Değişkenini Değer Değişikliklerine Karşı Koruma (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7975cbbc38c39223a4af5c87ac6bb090be548f2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="d9f7a-102">Nasıl yapılır: Bir Yordam Bağımsız Değişkenini Değer Değişikliklerine Karşı Koruma (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9f7a-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>
<span data-ttu-id="d9f7a-103">Bir yordam parametre olarak bildirirse [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] yordamı kod çağıran kodu değişkeninde temel programlama öğesi için doğrudan bir başvuru sağlar.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-103">If a procedure declares a parameter as [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="d9f7a-104">Bu, yordamı çağıran kodu değişkeninde alttaki değerini değiştirmek için izin verir.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="d9f7a-105">Bazı durumlarda, bu tür bir değişiklik karşı korumak çağıran kodu isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="d9f7a-106">Her zaman bir bağımsız değişken değişikliği karşılık gelen bir parametre bildirerek Koruyabileceğiniz [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) yordamda.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="d9f7a-107">Bazı durumlarda ancak diğer belirtilen bir bağımsız değişkeni değiştirmek istiyorsanız, bildirebilir `ByRef` ve her çağrıda geçirme mekanizması belirlemek çağıran kodu izin verin.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="d9f7a-108">Karşılık gelen bağımsız değişkeni değere göre geçirilecek parantez içinde kapsayan ya da bu başvuruya göre geçirmek için parantez içinde kapsayan değil bunu yapar.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="d9f7a-109">Daha fazla bilgi için bkz: [nasıl yapılır: bağımsız değişkeni değere göre bayraklarıdır için zorlama](./how-to-force-an-argument-to-be-passed-by-value.md).</span><span class="sxs-lookup"><span data-stu-id="d9f7a-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9f7a-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="d9f7a-110">Example</span></span>  
 <span data-ttu-id="d9f7a-111">Aşağıdaki örnek, bir dizi değişkeni alabilir ve çalışan iki yordam üzerinde öğeleri gösterir.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="d9f7a-112">`increase` Yordamı yalnızca ekler her öğe için.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="d9f7a-113">`replace` Yordamı atar yeni bir dizi parametre `a()` ve her öğe için ekler.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="d9f7a-114">Ancak, yeniden atama çağıran kodu temel alınan dizi değişkeni etkilemez.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 <span data-ttu-id="d9f7a-115">İlk `MsgBox` çağrısı görüntüler "increase(n) sonra: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="d9f7a-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="d9f7a-116">Çünkü dizi `n` bir başvuru türü `replace` geçirme mekanizması olmamasına rağmen bu grubun üyeleri değiştirebilirsiniz `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-116">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="d9f7a-117">İkinci `MsgBox` çağrısı görüntüler "replace(n) sonra: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="d9f7a-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="d9f7a-118">Çünkü `n` geçirilen `ByVal`, `replace` değişkeni değiştirilemiyor `n` yeni bir dizi atayarak çağıran kodu.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="d9f7a-119">Zaman `replace` yeni dizi örneği oluşturur `k` ve yerel bir değişkene atar `a`, başvuru kaybederse `n` çağıran kodu tarafından geçirilen.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="d9f7a-120">Üyeleri değiştiğinde `a`, yalnızca yerel dizi `k` etkilenir.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="d9f7a-121">Bu nedenle, `replace` dizi değerlerini artırmaz `n` çağıran kodu.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d9f7a-122">Kod Derleniyor</span><span class="sxs-lookup"><span data-stu-id="d9f7a-122">Compiling the Code</span></span>  
 <span data-ttu-id="d9f7a-123">Varsayılan olarak [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bağımsız değişkenleri değere göre geçirmektir.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-123">The default in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] is to pass arguments by value.</span></span> <span data-ttu-id="d9f7a-124">Ancak, ya da dahil etmek için uygulama programlama iyi [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) veya [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) bildirilen her parametre olan anahtar sözcük.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-124">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="d9f7a-125">Bu, kodunuzu okumak kolaylaştırır.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f7a-126">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d9f7a-126">See Also</span></span>  
 [<span data-ttu-id="d9f7a-127">Yordamları</span><span class="sxs-lookup"><span data-stu-id="d9f7a-127">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="d9f7a-128">Parametreler ve bağımsız değişkenler</span><span class="sxs-lookup"><span data-stu-id="d9f7a-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d9f7a-129">Nasıl yapılır: bir yordama bağımsız değişkenler geçirme</span><span class="sxs-lookup"><span data-stu-id="d9f7a-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="d9f7a-130">Bağımsız değişkenleri değere ve başvuruya göre geçirme</span><span class="sxs-lookup"><span data-stu-id="d9f7a-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d9f7a-131">Değiştirilebilir ve değiştirilemez bağımsız değişkenler arasındaki farklar</span><span class="sxs-lookup"><span data-stu-id="d9f7a-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="d9f7a-132">Değere ve başvuruya göre bağımsız değişken geçirme arasındaki farklar</span><span class="sxs-lookup"><span data-stu-id="d9f7a-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [<span data-ttu-id="d9f7a-133">Nasıl yapılır: bir yordam bağımsız değişkeninin değerini değiştirme</span><span class="sxs-lookup"><span data-stu-id="d9f7a-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="d9f7a-134">Nasıl yapılır: bağımsız değişkeni değere göre geçirilecek şekilde zorlama</span><span class="sxs-lookup"><span data-stu-id="d9f7a-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="d9f7a-135">Bağımsız değişkenleri konuma göre ve ada göre geçirme</span><span class="sxs-lookup"><span data-stu-id="d9f7a-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="d9f7a-136">Değer türleri ve başvuru türleri</span><span class="sxs-lookup"><span data-stu-id="d9f7a-136">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)