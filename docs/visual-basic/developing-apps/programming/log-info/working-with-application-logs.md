---
title: "Visual Basic'te Uygulama Günlükleriyle Çalışma"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- logs, application
- application event logs, Visual Basic
- application event logs
ms.assetid: 2581afd1-5791-4bc4-86b2-46244e9fe468
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea5f3699ca5a1b6b0859ac266656deb933839d3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="working-with-application-logs-in-visual-basic"></a><span data-ttu-id="d8032-102">Visual Basic'te Uygulama Günlükleriyle Çalışma</span><span class="sxs-lookup"><span data-stu-id="d8032-102">Working with Application Logs in Visual Basic</span></span>
<span data-ttu-id="d8032-103">`My.Applicaton.Log` Ve `My.Log` nesneleri kolaylaştırır günlüğe kaydetme ve izleme bilgilerini günlüklere yazılır.</span><span class="sxs-lookup"><span data-stu-id="d8032-103">The `My.Applicaton.Log` and `My.Log` objects make it easy to write logging and tracing information to logs.</span></span>  
  
## <a name="how-messages-are-logged"></a><span data-ttu-id="d8032-104">İletileri nasıl kaydedilir</span><span class="sxs-lookup"><span data-stu-id="d8032-104">How Messages are Logged</span></span>  
 <span data-ttu-id="d8032-105">İlk olarak, ileti önem ile işaretli <xref:System.Diagnostics.TraceSource.Switch%2A> günlüğün özelliğinin <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d8032-105">First, the severity of the message is checked with the <xref:System.Diagnostics.TraceSource.Switch%2A> property of the log's <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A> property.</span></span> <span data-ttu-id="d8032-106">Tarafından varsayılan, önem derecesi "Bilgi", yalnızca iletiler ve daha yüksek günlüğün içinde belirtilen izleme dinleyicileri için geçirilir `TraceListener` koleksiyonu.</span><span class="sxs-lookup"><span data-stu-id="d8032-106">By default, only messages of severity "Information" and higher are passed on to the trace listeners, specified in the log's `TraceListener` collection.</span></span> <span data-ttu-id="d8032-107">Ardından, iletinin önem derecesini dinleyiciye'nın her dinleyicisi karşılaştırır <xref:System.Diagnostics.TraceSource.Switch%2A> özelliği.</span><span class="sxs-lookup"><span data-stu-id="d8032-107">Then, each listener compares the severity of the message to the listener's <xref:System.Diagnostics.TraceSource.Switch%2A> property.</span></span> <span data-ttu-id="d8032-108">İleti önem derecesi yeterince yüksekse, dinleyiciyi iletisi yazar.</span><span class="sxs-lookup"><span data-stu-id="d8032-108">If the message's severity is high enough, the listener writes out the message.</span></span>  
  
 <span data-ttu-id="d8032-109">Yazılan bir ileti nasıl gösterir Aşağıdaki diyagramda `WriteEntry` yöntemi geçirilen `WriteLine` günlüğün yöntemlerinin izleme dinleyicilerini:</span><span class="sxs-lookup"><span data-stu-id="d8032-109">The following diagram shows how a message written to the `WriteEntry` method gets passed to the `WriteLine` methods of the log's trace listeners:</span></span>  
  
 <span data-ttu-id="d8032-110">![My günlük çağrısı](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")</span><span class="sxs-lookup"><span data-stu-id="d8032-110">![My Log Call](../../../../visual-basic/developing-apps/programming/log-info/media/mylogcall.png "MyLogCall")</span></span>  
  
 <span data-ttu-id="d8032-111">Günlük ve izleme dinleyicilerini davranışını uygulamanın yapılandırma dosyasını değiştirerek değiştirebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8032-111">You can change the behavior of the log and the trace listeners by changing the application's configuration file.</span></span> <span data-ttu-id="d8032-112">Aşağıdaki diyagramda günlük bölümlerini ve yapılandırma dosyası arasındaki ilişkiyi gösterir.</span><span class="sxs-lookup"><span data-stu-id="d8032-112">The following diagram shows the correspondence between the parts of the log and the configuration file.</span></span>  
  
 <span data-ttu-id="d8032-113">![Günlük yapılandırma](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")</span><span class="sxs-lookup"><span data-stu-id="d8032-113">![My Log Configuration](../../../../visual-basic/developing-apps/programming/log-info/media/mylogconfig.png "MyLogConfig")</span></span>  
  
## <a name="where-messages-are-logged"></a><span data-ttu-id="d8032-114">İleti günlüğe nerede kaydedildiğini</span><span class="sxs-lookup"><span data-stu-id="d8032-114">Where Messages are Logged</span></span>  
 <span data-ttu-id="d8032-115">Derleme herhangi bir yapılandırma dosyası varsa `My.Application.Log` ve `My.Log` nesneleri yazmak için uygulamanın hata ayıklama çıktısı (aracılığıyla <xref:System.Diagnostics.DefaultTraceListener> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="d8032-115">If the assembly has no configuration file, the `My.Application.Log` and `My.Log` objects write to the application's debug output (through the <xref:System.Diagnostics.DefaultTraceListener> class).</span></span> <span data-ttu-id="d8032-116">Ayrıca, `My.Application.Log` nesneyi derlemenin günlük dosyasına yazar (aracılığıyla <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> sınıfı), sırada `My.Log` nesnesi Yazar ASP.NET Web sayfasının çıkış (aracılığıyla <xref:System.Web.WebPageTraceListener> sınıfı).</span><span class="sxs-lookup"><span data-stu-id="d8032-116">In addition, the `My.Application.Log` object writes to the assembly's log file (through the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class), while the `My.Log` object writes to the ASP.NET Web page's output (through the <xref:System.Web.WebPageTraceListener> class).</span></span>  
  
 <span data-ttu-id="d8032-117">Hata ayıklama çıktısı görüntülenebilir [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] **çıkış** uygulamanızı hata ayıklama modunda çalışırken penceresi.</span><span class="sxs-lookup"><span data-stu-id="d8032-117">The debug output can be viewed in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] **Output** window when running your application in debug mode.</span></span> <span data-ttu-id="d8032-118">Açmak için **çıkış** penceresinde tıklatın **hata ayıklama** menü öğesi, noktasına **Windows**ve ardından **çıkış**.</span><span class="sxs-lookup"><span data-stu-id="d8032-118">To open the **Output** window, click the **Debug** menu item, point to **Windows**, and then click **Output**.</span></span> <span data-ttu-id="d8032-119">İçinde **çıkış** penceresinde, seçin **hata ayıklama** gelen **Göster çıktı** kutusu.</span><span class="sxs-lookup"><span data-stu-id="d8032-119">In the **Output** window, select **Debug** from the **Show output from** box.</span></span>  
  
 <span data-ttu-id="d8032-120">Varsayılan olarak, `My.Application.Log` yolunda kullanıcının uygulama verileri için günlük dosyasına yazar.</span><span class="sxs-lookup"><span data-stu-id="d8032-120">By default, `My.Application.Log` writes the log file in the path for the user's application data.</span></span> <span data-ttu-id="d8032-121">Yolundan alabilirsiniz <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> özelliği <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> nesnesi.</span><span class="sxs-lookup"><span data-stu-id="d8032-121">You can get the path from the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.FullLogFileName%2A> property of the <xref:Microsoft.VisualBasic.Logging.Log.DefaultFileLogWriter%2A> object.</span></span> <span data-ttu-id="d8032-122">Bu yol biçimi aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="d8032-122">The format of that path is as follows:</span></span>  
  
 `BasePath`\\`CompanyName`\\`ProductName`\\`ProductVersion`  
  
 <span data-ttu-id="d8032-123">İçin tipik bir değer `BasePath` aşağıdaki gibidir.</span><span class="sxs-lookup"><span data-stu-id="d8032-123">A typical value for `BasePath` is as follows.</span></span>  
  
 <span data-ttu-id="d8032-124">C:\Documents and Settings\\`username`\Application veri</span><span class="sxs-lookup"><span data-stu-id="d8032-124">C:\Documents and Settings\\`username`\Application Data</span></span>  
  
 <span data-ttu-id="d8032-125">Değerlerini `CompanyName`, `ProductName`, ve `ProductVersion` uygulamanın derleme bilgilerinden gelir.</span><span class="sxs-lookup"><span data-stu-id="d8032-125">The values of `CompanyName`, `ProductName`, and `ProductVersion` come from the application's assembly information.</span></span> <span data-ttu-id="d8032-126">Günlük dosyası adı biçimidir *AssemblyName*.log, burada *AssemblyName* dosya adı uzantısı olmadan derlemenin.</span><span class="sxs-lookup"><span data-stu-id="d8032-126">The form of the log file name is *AssemblyName*.log, where *AssemblyName* is the file name of the assembly without the extension.</span></span> <span data-ttu-id="d8032-127">Özgün günlüğü kullanılamadığında uygulama günlüğüne yazılması çalıştığında gibi birden fazla günlük dosyası gerekli olursa, günlük dosyası adı için formdur *AssemblyName*-*yineleme* .log, burada `iteration` bir pozitif olan `Integer`.</span><span class="sxs-lookup"><span data-stu-id="d8032-127">If more than one log file is needed, such as when the original log is unavailable when the application attempts to write to the log, the form for the log file name is *AssemblyName*-*iteration*.log, where `iteration` is a positive `Integer`.</span></span>  
  
 <span data-ttu-id="d8032-128">Ekleyerek veya bilgisayarın ve uygulamanın yapılandırma dosyalarını değiştirerek varsayılan davranışı geçersiz kılabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8032-128">You can override the default behavior by adding or changing the computer's and the application's configuration files.</span></span> <span data-ttu-id="d8032-129">Daha fazla bilgi için bkz: [izlenecek yol: değiştirmeyi burada My.Application.Log Yazar bilgi](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span><span class="sxs-lookup"><span data-stu-id="d8032-129">For more information, see [Walkthrough: Changing Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md).</span></span>  
  
## <a name="configuring-log-settings"></a><span data-ttu-id="d8032-130">Günlük ayarlarını yapılandırma</span><span class="sxs-lookup"><span data-stu-id="d8032-130">Configuring Log Settings</span></span>  
 <span data-ttu-id="d8032-131">`Log` Nesnesi, bir uygulama yapılandırma dosyası çalışır bir varsayılan uygulama sahip app.config. Varsayılanları değiştirmek için yeni ayarlar ile bir yapılandırma dosyası eklemeniz gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8032-131">The `Log` object has a default implementation that works without an application configuration file, app.config. To change the defaults, you must add a configuration file with the new settings.</span></span> <span data-ttu-id="d8032-132">Daha fazla bilgi için bkz: [izlenecek yol: My.Application.Log çıktısını filtreleme](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span><span class="sxs-lookup"><span data-stu-id="d8032-132">For more information, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="d8032-133">Günlük yapılandırma bölümlerinin bulunan `<system.diagnostics>` ana düğümünde `<configuration>` app.config dosyasının düğümü.</span><span class="sxs-lookup"><span data-stu-id="d8032-133">The log configuration sections are located in the `<system.diagnostics>` node in the main `<configuration>` node of the app.config file.</span></span> <span data-ttu-id="d8032-134">Günlük bilgilerini birkaç düğümü tanımlanır:</span><span class="sxs-lookup"><span data-stu-id="d8032-134">Log information is defined in several nodes:</span></span>  
  
-   <span data-ttu-id="d8032-135">Dinleyicileri için `Log` nesne tanımlanmış `<sources>` DefaultSource adlı düğüm.</span><span class="sxs-lookup"><span data-stu-id="d8032-135">The listeners for the `Log` object are defined in the `<sources>` node named DefaultSource.</span></span>  
  
-   <span data-ttu-id="d8032-136">Önem derecesi filtresi `Log` nesne tanımlanmış `<switches>` DefaultSwitch adlı düğüm.</span><span class="sxs-lookup"><span data-stu-id="d8032-136">The severity filter for the `Log` object is defined in the `<switches>` node named DefaultSwitch.</span></span>  
  
-   <span data-ttu-id="d8032-137">Günlük dinleyicileri tanımlanan `<sharedListeners>` düğümü.</span><span class="sxs-lookup"><span data-stu-id="d8032-137">The log listeners are defined in the `<sharedListeners>` node.</span></span>  
  
 <span data-ttu-id="d8032-138">Örnekleri `<sources>`, `<switches>`, ve `<sharedListeners>` düğümleri aşağıdaki kodda gösterildiği:</span><span class="sxs-lookup"><span data-stu-id="d8032-138">Examples of `<sources>`, `<switches>`, and `<sharedListeners>` nodes are shown in the following code:</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="DefaultSource" switchName="DefaultSwitch">  
        <listeners>  
          <add name="FileLog"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="DefaultSwitch" value="Information" />  
    </switches>  
    <sharedListeners>  
      <add name="FileLog"  
        type="Microsoft.VisualBasic.Logging.FileLogTraceListener,  
          Microsoft.VisualBasic, Version=8.0.0.0, Culture=neutral,   
          PublicKeyToken=b03f5f7f11d50a3a, processorArchitecture=MSIL"  
        initializeData="FileLogWriter"  
      />  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="changing-log-settings-after-deployment"></a><span data-ttu-id="d8032-139">Dağıtımdan sonra günlük ayarlarını değiştirme</span><span class="sxs-lookup"><span data-stu-id="d8032-139">Changing Log Settings after Deployment</span></span>  
 <span data-ttu-id="d8032-140">Bir uygulama geliştirirken, yapılandırma ayarlarını Yukarıdaki örneklerde gösterildiği gibi app.config dosyasında depolanır.</span><span class="sxs-lookup"><span data-stu-id="d8032-140">When you develop an application, its configuration settings are stored in the app.config file, as shown in the examples above.</span></span> <span data-ttu-id="d8032-141">Uygulamanızı dağıttıktan sonra yapılandırma dosyasını düzenleyerek günlük yapılandırabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="d8032-141">After you deploy your application, you can still configure the log by editing the configuration file.</span></span> <span data-ttu-id="d8032-142">Windows tabanlı bir uygulama, bu dosyanın adıdır *applicationName*. exe.config ve yürütülebilir dosya ile aynı klasörde bulunmalıdır.</span><span class="sxs-lookup"><span data-stu-id="d8032-142">In a Windows-based application, this file's name is *applicationName*.exe.config, and it must reside in the same folder as the executable file.</span></span> <span data-ttu-id="d8032-143">Bir Web uygulaması için bu yöntem, projeyle ilişkili Web.config dosyasıdır.</span><span class="sxs-lookup"><span data-stu-id="d8032-143">For a Web application, this is the Web.config file associated with the project.</span></span>  
  
 <span data-ttu-id="d8032-144">Uygulamanızı ilk kez bir sınıfının bir örneği oluşturan kodu yürütüldüğünde, nesne hakkında bilgi için yapılandırma dosyasını denetler.</span><span class="sxs-lookup"><span data-stu-id="d8032-144">When your application executes the code that creates an instance of a class for the first time, it checks the configuration file for information about the object.</span></span> <span data-ttu-id="d8032-145">İçin `Log` nesnesi, ilk defa aşması `Log` nesne erişilir.</span><span class="sxs-lookup"><span data-stu-id="d8032-145">For the `Log` object, this happens the first time the `Log` object is accessed.</span></span> <span data-ttu-id="d8032-146">Yapılandırma dosyası herhangi belirli bir nesnesi için yalnızca bir kez sistem inceler — ilk kez uygulamanızı nesnesi oluşturur.</span><span class="sxs-lookup"><span data-stu-id="d8032-146">The system examines the configuration file only once for any particular object—the first time your application creates the object.</span></span> <span data-ttu-id="d8032-147">Bu nedenle, değişikliklerin etkili olması uygulamanın yeniden başlatmanız gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="d8032-147">Therefore, you may need to restart the application for the changes to take effect.</span></span>  
  
 <span data-ttu-id="d8032-148">Dağıtılan bir uygulama, uygulama başlatılmadan önce anahtar nesneleri yapılandırarak izleme kodu etkinleştirin.</span><span class="sxs-lookup"><span data-stu-id="d8032-148">In a deployed application, you enable trace code by reconfiguring switch objects before your application starts.</span></span> <span data-ttu-id="d8032-149">Genellikle, bu anahtar nesneleri ve devre dışı veya üzerinde izleme düzeylerini değiştirme ve uygulamanızı yeniden başlatmayı içerir.</span><span class="sxs-lookup"><span data-stu-id="d8032-149">Typically, this involves turning the switch objects on and off or by changing the tracing levels, and then restarting your application.</span></span>  
  
## <a name="security-considerations"></a><span data-ttu-id="d8032-150">Güvenlik Değerlendirmeleri</span><span class="sxs-lookup"><span data-stu-id="d8032-150">Security Considerations</span></span>  
 <span data-ttu-id="d8032-151">Aşağıdaki veriler günlüğe yazılırken göz önünde bulundurun:</span><span class="sxs-lookup"><span data-stu-id="d8032-151">Consider the following when writing data to the log:</span></span>  
  
-   <span data-ttu-id="d8032-152">**Kullanıcı bilgilerini sızmasını önleyin.**</span><span class="sxs-lookup"><span data-stu-id="d8032-152">**Avoid leaking user information.**</span></span> <span data-ttu-id="d8032-153">Uygulama yazma günlüğe yazılacak bilgi yalnızca onaylanan emin olun.</span><span class="sxs-lookup"><span data-stu-id="d8032-153">Ensure that your application writes only approved information to the log.</span></span> <span data-ttu-id="d8032-154">Örneğin, kullanıcı adları, ancak kullanıcı parolalarını içerecek şekilde için Uygulama günlüğünü kabul edilebilir olabilir.</span><span class="sxs-lookup"><span data-stu-id="d8032-154">For example, it may be acceptable for the application log to contain user names, but not user passwords.</span></span>  
  
-   <span data-ttu-id="d8032-155">**Günlük konumları güvenli olun.**</span><span class="sxs-lookup"><span data-stu-id="d8032-155">**Make log locations secure.**</span></span> <span data-ttu-id="d8032-156">Olası hassas bilgiler içeren günlük güvenli bir konumda depolanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="d8032-156">Any log that contains potentially sensitive information should be stored in a secure location.</span></span>  
  
-   <span data-ttu-id="d8032-157">**Yanıltıcı bilgi kaçının.**</span><span class="sxs-lookup"><span data-stu-id="d8032-157">**Avoid misleading information.**</span></span> <span data-ttu-id="d8032-158">Genel olarak, uygulamanız bu verileri kullanmadan önce bir kullanıcı tarafından girilen tüm veriler doğrulamalıdır.</span><span class="sxs-lookup"><span data-stu-id="d8032-158">In general, your application should validate all data entered by a user before using that data.</span></span> <span data-ttu-id="d8032-159">Bu veri uygulama günlüğüne yazma içerir.</span><span class="sxs-lookup"><span data-stu-id="d8032-159">This includes writing data to the application log.</span></span>  
  
-   <span data-ttu-id="d8032-160">**Hizmet reddi kaçının.**</span><span class="sxs-lookup"><span data-stu-id="d8032-160">**Avoid denial of service.**</span></span> <span data-ttu-id="d8032-161">Uygulamanız çok fazla bilgileri günlüğe yazar. varsa, bu günlük doldurun veya önemli bilgiler zor bulabilmek.</span><span class="sxs-lookup"><span data-stu-id="d8032-161">If your application writes too much information to the log, it could fill the log or make finding important information difficult.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8032-162">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="d8032-162">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 [<span data-ttu-id="d8032-163">Uygulama içinden bilgileri günlüğe kaydetme</span><span class="sxs-lookup"><span data-stu-id="d8032-163">Logging Information from the Application</span></span>](../../../../visual-basic/developing-apps/programming/log-info/logging-information-from-the-application.md)