---
title: "Kullanıcı tanımlı işlevler (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f9e6bbd-8e5a-43e1-809f-f8a61338e522
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: b97834a500328f7853b8a361ec20d7ff06eda3d3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="user-defined-functions-entity-sql"></a><span data-ttu-id="55053-102">Kullanıcı tanımlı işlevler (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="55053-102">User-Defined Functions (Entity SQL)</span></span>
<span data-ttu-id="55053-103">Varlık SQL kullanıcı tanımlı işlevler sorguda çağırma destekler.</span><span class="sxs-lookup"><span data-stu-id="55053-103">Entity SQL supports calling user-defined functions in a query.</span></span> <span data-ttu-id="55053-104">Bu işlevler satır içi sorguyla tanımlayabilirsiniz (bkz [nasıl yapılır: kullanıcı tanımlı bir işlevi çağırmak](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) veya kavramsal modelin parçası olarak (bkz [nasıl yapılır: özel işlevlerde tanımlamak kavramsal Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span><span class="sxs-lookup"><span data-stu-id="55053-104">You can define these functions inline with the query (see [How to: Call a User-Defined Function](http://msdn.microsoft.com/en-us/ad131b86-8b4e-4747-8605-d4fc64fb9d02)) or as part of the conceptual model (see [How to: Define Custom Functions in the Conceptual Model](http://msdn.microsoft.com/en-us/0dad7b8b-58f6-4271-b238-f34810d68e5f)).</span></span> <span data-ttu-id="55053-105">Bir varlık SQL komutunu olarak tanımlı kavramsal model işlevler [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) öğesinin bir [işlevi](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) kavramsal modelde öğesi.</span><span class="sxs-lookup"><span data-stu-id="55053-105">Conceptual model functions are defined as an Entity SQL command in the [DefiningExpression](http://msdn.microsoft.com/en-us/d3da8d8b-a048-47ee-8d81-0c2ea3acdd3e) element of a [Function](http://msdn.microsoft.com/en-us/dc3beca7-55cf-4977-8db0-5064cdbab134) element in the conceptual model.</span></span>  
  
 <span data-ttu-id="55053-106">Varlık SQL sorgu komutu kendisini işlevleri tanımlamanızı sağlar.</span><span class="sxs-lookup"><span data-stu-id="55053-106">Entity SQL enables you to define functions in the query command itself.</span></span> <span data-ttu-id="55053-107">[İşlevi](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) işleci satır içi işlevleri tanımlar.</span><span class="sxs-lookup"><span data-stu-id="55053-107">The [FUNCTION](../../../../../../docs/framework/data/adonet/ef/language-reference/function-entity-sql.md) operator defines inline functions.</span></span> <span data-ttu-id="55053-108">İşlev imzalarında benzersiz olduğu sürece bu işlevler aynı işlev adı olabilir ve birden çok işlevi içinde tek bir komut tanımlayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="55053-108">You can define multiple functions in a single command, and these functions can have the same function name, as long as the function signatures are unique.</span></span> <span data-ttu-id="55053-109">Daha fazla bilgi için bkz: [işlevi aşırı yükleme çözümü](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="55053-109">For more information, see [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55053-110">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="55053-110">See Also</span></span>  
 [<span data-ttu-id="55053-111">İşlevler</span><span class="sxs-lookup"><span data-stu-id="55053-111">Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)