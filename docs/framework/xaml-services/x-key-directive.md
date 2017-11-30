---
title: "x:Key Yönergesi"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- xKey
- Key
- x:Key
helpviewer_keywords:
- x:Key attribute [XAML Services]
- Key attribute in XAML [XAML Services]
- XAML [XAML Services], x:Key attribute
ms.assetid: 1985cd45-f197-42d5-b75e-886add64b248
caps.latest.revision: "25"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5e2ad03fcb52db1ffdd01849381a392187082991
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="xkey-directive"></a><span data-ttu-id="a17ee-102">x:Key Yönergesi</span><span class="sxs-lookup"><span data-stu-id="a17ee-102">x:Key Directive</span></span>
<span data-ttu-id="a17ee-103">Oluşturulan ve XAML tanımlı bir sözlükte başvurulan öğeleri benzersiz şekilde tanımlar.</span><span class="sxs-lookup"><span data-stu-id="a17ee-103">Uniquely identifies elements that are created and referenced in a XAML-defined dictionary.</span></span> <span data-ttu-id="a17ee-104">Ekleme bir `x:Key` değerdir XAML nesne öğesi için bir kaynak örneğin bir WPF içinde bir kaynak sözlüğü olarak tanımlamak için en yaygın yolu <xref:System.Windows.ResourceDictionary>.</span><span class="sxs-lookup"><span data-stu-id="a17ee-104">Adding an `x:Key` value to a XAML object element is the most common way to identify a resource in a resource dictionary, for example in a WPF <xref:System.Windows.ResourceDictionary>.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="a17ee-105">XAML Öznitelik Kullanımı</span><span class="sxs-lookup"><span data-stu-id="a17ee-105">XAML Attribute Usage</span></span>  
  
```  
<object x:Key="stringKeyValue".../>  
-or-  
<object x:Key="{markupExtensionUsage}".../>  
```  
  
## <a name="xaml-attribute-usage-wpf-specific"></a><span data-ttu-id="a17ee-106">XAML öznitelik kullanımı (WPF özgü)</span><span class="sxs-lookup"><span data-stu-id="a17ee-106">XAML Attribute Usage (WPF-specific)</span></span>  
  
