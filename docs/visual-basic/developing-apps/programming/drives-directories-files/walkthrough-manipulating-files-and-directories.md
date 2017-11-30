---
title: "Dosyalar ve dizinler Visual Basic'te düzenleme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- files [Visual Basic], reading text
- reading files [Visual Basic], text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files [Visual Basic], walkthroughs
- Visual Basic code, file access
- files [Visual Basic], writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files [Visual Basic], walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: "49"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bd1e61503394741e7943d30d383f2e7c5ea35f68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="7dfae-102">İzlenecek Yol: Visual Basic'te Dosyaları ve Dizinleri Düzenleme</span><span class="sxs-lookup"><span data-stu-id="7dfae-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>
<span data-ttu-id="7dfae-103">Bu kılavuzda dosya g/ç ile ilgili temel bilgileri tanıtılmaktadır [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dfae-103">This walkthrough provides an introduction to the fundamentals of file I/O in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="7dfae-104">Listeler ve metin dosyaları bir dizinde inceler küçük bir uygulamasının nasıl oluşturulacağını açıklar.</span><span class="sxs-lookup"><span data-stu-id="7dfae-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="7dfae-105">Her seçili metin dosyası için dosya özniteliklerini ve içeriğindeki birinci satırın uygulama sağlar.</span><span class="sxs-lookup"><span data-stu-id="7dfae-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="7dfae-106">Bilgilerini bir günlük dosyasına yazmak için bir seçenek yoktur.</span><span class="sxs-lookup"><span data-stu-id="7dfae-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="7dfae-107">Bu kılavuzda üyeleri kullanılır `My.Computer.FileSystem Object`, kullanılabilir olduğu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7dfae-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="7dfae-108">Daha fazla bilgi edinmek için bkz. <xref:Microsoft.VisualBasic.FileIO.FileSystem>.</span><span class="sxs-lookup"><span data-stu-id="7dfae-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="7dfae-109">İzlenecek yol sonunda sınıflardan kullanan bir eşdeğer örnek sağlanır <xref:System.IO> ad alanı.</span><span class="sxs-lookup"><span data-stu-id="7dfae-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="7dfae-110">Proje oluşturmak için</span><span class="sxs-lookup"><span data-stu-id="7dfae-110">To create the project</span></span>  
  
1.  <span data-ttu-id="7dfae-111">Üzerinde **dosya** menüsünde tıklatın **yeni proje**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="7dfae-112">**Yeni proje** iletişim kutusu görüntülenir.</span><span class="sxs-lookup"><span data-stu-id="7dfae-112">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="7dfae-113">İçinde **yüklü şablonlar** bölmesini genişletin **Visual Basic**ve ardından **Windows**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="7dfae-114">İçinde **şablonları** Orta tıklatın bölmesinde **Windows Forms uygulaması**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="7dfae-115">İçinde **adı** kutusuna `FileExplorer` proje adını ayarlayın ve ardından **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="7dfae-116">projeye ekler **Çözüm Gezgini**, ve Windows Forms Tasarımcısı'nı açar.</span><span class="sxs-lookup"><span data-stu-id="7dfae-116"> adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4.  <span data-ttu-id="7dfae-117">Denetimleri aşağıdaki tabloda forma ekleme ve bunların özelliklerini karşılık gelen değerler ayarlayın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="7dfae-118">Denetim</span><span class="sxs-lookup"><span data-stu-id="7dfae-118">Control</span></span>|<span data-ttu-id="7dfae-119">Özellik</span><span class="sxs-lookup"><span data-stu-id="7dfae-119">Property</span></span>|<span data-ttu-id="7dfae-120">Değer</span><span class="sxs-lookup"><span data-stu-id="7dfae-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="7dfae-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="7dfae-121">**ListBox**</span></span>|<span data-ttu-id="7dfae-122">**Ad**</span><span class="sxs-lookup"><span data-stu-id="7dfae-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="7dfae-123">**Düğmesi**</span><span class="sxs-lookup"><span data-stu-id="7dfae-123">**Button**</span></span>|<span data-ttu-id="7dfae-124">**Ad**</span><span class="sxs-lookup"><span data-stu-id="7dfae-124">**Name**</span></span><br /><br /> <span data-ttu-id="7dfae-125">**Metin**</span><span class="sxs-lookup"><span data-stu-id="7dfae-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="7dfae-126">**Gözat**</span><span class="sxs-lookup"><span data-stu-id="7dfae-126">**Browse**</span></span>|  
    |<span data-ttu-id="7dfae-127">**Düğmesi**</span><span class="sxs-lookup"><span data-stu-id="7dfae-127">**Button**</span></span>|<span data-ttu-id="7dfae-128">**Ad**</span><span class="sxs-lookup"><span data-stu-id="7dfae-128">**Name**</span></span><br /><br /> <span data-ttu-id="7dfae-129">**Metin**</span><span class="sxs-lookup"><span data-stu-id="7dfae-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="7dfae-130">**İnceleyin**</span><span class="sxs-lookup"><span data-stu-id="7dfae-130">**Examine**</span></span>|  
    |<span data-ttu-id="7dfae-131">**Onay kutusu**</span><span class="sxs-lookup"><span data-stu-id="7dfae-131">**CheckBox**</span></span>|<span data-ttu-id="7dfae-132">**Ad**</span><span class="sxs-lookup"><span data-stu-id="7dfae-132">**Name**</span></span><br /><br /> <span data-ttu-id="7dfae-133">**Metin**</span><span class="sxs-lookup"><span data-stu-id="7dfae-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="7dfae-134">**Sonuçları Kaydet**</span><span class="sxs-lookup"><span data-stu-id="7dfae-134">**Save Results**</span></span>|  
    |<span data-ttu-id="7dfae-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="7dfae-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="7dfae-136">**Ad**</span><span class="sxs-lookup"><span data-stu-id="7dfae-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="7dfae-137">Bir klasör seçin ve bir klasördeki dosyaları listelemek için</span><span class="sxs-lookup"><span data-stu-id="7dfae-137">To select a folder, and list files in a folder</span></span>  
  
1.  <span data-ttu-id="7dfae-138">Oluşturma bir `Click` için olay işleyicisini `browseButton` formdaki denetim çift tıklatarak.</span><span class="sxs-lookup"><span data-stu-id="7dfae-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="7dfae-139">Kod Düzenleyicisi açılır.</span><span class="sxs-lookup"><span data-stu-id="7dfae-139">The Code Editor opens.</span></span>  
  
2.  <span data-ttu-id="7dfae-140">Aşağıdaki kodu ekleyin `Click` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-140">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]  
  
     <span data-ttu-id="7dfae-141">`FolderBrowserDialog1.ShowDialog` Çağrısı açılır **klasöre Gözat** iletişim kutusu.</span><span class="sxs-lookup"><span data-stu-id="7dfae-141">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="7dfae-142">Sonra kullanıcı **Tamam**, <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> özelliği için bağımsız değişken olarak gönderilir `ListFiles` sonraki adımda eklenen yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-142">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3.  <span data-ttu-id="7dfae-143">Aşağıdakileri ekleyin `ListFiles` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-143">Add the following `ListFiles` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]  
  
     <span data-ttu-id="7dfae-144">Bu kod ilk temizler **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-144">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="7dfae-145"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> Yöntemi sonra dizeler, bir dizinin her dosya için bir koleksiyonunu alır.</span><span class="sxs-lookup"><span data-stu-id="7dfae-145">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="7dfae-146">`GetFiles` Yöntemi, belirli bir desenle eşleşen dosyaları almak için bir arama deseni bağımsız değişkeni kabul eder.</span><span class="sxs-lookup"><span data-stu-id="7dfae-146">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="7dfae-147">Bu örnekte, yalnızca .txt uzantılı dosyalar döndürülür.</span><span class="sxs-lookup"><span data-stu-id="7dfae-147">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="7dfae-148">Tarafından döndürülen dize `GetFiles` yöntemi eklenir **ListBox**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-148">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4.  <span data-ttu-id="7dfae-149">Uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-149">Run the application.</span></span> <span data-ttu-id="7dfae-150">Tıklatın **Gözat** düğmesi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-150">Click the **Browse** button.</span></span> <span data-ttu-id="7dfae-151">İçinde **klasöre Gözat** iletişim kutusunda, Gözat .txt dosyaları içeren bir klasörü klasörü seçin ve tıklatın **Tamam**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-151">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="7dfae-152">`ListBox` .Txt dosyaları seçili klasörde listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="7dfae-152">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5.  <span data-ttu-id="7dfae-153">Uygulama çalışmayı durdurur.</span><span class="sxs-lookup"><span data-stu-id="7dfae-153">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="7dfae-154">Bir dosyanın özniteliklerini elde edin ve bir metin dosyasından içerik</span><span class="sxs-lookup"><span data-stu-id="7dfae-154">To obtain attributes of a file, and content from a text file</span></span>  
  
