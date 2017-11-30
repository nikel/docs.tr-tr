---
title: "Varlık Veri Modeli"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 69b72a824e6f9468c9b3d86073243d506382e766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model"></a><span data-ttu-id="06ccb-102">Varlık Veri Modeli</span><span class="sxs-lookup"><span data-stu-id="06ccb-102">Entity Data Model</span></span>
<span data-ttu-id="06ccb-103">Varlık veri modeli (EDM) depolanan form bağımsız olarak verilerin yapısını açıklayan kavramları kümesidir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="06ccb-104">EDM varlık ilişkisi içinde 1976 Peter Chen tarafından açıklanan modelinden taşır, ancak ayrıca varlık ilişkisi modeline oluşturur ve geleneksel kullanımları genişletir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="06ccb-105">EDM birçok formlarında depolanan verilere sahip olmak ortaya sorunlarını ele alır.</span><span class="sxs-lookup"><span data-stu-id="06ccb-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="06ccb-106">Örneğin, ilişkisel veritabanları, metin dosyaları, XML dosyalarını, elektronik tablolar ve raporlar verilerini depolayan bir iş göz önünde bulundurun.</span><span class="sxs-lookup"><span data-stu-id="06ccb-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="06ccb-107">Modelleme verileri, uygulama tasarımı ve veri erişimi önemli sorunları gösterir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="06ccb-108">Veri odaklı bir uygulama tasarlarken, sınama verimli ve sürdürülebilir kod verimli veri erişimi, depolama ve ölçeklenebilirlik ödün vermeden yazmaktır.</span><span class="sxs-lookup"><span data-stu-id="06ccb-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="06ccb-109">Veri ilişkisel yapısı olduğunda, veri erişimi, depolama ve ölçeklenebilirlik çok verimli ancak verimli ve sürdürülebilir kod yazma daha zorlaşır.</span><span class="sxs-lookup"><span data-stu-id="06ccb-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="06ccb-110">Verileri bir nesne yapısına sahip olduğunda, dengelemeler alınır: verimli ve sürdürülebilir kod yazma gelen verimli veri erişimi, depolama ve ölçeklenebilirlik artması pahasına olur.</span><span class="sxs-lookup"><span data-stu-id="06ccb-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="06ccb-111">Bu dengelemeler arasında doğru dengeyi bulunabilir olsa bile, verileri bir biçimden diğerine taşındığında ve başka bir yeni zorluklar ortaya çıkar.</span><span class="sxs-lookup"><span data-stu-id="06ccb-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="06ccb-112">Varlık veri modeli, varlıkları ve tüm depolama şeması bağımsız ilişkileri açısından verilerin yapısını açıklayarak bu sorunlarını ele alır.</span><span class="sxs-lookup"><span data-stu-id="06ccb-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="06ccb-113">Bu veri depolanan form ilgisiz uygulama tasarımı ve geliştirme sağlar.</span><span class="sxs-lookup"><span data-stu-id="06ccb-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="06ccb-114">Ayrıca, bir uygulama (değil, depolanan form) kullanıldığı gibi varlıkları ve ilişkileri veri yapısını tanımlamak için bir uygulama geliştikçe bunlar gelişmesi.</span><span class="sxs-lookup"><span data-stu-id="06ccb-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="06ccb-115">A `conceptual model` genellikle, EDM kavramlarını uygulayan bir etki alanına özgü dil (DSL) tanımlanan ve bir özel veri yapısını varlıkları ve ilişkileri olarak gösterimidir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="06ccb-116">[Kavramsal şema tanım dili (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) gibi bir etki alanına özgü dil örneğidir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="06ccb-117">Varlıkları ve ilişkileri kavramsal modelde tanımlanan, nesneler ve ilişkilendirmelerini uygulamadaki soyutlamalar olarak düşünülebilir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="06ccb-118">Bu depolama şema kaygısı olmadan kavramsal model odaklanmak yayınlamasına izin verir ve verimliliği ve bakımı aklınızda ile kod yazmanıza olanak sağlar.</span><span class="sxs-lookup"><span data-stu-id="06ccb-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="06ccb-119">Bu sırada depolama şema tasarımcıları veri erişimi, depolama ve ölçeklenebilirlik verimliliğini odaklanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="06ccb-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06ccb-120">Bu Bölümde</span><span class="sxs-lookup"><span data-stu-id="06ccb-120">In This Section</span></span>  
 <span data-ttu-id="06ccb-121">Bu bölümdeki konular, varlık veri modeli kavramlarını açıklar.</span><span class="sxs-lookup"><span data-stu-id="06ccb-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="06ccb-122">EDM uygulayan DSL burada açıklanan kavramları içermelidir.</span><span class="sxs-lookup"><span data-stu-id="06ccb-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="06ccb-123">Unutmayın [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) CSDL kavramsal modeller tanımlamak için kullanır.</span><span class="sxs-lookup"><span data-stu-id="06ccb-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="06ccb-124">Daha fazla bilgi için bkz: [CSDL belirtimi](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="06ccb-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="06ccb-125">Varlık veri modeli temel kavramları</span><span class="sxs-lookup"><span data-stu-id="06ccb-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="06ccb-126">Varlık veri modeli: ad alanları</span><span class="sxs-lookup"><span data-stu-id="06ccb-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="06ccb-127">Varlık veri modeli: Basit veri türleri</span><span class="sxs-lookup"><span data-stu-id="06ccb-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="06ccb-128">Varlık veri modeli: devralma</span><span class="sxs-lookup"><span data-stu-id="06ccb-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="06ccb-129">ilişki ucu</span><span class="sxs-lookup"><span data-stu-id="06ccb-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="06ccb-130">İlişki uç Çokluk</span><span class="sxs-lookup"><span data-stu-id="06ccb-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="06ccb-131">ilişkilendirme kümesi</span><span class="sxs-lookup"><span data-stu-id="06ccb-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="06ccb-132">İlişki sonu Ayarla</span><span class="sxs-lookup"><span data-stu-id="06ccb-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="06ccb-133">ilişki türü</span><span class="sxs-lookup"><span data-stu-id="06ccb-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="06ccb-134">karmaşık türü</span><span class="sxs-lookup"><span data-stu-id="06ccb-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="06ccb-135">Varlık kapsayıcısı</span><span class="sxs-lookup"><span data-stu-id="06ccb-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="06ccb-136">Varlık anahtarı</span><span class="sxs-lookup"><span data-stu-id="06ccb-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="06ccb-137">Varlık kümesi</span><span class="sxs-lookup"><span data-stu-id="06ccb-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="06ccb-138">varlık türü</span><span class="sxs-lookup"><span data-stu-id="06ccb-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="06ccb-139">modeli</span><span class="sxs-lookup"><span data-stu-id="06ccb-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="06ccb-140">yabancı anahtar özelliği</span><span class="sxs-lookup"><span data-stu-id="06ccb-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="06ccb-141">Model bildirilen işlevi</span><span class="sxs-lookup"><span data-stu-id="06ccb-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="06ccb-142">Model tanımlı işlevi</span><span class="sxs-lookup"><span data-stu-id="06ccb-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="06ccb-143">Gezinme özelliği</span><span class="sxs-lookup"><span data-stu-id="06ccb-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="06ccb-144">özelliği</span><span class="sxs-lookup"><span data-stu-id="06ccb-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="06ccb-145">başvuru bütünlüğü kısıtlaması</span><span class="sxs-lookup"><span data-stu-id="06ccb-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="06ccb-146">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="06ccb-146">See Also</span></span>  
 [<span data-ttu-id="06ccb-147">ADO.NET varlık veri modeli araçları</span><span class="sxs-lookup"><span data-stu-id="06ccb-147">ADO.NET Entity Data Model  Tools</span></span>](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="06ccb-148">.edmx dosyasının genel bakış</span><span class="sxs-lookup"><span data-stu-id="06ccb-148">.edmx File Overview</span></span>](http://msdn.microsoft.com/en-us/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="06ccb-149">CSDL belirtimi</span><span class="sxs-lookup"><span data-stu-id="06ccb-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)