```  
<object.Resources>  
  <object x:Key="stringKeyValue".../>  
</object.Resources>  
-or-  
<object.Resources>  
  <object x:Key="{markupExtensionUsage}".../>  
</object.Resources>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="a17ee-107">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="a17ee-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`stringKeyValue`|<span data-ttu-id="a17ee-108">Bir anahtar olarak kullanılacak bir metin dizesi.</span><span class="sxs-lookup"><span data-stu-id="a17ee-108">A text string to use as a key.</span></span> <span data-ttu-id="a17ee-109">Metin dizesi uygun olmalıdır [XamlName Dilbilgisi](../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-109">The text string must conform to the [XamlName Grammar](../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span>|  
|`markupExtensionUsage`|<span data-ttu-id="a17ee-110">Biçimlendirme uzantısı sınırlayıcıları {} içinde bir biçimlendirme uzantısı kullanımı, bir anahtar olarak kullanılacak bir nesne sağlar.</span><span class="sxs-lookup"><span data-stu-id="a17ee-110">Within the markup extension delimiters {}, a markup extension usage that provides an object to use as a key.</span></span> <span data-ttu-id="a17ee-111">Açıklamalar bakın.</span><span class="sxs-lookup"><span data-stu-id="a17ee-111">See Remarks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a17ee-112">Açıklamalar</span><span class="sxs-lookup"><span data-stu-id="a17ee-112">Remarks</span></span>  
 <span data-ttu-id="a17ee-113">`x:Key`XAML kaynağı sözlük kavramını destekler.</span><span class="sxs-lookup"><span data-stu-id="a17ee-113">`x:Key` supports the XAML resource dictionary concept.</span></span> <span data-ttu-id="a17ee-114">Belirli kullanıcı Arabirimi çerçeveleri sol bir kaynak sözlüğü uygulaması, XAML dili olarak tanımlamıyor.</span><span class="sxs-lookup"><span data-stu-id="a17ee-114">XAML as a language doesn't define a resource dictionary implementation, that is left to specific UI frameworks.</span></span> <span data-ttu-id="a17ee-115">WPF'de XAML kaynak sözlüklerindeki nasıl uygulandığı hakkında daha fazla bilgi için bkz: [XAML kaynakları](../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-115">To learn more about how XAML resource dictionaries are implemented in WPF, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="a17ee-116">XAML 2006 ve WPF, `x:Key` bir özniteliği olarak sağlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-116">In XAML 2006 and WPF, `x:Key` must be provided as an attribute.</span></span> <span data-ttu-id="a17ee-117">Dize olmayan anahtarlarını kullanmaya devam edebilirsiniz, ancak bu öznitelik formda dize olmayan değeri sağlamak için bir biçimlendirme uzantısı kullanımı gerektirir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-117">You can still use nonstring keys, but this requires a markup extension usage in order to provide the nonstring value in attribute form.</span></span> <span data-ttu-id="a17ee-118">XAML 2009 kullanıyorsanız `x:Key` belirtilebilir bir öğe açıkça nesne türleri tarafından dışında anahtarlı sözlükler desteklemek için dizeleri Ara biçimlendirme uzantısı gerek kalmadan.</span><span class="sxs-lookup"><span data-stu-id="a17ee-118">If you are using XAML 2009, `x:Key` can be specified as an element, to explicitly support dictionaries keyed by object types other than strings without requiring a markup extension intermediate.</span></span> <span data-ttu-id="a17ee-119">Bu konudaki "XAML 2009" bölümüne bakın.</span><span class="sxs-lookup"><span data-stu-id="a17ee-119">See the "XAML 2009" section in this topic.</span></span> <span data-ttu-id="a17ee-120">Açıklamalar bölümüne geri kalanı özellikle XAML 2006 uygulaması için geçerlidir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-120">The remainder of the Remarks section applies specifically to the XAML 2006 implementation.</span></span>  
  
 <span data-ttu-id="a17ee-121">Öznitelik değeri `x:Key` herhangi bir dize olarak tanımlanabilir [XamlName Dilbilgisi](../../../docs/framework/xaml-services/xamlname-grammar.md) veya can biçimlendirme uzantısı aracılığıyla hesaplanan bir nesne olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-121">The attribute value of `x:Key` can be any string defined in the [XamlName Grammar](../../../docs/framework/xaml-services/xamlname-grammar.md) or can be an object evaluated through a markup extension.</span></span> <span data-ttu-id="a17ee-122">"WPF kullanım notları" WPF bir örnek için bkz.</span><span class="sxs-lookup"><span data-stu-id="a17ee-122">See "WPF Usage Notes" for an example from WPF.</span></span>  
  
 <span data-ttu-id="a17ee-123">Alt öğeleri olan bir üst öğesi bir <xref:System.Collections.IDictionary> uygulaması genellikle içermelidir bir `x:Key` Bu sözlük içinde benzersiz bir anahtar değeri belirten özniteliği.</span><span class="sxs-lookup"><span data-stu-id="a17ee-123">Child elements of a parent element that is an <xref:System.Collections.IDictionary> implementation must typically include an `x:Key` attribute that specifies a unique key value within that dictionary.</span></span> <span data-ttu-id="a17ee-124">Çerçeveler yerine için anahtar özellikler diğer uygulamak `x:Key` belirli türlerinde; gibi özellikleri tanımlamak türleri ile öznitelikli <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a17ee-124">Frameworks might implement aliased key properties to substitute for `x:Key` on particular types; types that define such properties should be attributed with <xref:System.Windows.Markup.DictionaryKeyPropertyAttribute>.</span></span>  
  
 <span data-ttu-id="a17ee-125">Belirtmenin kod eşdeğer `x:Key` arka plandaki için kullanılan anahtardır <xref:System.Collections.IDictionary>.</span><span class="sxs-lookup"><span data-stu-id="a17ee-125">The code equivalent of specifying `x:Key` is the key that is used for the underlying <xref:System.Collections.IDictionary>.</span></span> <span data-ttu-id="a17ee-126">Örneğin, bir `x:Key` uygulanan biçimlendirme WPF kaynak değerine denktir için `key` parametresinin <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> bir WPF kaynak eklediğinizde <xref:System.Windows.ResourceDictionary> kod.</span><span class="sxs-lookup"><span data-stu-id="a17ee-126">For example, an `x:Key` that is applied in markup for a resource in WPF is equivalent to the value of the `key` parameter of <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> when you add the resource to a WPF <xref:System.Windows.ResourceDictionary> in code.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="a17ee-127">WPF kullanım notları</span><span class="sxs-lookup"><span data-stu-id="a17ee-127">WPF Usage Notes</span></span>  
 <span data-ttu-id="a17ee-128">Bir üst alt nesnelerin nesne başka bir deyişle bir <xref:System.Collections.IDictionary> WPF gibi uygulama <xref:System.Windows.ResourceDictionary>, genellikle içermelidir bir `x:Key` özniteliği ve anahtar değeri bu sözlük içinde benzersiz olmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-128">Child objects of a parent object that is an <xref:System.Collections.IDictionary> implementation, such as the WPF <xref:System.Windows.ResourceDictionary>, must typically include an `x:Key` attribute, and the key value must be unique within that dictionary.</span></span> <span data-ttu-id="a17ee-129">İki önemli özel durum vardır:</span><span class="sxs-lookup"><span data-stu-id="a17ee-129">There are two notable exceptions:</span></span>  
  
-   <span data-ttu-id="a17ee-130">Bazı WPF türleri sözlük kullanım için örtük bir anahtar bildirin.</span><span class="sxs-lookup"><span data-stu-id="a17ee-130">Some WPF types declare an implicit key for dictionary usage.</span></span> <span data-ttu-id="a17ee-131">Örneğin, bir <xref:System.Windows.Style> ile bir <xref:System.Windows.Style.TargetType%2A>, veya bir <xref:System.Windows.DataTemplate> ile bir <xref:System.Windows.DataTemplate.DataType%2A>, kullanılabilir bir <xref:System.Windows.ResourceDictionary> ve örtülü anahtar kullanın.</span><span class="sxs-lookup"><span data-stu-id="a17ee-131">For example, a <xref:System.Windows.Style> with a <xref:System.Windows.Style.TargetType%2A>, or a <xref:System.Windows.DataTemplate> with a <xref:System.Windows.DataTemplate.DataType%2A>, can be  in a <xref:System.Windows.ResourceDictionary> and use the implicit key.</span></span>  
  
-   <span data-ttu-id="a17ee-132">WPF birleştirilmiş kaynak sözlüğü kavramını destekler.</span><span class="sxs-lookup"><span data-stu-id="a17ee-132">WPF supports a merged resource dictionary concept.</span></span> <span data-ttu-id="a17ee-133">Anahtarları birleştirilmiş sözlükler arasında paylaşılabilir ve paylaşılan anahtar davranışı kullanılarak erişilebilir <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span><span class="sxs-lookup"><span data-stu-id="a17ee-133">Keys can be shared between the merged dictionaries, and the shared key behavior can be accessed using <xref:System.Windows.FrameworkContentElement.FindResource%2A>.</span></span> <span data-ttu-id="a17ee-134">Daha fazla bilgi için bkz: [birleştirilmiş kaynak sözlükleri](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-134">For more information, see [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
 <span data-ttu-id="a17ee-135">Genel WPF XAML uygulama ve uygulama modeli, anahtar benzersizlik XAML biçimlendirme derleyici tarafından kontrol edilmez.</span><span class="sxs-lookup"><span data-stu-id="a17ee-135">In the overall WPF XAML implementation and application model, key uniqueness is not checked by the XAML markup compiler.</span></span> <span data-ttu-id="a17ee-136">Bunun yerine, eksik veya benzer `x:Key` değerleri yükleme zamanı XAML ayrıştırıcı hatalarına neden olabilir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-136">Instead, missing or nonunique `x:Key` values cause load-time XAML parser errors.</span></span> <span data-ttu-id="a17ee-137">Ancak, [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] genellikle gibi hataları WPF tasarım aşamasında fark edebilirsiniz için sözlükleri işleme.</span><span class="sxs-lookup"><span data-stu-id="a17ee-137">However, [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)] handling of dictionaries for WPF can often note such errors in the design phase.</span></span>  
  
 <span data-ttu-id="a17ee-138">Gösterilen sözdiziminde unutmayın <xref:System.Windows.ResourceDictionary> nesnesidir nasıl WPF XAML işlemci üreten bir koleksiyonun doldurmak için örtük bir <xref:System.Windows.FrameworkElement.Resources%2A> koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="a17ee-138">Note that in the syntax shown, the <xref:System.Windows.ResourceDictionary> object is implicit in how the WPF XAML processor produces a collection to populate a <xref:System.Windows.FrameworkElement.Resources%2A> collection.</span></span> <span data-ttu-id="a17ee-139">A <xref:System.Windows.ResourceDictionary> bazı durumlarda daha anlaşılır olması için istediyseniz olabilir ancak genellikle açıkça biçimlendirme, bir öğe olarak sağlanmadı (bir koleksiyon nesnesi öğesi arasında olacaktır <xref:System.Windows.FrameworkElement.Resources%2A> özellik öğesi ve öğeleri içindeki doldurma Sözlük).</span><span class="sxs-lookup"><span data-stu-id="a17ee-139">A <xref:System.Windows.ResourceDictionary> is not typically provided explicitly as an element in markup, although it can be in some cases if wanted for clarity (it would be a collection object element between the <xref:System.Windows.FrameworkElement.Resources%2A> property element and the items within that populate the dictionary).</span></span> <span data-ttu-id="a17ee-140">Bir koleksiyon nesnesi örtük öğenin biçimlendirmesi içinde neredeyse her zaman neden olduğu hakkında daha fazla bilgi için bkz: [içinde XAML sözdizimi ayrıntı](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-140">For information about why a collection object is almost always an implicit element in markup, see [XAML Syntax In Detail](../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md).</span></span>  
  
 <span data-ttu-id="a17ee-141">WPF XAML uygulamasında kaynak sözlük anahtarları için işleme tarafından tanımlanan <xref:System.Windows.ResourceKey> soyut sınıf.</span><span class="sxs-lookup"><span data-stu-id="a17ee-141">In the WPF XAML implementation, the handling for resource dictionary keys is defined by the <xref:System.Windows.ResourceKey> abstract class.</span></span> <span data-ttu-id="a17ee-142">Ancak WPF XAML işlemci kullanımlarının üzerinde temel anahtarları için farklı temel uzantı türleri oluşturur.</span><span class="sxs-lookup"><span data-stu-id="a17ee-142">However the WPF XAML processor produces different underlying extension types for keys based on their usages.</span></span> <span data-ttu-id="a17ee-143">Örneğin, anahtar için bir <xref:System.Windows.DataTemplate> veya türetilmiş bir sınıf ayrı ayrı işlenir ve farklı üretir <xref:System.Windows.DataTemplateKey> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="a17ee-143">For example, the key for a <xref:System.Windows.DataTemplate> or any derived class is handled separately, and produces a distinct <xref:System.Windows.DataTemplateKey> object.</span></span>  
  
 <span data-ttu-id="a17ee-144">Anahtarlar ve adları farklı yönergeleri ve dil öğeleri kullanın (`x:Key` karşı `x:Name`) temel XAML tanımı'nda.</span><span class="sxs-lookup"><span data-stu-id="a17ee-144">Keys and names use different directives and language elements (`x:Key` versus `x:Name`) in the basic XAML definition.</span></span> <span data-ttu-id="a17ee-145">Ayrıca anahtarları ve adları farklı durumlarda WPF tanım ve bu kavramları uygulama tarafından kullanılır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-145">Keys and names are also used in different situations by the WPF definition and application of these concepts.</span></span> <span data-ttu-id="a17ee-146">Ayrıntılar için bkz [WPF XAML ad kapsamları](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-146">For details, see [WPF XAML Namescopes](../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md).</span></span>  
  
 <span data-ttu-id="a17ee-147">Daha önce belirtildiği gibi bir anahtarın değerini biçimlendirme uzantısı aracılığıyla sağlanabilir ve dışında bir dize değeri olabilir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-147">As stated previously, the value of a key can be supplied through a markup extension and can be other than a string value.</span></span> <span data-ttu-id="a17ee-148">Örnek bir WPF senaryo, değeri `x:Key` olabilir bir[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-148">An example WPF scenario is that the value of `x:Key` may be a[ComponentResourceKey](../../../docs/framework/wpf/advanced/componentresourcekey-markup-extension.md).</span></span> <span data-ttu-id="a17ee-149">Belirli denetimleri bu tür tamamen stili değiştirmeden bölümü görünümünü ve davranışını denetleyen etkilediğini özel stil kaynağı için bir stil anahtarı kullanır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-149">Certain controls expose a style key of that type for a custom style resource that influences part of the appearance and behavior of that control without totally replacing the style.</span></span> <span data-ttu-id="a17ee-150">Böyle bir anahtar örneğidir <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="a17ee-150">An example of such a key is <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>.</span></span>  
  
 <span data-ttu-id="a17ee-151">WPF birleştirilmiş sözlük özelliği anahtar benzersizliği ve anahtar arama davranışı için ek hususlar sunmaktadır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-151">The WPF merged dictionary feature introduces additional considerations for key uniqueness and key lookup behavior.</span></span> <span data-ttu-id="a17ee-152">Daha fazla bilgi için bkz: [birleştirilmiş kaynak sözlükleri](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span><span class="sxs-lookup"><span data-stu-id="a17ee-152">For more information, see [Merged Resource Dictionaries](../../../docs/framework/wpf/advanced/merged-resource-dictionaries.md).</span></span>  
  
## <a name="xaml-2009"></a><span data-ttu-id="a17ee-153">XAML 2009</span><span class="sxs-lookup"><span data-stu-id="a17ee-153">XAML 2009</span></span>  
 <span data-ttu-id="a17ee-154">XAML 2009 rahatlatır kısıtlama, `x:Key` özniteliği formunda her zaman sağlanmalıdır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-154">XAML 2009 relaxes the restriction that `x:Key` always be provided in attribute form.</span></span>  
  
 <span data-ttu-id="a17ee-155">WPF'de, ancak yalnızca biçimlendirme-derlenmemiş XAML için XAML 2009 özellikleri kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="a17ee-155">In WPF, you can use XAML 2009 features, but only for XAML that is not markup-compiled.</span></span> <span data-ttu-id="a17ee-156">XAML biçimlendirme derlenmiş WPF ve XAML BAML form için şu anda desteklemediği XAML 2009 anahtar sözcükleri ve özellikler.</span><span class="sxs-lookup"><span data-stu-id="a17ee-156">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span>  
  
 <span data-ttu-id="a17ee-157">XAML 2009 altında belirttiğiniz `x:Key` aşağıdaki kullanımı aracılığıyla öğelerin:</span><span class="sxs-lookup"><span data-stu-id="a17ee-157">Under XAML 2009, you can specify `x:Key` elements through the following usage:</span></span>  
  
### <a name="xaml-element-usage-xaml-2009-only"></a><span data-ttu-id="a17ee-158">XAML öğesi kullanımı (yalnızca XAML 2009)</span><span class="sxs-lookup"><span data-stu-id="a17ee-158">XAML Element Usage (XAML 2009 only)</span></span>  
  
```  
<object>  
  <x:Key>  
