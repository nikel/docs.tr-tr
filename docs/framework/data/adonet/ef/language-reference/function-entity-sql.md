---
title: "İŞLEVİ (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 40c8f218238492bbbc4af543aa6f9a635454b359
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="function-entity-sql"></a><span data-ttu-id="63dc7-102">İŞLEVİ (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="63dc7-102">FUNCTION (Entity SQL)</span></span>
<span data-ttu-id="63dc7-103">Varlık SQL sorgu komutunu kapsamında bir işlevi tanımlar.</span><span class="sxs-lookup"><span data-stu-id="63dc7-103">Defines a function in the scope of an Entity SQL query command.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63dc7-104">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="63dc7-104">Syntax</span></span>  
  
```  
FUNCTION function-name  
( [ { parameter_name <type_definition>   
        [ ,...n ]  
  ]  
) AS ( function_expression )   
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )   
                | REF ( data_type )   
                | ROW ( row_expression )   
        }   
```  
  
## <a name="arguments"></a><span data-ttu-id="63dc7-105">Arguments</span><span class="sxs-lookup"><span data-stu-id="63dc7-105">Arguments</span></span>  
 `function-name`  
 <span data-ttu-id="63dc7-106">İşlevin adı.</span><span class="sxs-lookup"><span data-stu-id="63dc7-106">Name of the function.</span></span>  
  
 `parameter-name`  
 <span data-ttu-id="63dc7-107">İşlev içindeki bir parametre adı.</span><span class="sxs-lookup"><span data-stu-id="63dc7-107">Name of a parameter in the function.</span></span>  
  
 `function_expression`  
 <span data-ttu-id="63dc7-108">İşlev geçerli bir varlık SQL ifadesi.</span><span class="sxs-lookup"><span data-stu-id="63dc7-108">A valid Entity SQL expression that is the function.</span></span> <span data-ttu-id="63dc7-109">İşlev komutta çalışabilmek için `parameter_name` işlevine geçirilen parametreleri.</span><span class="sxs-lookup"><span data-stu-id="63dc7-109">The command in the function can act on `parameter_name` parameters passed to the function.</span></span>  
  
 `data_type`  
 <span data-ttu-id="63dc7-110">Desteklenen bir tür adı.</span><span class="sxs-lookup"><span data-stu-id="63dc7-110">Name of a supported type.</span></span>  
  
 <span data-ttu-id="63dc7-111">KOLEKSİYON (< type_definition`>` )</span><span class="sxs-lookup"><span data-stu-id="63dc7-111">COLLECTION ( <type_definition`>` )</span></span>  
 <span data-ttu-id="63dc7-112">Desteklenen türler, satır veya başvuruları koleksiyonu döndüren bir ifade.</span><span class="sxs-lookup"><span data-stu-id="63dc7-112">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
 <span data-ttu-id="63dc7-113">REF **(**`data_type`**)**</span><span class="sxs-lookup"><span data-stu-id="63dc7-113">REF **(**`data_type`**)**</span></span>  
 <span data-ttu-id="63dc7-114">Bir varlık türü referansı döndüren bir ifade.</span><span class="sxs-lookup"><span data-stu-id="63dc7-114">An expression that returns a reference to an entity type.</span></span>  
  
 <span data-ttu-id="63dc7-115">SATIR **(**`row_expression`**)**</span><span class="sxs-lookup"><span data-stu-id="63dc7-115">ROW **(**`row_expression`**)**</span></span>  
 <span data-ttu-id="63dc7-116">Anonim, döndüren bir ifadeye yapısal olarak bir veya daha fazla değer kayıtlarından belirtilmiş.</span><span class="sxs-lookup"><span data-stu-id="63dc7-116">An expression that returns anonymous, structurally typed records from one or more values.</span></span> <span data-ttu-id="63dc7-117">Daha fazla bilgi için bkz: [satır](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="63dc7-117">For more information, see [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="63dc7-118">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="63dc7-118">Remarks</span></span>  
 <span data-ttu-id="63dc7-119">İşlev imzalarında farklı olduğu sürece aynı ada sahip birden çok işlev satır içi, bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="63dc7-119">Multiple functions with the same name can be declared inline, as long as the function signatures are different.</span></span> <span data-ttu-id="63dc7-120">Daha fazla bilgi için bkz: [işlevi aşırı yükleme çözümü](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="63dc7-120">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
 <span data-ttu-id="63dc7-121">Bu komutta yalnızca tanımlandıktan sonra bir satır içi işlevi bir varlık SQL komutunu çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="63dc7-121">An inline function can be called in an Entity SQL command only after it has been defined in that command.</span></span> <span data-ttu-id="63dc7-122">Ancak, bir satır içi işlev önce ya da çağrılan işlev tanımlandıktan sonra başka bir satır içi işlev içinde çağrılabilir.</span><span class="sxs-lookup"><span data-stu-id="63dc7-122">However, an inline function can be called inside another inline function either before or after the called function has been defined.</span></span> <span data-ttu-id="63dc7-123">B işlevi tanımlanmadan önce aşağıdaki örnekte, işlevi A B işlev çağrıları:</span><span class="sxs-lookup"><span data-stu-id="63dc7-123">In the following example, function A calls function B before function B is defined:</span></span>  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 <span data-ttu-id="63dc7-124">Daha fazla bilgi için bkz: [nasıl yapılır: bir kullanıcı tanımlı işlev çağrısı](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02).</span><span class="sxs-lookup"><span data-stu-id="63dc7-124">For more information, see [How to: Call a User-Defined Function](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02).</span></span>  
  
 <span data-ttu-id="63dc7-125">İşlevler de modelinde bildirilebilir.</span><span class="sxs-lookup"><span data-stu-id="63dc7-125">Functions can also be declared in the model itself.</span></span> <span data-ttu-id="63dc7-126">Model içinde bildirilen işlevler komutta bildirilen satır içi işlevleri gibi aynı şekilde yürütülür.</span><span class="sxs-lookup"><span data-stu-id="63dc7-126">Functions declared in the model are executed in the same way as functions declared inline in the command.</span></span> <span data-ttu-id="63dc7-127">Daha fazla bilgi için bkz: [kullanıcı tanımlı işlevler](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="63dc7-127">For more information, see [User-Defined Functions](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63dc7-128">Örnek</span><span class="sxs-lookup"><span data-stu-id="63dc7-128">Example</span></span>  
 <span data-ttu-id="63dc7-129">Aşağıdaki varlık SQL komutunu işlevini tanımlar `Products` döndürülen ürünleri filtrelemek için bir tamsayı değeri alır.</span><span class="sxs-lookup"><span data-stu-id="63dc7-129">The following Entity SQL command defines a function `Products` that takes an integer value to filter the returned products.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a><span data-ttu-id="63dc7-130">Örnek</span><span class="sxs-lookup"><span data-stu-id="63dc7-130">Example</span></span>  
 <span data-ttu-id="63dc7-131">Aşağıdaki varlık SQL komutunu işlevini tanımlar `StringReturnsCollection` döndürülen kişiler filtrelemek için dizeleri koleksiyonu alır.</span><span class="sxs-lookup"><span data-stu-id="63dc7-131">The following Entity SQL command defines a function `StringReturnsCollection` that takes a collection of strings to filter the returned contacts.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a><span data-ttu-id="63dc7-132">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="63dc7-132">See Also</span></span>  
 [<span data-ttu-id="63dc7-133">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="63dc7-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="63dc7-134">Varlık SQL dili</span><span class="sxs-lookup"><span data-stu-id="63dc7-134">Entity SQL Language</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)