1.  <span data-ttu-id="7dfae-155">Oluşturma bir `Click` için olay işleyicisini `examineButton` formdaki denetim çift tıklatarak.</span><span class="sxs-lookup"><span data-stu-id="7dfae-155">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2.  <span data-ttu-id="7dfae-156">Aşağıdaki kodu ekleyin `Click` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-156">Add the following code to the `Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]  
  
     <span data-ttu-id="7dfae-157">Kod bir öğe seçili olduğunu doğrular `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="7dfae-157">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="7dfae-158">Ardından dosya yolu girişinden elde `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="7dfae-158">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="7dfae-159"><xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> Yöntemi, dosyanın hala var olup olmadığını denetlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7dfae-159">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="7dfae-160">Dosya yolu için bağımsız değişken olarak gönderilen `GetTextForOutput` sonraki adımda eklenen yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-160">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="7dfae-161">Bu yöntem, dosya bilgileri içeren bir dize döndürür.</span><span class="sxs-lookup"><span data-stu-id="7dfae-161">This method returns a string that contains file information.</span></span> <span data-ttu-id="7dfae-162">Dosya bilgileri görünür bir **MessageBox**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-162">The file information appears in a **MessageBox**.</span></span>  
  
3.  <span data-ttu-id="7dfae-163">Aşağıdakileri ekleyin `GetTextForOutput` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-163">Add the following `GetTextForOutput` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]  
  
     <span data-ttu-id="7dfae-164">Kod kullanan <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> dosya parametrelerini elde etmek için yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-164">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="7dfae-165">Dosya parametrelerini eklenen bir <xref:System.Text.StringBuilder>.</span><span class="sxs-lookup"><span data-stu-id="7dfae-165">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="7dfae-166"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> Yöntemi okur içine dosya içeriğini bir <xref:System.IO.StreamReader>.</span><span class="sxs-lookup"><span data-stu-id="7dfae-166">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="7dfae-167">İlk satırı içeriği ile elde edilen `StreamReader` ve eklenir `StringBuilder`.</span><span class="sxs-lookup"><span data-stu-id="7dfae-167">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4.  <span data-ttu-id="7dfae-168">Uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-168">Run the application.</span></span> <span data-ttu-id="7dfae-169">Tıklatın **Gözat**ve .txt dosyaları içeren bir klasöre göz atın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-169">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="7dfae-170">**Tamam**'ı tıklatın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-170">Click **OK**.</span></span>  
  
     <span data-ttu-id="7dfae-171">Bir dosya seçin `ListBox`ve ardından **inceleyin**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-171">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="7dfae-172">A `MessageBox` dosya bilgilerini gösterir.</span><span class="sxs-lookup"><span data-stu-id="7dfae-172">A `MessageBox` shows the file information.</span></span>  
  
