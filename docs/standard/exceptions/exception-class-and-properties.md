---
title: "Özel Durumu Sınıfı ve Özellikleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 253a9846e484aa4e54c3433b0bbc8623519bbb7e
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2017
---
# <a name="exception-class-and-properties"></a><span data-ttu-id="f73aa-102">Özel durum sınıfı ve özellikleri</span><span class="sxs-lookup"><span data-stu-id="f73aa-102">Exception class and properties</span></span>

<span data-ttu-id="f73aa-103"><xref:System.Exception> Sınıftır içinden özel durum devral temel sınıf.</span><span class="sxs-lookup"><span data-stu-id="f73aa-103">The <xref:System.Exception> class is the base class from which exceptions inherit.</span></span> <span data-ttu-id="f73aa-104">Örneğin, <xref:System.InvalidCastException> sınıf hiyerarşisi aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="f73aa-104">For example, the <xref:System.InvalidCastException> class hierarchy is as follows:</span></span>

```
Object
  Exception
    SystemException
       InvalidCastException
```

<span data-ttu-id="f73aa-105"><xref:System.Exception> Sınıfı daha kolay bir özel durum anlama sağlamak aşağıdaki özellikleri vardır.</span><span class="sxs-lookup"><span data-stu-id="f73aa-105">The <xref:System.Exception> class has the following properties that help make understanding an exception easier.</span></span>

| <span data-ttu-id="f73aa-106">Özellik adı</span><span class="sxs-lookup"><span data-stu-id="f73aa-106">Property Name</span></span> | <span data-ttu-id="f73aa-107">Açıklama</span><span class="sxs-lookup"><span data-stu-id="f73aa-107">Description</span></span> |
| ------------- | ----------- |
| <xref:System.Exception.Data> | <span data-ttu-id="f73aa-108">Bir <xref:System.Collections.IDictionary> , anahtar-değer çiftlerini rastgele verileri tutar.</span><span class="sxs-lookup"><span data-stu-id="f73aa-108">An <xref:System.Collections.IDictionary> that holds arbitrary data in key-value pairs.</span></span> |
| <xref:System.Exception.HelpLink> | <span data-ttu-id="f73aa-109">Bir URL (veya URN) bir özel durumun nedeni hakkında kapsamlı bilgi sağlayan bir Yardım dosyası basılı tutabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f73aa-109">Can hold a URL (or URN) to a help file that provides extensive information about the cause of an exception.</span></span> |
| <xref:System.Exception.InnerException> | <span data-ttu-id="f73aa-110">Bu özellik, oluşturma ve özel durum işleme sırasında özel durumlar bir dizi korumak için kullanılabilir.</span><span class="sxs-lookup"><span data-stu-id="f73aa-110">This property can be used to create and preserve a series of exceptions during exception handling.</span></span> <span data-ttu-id="f73aa-111">Daha önce Yakalanan özel durumlar içeren yeni bir özel durum oluşturmak için kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="f73aa-111">You can use it to create a new exception that contains previously caught exceptions.</span></span> <span data-ttu-id="f73aa-112">İkinci özel durum tarafından orijinal özel durumu yakalandı <xref:System.Exception.InnerException> özelliği, ek bilgileri incelemek için ikinci özel durumu işleyen kodu izin verme.</span><span class="sxs-lookup"><span data-stu-id="f73aa-112">The original exception can be captured by the second exception in the <xref:System.Exception.InnerException> property, allowing code that handles the second exception to examine the additional information.</span></span> <span data-ttu-id="f73aa-113">Örneğin, hatalı biçimlendirilmiş bir bağımsız değişken alan bir yöntem olduğunu varsayalım.</span><span class="sxs-lookup"><span data-stu-id="f73aa-113">For example, suppose you have a method that receives an argument that's improperly formatted.</span></span>  <span data-ttu-id="f73aa-114">Kod bağımsız değişkeni okumaya çalışır, ancak bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="f73aa-114">The code tries to read the argument, but an exception is thrown.</span></span> <span data-ttu-id="f73aa-115">Yöntemi özel durum yakalar ve oluşturur bir <xref:System.FormatException>.</span><span class="sxs-lookup"><span data-stu-id="f73aa-115">The method catches the exception and throws a <xref:System.FormatException>.</span></span> <span data-ttu-id="f73aa-116">Bir özel durum nedenini belirlemek için çağıranın yeteneğini geliştirmek için onu bazen Yardımcısı yordamı tarafından oluşturulan bir özel catch ve sonra gerçekleşen hata daha hatırlanması bir özel durum için bir yöntem için önerilir.</span><span class="sxs-lookup"><span data-stu-id="f73aa-116">To improve the caller's ability to determine the reason an exception is thrown, it is sometimes desirable for a method to catch an exception thrown by a helper routine and then throw an exception more indicative of the error that has occurred.</span></span> <span data-ttu-id="f73aa-117">İç özel duruma başvuru için orijinal özel durumu burada ayarlanabilir yeni ve daha anlamlı bir özel durum oluşturulabilir.</span><span class="sxs-lookup"><span data-stu-id="f73aa-117">A new and more meaningful exception can be created, where the inner exception reference can be set to the original exception.</span></span> <span data-ttu-id="f73aa-118">Bu daha anlamlı özel sonra çağırana durum.</span><span class="sxs-lookup"><span data-stu-id="f73aa-118">This more meaningful exception can then be thrown to the caller.</span></span> <span data-ttu-id="f73aa-119">Bu işlev ile ilk oluşturulan özel durum ile biten bir dizi bağlantılı özel durumlar oluşturabilirsiniz unutmayın.</span><span class="sxs-lookup"><span data-stu-id="f73aa-119">Note that with this functionality, you can create a series of linked exceptions that ends with the exception that was thrown first.</span></span> |
| <xref:System.Exception.Message> | <span data-ttu-id="f73aa-120">Bir özel durumun nedeni olan hakkında ayrıntılar sağlar.</span><span class="sxs-lookup"><span data-stu-id="f73aa-120">Provides details about the cause of an exception.</span></span>
| <xref:System.Exception.Source> | <span data-ttu-id="f73aa-121">Alır veya uygulama veya hataya neden nesnesinin adını ayarlar.</span><span class="sxs-lookup"><span data-stu-id="f73aa-121">Gets or sets the name of the application or the object that causes the error.</span></span> |
| <xref:System.Exception.StackTrace>| <span data-ttu-id="f73aa-122">Bir hatanın oluştuğu belirlemek için kullanılan bir yığın izlemeyi içerir.</span><span class="sxs-lookup"><span data-stu-id="f73aa-122">Contains a stack trace that can be used to determine where an error occurred.</span></span> <span data-ttu-id="f73aa-123">Hata ayıklama bilgileri kullanılabiliyorsa, yığın izleme kaynak dosya adı ve program satır sayısını içerir.</span><span class="sxs-lookup"><span data-stu-id="f73aa-123">The stack trace includes the source file name and program line number if debugging information is available.</span></span> |

