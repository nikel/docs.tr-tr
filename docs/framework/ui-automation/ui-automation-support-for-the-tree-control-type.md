---
title: "Ağaç Denetim Türü İçin UI Otomasyon Desteği"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- control types, Tree
- Tree control type
- UI Automation, Tree control type
ms.assetid: 312dd04d-a86b-4072-8b12-2beeabdff5e3
caps.latest.revision: "20"
author: Xansky
ms.author: mhopkins
manager: markl
ms.openlocfilehash: 7468a7a85d6770e1953aa8c3dd39c9895999d188
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ui-automation-support-for-the-tree-control-type"></a><span data-ttu-id="50d93-102">Ağaç Denetim Türü İçin UI Otomasyon Desteği</span><span class="sxs-lookup"><span data-stu-id="50d93-102">UI Automation Support for the Tree Control Type</span></span>
> [!NOTE]
>  <span data-ttu-id="50d93-103">Bu belge yönetilen kullanmak isteyen .NET Framework için tasarlanan [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tanımlanan sınıflar <xref:System.Windows.Automation> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="50d93-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="50d93-104">Hakkında en yeni bilgiler için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], bkz: [Windows Otomasyon API: UI Otomasyonu](http://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="50d93-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="50d93-105">Bu konu aşağıdakiler hakkında bilgi sağlar [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç denetim türü için destek.</span><span class="sxs-lookup"><span data-stu-id="50d93-105">This topic provides information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] support for the Tree control type.</span></span> <span data-ttu-id="50d93-106">İçinde [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], Denetim türü bir denetimi kullanmak için karşılaması gereken koşulları kümesidir <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> özelliği.</span><span class="sxs-lookup"><span data-stu-id="50d93-106">In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], a control type is a set of conditions that a control must meet in order to use the <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> property.</span></span> <span data-ttu-id="50d93-107">Koşullar özel yönergeleri dahil [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç yapısı, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] özellik değerlerini ve denetim düzenleri.</span><span class="sxs-lookup"><span data-stu-id="50d93-107">The conditions include specific guidelines for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] property values, and control patterns.</span></span>  
  
 <span data-ttu-id="50d93-108">İşlemleriyle dosya ve klasörleri'nin sol bölmesinde görüntülendiği gibi ağaç denetim türü içerikleri sahip bir hiyerarşi düğüm olarak ilgi kapsayıcıları için kullanılan [!INCLUDE[TLA#tla_winexpl](../../../includes/tlasharptla-winexpl-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50d93-108">The Tree control type is used for containers whose contents have relevance as a hierarchy of nodes, as with the way files and folders are displayed in the left pane of [!INCLUDE[TLA#tla_winexpl](../../../includes/tlasharptla-winexpl-md.md)].</span></span> <span data-ttu-id="50d93-109">Her düğümün alt düğümleri olarak adlandırılan, diğer düğümleri içerecek şekilde olasılığı vardır.</span><span class="sxs-lookup"><span data-stu-id="50d93-109">Each node has the potential to contain other nodes, called child nodes.</span></span> <span data-ttu-id="50d93-110">Üst düğüm ya da alt düğümleri içeren düğümleri görüntülenebilir genişletilmiş olarak veya daraltılmış.</span><span class="sxs-lookup"><span data-stu-id="50d93-110">Parent nodes, or nodes that contain child nodes, can be displayed as expanded or collapsed.</span></span>  
  
 <span data-ttu-id="50d93-111">Aşağıdaki bölümlerde gerekli tanımlamak [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç yapısı, özellikler, Denetim desenleri ve olayları ağaç denetim türü için.</span><span class="sxs-lookup"><span data-stu-id="50d93-111">The following sections define the required [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree structure, properties, control patterns, and events for the Tree control type.</span></span> <span data-ttu-id="50d93-112">[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Gereksinimleri tüm ağaç denetimleri için geçerli olup olmadığını [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], veya [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="50d93-112">The [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] requirements apply to all tree controls, whether [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], or [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a><span data-ttu-id="50d93-113">Gerekli UI Otomasyon ağaç yapısı</span><span class="sxs-lookup"><span data-stu-id="50d93-113">Required UI Automation Tree Structure</span></span>  
 <span data-ttu-id="50d93-114">Denetim Görünüm ve içerik görünümünü aşağıdaki tabloda gösterilmektedir [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , ağaç denetimleri için geçerlidir ve her bir görünümde bulunabilir açıklayan ağacı.</span><span class="sxs-lookup"><span data-stu-id="50d93-114">The following table depicts the control view and the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree that pertains to tree controls and describes what can be contained in each view.</span></span> <span data-ttu-id="50d93-115">Daha fazla bilgi için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç bkz [UI Otomasyon ağacına genel bakış](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50d93-115">For more information on the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree, see [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).</span></span>  
  
|<span data-ttu-id="50d93-116">Denetim Görünüm</span><span class="sxs-lookup"><span data-stu-id="50d93-116">Control View</span></span>|<span data-ttu-id="50d93-117">İçerik görünümü</span><span class="sxs-lookup"><span data-stu-id="50d93-117">Content View</span></span>|  
|------------------|------------------|  
|<span data-ttu-id="50d93-118">Ağaç</span><span class="sxs-lookup"><span data-stu-id="50d93-118">Tree</span></span><br /><br /> <ul><li><span data-ttu-id="50d93-119">DataItem (0 veya daha fazla)</span><span class="sxs-lookup"><span data-stu-id="50d93-119">DataItem (0 or more)</span></span></li><li><span data-ttu-id="50d93-120">Treeıtem (0 veya daha fazla)</span><span class="sxs-lookup"><span data-stu-id="50d93-120">TreeItem (0 or more)</span></span><br /><br /> <ul><li><span data-ttu-id="50d93-121">Treeıtem (0 veya daha fazla) •...</span><span class="sxs-lookup"><span data-stu-id="50d93-121">TreeItem (0 or more)•    …</span></span></li></ul></li><li><span data-ttu-id="50d93-122">ScrollBar (0, 1, 2)</span><span class="sxs-lookup"><span data-stu-id="50d93-122">ScrollBar (0, 1, 2)</span></span></li></ul>|<span data-ttu-id="50d93-123">Ağaç</span><span class="sxs-lookup"><span data-stu-id="50d93-123">Tree</span></span><br /><br /> <ul><li><span data-ttu-id="50d93-124">DataItem (0 veya daha fazla)</span><span class="sxs-lookup"><span data-stu-id="50d93-124">DataItem (0 or more)</span></span></li><li><span data-ttu-id="50d93-125">Treeıtem (0 veya daha fazla)</span><span class="sxs-lookup"><span data-stu-id="50d93-125">TreeItem (0 or more)</span></span><br /><br /> <ul><li><span data-ttu-id="50d93-126">Treeıtem (0 veya daha fazla) •...</span><span class="sxs-lookup"><span data-stu-id="50d93-126">TreeItem (0 or more)•    …</span></span></li></ul></li></ul>|  
  
 <span data-ttu-id="50d93-127">Denetim görünümünü [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağaç oluşur:</span><span class="sxs-lookup"><span data-stu-id="50d93-127">The control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree consists of:</span></span>  
  
-   <span data-ttu-id="50d93-128">(Öğeleri ağaç öğesi, veri öğesi veya diğer denetim türü dayanabilir) kapsayıcı içinde birçok sıfır öğe.</span><span class="sxs-lookup"><span data-stu-id="50d93-128">Zero to many items within the container (items can be based on the Tree Item, Data Item, or other control type).</span></span>  
  
-   <span data-ttu-id="50d93-129">Sıfır, bir veya iki kaydırma çubukları.</span><span class="sxs-lookup"><span data-stu-id="50d93-129">Zero, one or two scroll bars.</span></span>  
  
 <span data-ttu-id="50d93-130">İçerik görünümünü [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] sıfır veya daha çok öğeleri (öğeleri temel alabilir ağaç öğesi, veri öğesi veya diğer denetim türü) kapsayıcıdaki ağaç oluşur.</span><span class="sxs-lookup"><span data-stu-id="50d93-130">The content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree consists of zero or many items within the container (items can be based on the Tree Item, Data Item, or other control type).</span></span>  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a><span data-ttu-id="50d93-131">Gerekli UI Otomasyon özellikleri</span><span class="sxs-lookup"><span data-stu-id="50d93-131">Required UI Automation Properties</span></span>  
 <span data-ttu-id="50d93-132">Aşağıdaki tabloda [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] , değer veya tanımı liste denetimleri için özellikle ilgili özellikler.</span><span class="sxs-lookup"><span data-stu-id="50d93-132">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties whose value or definition is especially relevant to list controls.</span></span> <span data-ttu-id="50d93-133">Hakkında daha fazla bilgi için [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] özellikleri, görmek [istemciler için UI Otomasyon özellikleri](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span><span class="sxs-lookup"><span data-stu-id="50d93-133">For more information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] properties, see [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="50d93-134">Özelliği</span><span class="sxs-lookup"><span data-stu-id="50d93-134"> Property</span></span>|<span data-ttu-id="50d93-135">Değer</span><span class="sxs-lookup"><span data-stu-id="50d93-135">Value</span></span>|<span data-ttu-id="50d93-136">Notlar</span><span class="sxs-lookup"><span data-stu-id="50d93-136">Notes</span></span>|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|<span data-ttu-id="50d93-137">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-137">See notes.</span></span>|<span data-ttu-id="50d93-138">Bu özelliğin değeri bir uygulamadaki tüm denetimler arasında benzersiz olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="50d93-138">The value of this property needs to be unique across all controls in an application.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|<span data-ttu-id="50d93-139">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-139">See notes.</span></span>|<span data-ttu-id="50d93-140">Tam denetimi içeren en dıştaki dikdörtgen.</span><span class="sxs-lookup"><span data-stu-id="50d93-140">The outermost rectangle that contains the whole control.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|<span data-ttu-id="50d93-141">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-141">See notes.</span></span>|<span data-ttu-id="50d93-142">Ağaç denetimleri ağaçtaki veya veya bir öğeleri ağaç bunlarda ayarlı odağa sahip kapsayıcıya neden olacak bir tıklanabilir noktasına sahip.</span><span class="sxs-lookup"><span data-stu-id="50d93-142">Tree controls have a clickable point that will cause the tree or one the items in the tree container to have the focus set on them.</span></span> <span data-ttu-id="50d93-143">Seçili get odağı öğelerden birini neden olmaz bir yere tıklayın yalnızca, bir ağaç için tıklanabilir noktası alın.</span><span class="sxs-lookup"><span data-stu-id="50d93-143">You get a clickable point for a tree only if you can click somewhere that doesn't cause one of the items to be selected/get focus.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|<span data-ttu-id="50d93-144">Ağaç</span><span class="sxs-lookup"><span data-stu-id="50d93-144">Tree</span></span>|<span data-ttu-id="50d93-145">Bu değer tüm UI çerçeveler için aynıdır.</span><span class="sxs-lookup"><span data-stu-id="50d93-145">This value is the same for all UI frameworks.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|<span data-ttu-id="50d93-146">Doğru</span><span class="sxs-lookup"><span data-stu-id="50d93-146">True</span></span>|<span data-ttu-id="50d93-147">Ağaç denetimi her zaman içerik görünümünde dahil [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağacı.</span><span class="sxs-lookup"><span data-stu-id="50d93-147">The tree control is always included in the content view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|<span data-ttu-id="50d93-148">Doğru</span><span class="sxs-lookup"><span data-stu-id="50d93-148">True</span></span>|<span data-ttu-id="50d93-149">Ağaç denetimi her zaman denetim görünümünde dahil [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ağacı.</span><span class="sxs-lookup"><span data-stu-id="50d93-149">The tree control is always included in the control view of the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] tree.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|<span data-ttu-id="50d93-150">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-150">See notes.</span></span>|<span data-ttu-id="50d93-151">Klavye odağı denetimi alamıyorsa, bu özelliği desteklemelidir.</span><span class="sxs-lookup"><span data-stu-id="50d93-151">If the control can receive keyboard focus, it must support this property.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|<span data-ttu-id="50d93-152">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-152">See notes.</span></span>|<span data-ttu-id="50d93-153">Ağaç denetimi ile ilişkili bir etiket varsa, bu özellik döndürülecek bir <xref:System.Windows.Automation.AutomationElement> etiket için.</span><span class="sxs-lookup"><span data-stu-id="50d93-153">If the tree control has a label associated with it, this property will return an <xref:System.Windows.Automation.AutomationElement> for that label.</span></span> <span data-ttu-id="50d93-154">Aksi takdirde, özellik null bir başvuru döndürür (`Nothing` içinde [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="50d93-154">Otherwise, the property will return a null reference (`Nothing` in [!INCLUDE[TLA#tla_visualbnet](../../../includes/tlasharptla-visualbnet-md.md)]).</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|<span data-ttu-id="50d93-155">"Ağaç"</span><span class="sxs-lookup"><span data-stu-id="50d93-155">"tree"</span></span>|<span data-ttu-id="50d93-156">Liste Denetim türü için karşılık gelen yerelleştirilmiş dize.</span><span class="sxs-lookup"><span data-stu-id="50d93-156">Localized string corresponding to the List control type.</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|<span data-ttu-id="50d93-157">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-157">See notes.</span></span>|<span data-ttu-id="50d93-158">Ağaç denetim adı özelliğinin değeri genellikle denetimi etiketler metinden gelir.</span><span class="sxs-lookup"><span data-stu-id="50d93-158">The value of a tree control's name property usually comes from text that labels the control.</span></span> <span data-ttu-id="50d93-159">Metin etiketi ise, uygulama geliştiricisi bu özellik için bir değer girmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="50d93-159">If there is no text label, then the application developer must provide a value for this property.</span></span>|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a><span data-ttu-id="50d93-160">Gerekli UI Otomasyon denetim düzenleri</span><span class="sxs-lookup"><span data-stu-id="50d93-160">Required UI Automation Control Patterns</span></span>  
 <span data-ttu-id="50d93-161">Aşağıdaki tabloda [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] denetim düzenleri liste denetimleri tarafından desteklenmesi için gerekli.</span><span class="sxs-lookup"><span data-stu-id="50d93-161">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] control patterns required to be supported by list controls.</span></span> <span data-ttu-id="50d93-162">Denetim desenleri hakkında daha fazla bilgi için bkz: [UI Otomasyon denetim düzenlerine genel bakış](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50d93-162">For more information on control patterns, see [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).</span></span>  
  
|<span data-ttu-id="50d93-163">Denetim düzeni/deseni özelliği</span><span class="sxs-lookup"><span data-stu-id="50d93-163">Control Pattern/Pattern Property</span></span>|<span data-ttu-id="50d93-164">Destek/değer</span><span class="sxs-lookup"><span data-stu-id="50d93-164">Support/Value</span></span>|<span data-ttu-id="50d93-165">Notlar</span><span class="sxs-lookup"><span data-stu-id="50d93-165">Notes</span></span>|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|<span data-ttu-id="50d93-166">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-166">Depends</span></span>|<span data-ttu-id="50d93-167">Bu denetim düzeni seçilebilir öğeleri kümesi içeren bir ağaç denetimleri uygulamalıdır.</span><span class="sxs-lookup"><span data-stu-id="50d93-167">Tree controls that contain a set of selectable items must implement this control pattern.</span></span> <span data-ttu-id="50d93-168">Bu denetim düzeni öğeyi seçerek kullanıcıya anlamlı bilgiler iletmek değil, uygulanacak yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-168">This control pattern does not have to be implemented if selecting an item does not convey meaningful information to the user.</span></span>|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|<span data-ttu-id="50d93-169">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-169">See notes.</span></span>|<span data-ttu-id="50d93-170">Ağaç denetimi (çoğu ağaç denetimleri çoklu seçim desteklemez) birden çok seçim destekliyorsa bu özellik uygulayın.</span><span class="sxs-lookup"><span data-stu-id="50d93-170">Implement this property if the tree control supports multiple selection (most tree controls do not support multiple selection).</span></span>|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.IsSelectionRequired%2A>|<span data-ttu-id="50d93-171">Notlarına bakın.</span><span class="sxs-lookup"><span data-stu-id="50d93-171">See notes.</span></span>|<span data-ttu-id="50d93-172">Bir öğenin seçilmesi denetimi gerektiriyorsa, bu özelliğin değeri açıktır.</span><span class="sxs-lookup"><span data-stu-id="50d93-172">The value of this property is exposed if the control requires that an item be selected.</span></span>|  
|<xref:System.Windows.Automation.Provider.IScrollProvider>|<span data-ttu-id="50d93-173">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-173">Depends</span></span>|<span data-ttu-id="50d93-174">Ağaç kapsayıcı içeriğini kaydırılabileceğini varsa bu denetim deseni uygular.</span><span class="sxs-lookup"><span data-stu-id="50d93-174">Implement this control pattern if the contents of the tree container can be scrolled.</span></span>|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a><span data-ttu-id="50d93-175">Gerekli UI Otomasyon olayları</span><span class="sxs-lookup"><span data-stu-id="50d93-175">Required UI Automation Events</span></span>  
 <span data-ttu-id="50d93-176">Aşağıdaki tabloda [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] olayları tüm ağaç denetimleri tarafından desteklenmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="50d93-176">The following table lists the [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] events required to be supported by all tree controls.</span></span> <span data-ttu-id="50d93-177">Olaylar hakkında daha fazla bilgi için bkz: [UI Otomasyonu olaylarına genel bakış](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50d93-177">For more information on events, see [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).</span></span>  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]<span data-ttu-id="50d93-178">Olay</span><span class="sxs-lookup"><span data-stu-id="50d93-178"> Event</span></span>|<span data-ttu-id="50d93-179">Destek</span><span class="sxs-lookup"><span data-stu-id="50d93-179">Support</span></span>|<span data-ttu-id="50d93-180">Notlar</span><span class="sxs-lookup"><span data-stu-id="50d93-180">Notes</span></span>|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|<span data-ttu-id="50d93-181">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-181">Depends</span></span>|<span data-ttu-id="50d93-182">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-182">None</span></span>|  
|<span data-ttu-id="50d93-183"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-183"><xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-184">Gerekli</span><span class="sxs-lookup"><span data-stu-id="50d93-184">Required</span></span>|<span data-ttu-id="50d93-185">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-185">None</span></span>|  
|<span data-ttu-id="50d93-186"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-186"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-187">Gerekli</span><span class="sxs-lookup"><span data-stu-id="50d93-187">Required</span></span>|<span data-ttu-id="50d93-188">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-188">None</span></span>|  
|<span data-ttu-id="50d93-189"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-189"><xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-190">Gerekli</span><span class="sxs-lookup"><span data-stu-id="50d93-190">Required</span></span>|<span data-ttu-id="50d93-191">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-191">None</span></span>|  
|<span data-ttu-id="50d93-192"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-192"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-193">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-193">Depends</span></span>|<span data-ttu-id="50d93-194">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-194">None</span></span>|  
|<span data-ttu-id="50d93-195"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-195"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-196">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-196">Depends</span></span>|<span data-ttu-id="50d93-197">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-197">None</span></span>|  
|<span data-ttu-id="50d93-198"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-198"><xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-199">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-199">Depends</span></span>|<span data-ttu-id="50d93-200">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-200">None</span></span>|  
|<span data-ttu-id="50d93-201"><xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-201"><xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-202">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-202">Depends</span></span>|<span data-ttu-id="50d93-203">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-203">None</span></span>|  
|<span data-ttu-id="50d93-204"><xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-204"><xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-205">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-205">Depends</span></span>|<span data-ttu-id="50d93-206">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-206">None</span></span>|  
|<span data-ttu-id="50d93-207"><xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty>özellik değişti olayı.</span><span class="sxs-lookup"><span data-stu-id="50d93-207"><xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> property-changed event.</span></span>|<span data-ttu-id="50d93-208">Bağlıdır</span><span class="sxs-lookup"><span data-stu-id="50d93-208">Depends</span></span>|<span data-ttu-id="50d93-209">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-209">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|<span data-ttu-id="50d93-210">Gerekli</span><span class="sxs-lookup"><span data-stu-id="50d93-210">Required</span></span>|<span data-ttu-id="50d93-211">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-211">None</span></span>|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|<span data-ttu-id="50d93-212">Gerekli</span><span class="sxs-lookup"><span data-stu-id="50d93-212">Required</span></span>|<span data-ttu-id="50d93-213">Yok.</span><span class="sxs-lookup"><span data-stu-id="50d93-213">None</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="50d93-214">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="50d93-214">See Also</span></span>  
 <xref:System.Windows.Automation.ControlType.Tree>  
 [<span data-ttu-id="50d93-215">UI Otomasyon denetim türlerine genel bakış</span><span class="sxs-lookup"><span data-stu-id="50d93-215">UI Automation Control Types Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)  
 [<span data-ttu-id="50d93-216">UI Otomasyon genel bakış</span><span class="sxs-lookup"><span data-stu-id="50d93-216">UI Automation Overview</span></span>](../../../docs/framework/ui-automation/ui-automation-overview.md)