5.  <span data-ttu-id="7dfae-173">Uygulama çalışmayı durdurur.</span><span class="sxs-lookup"><span data-stu-id="7dfae-173">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="7dfae-174">Bir günlük girdisi eklemek için</span><span class="sxs-lookup"><span data-stu-id="7dfae-174">To add a log entry</span></span>  
  
1.  <span data-ttu-id="7dfae-175">Sonuna aşağıdaki kodu ekleyin `examineButton_Click` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-175">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]  
  
     <span data-ttu-id="7dfae-176">Günlük dosyası seçilen dosyanın aynı dizine koyun için günlük dosyası yolu ayarlar.</span><span class="sxs-lookup"><span data-stu-id="7dfae-176">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="7dfae-177">Günlük girişi metnin geçerli tarih ve saate göre dosya bilgileri ve ardından ayarlanır.</span><span class="sxs-lookup"><span data-stu-id="7dfae-177">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="7dfae-178"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> Yöntemi ile `append` değişkenini `True`, günlük girişi oluşturmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7dfae-178">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2.  <span data-ttu-id="7dfae-179">Uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-179">Run the application.</span></span> <span data-ttu-id="7dfae-180">Bir metin dosyasına göz atın, seçin `ListBox`seçin **Sonuçları Kaydet** onay kutusunu işaretleyin ve ardından **inceleyin**.</span><span class="sxs-lookup"><span data-stu-id="7dfae-180">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="7dfae-181">Günlük girişi için yazıldığından emin olun `log.txt` dosya.</span><span class="sxs-lookup"><span data-stu-id="7dfae-181">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3.  <span data-ttu-id="7dfae-182">Uygulama çalışmayı durdurur.</span><span class="sxs-lookup"><span data-stu-id="7dfae-182">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="7dfae-183">Geçerli dizin kullanmak için</span><span class="sxs-lookup"><span data-stu-id="7dfae-183">To use the current directory</span></span>  
  
