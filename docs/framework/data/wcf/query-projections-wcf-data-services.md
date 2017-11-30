---
title: Sorgu projeksiyonlar (WCF Veri Hizmetleri)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: a09f4985-9f0d-48c8-b183-83d67a3dfe5f
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a3546bf13eefd14f6bdc119541262cdfdc25e863
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="query-projections-wcf-data-services"></a><span data-ttu-id="ba535-102">Sorgu projeksiyonlar (WCF Veri Hizmetleri)</span><span class="sxs-lookup"><span data-stu-id="ba535-102">Query Projections (WCF Data Services)</span></span>
<span data-ttu-id="ba535-103">Projeksiyon bir mekanizma sağlar [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] yalnızca belirli özellikleri bir varlığın yanıtta döndürülen belirterek bir sorgu tarafından döndürülen akıştaki veri miktarını azaltmak için.</span><span class="sxs-lookup"><span data-stu-id="ba535-103">Projection provides a mechanism in the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] to reduce the amount of data in the feed returned by a query by specifying that only certain properties of an entity are returned in the response.</span></span> <span data-ttu-id="ba535-104">Daha fazla bilgi için bkz: [OData: Sistem sorgusu seçeneği ($select)](http://go.microsoft.com/fwlink/?LinkId=186076).</span><span class="sxs-lookup"><span data-stu-id="ba535-104">For more information, see [OData: Select System Query Option ($select)](http://go.microsoft.com/fwlink/?LinkId=186076).</span></span>  
  
 <span data-ttu-id="ba535-105">Bu konuda nasıl varlık için gereksinimler nelerdir sorgu projeksiyon tanımlamak için ve varlık olmayan türleri, yapmadan güncelleştirmeleri tahmini sonuçları için tahmini türleri oluşturma ve bazı projeksiyon konular listelenmiştir açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="ba535-105">This topic describes how to define a query projection, what the requirements are for entity and non-entity types, making updates to projected results, creating projected types, and lists some projection considerations.</span></span>  
  
## <a name="defining-a-query-projection"></a><span data-ttu-id="ba535-106">Bir sorgu projeksiyon tanımlama</span><span class="sxs-lookup"><span data-stu-id="ba535-106">Defining a Query Projection</span></span>  
 <span data-ttu-id="ba535-107">Projeksiyon yan tümcesi bir sorgu kullanarak ya da ekleyebilirsiniz `$select` sorgu seçeneği bir URI veya kullanarak [seçin](~/docs/csharp/language-reference/keywords/select-clause.md) yan tümcesi ([seçin](~/docs/visual-basic/language-reference/queries/select-clause.md) Visual Basic'te) LINQ Sorgu.</span><span class="sxs-lookup"><span data-stu-id="ba535-107">You can add a projection clause to a query either by using the `$select` query option in a URI or by using the [select](~/docs/csharp/language-reference/keywords/select-clause.md) clause ([Select](~/docs/visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in a LINQ query.</span></span> <span data-ttu-id="ba535-108">Varlık veri öngörülen varlık türleri veya varlık olmayan türler istemcide döndürdü.</span><span class="sxs-lookup"><span data-stu-id="ba535-108">Returned entity data can be projected into either entity types or non-entity types on the client.</span></span> <span data-ttu-id="ba535-109">Bu konudaki örnekler nasıl kullanılacağını göstermektedir `select` yan tümcesinde bir LINQ Sorgu.</span><span class="sxs-lookup"><span data-stu-id="ba535-109">Examples in this topic demonstrate how to use the `select` clause in a LINQ query.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba535-110">Tahmini türleri için yapılan güncelleştirmeler kaydettiğinizde, veri hizmeti veri kaybı oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="ba535-110">Data loss might occur in the data service when you save updates that were made to projected types.</span></span> <span data-ttu-id="ba535-111">Daha fazla bilgi için bkz: [projeksiyon konuları](#considerations).</span><span class="sxs-lookup"><span data-stu-id="ba535-111">For more information, see [Projection Considerations](#considerations).</span></span>  
  
## <a name="requirements-for-entity-and-non-entity-types"></a><span data-ttu-id="ba535-112">Varlık ve varlık olmayan türleri için gereksinimleri</span><span class="sxs-lookup"><span data-stu-id="ba535-112">Requirements for Entity and Non-Entity Types</span></span>  
 <span data-ttu-id="ba535-113">Varlık türleri Varlık anahtarı oluşturan bir veya daha fazla kimlik özellikleri olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba535-113">Entity types must have one or more identity properties that make up the entity key.</span></span> <span data-ttu-id="ba535-114">Varlık türleri istemcilerde aşağıdaki yollardan biriyle tanımlanmıştır:</span><span class="sxs-lookup"><span data-stu-id="ba535-114">Entity types are defined on clients in one of the following ways:</span></span>  
  
-   <span data-ttu-id="ba535-115">Uygulayarak <xref:System.Data.Services.Common.DataServiceKeyAttribute> veya <xref:System.Data.Services.Common.DataServiceEntityAttribute> türü.</span><span class="sxs-lookup"><span data-stu-id="ba535-115">By applying the <xref:System.Data.Services.Common.DataServiceKeyAttribute> or <xref:System.Data.Services.Common.DataServiceEntityAttribute> to the type.</span></span>  
  
-   <span data-ttu-id="ba535-116">Adlı bir özellik türüne sahip olduğunda `ID`.</span><span class="sxs-lookup"><span data-stu-id="ba535-116">When the type has a property named `ID`.</span></span>  
  
-   <span data-ttu-id="ba535-117">Adlı bir özellik türüne sahip olduğunda *türü*`ID`, burada *türü* türünün adı.</span><span class="sxs-lookup"><span data-stu-id="ba535-117">When the type has a property named *type*`ID`, where *type* is the name of the type.</span></span>  
  
 <span data-ttu-id="ba535-118">İstemcide tanımlanan bir türü içine sorgu sonuçları projenizin varsayılan olarak, istemci türünde projeksiyon istenen özellikler mevcut olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba535-118">By default, when you project query results into a type defined at the client, the properties requested in the projection must exist in the client type.</span></span> <span data-ttu-id="ba535-119">Ancak, değerini belirttiğinizde `true` için <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> özelliği <xref:System.Data.Services.Client.DataServiceContext>, projeksiyon belirtilen özellikler istemci türü gerçekleşmesi için gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="ba535-119">However, when you specify a value of `true` for the <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> property of the <xref:System.Data.Services.Client.DataServiceContext>, properties specified in the projection are not required to occur in the client type.</span></span>  
  
### <a name="making-updates-to-projected-results"></a><span data-ttu-id="ba535-120">Tahmini sonuçları güncelleştirmeleri yapma</span><span class="sxs-lookup"><span data-stu-id="ba535-120">Making Updates to Projected Results</span></span>  
 <span data-ttu-id="ba535-121">Sorgu sonuçları istemci üzerinde varlık türlerine projenizin <xref:System.Data.Services.Client.DataServiceContext> verileri yedekleyin gönderilmek üzere güncelleştirmeleri bu nesnelerle izleyebilirsiniz ne zaman hizmet <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> yöntemi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="ba535-121">When you project query results into entity types on the client, the <xref:System.Data.Services.Client.DataServiceContext> can track those objects with updates to be sent back to the data service when the <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> method is called.</span></span> <span data-ttu-id="ba535-122">Bununla birlikte, varlık olmayan türlerine istemcide öngörülen verilere yapılan güncelleştirmeler veri hizmetine gönderilemiyor.</span><span class="sxs-lookup"><span data-stu-id="ba535-122">However, updates that are made to data projected into non-entity types on the client cannot be sent back to the data service.</span></span> <span data-ttu-id="ba535-123">Varlık örneği tanımlamak için bir anahtar olmadan, veri hizmeti veri kaynağının doğru varlık güncelleştirilemez olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="ba535-123">This is because without a key to identify the entity instance, the data service cannot update the correct entity in the data source.</span></span> <span data-ttu-id="ba535-124">Olmayan varlık türleri değil bağlanan <xref:System.Data.Services.Client.DataServiceContext>.</span><span class="sxs-lookup"><span data-stu-id="ba535-124">Non-entity types are not attached to the <xref:System.Data.Services.Client.DataServiceContext>.</span></span>  
  
 <span data-ttu-id="ba535-125">Veri Hizmeti tanımlanan bir varlık türünün bir veya daha fazla özelliklerini içine varlık yansıtılır istemci türünde değil gerçekleştiğinde, yeni varlık ekler bu eksik özellikleri içermez.</span><span class="sxs-lookup"><span data-stu-id="ba535-125">When one or more properties of an entity type defined in the data service do not occur in the client type into which the entity is projected, inserts of new entities will not contain these missing properties.</span></span> <span data-ttu-id="ba535-126">Bu durumda, var olan varlıkları için yapılan güncelleştirmeler olacak **de** bu eksik özellikler eklemeniz gerekmez.</span><span class="sxs-lookup"><span data-stu-id="ba535-126">In this case, updates that are made to existing entities will **also** not include these missing properties.</span></span> <span data-ttu-id="ba535-127">Böyle bir özellik için bir değer mevcut olduğunda, güncelleştirme, bir özellik için varsayılan değer veri kaynağında tanımlanan sıfırlar.</span><span class="sxs-lookup"><span data-stu-id="ba535-127">When a value exists for such a property, the update resets it to the default value for the property, as defined in the data source.</span></span>  
  
### <a name="creating-projected-types"></a><span data-ttu-id="ba535-128">Tahmini türleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="ba535-128">Creating Projected Types</span></span>  
 <span data-ttu-id="ba535-129">Aşağıdaki örnek, adresi ilgili özelliklerini projeleri anonim bir LINQ sorgusu kullanır `Customers` yeni bir türe `CustomerAddress` istemcide tanımlanır ve varlık türü olarak öznitelikli türü:</span><span class="sxs-lookup"><span data-stu-id="ba535-129">The following example uses an anonymous LINQ query that projects the address-related properties of the `Customers` type into a new `CustomerAddress` type, which is defined on the client and is attributed as an entity type:</span></span>  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressspecific)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressSpecific](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressspecific)]  
  
 <span data-ttu-id="ba535-130">Bu örnekte, nesne Başlatıcı düzeni yeni bir örneğini oluşturmak için kullanılan `CustmerAddress` bir oluşturucu çağırarak yerine türü.</span><span class="sxs-lookup"><span data-stu-id="ba535-130">In this example, the object initializer pattern is used to create a new instance of the `CustmerAddress` type instead of calling a constructor.</span></span> <span data-ttu-id="ba535-131">Varlık türleriyle yansıtılırken oluşturucuları desteklenmiyor ancak varlık olmayan ve anonim türler yansıtılırken kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="ba535-131">Constructors are not supported when projecting into entity types, but they can be used when projecting into non-entity and anonymous types.</span></span> <span data-ttu-id="ba535-132">Çünkü `CustomerAddress` bir varlık türü olduğu değişiklikleri yapılan ve veri hizmetine gönderilir.</span><span class="sxs-lookup"><span data-stu-id="ba535-132">Because `CustomerAddress` is an entity type, changes can be made and sent back to the data service.</span></span>  
  
 <span data-ttu-id="ba535-133">Ayrıca, verileri `Customer` türü örneğini öngörülen `CustomerAddress` anonim bir tür yerine varlık türü.</span><span class="sxs-lookup"><span data-stu-id="ba535-133">Also, the data from the `Customer` type is projected into an instance of the `CustomerAddress` entity type instead of an anonymous type.</span></span> <span data-ttu-id="ba535-134">Anonim türler içine projeksiyon desteklenir, ancak anonim türler, varlık olmayan türleri olarak değerlendirildiğinden veriler salt okunur.</span><span class="sxs-lookup"><span data-stu-id="ba535-134">Projection into anonymous types is supported, but the data is read-only because anonymous types are treated as non-entity types.</span></span>  
  
 <span data-ttu-id="ba535-135"><xref:System.Data.Services.Client.MergeOption> Ayarlarını <xref:System.Data.Services.Client.DataServiceContext> kimlik çözümlemesi için sorgu projeksiyon sırasında kullanılır.</span><span class="sxs-lookup"><span data-stu-id="ba535-135">The <xref:System.Data.Services.Client.MergeOption> settings of the <xref:System.Data.Services.Client.DataServiceContext> are used for identity resolution during query projection.</span></span> <span data-ttu-id="ba535-136">Bu örneği olması durumunda gelir `Customer` türü zaten <xref:System.Data.Services.Client.DataServiceContext>, örneği `CustomerAddress` aynı kimlikle tarafından belirlenen kuralları kimlik çözümleme izler<xref:System.Data.Services.Client.MergeOption></span><span class="sxs-lookup"><span data-stu-id="ba535-136">This means that if an instance of the `Customer` type already exists in the <xref:System.Data.Services.Client.DataServiceContext>, an instance of `CustomerAddress` with the same identity will follow the identity resolution rules set by the <xref:System.Data.Services.Client.MergeOption></span></span>  
  
 <span data-ttu-id="ba535-137">Aşağıdaki tabloda, varlık ve varlık olmayan türlerine sonuçları yansıtılırken davranışları açıklanmaktadır:</span><span class="sxs-lookup"><span data-stu-id="ba535-137">The following table describes the behaviors when projecting results into entity and non-entity types:</span></span>  
  
