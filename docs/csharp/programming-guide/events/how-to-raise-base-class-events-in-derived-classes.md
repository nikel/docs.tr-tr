---
title: "Nasıl yapılır: Türetilmiş Sınıflarda Temel Sınıf Olayları Oluşturma (C# Programlama Kılavuzu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 548409d3f632213f3ff1de0a27a70b9f42b18332
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a><span data-ttu-id="17db7-102">Nasıl yapılır: Türetilmiş Sınıflarda Temel Sınıf Olayları Oluşturma (C# Programlama Kılavuzu)</span><span class="sxs-lookup"><span data-stu-id="17db7-102">How to: Raise Base Class Events in Derived Classes (C# Programming Guide)</span></span>
<span data-ttu-id="17db7-103">Aşağıdaki basit örnek türetilmiş sınıflarından ayrıca yükseltilebilir böylece bir temel sınıf olayları bildirme standart yolu gösterir.</span><span class="sxs-lookup"><span data-stu-id="17db7-103">The following simple example shows the standard way to declare events in a base class so that they can also be raised from derived classes.</span></span> <span data-ttu-id="17db7-104">Bu deseni Windows Forms sınıfları yaygın olarak kullanılan [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] sınıf kitaplığı.</span><span class="sxs-lookup"><span data-stu-id="17db7-104">This pattern is used extensively in Windows Forms classes in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] class library.</span></span>  
  
 <span data-ttu-id="17db7-105">Diğer sınıflar için temel sınıf olarak kullanılabilir bir sınıf oluşturduğunuzda, olaylar yalnızca gelen bunları bildirilen sınıfı içinde çağrılabilir temsilci özel bir tür bulunmasına düşünmelisiniz.</span><span class="sxs-lookup"><span data-stu-id="17db7-105">When you create a class that can be used as a base class for other classes, you should consider the fact that events are a special type of delegate that can only be invoked from within the class that declared them.</span></span> <span data-ttu-id="17db7-106">Türetilmiş sınıflar temel sınıf içinde bildirilen olayları doğrudan çağrılamıyor.</span><span class="sxs-lookup"><span data-stu-id="17db7-106">Derived classes cannot directly invoke events that are declared within the base class.</span></span> <span data-ttu-id="17db7-107">Çoğu zaman, yalnızca temel sınıfı tarafından gerçekleştirilen bir olay bazen isteyebilirsiniz karşın, temel sınıf olayları çağırmak türetilmiş sınıf etkinleştirmeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="17db7-107">Although sometimes you may want an event that can only be raised by the base class, most of the time, you should enable the derived class to invoke base class events.</span></span> <span data-ttu-id="17db7-108">Bunu yapmak için olay sarmalar taban sınıf içinde korumalı bildirilecekse yöntemi oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17db7-108">To do this, you can create a protected invoking method in the base class that wraps the event.</span></span> <span data-ttu-id="17db7-109">Türetilen sınıflar çağrılırken veya bildirilecekse bu yöntemi geçersiz kılma, olay dolaylı olarak çağırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="17db7-109">By calling or overriding this invoking method, derived classes can invoke the event indirectly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17db7-110">Sanal bir temel sınıf olayları bildirme değil ve türetilen bir sınıfta geçersiz.</span><span class="sxs-lookup"><span data-stu-id="17db7-110">Do not declare virtual events in a base class and override them in a derived class.</span></span> <span data-ttu-id="17db7-111">C# Derleyici doğru bu işlemez ve türetilen olaya abone gerçekte temel sınıf olaya abone olup olmadığını tahmin edilemez.</span><span class="sxs-lookup"><span data-stu-id="17db7-111">The C# compiler does not handle these correctly and it is unpredictable whether a subscriber to the derived event will actually be subscribing to the base class event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17db7-112">Örnek</span><span class="sxs-lookup"><span data-stu-id="17db7-112">Example</span></span>  
 [!code-csharp[csProgGuideEvents#1](../../../csharp/programming-guide/events/codesnippet/CSharp/how-to-raise-base-class-events-in-derived-classes_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="17db7-113">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="17db7-113">See Also</span></span>  
 [<span data-ttu-id="17db7-114">C# programlama kılavuzu</span><span class="sxs-lookup"><span data-stu-id="17db7-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="17db7-115">Olayları</span><span class="sxs-lookup"><span data-stu-id="17db7-115">Events</span></span>](../../../csharp/programming-guide/events/index.md)  
 [<span data-ttu-id="17db7-116">Temsilciler</span><span class="sxs-lookup"><span data-stu-id="17db7-116">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)  
 [<span data-ttu-id="17db7-117">Erişim değiştiricileri</span><span class="sxs-lookup"><span data-stu-id="17db7-117">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="17db7-118">Windows Forms'ta olay işleyicileri oluşturma</span><span class="sxs-lookup"><span data-stu-id="17db7-118">Creating Event Handlers in Windows Forms</span></span>](https://msdn.microsoft.com/library/dacysss4.aspx)