1.  <span data-ttu-id="7dfae-184">İçin bir olay işleyicisi oluşturun `Form1_Load` formun çift tıklatarak.</span><span class="sxs-lookup"><span data-stu-id="7dfae-184">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2.  <span data-ttu-id="7dfae-185">Olay işleyicisi için aşağıdaki kodu ekleyin.</span><span class="sxs-lookup"><span data-stu-id="7dfae-185">Add the following code to the event handler.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]  
  
     <span data-ttu-id="7dfae-186">Bu kod varsayılan dizini klasörü tarayıcının geçerli dizine ayarlar.</span><span class="sxs-lookup"><span data-stu-id="7dfae-186">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3.  <span data-ttu-id="7dfae-187">Uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-187">Run the application.</span></span> <span data-ttu-id="7dfae-188">Tıkladığınızda **Gözat** ilk kez **klasöre Gözat** geçerli dizine iletişim kutusu açılır.</span><span class="sxs-lookup"><span data-stu-id="7dfae-188">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4.  <span data-ttu-id="7dfae-189">Uygulama çalışmayı durdurur.</span><span class="sxs-lookup"><span data-stu-id="7dfae-189">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="7dfae-190">Denetimleri seçmeli olarak etkinleştirmek için</span><span class="sxs-lookup"><span data-stu-id="7dfae-190">To selectively enable controls</span></span>  
  
1.  <span data-ttu-id="7dfae-191">Aşağıdakileri ekleyin `SetEnabled` yöntemi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-191">Add the following `SetEnabled` method.</span></span>  
  
     [!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]  
  
     <span data-ttu-id="7dfae-192">`SetEnabled` Yöntemi etkinleştirir veya öğeyi olup seçildiyse bağlı olarak denetimleri devre dışı bırakan `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="7dfae-192">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2.  <span data-ttu-id="7dfae-193">Oluşturma bir `SelectedIndexChanged` için olay işleyicisini `filesListBox` çift tıklatarak `ListBox` form üzerinde denetim.</span><span class="sxs-lookup"><span data-stu-id="7dfae-193">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3.  <span data-ttu-id="7dfae-194">Bir çağrı ekleyin `SetEnabled` yeni `filesListBox_SelectedIndexChanged` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-194">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4.  <span data-ttu-id="7dfae-195">Bir çağrı ekleyin `SetEnabled` sonunda `browseButton_Click` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-195">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5.  <span data-ttu-id="7dfae-196">Bir çağrı ekleyin `SetEnabled` sonunda `Form1_Load` olay işleyicisi.</span><span class="sxs-lookup"><span data-stu-id="7dfae-196">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6.  <span data-ttu-id="7dfae-197">Uygulamayı çalıştırın.</span><span class="sxs-lookup"><span data-stu-id="7dfae-197">Run the application.</span></span> <span data-ttu-id="7dfae-198">**Sonuçları Kaydet** onay kutusunu ve **inceleyin** içinde bir öğe seçili değilse düğmesi devre dışı `ListBox`.</span><span class="sxs-lookup"><span data-stu-id="7dfae-198">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="7dfae-199">My.Computer.FileSystem kullanarak tam örnek</span><span class="sxs-lookup"><span data-stu-id="7dfae-199">Full example using My.Computer.FileSystem</span></span>  
 <span data-ttu-id="7dfae-200">Tam bir örnek verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="7dfae-200">Following is the complete example.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="7dfae-201">System.IO kullanarak tam örnek</span><span class="sxs-lookup"><span data-stu-id="7dfae-201">Full example using System.IO</span></span>  
 <span data-ttu-id="7dfae-202">Aşağıdaki eşdeğer örnek sınıflardan kullanır <xref:System.IO> kullanmak yerine ad alanı `My.Computer.FileSystem` nesneleri.</span><span class="sxs-lookup"><span data-stu-id="7dfae-202">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 [!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="7dfae-203">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7dfae-203">See Also</span></span>  
 <xref:System.IO>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A>  
 [<span data-ttu-id="7dfae-204">İzlenecek yol: .NET Framework yöntemlerini kullanarak dosyaları düzenleme</span><span class="sxs-lookup"><span data-stu-id="7dfae-204">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)