<span data-ttu-id="f73aa-124">Devralınan sınıfların çoğu <xref:System.Exception> etmeyin ek üyeleri uygulayan veya ek işlevsellik sağlar; bunlar yalnızca devralınan <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="f73aa-124">Most of the classes that inherit from <xref:System.Exception> do not implement additional members or provide additional functionality; they simply inherit from <xref:System.Exception>.</span></span> <span data-ttu-id="f73aa-125">Bu nedenle, özel durum sınıfları, özel durum adı ve özel durum yer alan bilgileri hiyerarşideki bir özel durum için en önemli bilgiler bulunabilir.</span><span class="sxs-lookup"><span data-stu-id="f73aa-125">Therefore, the most important information for an exception can be found in the hierarchy of exception classes, the exception name, and the information contained in the exception.</span></span>

<span data-ttu-id="f73aa-126">Throw ve catch öğesinden türetilen nesneler öneririz <xref:System.Exception>, ancak türetilen herhangi bir nesne throw <xref:System.Object> sınıfı bir özel durum.</span><span class="sxs-lookup"><span data-stu-id="f73aa-126">We recommend that you throw and catch only objects that derive from <xref:System.Exception>, but you can throw any object that derives from the <xref:System.Object> class as an exception.</span></span> <span data-ttu-id="f73aa-127">Tüm diller oluşturma ve yakalama öğesinden türetilen olmayan nesneler desteklediğini unutmayın <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="f73aa-127">Note that not all languages support throwing and catching objects that do not derive from <xref:System.Exception>.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f73aa-128">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="f73aa-128">See Also</span></span>  
[<span data-ttu-id="f73aa-129">Özel durumlar</span><span class="sxs-lookup"><span data-stu-id="f73aa-129">Exceptions</span></span>](index.md)