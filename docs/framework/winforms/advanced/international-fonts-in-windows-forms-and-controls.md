---
title: "Windows Formları ve Denetimlerindeki Uluslararası Yazı Tipleri"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fonts [Windows Forms], international
- international applications [Windows Forms], character display
- fonts [Windows Forms], globalization considerations
- localization [Windows Forms], fonts
- Windows Forms controls, labels
- font fallback in Windows Forms
- globalization [Windows Forms], character sets
ms.assetid: 2c3066df-9bac-479a-82b2-79e484b346a3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e7b6574e452faf4f0396f7633ba7f21519948262
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="international-fonts-in-windows-forms-and-controls"></a>Windows Formları ve Denetimlerindeki Uluslararası Yazı Tipleri
Uluslararası uygulamalar yazı tipleri seçme önerilen yöntem yazı tipi geri dönüşü mümkün olduğunda kullanmaktır. Ait ne karakter komut dosyası sistemini belirler yazı tipi geri dönüş anlamına gelir.  
  
## <a name="using-font-fallback"></a>Yazı tipi geri dönüşü kullanma  
 Bu özelliğin avantajlarından yararlanmak için ayarlamayın <xref:System.Drawing.Font> formunuz veya başka bir öğenin özellik. Uygulama, işletim sisteminin bir yerelleştirilmiş dilden diğerine farklı varsayılan sistem yazı otomatik olarak kullanır. Uygulama çalıştığında, sistem doğru yazı tipi işletim sisteminde seçilen kültür için otomatik olarak sağlar.  
  
 Yazı tipi stilini değiştirmek için yazı tipi ayarı bulunamadı, kural için bir özel yoktur. Bu, kullanıcı bir düğme kalın olarak bir metin kutusundaki metin görünür yapmak için bir uygulama için önemli olabilir. Bunu yapmak için kalın, metin kutusunun yazı tipi stilini değiştirmek için bir işlev ne olursa olsun formun yazı tipi temel alınarak yazarsınız. İki yerde bu işlevi çağırmak önemlidir: düğmenin içinde <xref:System.Windows.Forms.Control.Click> olay işleyicisi ve <xref:System.Windows.Forms.Control.FontChanged> olay işleyicisi. İşlevi yalnızca çağrıldıysa <xref:System.Windows.Forms.Control.Click> olay işleyicisi ve bazı diğer kod parçası, formun tamamı yazı tipi ailesi değiştirir, metin kutusuna form geri kalanı ile değiştirmez.  
  
```  
' Visual Basic  
Private Sub MakeBold()  
   ' Change the TextBox to a bold version of the form font  
   TextBox1.Font = New Font(Me.Font, FontStyle.Bold)  
End Sub  
  
Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
   ' Clicking this button makes the TextBox bold  
   MakeBold()  
End Sub  
  
Private Sub Form1_FontChanged(ByVal sender As Object, ByVal e As System.EventArgs) Handles MyBase.FontChanged  
   ' If the TextBox is already bold and the form's font changes,  
   ' change the TextBox to a bold version of the new form font  
   If (TextBox1.Font.Style = FontStyle.Bold) Then  
      MakeBold()  
   End If  
End Sub  
  
// C#  
private void button1_Click(object sender, System.EventArgs e)  
{  
   // Clicking this button makes the TextBox bold  
   MakeBold();  
}  
  
private void MakeBold()   
{  
   // Change the TextBox to a bold version of the form's font  
   textBox1.Font = new Font(this.Font, FontStyle.Bold);  
}  
  
private void Form1_FontChanged(object sender, System.EventArgs e)  
{  
   // If the TextBox is already bold and the form's font changes,  
   // change the TextBox to a bold version of the new form font  
   if (textBox1.Font.Style == FontStyle.Bold)   
   {  
      MakeBold();  
   }  
}  
```  
  
 Ancak, uygulamanızı yerelleştirme sırasında kalın yazı tipiyle kötü belirli diller görüntüleyebilir. İlgili bir sorun varsa, normal metne kalın gelen yazı tipini değiştirme seçeneğiniz çevirmenler istiyorsunuz. Çevirmenler genelde geliştiricilerinin değildir ve kaynak koduna erişim hakkınız yok olduğundan, kaynak dosyaları için yalnızca bu seçenek kaynak dosyalarında ayarlanması gerekir. Bunu yapmak için ayarlamalısınız <xref:System.Drawing.Font.Bold%2A> özelliğine `true`. Bu, kaynak dosyaları nerede çevirmenler düzenleyebilirsiniz, yazılmakta yazı tipi ayarı sonuçlanır. Ardından koddan sonra Yazma `InitializeComponent` yazı tipi sıfırlama yöntemi temel ne olursa olsun formun yazı tipi açıktır, ancak kaynak dosyasında belirtilen yazı tipi stilini kullanarak.  
  
```  
' Visual Basic  
TextBox1.Font = New System.Drawing.Font(Me.Font, TextBox1.Font.Style)  
  
// C#  
textBox1.Font = new System.Drawing.Font(this.Font, textBox1.Font.Style);  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Forms’u Genelleştirme](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)  
 [Yazı Tipleri ve Metin Kullanma](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
