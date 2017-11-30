---
title: "&amp;&amp;(VE) (Varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 098f9a09ba4fe114a3ad63f6d98efcd6bb090ac4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="ampamp-and-entity-sql"></a><span data-ttu-id="6ac5b-102">&amp;&amp;(VE) (Varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="6ac5b-102">&amp;&amp; (AND) (Entity SQL)</span></span>
<span data-ttu-id="6ac5b-103">Döndürür `true` hem ifadeler `true`; Aksi halde, `false` veya `NULL`.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-103">Returns `true` if both expressions are `true`; otherwise, `false` or `NULL`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ac5b-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="6ac5b-104">Syntax</span></span>  
  
```  
boolean_expression AND boolean_expression  
or  
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a><span data-ttu-id="6ac5b-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="6ac5b-105">Arguments</span></span>  
 `boolean_expression`  
 <span data-ttu-id="6ac5b-106">Tüm geçerli ifade bir Boole değeri döndürür.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-106">Any valid expression that returns a Boolean.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6ac5b-107">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="6ac5b-107">Remarks</span></span>  
 <span data-ttu-id="6ac5b-108">Çift ve işaretlerini (& &) ve işlecini aynı işlevselliğe sahiptir.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-108">Double ampersands (&&) have the same functionality as the AND operator.</span></span>  
  
 <span data-ttu-id="6ac5b-109">Aşağıdaki tabloda olası giriş değerleri gösterir ve dönüş türleri.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-109">The following table shows possible input values and return types.</span></span>  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|<span data-ttu-id="6ac5b-110">TRUE</span><span class="sxs-lookup"><span data-stu-id="6ac5b-110">TRUE</span></span>|<span data-ttu-id="6ac5b-111">FALSE</span><span class="sxs-lookup"><span data-stu-id="6ac5b-111">FALSE</span></span>|<span data-ttu-id="6ac5b-112">NULL</span><span class="sxs-lookup"><span data-stu-id="6ac5b-112">NULL</span></span>|  
|`FALSE`|<span data-ttu-id="6ac5b-113">FALSE</span><span class="sxs-lookup"><span data-stu-id="6ac5b-113">FALSE</span></span>|<span data-ttu-id="6ac5b-114">FALSE</span><span class="sxs-lookup"><span data-stu-id="6ac5b-114">FALSE</span></span>|<span data-ttu-id="6ac5b-115">FALSE</span><span class="sxs-lookup"><span data-stu-id="6ac5b-115">FALSE</span></span>|  
|`NULL`|<span data-ttu-id="6ac5b-116">NULL</span><span class="sxs-lookup"><span data-stu-id="6ac5b-116">NULL</span></span>|<span data-ttu-id="6ac5b-117">FALSE</span><span class="sxs-lookup"><span data-stu-id="6ac5b-117">FALSE</span></span>|<span data-ttu-id="6ac5b-118">NULL</span><span class="sxs-lookup"><span data-stu-id="6ac5b-118">NULL</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6ac5b-119">Örnek</span><span class="sxs-lookup"><span data-stu-id="6ac5b-119">Example</span></span>  
 <span data-ttu-id="6ac5b-120">Aşağıdaki varlık SQL sorgusunu ve işlecini kullanmayı gösterir.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-120">The following Entity SQL query demonstrates how to use the AND operator.</span></span> <span data-ttu-id="6ac5b-121">Sorgu AdventureWorks satış modelini temel alır.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-121">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="6ac5b-122">Derlemek ve bu sorguyu çalıştırmak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="6ac5b-122">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="6ac5b-123">Yordamı izleyin [nasıl yapılır: Sorgu döndürür StructuralType sonucu](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="6ac5b-123">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="6ac5b-124">Aşağıdaki sorgu bağımsız değişken olarak geçirmek `ExecuteStructuralTypeQuery` yöntemi:</span><span class="sxs-lookup"><span data-stu-id="6ac5b-124">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a><span data-ttu-id="6ac5b-125">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="6ac5b-125">See Also</span></span>  
 [<span data-ttu-id="6ac5b-126">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="6ac5b-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)