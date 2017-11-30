---
title: "Veri Sözleşmesi Sürümü Oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- versioning [WCF], data contracts
- versioning [WCF]
- data contracts [WCF], versioning
ms.assetid: 4a0700cb-5f5f-4137-8705-3a3ecf06461f
caps.latest.revision: "35"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 58e88e319da6d78071293ce92bb7e9ebb33224bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="data-contract-versioning"></a><span data-ttu-id="fafa0-102">Veri Sözleşmesi Sürümü Oluşturma</span><span class="sxs-lookup"><span data-stu-id="fafa0-102">Data Contract Versioning</span></span>
<span data-ttu-id="fafa0-103">Uygulamaları geliştikçe, aynı zamanda değiştirmeniz gerekebilir Hizmetleri kullanım verileri sözleşme.</span><span class="sxs-lookup"><span data-stu-id="fafa0-103">As applications evolve, you may also have to change the data contracts the services use.</span></span> <span data-ttu-id="fafa0-104">Bu konuda açıklanmaktadır sürüm veri sözleşmeleri nasıl.</span><span class="sxs-lookup"><span data-stu-id="fafa0-104">This topic explains how to version data contracts.</span></span> <span data-ttu-id="fafa0-105">Bu konuda veri sözleşmesi sürümü oluşturma mekanizmaları açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="fafa0-105">This topic describes the data contract versioning mechanisms.</span></span> <span data-ttu-id="fafa0-106">Tam genel bakış ve düzenleyici sürüm oluşturma yönergeleri için bkz: [en iyi uygulamalar: veri sözleşmesi sürümü oluşturma](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-106">For a complete overview and prescriptive versioning guidance, see [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span></span>  
  
## <a name="breaking-vs-nonbreaking-changes"></a><span data-ttu-id="fafa0-107">VS kesiliyor. Bölünemez değişiklikleri</span><span class="sxs-lookup"><span data-stu-id="fafa0-107">Breaking vs. Nonbreaking Changes</span></span>  
 <span data-ttu-id="fafa0-108">Bir veri sözleşmesi önemli değişiklikler veya bölünemez.</span><span class="sxs-lookup"><span data-stu-id="fafa0-108">Changes to a data contract can be breaking or nonbreaking.</span></span> <span data-ttu-id="fafa0-109">Veri sözleşmesi bölünemez şekilde değiştirildiğinde Sözleşmesi'nin daha eski sürümünü kullanan bir uygulamayı daha yeni sürümünü kullanarak bir uygulama ile iletişim kurabilir ve Sözleşmesi'nin daha yeni sürümünü kullanan bir uygulama bir uygulamayla iletişim kurabilir eski sürümü kullanıyor.</span><span class="sxs-lookup"><span data-stu-id="fafa0-109">When a data contract is changed in a nonbreaking way, an application using the older version of the contract can communicate with an application using the newer version, and an application using the newer version of the contract can communicate with an application using the older version.</span></span> <span data-ttu-id="fafa0-110">Diğer taraftan, önemli bir değişiklik bir ya da her iki yönde iletişimi engeller.</span><span class="sxs-lookup"><span data-stu-id="fafa0-110">On the other hand, a breaking change prevents communication in one or both directions.</span></span>  
  
 <span data-ttu-id="fafa0-111">Nasıl, gönderilen ve alınan etkilemeyen tüm değişiklikler türüne bölünemez.</span><span class="sxs-lookup"><span data-stu-id="fafa0-111">Any changes to a type that do not affect how it is transmitted and received are nonbreaking.</span></span> <span data-ttu-id="fafa0-112">Bu değişiklikleri veri sözleşmesi, yalnızca temel alınan tür değiştirmeyin.</span><span class="sxs-lookup"><span data-stu-id="fafa0-112">Such changes do not change the data contract, only the underlying type.</span></span> <span data-ttu-id="fafa0-113">Ardından ayarlarsanız, örneğin, bir alanın adını bölünemez şekilde değiştirebileceğiniz <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> özelliği <xref:System.Runtime.Serialization.DataMemberAttribute> eski sürüm adı.</span><span class="sxs-lookup"><span data-stu-id="fafa0-113">For example, you can change the name of a field in a nonbreaking way if you then set the <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to the older version name.</span></span> <span data-ttu-id="fafa0-114">Aşağıdaki kod, bir veri sözleşmesi 1 sürümünü gösterir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-114">The following code shows version 1 of a data contract.</span></span>  
  
 [!code-csharp[C_DataContractVersioning#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#1)]
 [!code-vb[C_DataContractVersioning#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#1)]  
  
 <span data-ttu-id="fafa0-115">Aşağıdaki kod bölünemez değişiklik gösterir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-115">The following code shows a nonbreaking change.</span></span>  
  
 [!code-csharp[C_DataContractVersioning#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#2)]
 [!code-vb[C_DataContractVersioning#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#2)]  
  
 <span data-ttu-id="fafa0-116">Bazı değişiklikler iletilen verileri değiştirebilir, ancak olabilir veya sonu değil.</span><span class="sxs-lookup"><span data-stu-id="fafa0-116">Some changes do modify the transmitted data, but may or may not be breaking.</span></span> <span data-ttu-id="fafa0-117">Her zaman yeni aşağıdaki değişiklikler:</span><span class="sxs-lookup"><span data-stu-id="fafa0-117">The following changes are always breaking:</span></span>  
  
-   <span data-ttu-id="fafa0-118">Değiştirme <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> veya <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> bir veri sözleşmesi değeri.</span><span class="sxs-lookup"><span data-stu-id="fafa0-118">Changing the <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> or <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A> value of a data contract.</span></span>  
  
-   <span data-ttu-id="fafa0-119">Veri üyeleri sırasını kullanarak değiştirme <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> özelliği <xref:System.Runtime.Serialization.DataMemberAttribute>.</span><span class="sxs-lookup"><span data-stu-id="fafa0-119">Changing the order of data members by using the <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute>.</span></span>  
  
-   <span data-ttu-id="fafa0-120">Bir veri üyesi yeniden adlandırılıyor.</span><span class="sxs-lookup"><span data-stu-id="fafa0-120">Renaming a data member.</span></span>  
  
-   <span data-ttu-id="fafa0-121">Veri sözleşmesi veri üyesi değiştirme.</span><span class="sxs-lookup"><span data-stu-id="fafa0-121">Changing the data contract of a data member.</span></span> <span data-ttu-id="fafa0-122">Örneğin, "Müşteri", "Kişi" adlı bir veri sözleşmesi ile bir türe adlı bir veri sözleşmesi ile bir dizeyi bir tamsayıya veya bir tür veri üyesi türünü değiştirme.</span><span class="sxs-lookup"><span data-stu-id="fafa0-122">For example, changing the type of data member from an integer to a string, or from a type with a data contract named "Customer" to a type with a data contract named "Person".</span></span>  
  
 <span data-ttu-id="fafa0-123">Aşağıdaki değişiklikleri da mümkündür.</span><span class="sxs-lookup"><span data-stu-id="fafa0-123">The following changes are also possible.</span></span>  
  
## <a name="adding-and-removing-data-members"></a><span data-ttu-id="fafa0-124">Ekleme ve kaldırma veri üyeleri</span><span class="sxs-lookup"><span data-stu-id="fafa0-124">Adding and Removing Data Members</span></span>  
 <span data-ttu-id="fafa0-125">Kesin Şema geçerlilik (yeni örnekleri eski şemasına göre doğrulanıyor) gerektirmedikçe çoğu durumda, ekleme veya kaldırma veri üye önemli bir değişiklik değil.</span><span class="sxs-lookup"><span data-stu-id="fafa0-125">In most cases, adding or removing a data member is not a breaking change, unless you require strict schema validity (new instances validating against the old schema).</span></span>  
  
 <span data-ttu-id="fafa0-126">Fazladan bir alan türüyle alanı eksik türüyle içine seri durumdan olduğunda, ek bilgileri göz ardı edilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-126">When a type with an extra field is deserialized into a type with a missing field, the extra information is ignored.</span></span> <span data-ttu-id="fafa0-127">(Ayrıca olabilir depolanan gidiş amacıyla; daha fazla bilgi için bkz: [İleri uyumlu veri sözleşmeleri](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)).</span><span class="sxs-lookup"><span data-stu-id="fafa0-127">(It may also be stored for round-tripping purposes; for more information, see [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)).</span></span>  
  
 <span data-ttu-id="fafa0-128">Eksik alan türüyle fazladan bir alan türüyle içine seri durumdan olduğunda, ek alan, varsayılan değer olarak bırakılır, genellikle sıfır veya `null`.</span><span class="sxs-lookup"><span data-stu-id="fafa0-128">When a type with a missing field is deserialized into a type with an extra field, the extra field is left at its default value, usually zero or `null`.</span></span> <span data-ttu-id="fafa0-129">(Varsayılan değer değiştirilebilir; daha fazla bilgi için bkz: [sürüm toleranslı seri hale getirme geri çağrıları](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md).)</span><span class="sxs-lookup"><span data-stu-id="fafa0-129">(The default value may be changed; for more information, see [Version-Tolerant Serialization Callbacks](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md).)</span></span>  
  
 <span data-ttu-id="fafa0-130">Örneğin, kullanabilirsiniz `CarV1` sınıfı bir istemcide ve `CarV2` sınıfı bir hizmet veya kullanabilir `CarV1` bir hizmet sınıfında ve `CarV2` bir istemcide sınıfı.</span><span class="sxs-lookup"><span data-stu-id="fafa0-130">For example, you can use the `CarV1` class on a client and the `CarV2` class on a service, or you can use the `CarV1` class on a service and the `CarV2` class on a client.</span></span>  
  
 [!code-csharp[C_DataContractVersioning#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractversioning/cs/source.cs#3)]
 [!code-vb[C_DataContractVersioning#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractversioning/vb/source.vb#3)]  
  
 <span data-ttu-id="fafa0-131">Sürüm 2 uç noktası başarıyla sürüm 1 uç noktasına veri gönderebilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-131">The version 2 endpoint can successfully send data to the version 1 endpoint.</span></span> <span data-ttu-id="fafa0-132">Biçimlendiricisi sürüm 2 `Car` veri sözleşmesi XML aşağıdakine benzer verir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-132">Serializing version 2 of the `Car` data contract yields XML similar to the following.</span></span>  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
    <HorsePower>300</HorsePower>  
</Car>  
```  
  
 <span data-ttu-id="fafa0-133">V1 seri durumdan çıkarma altyapısı için eşleşen bir veri üyesi bulamazsa `HorsePower` alan ve bu verileri atar.</span><span class="sxs-lookup"><span data-stu-id="fafa0-133">The deserialization engine on V1 does not find a matching data member for the `HorsePower` field, and discards that data.</span></span>  
  
 <span data-ttu-id="fafa0-134">Ayrıca, sürüm 1 endpoint sürüm 2 uç noktasına veri gönderebilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-134">Also, the version 1 endpoint can send data to the version 2 endpoint.</span></span> <span data-ttu-id="fafa0-135">Biçimlendiricisi sürümü 1 `Car` veri sözleşmesi XML aşağıdakine benzer verir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-135">Serializing version 1 of the `Car` data contract yields XML similar to the following.</span></span>  
  
```xml  
<Car>  
    <Model>Porsche</Model>  
</Car>  
```  
  
 <span data-ttu-id="fafa0-136">Sürüm 2 seri durumdan çıkarıcının ne ayarlamak bilmez `HorsePower` alanı, gelen XML içinde eşleşen verileri olduğundan.</span><span class="sxs-lookup"><span data-stu-id="fafa0-136">The version 2 deserializer does not know what to set the `HorsePower` field to, because there is no matching data in the incoming XML.</span></span> <span data-ttu-id="fafa0-137">Bunun yerine, alanın 0 varsayılan değerine ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="fafa0-137">Instead, the field is set to the default value of 0.</span></span>  
  
## <a name="required-data-members"></a><span data-ttu-id="fafa0-138">Gerekli veri üyeleri</span><span class="sxs-lookup"><span data-stu-id="fafa0-138">Required Data Members</span></span>  
 <span data-ttu-id="fafa0-139">Bir veri üyesi ayarlayarak gerektiği olarak işaretlenmiş olabilir <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> özelliği <xref:System.Runtime.Serialization.DataMemberAttribute> için `true`.</span><span class="sxs-lookup"><span data-stu-id="fafa0-139">A data member may be marked as being required by setting the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property of the <xref:System.Runtime.Serialization.DataMemberAttribute> to `true`.</span></span> <span data-ttu-id="fafa0-140">Veriler eksik kaldırılırken gerekirse, veri üyesi varsayılan değer olarak ayarlamak yerine bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="fafa0-140">If required data is missing while deserializing, an exception is thrown instead of setting the data member to its default value.</span></span>  
  
 <span data-ttu-id="fafa0-141">Gerekli veri üye ekleme sonu bir değişikliktir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-141">Adding a required data member is a breaking change.</span></span> <span data-ttu-id="fafa0-142">Diğer bir deyişle, yeni türü hala Uç noktalara eski türü, ancak şekilde geçici gönderilebilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-142">That is, the newer type can still be sent to endpoints with the older type, but not the other way around.</span></span> <span data-ttu-id="fafa0-143">Olarak işaretlenmiş bir veri üyesini kaldırma gereken tüm önceki sürümü de önemli bir değişiklik ' dir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-143">Removing a data member that was marked as required in any prior version is also a breaking change.</span></span>  
  
 <span data-ttu-id="fafa0-144">Değiştirme <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> özellik değerinden `true` için `false` değil parçalamak, ancak ondan değiştirme `false` için `true` türü önceki tüm sürümlerini veri üyesi yoksa söz konusu çiğnemekten.</span><span class="sxs-lookup"><span data-stu-id="fafa0-144">Changing the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property value from `true` to `false` is not breaking, but changing it from `false` to `true` may be breaking if any prior versions of the type do not have the data member in question.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fafa0-145">Ancak <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> özelliği ayarlanmış `true`, gelen veri boş olabilir veya sıfır ve bir türü olmalıdır hazırlanan bu olasılığı işlemek için.</span><span class="sxs-lookup"><span data-stu-id="fafa0-145">Although the <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> property is set to `true`, the incoming data may be null or zero, and a type must be prepared to handle this possibility.</span></span> <span data-ttu-id="fafa0-146">Kullanmayın <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> hatalı gelen veri karşı korumak için bir güvenlik mekanizması olarak.</span><span class="sxs-lookup"><span data-stu-id="fafa0-146">Do not use <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> as a security mechanism to protect against bad incoming data.</span></span>  
  
## <a name="omitted-default-values"></a><span data-ttu-id="fafa0-147">Belirtilmemişse varsayılan değerler</span><span class="sxs-lookup"><span data-stu-id="fafa0-147">Omitted Default Values</span></span>  
 <span data-ttu-id="fafa0-148">(Önerilmez rağmen) mümkündür ayarlamak için `EmitDefaultValue` örneğin özniteliğine özellik `false`açıklandığı gibi [veri üyesi varsayılan değerler](../../../../docs/framework/wcf/feature-details/data-member-default-values.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-148">It is possible (although not recommended) to set the `EmitDefaultValue` property on the DataMemberAttribute attribute to `false`, as described in [Data Member Default Values](../../../../docs/framework/wcf/feature-details/data-member-default-values.md).</span></span> <span data-ttu-id="fafa0-149">Bu ayar ise `false`, varsayılan değer olarak ayarlanırsa veri üyesi yayılan değil (genellikle boş veya sıfır).</span><span class="sxs-lookup"><span data-stu-id="fafa0-149">If this setting is `false`, the data member will not be emitted if it is set to its default value (usually null or zero).</span></span> <span data-ttu-id="fafa0-150">Bu iki yolla farklı sürümleri gerekli veri üyeleri ile uyumlu değil:</span><span class="sxs-lookup"><span data-stu-id="fafa0-150">This is not compatible with required data members in different versions in two ways:</span></span>  
  
-   <span data-ttu-id="fafa0-151">Bir veri sözleşmesine bir sürümünde gerekli bir veri üyesi varsayılan alamaz (null veya sıfır) farklı bir sürüm veri üyesi olan verileri `EmitDefaultValue` kümesine `false`.</span><span class="sxs-lookup"><span data-stu-id="fafa0-151">A data contract with a data member that is required in one version cannot receive default (null or zero) data from a different version in which the data member has `EmitDefaultValue` set to `false`.</span></span>  
  
-   <span data-ttu-id="fafa0-152">Gerekli veri üyesi olan `EmitDefaultValue` kümesine `false` varsayılan seri hale getirmek için kullanılamaz (null veya sıfır) değeri, ancak böyle bir değer seri durumdan çıkarma işleminde alabilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-152">A required data member that has `EmitDefaultValue` set to `false` cannot be used to serialize its default (null or zero) value, but can receive such a value on deserialization.</span></span> <span data-ttu-id="fafa0-153">Bu gidiş sorun oluşturur (veri okunabilir ancak aynı veri sonra yazılamaz).</span><span class="sxs-lookup"><span data-stu-id="fafa0-153">This creates a round-tripping problem (data can be read in but the same data cannot then be written out).</span></span> <span data-ttu-id="fafa0-154">Bu nedenle, varsa `IsRequired` olan `true` ve `EmitDefaultValue` olan `false` sağlayacak şekilde herhangi bir veri sözleşmesi sürümü bir gidiş dönüş sonuçlanmaz bir değer üretmek edebilir tüm diğer sürümleri için bir sürümde aynı bileşimini uygulamalıdır.</span><span class="sxs-lookup"><span data-stu-id="fafa0-154">Therefore, if `IsRequired` is `true` and `EmitDefaultValue` is `false` in one version, the same combination should apply to all other versions such that no version of the data contract would be able to produce a value that does not result in a round trip.</span></span>  
  
## <a name="schema-considerations"></a><span data-ttu-id="fafa0-155">Şema konuları</span><span class="sxs-lookup"><span data-stu-id="fafa0-155">Schema Considerations</span></span>  
 <span data-ttu-id="fafa0-156">Veri sözleşmesi türleri için hangi şema üretilen açıklama için bkz: [veri sözleşmesi şema başvurusu](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-156">For an explanation of what schema is produced for data contract types, see [Data Contract Schema Reference](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md).</span></span>  
  
 <span data-ttu-id="fafa0-157">Şema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] üretir veri sözleşme türleri için sürüm oluşturma için hiç hükümleri yapar.</span><span class="sxs-lookup"><span data-stu-id="fafa0-157">The schema [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces for data contract types makes no provisions for versioning.</span></span> <span data-ttu-id="fafa0-158">Diğer bir deyişle, yalnızca bu sürümde mevcut veri üyeleri bir türü sürümünden dışa aktarılan bir şema içeriyor.</span><span class="sxs-lookup"><span data-stu-id="fafa0-158">That is, the schema exported from a certain version of a type contains only those data members present in that version.</span></span> <span data-ttu-id="fafa0-159">Uygulama <xref:System.Runtime.Serialization.IExtensibleDataObject> arabirimi bir türüne ilişkin şema değiştirmez.</span><span class="sxs-lookup"><span data-stu-id="fafa0-159">Implementing the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface does not change the schema for a type.</span></span>  
  
 <span data-ttu-id="fafa0-160">Veri üyeleri için şema varsayılan olarak isteğe bağlı öğeleri olarak dışarı aktarılır.</span><span class="sxs-lookup"><span data-stu-id="fafa0-160">Data members are exported to the schema as optional elements by default.</span></span> <span data-ttu-id="fafa0-161">Diğer bir deyişle, `minOccurs` (XML özniteliği) değerini 0 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="fafa0-161">That is, the `minOccurs` (XML attribute) value is set to 0.</span></span> <span data-ttu-id="fafa0-162">Gerekli veri üyeleri ile verilir `minOccurs` 1 olarak ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="fafa0-162">Required data members are exported with `minOccurs` set to 1.</span></span>  
  
 <span data-ttu-id="fafa0-163">Değişikliklerin birçoğunu kabul olmasını bölünemez gerçekte şemaya katı bağlılığı gerekiyorsa sonu.</span><span class="sxs-lookup"><span data-stu-id="fafa0-163">Many of the changes considered to be nonbreaking are actually breaking if strict adherence to the schema is required.</span></span> <span data-ttu-id="fafa0-164">Önceki örnekte, bir `CarV1` örneği yalnızca `Model` öğesi doğrulamak karşı `CarV2` şeması (her ikisi de olan `Model` ve `Horsepower`, ancak her ikisi de isteğe bağlı).</span><span class="sxs-lookup"><span data-stu-id="fafa0-164">In the preceding example, a `CarV1` instance with just the `Model` element would validate against the `CarV2` schema (which has both `Model` and `Horsepower`, but both are optional).</span></span> <span data-ttu-id="fafa0-165">Ancak, bu durumun tersi geçerli değildir: bir `CarV2` örneği karşı doğrulama başarısız olurdu `CarV1` şema.</span><span class="sxs-lookup"><span data-stu-id="fafa0-165">However, the reverse is not true: a `CarV2` instance would fail validation against the `CarV1` schema.</span></span>  
  
 <span data-ttu-id="fafa0-166">Gidiş ayrıca bazı hususlar kapsar.</span><span class="sxs-lookup"><span data-stu-id="fafa0-166">Round-tripping also entails some additional considerations.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fafa0-167">"Şema hususlar" bölümünde [İleri uyumlu veri sözleşmeleri](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-167"> the "Schema Considerations" section in [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
### <a name="other-permitted-changes"></a><span data-ttu-id="fafa0-168">Diğer değişiklikler de izin verilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-168">Other Permitted Changes</span></span>  
 <span data-ttu-id="fafa0-169">Uygulama <xref:System.Runtime.Serialization.IExtensibleDataObject> bölünemez değişikliği bir arabirimdir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-169">Implementing the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface is a nonbreaking change.</span></span> <span data-ttu-id="fafa0-170">Ancak, gidiş destek türü olan sürümden önceki sürümler için yok <xref:System.Runtime.Serialization.IExtensibleDataObject> uygulanmıştır.</span><span class="sxs-lookup"><span data-stu-id="fafa0-170">However, round-tripping support does not exist for versions of the type prior to the version in which <xref:System.Runtime.Serialization.IExtensibleDataObject> was implemented.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fafa0-171">[İleri uyumlu veri sözleşmeleri](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-171"> [Forward-Compatible Data Contracts](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md).</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="fafa0-172">Numaralandırmalar</span><span class="sxs-lookup"><span data-stu-id="fafa0-172">Enumerations</span></span>  
 <span data-ttu-id="fafa0-173">Kesme ekleyerek veya kaldırarak bir numaralandırma üyesine farklıdır.</span><span class="sxs-lookup"><span data-stu-id="fafa0-173">Adding or removing an enumeration member is a breaking change.</span></span> <span data-ttu-id="fafa0-174">Bir numaralandırma üyesine adının değiştirilmesi parçalamak, sözleşme adının eski sürüm ile aynı kullanarak tutulur sürece `EnumMemberAtttribute` özniteliği.</span><span class="sxs-lookup"><span data-stu-id="fafa0-174">Changing the name of an enumeration member is breaking, unless its contract name is kept the same as in the old version by using the `EnumMemberAtttribute` attribute.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="fafa0-175">[Veri sözleşmelerinde Numaralandırma türleri](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-175"> [Enumeration Types in Data Contracts](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).</span></span>  
  
## <a name="collections"></a><span data-ttu-id="fafa0-176">Koleksiyonlar</span><span class="sxs-lookup"><span data-stu-id="fafa0-176">Collections</span></span>  
 <span data-ttu-id="fafa0-177">Çoğu koleksiyonu değişiklikler bölünemez çoğu koleksiyon türü veri sözleşmesi modelinde birbirleri ile karşılıklı olduğundan.</span><span class="sxs-lookup"><span data-stu-id="fafa0-177">Most collection changes are nonbreaking because most collection types are interchangeable with each other in the data contract model.</span></span> <span data-ttu-id="fafa0-178">Ancak, özelleştirilmiş bir noncustomized koleksiyon yapma veya tersi önemli bir değişiklik olabilir.</span><span class="sxs-lookup"><span data-stu-id="fafa0-178">However, making a noncustomized collection customized or vice versa is a breaking change.</span></span> <span data-ttu-id="fafa0-179">Ayrıca, koleksiyonun özelleştirme ayarlarını değiştirmek önemli bir değişiklik, diğer bir deyişle, kendi veri sözleşme adına ve ad alanı, yinelenen öğe adı, anahtar öğe adı ve değeri öğe adı değiştirme.</span><span class="sxs-lookup"><span data-stu-id="fafa0-179">Also, changing the collection's customization settings is a breaking change; that is, changing its data contract name and namespace, repeating element name, key element name, and value element name.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="fafa0-180">Koleksiyon özelleştirme bkz [veri sözleşmelerinde koleksiyon türleri](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="fafa0-180"> collection customization, see [Collection Types in Data Contracts](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).</span></span>  
<span data-ttu-id="fafa0-181">Doğal olarak, koleksiyon (örneğin, bir tamsayı listesinden dizeleri listesine değiştirme) içeriğinin veri sözleşmesi değiştirmek önemli bir değişiklik.</span><span class="sxs-lookup"><span data-stu-id="fafa0-181">Naturally, changing the data contract of contents of a collection (for example, changing from a list of integers to a list of strings) is a breaking change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fafa0-182">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="fafa0-182">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute.Name%2A>  
 <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.Order%2A>  
 <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A>  
 <xref:System.Runtime.Serialization.SerializationException>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 [<span data-ttu-id="fafa0-183">Sürüm toleranslı seri hale getirme geri çağrıları</span><span class="sxs-lookup"><span data-stu-id="fafa0-183">Version-Tolerant Serialization Callbacks</span></span>](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)  
 [<span data-ttu-id="fafa0-184">En iyi uygulamalar: Veri sözleşmesi sürümü oluşturma</span><span class="sxs-lookup"><span data-stu-id="fafa0-184">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)  
 [<span data-ttu-id="fafa0-185">Veri sözleşmelerini kullanma</span><span class="sxs-lookup"><span data-stu-id="fafa0-185">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="fafa0-186">Veri sözleşmesi eşitliği</span><span class="sxs-lookup"><span data-stu-id="fafa0-186">Data Contract Equivalence</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [<span data-ttu-id="fafa0-187">İleri uyumlu veri sözleşmeleri</span><span class="sxs-lookup"><span data-stu-id="fafa0-187">Forward-Compatible Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)