|<span data-ttu-id="ba535-138">Eylem</span><span class="sxs-lookup"><span data-stu-id="ba535-138">Action</span></span>|<span data-ttu-id="ba535-139">Varlık türü</span><span class="sxs-lookup"><span data-stu-id="ba535-139">Entity Type</span></span>|<span data-ttu-id="ba535-140">Varlık dışı türü</span><span class="sxs-lookup"><span data-stu-id="ba535-140">Non-Entity Type</span></span>|  
|------------|-----------------|----------------------|  
|<span data-ttu-id="ba535-141">Aşağıdaki örnekte olduğu gibi başlatıcıları kullanarak yeni bir tahmini örneği oluşturma:</span><span class="sxs-lookup"><span data-stu-id="ba535-141">Creating a new projected instance by using initializers, as in the following example:</span></span><br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithinitializer)]
 [!code-vb[Astoria Northwind Client#ProjectWithInitializer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithinitializer)]|<span data-ttu-id="ba535-142">Desteklenir</span><span class="sxs-lookup"><span data-stu-id="ba535-142">Supported</span></span>|<span data-ttu-id="ba535-143">Desteklenir</span><span class="sxs-lookup"><span data-stu-id="ba535-143">Supported</span></span>|  
|<span data-ttu-id="ba535-144">Aşağıdaki örnekte olduğu gibi oluşturucuları kullanarak yeni bir tahmini örneği oluşturma:</span><span class="sxs-lookup"><span data-stu-id="ba535-144">Creating a new projected instance by using constructors, as in the following example:</span></span><br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithconstructor)]
 [!code-vb[Astoria Northwind Client#ProjectWithConstructor](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithconstructor)]|<span data-ttu-id="ba535-145">A <xref:System.NotSupportedException> tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="ba535-145">A <xref:System.NotSupportedException> is raised.</span></span>|<span data-ttu-id="ba535-146">Desteklenir</span><span class="sxs-lookup"><span data-stu-id="ba535-146">Supported</span></span>|  
|<span data-ttu-id="ba535-147">Projeksiyon kullanarak aşağıdaki örnekteki gibi bir özellik değeri dönüştürmek için:</span><span class="sxs-lookup"><span data-stu-id="ba535-147">Using projection to transform a property value, as in the following example:</span></span><br /><br /> [!code-csharp[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#projectwithtransform)]
 [!code-vb[Astoria Northwind Client#ProjectWithTransform](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#projectwithtransform)]<br /><br /> <span data-ttu-id="ba535-148">Karışıklığı önlemek için ve büyük olasılıkla başka bir varlığa ait veri kaynağındaki verileri üzerine neden olabilir çünkü bu dönüşüm varlık türleri için desteklenmiyor.</span><span class="sxs-lookup"><span data-stu-id="ba535-148">This transformation is not supported for entity types because it can lead to confusion and potentially overwriting the data in the data source that belongs to another entity.</span></span>|<span data-ttu-id="ba535-149">A <xref:System.NotSupportedException> tetiklenir.</span><span class="sxs-lookup"><span data-stu-id="ba535-149">A <xref:System.NotSupportedException> is raised.</span></span>|<span data-ttu-id="ba535-150">Desteklenir</span><span class="sxs-lookup"><span data-stu-id="ba535-150">Supported</span></span>|  
  
<a name="considerations"></a>   
## <a name="projection-considerations"></a><span data-ttu-id="ba535-151">Projeksiyon konuları</span><span class="sxs-lookup"><span data-stu-id="ba535-151">Projection Considerations</span></span>  
 <span data-ttu-id="ba535-152">Bir sorgu projeksiyon tanımlarken aşağıdaki hususlar geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="ba535-152">The following additional considerations apply when defining a query projection.</span></span>  
  
-   <span data-ttu-id="ba535-153">Atom biçimi için özel akışları tanımladığınızda, tanımlı özel eşlemeleri sahip tüm varlık özellikleri projeksiyon içerdiği emin olmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba535-153">When you define custom feeds for the Atom format, you must make sure that all entity properties that have custom mappings defined are included in the projection.</span></span> <span data-ttu-id="ba535-154">Eşlenen varlık özelliği cinsinden izdüşümünü bulunmaz, veri kaybı oluşabilir.</span><span class="sxs-lookup"><span data-stu-id="ba535-154">When a mapped entity property is not included in the projection, data loss might occur.</span></span> <span data-ttu-id="ba535-155">Daha fazla bilgi için bkz: [akış özelleştirme](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba535-155">For more information, see [Feed Customization](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).</span></span>  
  
-   <span data-ttu-id="ba535-156">Ekler, varlık veri hizmetinin veri modelindeki özelliklerin tümünü içermiyor tahmini bir türe yapıldığında, istemcide projeksiyon bulunmayan özellikler varsayılan değerlerine ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="ba535-156">When inserts are made to a projected type that does not contain all of the properties of the entity in the data model of the data service, the properties not included in the projection at the client are set to their default values.</span></span>  
  
-   <span data-ttu-id="ba535-157">Varlık veri hizmetinin veri modelindeki özelliklerin tümünü içermiyor tahmini bir türe güncelleştirmeleri yapıldığında istemcide projeksiyon bulunmayan mevcut değerleri başlatılmamış varsayılan değerlerle üzerine yazılır.</span><span class="sxs-lookup"><span data-stu-id="ba535-157">When updates are made to a projected type that does not contain all of the properties of the entity in the data model of the data service, existing values not included in the projection on the client will be overwritten with uninitialized default values.</span></span>  
  
-   <span data-ttu-id="ba535-158">Bir yansıtma karmaşık bir özellik varsa, tüm karmaşık nesne iade edilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="ba535-158">When a projection includes a complex property, the entire complex object must be returned.</span></span>  
  
-   <span data-ttu-id="ba535-159">Bir yansıtma bir gezinti özelliği içerdiğinde, ilgili nesneleri örtük olarak çağrı yapmak zorunda kalmadan yüklenen <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> yöntemi.</span><span class="sxs-lookup"><span data-stu-id="ba535-159">When a projection includes a navigation property, the related objects are loaded implicitly without having to call the <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method.</span></span> <span data-ttu-id="ba535-160"><xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> Yöntemi tahmini sorguda kullanım için desteklenmez.</span><span class="sxs-lookup"><span data-stu-id="ba535-160">The <xref:System.Data.Services.Client.DataServiceQuery%601.Expand%2A> method is not supported for use in a projected query.</span></span>  
  
-   <span data-ttu-id="ba535-161">Sorgu tahminleri sorgular istemcide kullanmak üzere çevrilen `$select` seçeneği URI isteğinde sorgu.</span><span class="sxs-lookup"><span data-stu-id="ba535-161">Query projections queries on the client are translated to use the `$select` query option in the request URI.</span></span> <span data-ttu-id="ba535-162">Ne zaman bir sorgu projeksiyon yürütüldüğünde önceki bir sürümünü karşı [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] , desteklemiyor `$select` sorgu seçeneği bir hata döndürülür.</span><span class="sxs-lookup"><span data-stu-id="ba535-162">When a query with projection is executed against a previous version of [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] that does not support the `$select` query option, an error is returned.</span></span> <span data-ttu-id="ba535-163">Bu da gerçekleşebilir, <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> , <xref:System.Data.Services.DataServiceBehavior> için veri hizmeti değerine ayarlanır <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1>.</span><span class="sxs-lookup"><span data-stu-id="ba535-163">This can also happen when the <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> of the <xref:System.Data.Services.DataServiceBehavior> for the data service is set to a value of <xref:System.Data.Services.Common.DataServiceProtocolVersion.V1>.</span></span> <span data-ttu-id="ba535-164">Daha fazla bilgi için bkz: [veri hizmeti sürüm](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba535-164">For more information, see [Data Service Versioning](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="ba535-165">Daha fazla bilgi için bkz: [nasıl yapılır: Proje sorgu sonuçları](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ba535-165">For more information, see [How to: Project Query Results](../../../../docs/framework/data/wcf/how-to-project-query-results-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba535-166">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="ba535-166">See Also</span></span>  
 [<span data-ttu-id="ba535-167">Veri Hizmeti sorgulama</span><span class="sxs-lookup"><span data-stu-id="ba535-167">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)