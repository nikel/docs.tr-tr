---
title: "My.Resources ve My.Settings ile Hızlı Uygulama Geliştirme (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My.Settings object [Visual Basic], developing applications
- rapid application development (RAD), My.Resources
- rapid application development (RAD), My.Settings
- My.Resources object [Visual Basic], developing applications
ms.assetid: 68284ab1-b685-4814-a2a4-01ae40445ff8
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7339afdc35341739b592b2a327094754031c346c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rapid-application-development-with-myresources-and-mysettings-visual-basic"></a>My.Resources ve My.Settings ile Hızlı Uygulama Geliştirme (Visual Basic)
`My.Resources` Nesne uygulamanın kaynaklarına erişmesini sağlar ve uygulamanız için kaynakları dinamik olarak almanıza olanak tanır.  
  
## <a name="retrieving-resources"></a>Kaynakları Alma  
 Ses dosyalarını, simgeler, görüntüler ve dizeler gibi kaynakları çeşitli alınabilir `My.Resources` nesnesi. Örneğin, uygulamanın kültüre özgü kaynak dosyalara erişebilirsiniz. Aşağıdaki örnek form simgesini adlı simgesi ayarlar `Form1Icon` uygulamanın kaynak dosyasında depolanır.  
  
 [!code-vb[VbVbcnMy#7](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/rapid-application-development-with-my-resources-and-my-settings_1.vb)]  
  
 `My.Resources` Nesne yalnızca Genel kaynaklar kullanıma sunar. Formları ile ilişkili kaynak dosyalarına erişim sağlamaz. Form kaynaklarını formdan erişmeniz gerekir.  
  
 Benzer şekilde, `My.Settings` nesne uygulamanın ayarlarına erişim sağlar ve dinamik olarak depolamak ve özellik ayarları ve uygulamanız için diğer bilgilerini almak sağlar. Daha fazla bilgi için bkz: [My.Resources nesnesi](../../../visual-basic/language-reference/objects/my-resources-object.md) ve [My.Settings nesnesi](../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [My.Resources Nesnesi](../../../visual-basic/language-reference/objects/my-resources-object.md)  
 [My.Settings Nesnesi](../../../visual-basic/language-reference/objects/my-settings-object.md)  
 [Uygulama Ayarlarına Erişme](../../../visual-basic/developing-apps/programming/app-settings/accessing-application-settings.md)
