---
title: "KOLEKSİYON (varlık SQL)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03228bfa-be3a-4ccc-82f8-eee429f85cf1
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8d078749d20740cdade323edab975ce221e72cfa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="collection-entity-sql"></a><span data-ttu-id="58534-102">KOLEKSİYON (varlık SQL)</span><span class="sxs-lookup"><span data-stu-id="58534-102">COLLECTION (Entity SQL)</span></span>
<span data-ttu-id="58534-103">KOLEKSİYON anahtar sözcüğü yalnızca bir satır içi işlev tanımı'nda kullanılır.</span><span class="sxs-lookup"><span data-stu-id="58534-103">The COLLECTION keyword is only used in the definition of an inline function.</span></span> <span data-ttu-id="58534-104">Toplama işlevleri değerler koleksiyonu üzerinde çalışan ve skaler bir çıktı oluşturmak işlevlerdir.</span><span class="sxs-lookup"><span data-stu-id="58534-104">Collection functions are functions that operate on a collection of values and produce a scalar output.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58534-105">Sözdizimi</span><span class="sxs-lookup"><span data-stu-id="58534-105">Syntax</span></span>  
  
```  
COLLECTION(type_definition)   
```  
  
## <a name="arguments"></a><span data-ttu-id="58534-106">Arguments</span><span class="sxs-lookup"><span data-stu-id="58534-106">Arguments</span></span>  
 `type_definition`  
 <span data-ttu-id="58534-107">Desteklenen türler, satır veya başvuruları koleksiyonu döndüren bir ifade.</span><span class="sxs-lookup"><span data-stu-id="58534-107">An expression that returns a collection of supported types, rows, or references.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58534-108">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="58534-108">Remarks</span></span>  
 <span data-ttu-id="58534-109">KOLEKSİYON anahtar sözcüğü hakkında daha fazla bilgi için bkz: [tür tanımları](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span><span class="sxs-lookup"><span data-stu-id="58534-109">For more information about the COLLECTION keyword, see [Type Definitions](../../../../../../docs/framework/data/adonet/ef/language-reference/type-definitions-entity-sql.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="58534-110">Örnek</span><span class="sxs-lookup"><span data-stu-id="58534-110">Example</span></span>  
 <span data-ttu-id="58534-111">Aşağıdaki örnek, KOLEKSİYON anahtar sözcüğü ondalık bir koleksiyon için bir satır içi sorgu işlevi bağımsız değişken olarak bildirmek için nasıl kullanılacağını gösterir.</span><span class="sxs-lookup"><span data-stu-id="58534-111">The following sample shows how to use the COLLECTION keyword to declare a collection of decimals as an argument for an inline query function.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#Collection_GroupPartition](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#collection_grouppartition)]  
  
## <a name="see-also"></a><span data-ttu-id="58534-112">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="58534-112">See Also</span></span>  
 [<span data-ttu-id="58534-113">Varlık SQL Başvurusu</span><span class="sxs-lookup"><span data-stu-id="58534-113">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)