keyObject  
  </x:Key>  
...  
</object>  
```  
  
### <a name="xaml-values"></a><span data-ttu-id="a17ee-159">XAML Değerleri</span><span class="sxs-lookup"><span data-stu-id="a17ee-159">XAML Values</span></span>  
  
|||  
|-|-|  
|`keyObject`|<span data-ttu-id="a17ee-160">Object öğesi için anahtar olarak kullanılan nesne için bir verilen `object` özel sözlükteki.</span><span class="sxs-lookup"><span data-stu-id="a17ee-160">Object element for the object that is used as the key for a given `object` in a specialized dictionary.</span></span>|  
  
-   <span data-ttu-id="a17ee-161">Bu tür bir kullanım için kapsayıcı/üst burada gösterilmiyor.</span><span class="sxs-lookup"><span data-stu-id="a17ee-161">The container/parent for this kind of use is not shown here.</span></span> <span data-ttu-id="a17ee-162">`object`Özel sözlük uygulamasını temsil eder bir nesne öğenin alt öğesi olması beklenir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-162">`object` is expected to be a child of an object element that represents a specialized dictionary implementation.</span></span> <span data-ttu-id="a17ee-163">`keyObject`bir nesne örneği (veya bir değer türünde bir değer) olması bekleniyor, belirli özel sözlük uygulaması için anahtar olarak uygun olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="a17ee-163">`keyObject` is expected to be an object instance (or a value of a value type) that is appropriate as the key for that particular specialized dictionary implementation.</span></span>  
  
-   <span data-ttu-id="a17ee-164">WPF bu kullanımını gerektiren sözlükler uygulamıyor.</span><span class="sxs-lookup"><span data-stu-id="a17ee-164">WPF does not implement dictionaries that require this usage.</span></span> <span data-ttu-id="a17ee-165">Nesne anahtarları özelliğidir daha genel XAML'de sözlük oluşturma arzu olduğu belirli özel sözlük senaryolar için büyük olasılıkla yararlı XAML dili.</span><span class="sxs-lookup"><span data-stu-id="a17ee-165">Object keys is more a general feature of the XAML language, possibly useful for certain custom dictionary scenarios where creating the dictionary in XAML is desirable.</span></span> <span data-ttu-id="a17ee-166">Bir nesne anahtarı kullanarak gerekli değildir kaynaklar için dize olmayan tuşlarını örtülü stiller gibi WPF özellikleri için oluşturma veya anahtarları belirleme için başka teknikler, mevcut.</span><span class="sxs-lookup"><span data-stu-id="a17ee-166">For WPF features such as implicit styles that use non-string keys for resources, other techniques for establishing or specifying the keys exist, so using an object key is not necessary.</span></span>  
  
-   <span data-ttu-id="a17ee-167">*keyObject* biçimlendirme uzantısı kullanımı doğrudan nesne örneği yerine nesne öğesi formu de olabilir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-167">*keyObject* could also be a markup extension usage in object element form, rather than a direct object instance.</span></span>  
  
## <a name="silverlight-usage-notes"></a><span data-ttu-id="a17ee-168">Silverlight kullanım notları</span><span class="sxs-lookup"><span data-stu-id="a17ee-168">Silverlight Usage Notes</span></span>  
 <span data-ttu-id="a17ee-169">`x:Key`Silverlight için ayrı olarak belgelenmiştir.</span><span class="sxs-lookup"><span data-stu-id="a17ee-169">`x:Key` for Silverlight is documented separately.</span></span> <span data-ttu-id="a17ee-170">Daha fazla bilgi için bkz: [XAML Namespace (x:) Dil özellikleri (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).</span><span class="sxs-lookup"><span data-stu-id="a17ee-170">For more information, see [XAML Namespace (x:) Language Features (Silverlight)](http://go.microsoft.com/fwlink/?LinkId=199081).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a17ee-171">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="a17ee-171">See Also</span></span>  
 [<span data-ttu-id="a17ee-172">XAML kaynakları</span><span class="sxs-lookup"><span data-stu-id="a17ee-172">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="a17ee-173">Kaynaklar ve kod</span><span class="sxs-lookup"><span data-stu-id="a17ee-173">Resources and Code</span></span>](../../../docs/framework/wpf/advanced/resources-and-code.md)  
 [<span data-ttu-id="a17ee-174">StaticResource biçimlendirme uzantısı</span><span class="sxs-lookup"><span data-stu-id="a17ee-174">StaticResource Markup Extension</span></span>](../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)