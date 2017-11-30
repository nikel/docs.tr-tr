---
title: ".NET Core kaynağından derleme"
description: ".NET Core ve kaynak kodu .NET Core CLI oluşturmayı öğrenin."
keywords: ".NET, .NET core, kaynak, yapı"
author: bleroy
ms.author: mairaw
ms.date: 06/28/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8b49079c-6ede-429a-92d7-ecd2fda1ab0e
ms.openlocfilehash: b2e62074992432dc5ee1360e17f87c782685dc35
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="build-net-core-from-source"></a><span data-ttu-id="c05f1-104">.NET Core kaynağından derleme</span><span class="sxs-lookup"><span data-stu-id="c05f1-104">Build .NET Core from source</span></span>

<span data-ttu-id="c05f1-105">.NET Core kendi kaynak kodundan oluşturma yeteneği birden çok yolla önemlidir: .NET Core numaralı bağlantı noktasına yeni platformlar için kolaylaştırır, katkı sağlar ve düzeltmeleri ürüne ve .NET özel sürümlerinin oluşturulmasını sağlar.</span><span class="sxs-lookup"><span data-stu-id="c05f1-105">The ability to build .NET Core from its source code is important in multiple ways: it makes it easier to port .NET Core to new platforms, it enables contributions and fixes to the product, and it enables the creation of custom versions of .NET.</span></span>
<span data-ttu-id="c05f1-106">Bu makalede oluşturmak ve kendi sürümlerini .NET Core dağıtmak isteyen geliştiriciler için yönergeler sağlar.</span><span class="sxs-lookup"><span data-stu-id="c05f1-106">This article gives guidance to developers who want to build and distribute their own versions of .NET Core.</span></span>

## <a name="build-the-clr-from-source"></a><span data-ttu-id="c05f1-107">Kaynağından CLR derleme</span><span class="sxs-lookup"><span data-stu-id="c05f1-107">Build the CLR from source</span></span>

<span data-ttu-id="c05f1-108">.NET CoreCLR için kaynak kodunu bulunabilir [ `dotnet/coreclr` github'daki](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="c05f1-108">The source code for the .NET CoreCLR can be found in [the `dotnet/coreclr` repository on GitHub](https://github.com/dotnet/coreclr/).</span></span>

<span data-ttu-id="c05f1-109">Yapı şu anda üzerinde aşağıdaki önkoşullar bağlıdır:</span><span class="sxs-lookup"><span data-stu-id="c05f1-109">The build currently depends on the following prerequisites:</span></span>
* [<span data-ttu-id="c05f1-110">Git</span><span class="sxs-lookup"><span data-stu-id="c05f1-110">Git</span></span>](https://git-scm.com/)
* [<span data-ttu-id="c05f1-111">CMake</span><span class="sxs-lookup"><span data-stu-id="c05f1-111">CMake</span></span>](https://cmake.org/)
* [<span data-ttu-id="c05f1-112">Python</span><span class="sxs-lookup"><span data-stu-id="c05f1-112">Python</span></span>](https://www.python.org/)
* <span data-ttu-id="c05f1-113">C++ derleyicisi.</span><span class="sxs-lookup"><span data-stu-id="c05f1-113">a C++ compiler.</span></span>

<span data-ttu-id="c05f1-114">Yükledikten sonra bu Önkoşullar yüklendi, derleme betiğindeki çağırarak CLR oluşturabilirsiniz (`build.cmd` , Windows'da veya `build.sh` Linux ve macOS) temeline [CoreCLR depo](https://github.com/dotnet/coreclr/).</span><span class="sxs-lookup"><span data-stu-id="c05f1-114">After you've installed these prerequisites are installed, you can build the CLR by invoking the build script (`build.cmd` on Windows, or `build.sh` on Linux and macOS) at the base of [the CoreCLR repository](https://github.com/dotnet/coreclr/).</span></span>

<span data-ttu-id="c05f1-115">Bileşenlerini yükleme (OS) işletim sistemine bağlı olarak farklılık gösterir.</span><span class="sxs-lookup"><span data-stu-id="c05f1-115">Installing the components differ depending on the operating system (OS).</span></span> <span data-ttu-id="c05f1-116">Belirli işletim sisteminizi yapı yönergelerine bakın:</span><span class="sxs-lookup"><span data-stu-id="c05f1-116">See the build instructions for your specific OS:</span></span>

 * [<span data-ttu-id="c05f1-117">Windows</span><span class="sxs-lookup"><span data-stu-id="c05f1-117">Windows</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/windows-instructions.md)
 * [<span data-ttu-id="c05f1-118">Linux</span><span class="sxs-lookup"><span data-stu-id="c05f1-118">Linux</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/linux-instructions.md)
 * [<span data-ttu-id="c05f1-119">macOS</span><span class="sxs-lookup"><span data-stu-id="c05f1-119">macOS</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/osx-instructions.md)
 * [<span data-ttu-id="c05f1-120">FreeBSD</span><span class="sxs-lookup"><span data-stu-id="c05f1-120">FreeBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/freebsd-instructions.md) 
 * [<span data-ttu-id="c05f1-121">NetBSD</span><span class="sxs-lookup"><span data-stu-id="c05f1-121">NetBSD</span></span>](https://github.com/dotnet/coreclr/blob/master/Documentation/building/netbsd-instructions.md)

<span data-ttu-id="c05f1-122">İşletim sistemi (X64 üzerinde yerleşik yalnızca ARM için) arasında çapraz yapı yoktur.</span><span class="sxs-lookup"><span data-stu-id="c05f1-122">There is no cross-building across OS (only for ARM, which is built on X64).</span></span>  
<span data-ttu-id="c05f1-123">Bu platform oluşturmak için belirli platformda olması gerekir.</span><span class="sxs-lookup"><span data-stu-id="c05f1-123">You have to be on the particular platform to build that platform.</span></span>  

<span data-ttu-id="c05f1-124">İki ana derleme sahip `buildTypes`:</span><span class="sxs-lookup"><span data-stu-id="c05f1-124">The build has two main `buildTypes`:</span></span>

 * <span data-ttu-id="c05f1-125">Hata ayıklama (varsayılan) - en az en iyi duruma getirme ve ek çalışma zamanı denetimleri ile çalışma zamanı derler (onaylar).</span><span class="sxs-lookup"><span data-stu-id="c05f1-125">Debug (default)- Compiles the runtime with minimal optimizations and additional runtime checks (asserts).</span></span> <span data-ttu-id="c05f1-126">Bu en iyi duruma getirme düzeyini düşüş ve ek denetimler çalışma zamanı yürütme yavaş ancak hata ayıklama için değerlidir.</span><span class="sxs-lookup"><span data-stu-id="c05f1-126">This reduction in optimization level and the additional checks slow runtime execution but are valuable for debugging.</span></span> <span data-ttu-id="c05f1-127">Geliştirme ve test ortamları için Önerilen ayar budur.</span><span class="sxs-lookup"><span data-stu-id="c05f1-127">This is the recommended setting for development and testing environments.</span></span>
 * <span data-ttu-id="c05f1-128">Yayın - ek çalışma zamanı denetimleri olmadan tam iyileştirmeler ile çalışma zamanı derler.</span><span class="sxs-lookup"><span data-stu-id="c05f1-128">Release - Compiles the runtime with full optimizations and without the additional runtime checks.</span></span> <span data-ttu-id="c05f1-129">Bu kadar daha hızlı çalışma süresi performans sunacak ancak oluşturmak biraz uzun sürebilir ve hata ayıklama zor olabilir.</span><span class="sxs-lookup"><span data-stu-id="c05f1-129">This will yield much faster run time performance but it can take a bit longer to build and can be difficult to debug.</span></span> <span data-ttu-id="c05f1-130">Geçirmek `release` yapı bu seçmek için komut dosyası derleme türü.</span><span class="sxs-lookup"><span data-stu-id="c05f1-130">Pass `release` to the build script to select this build type.</span></span>

<span data-ttu-id="c05f1-131">Ayrıca, varsayılan olarak yapı yalnızca çalışma zamanı yürütülebilir dosyaları oluşturur, ancak aynı zamanda tüm testleri oluşturur.</span><span class="sxs-lookup"><span data-stu-id="c05f1-131">In addition, by default the build not only creates the runtime executables, but it also builds all the tests.</span></span>
<span data-ttu-id="c05f1-132">Önemli miktarda yalnızca değişikliklerle denemek istiyorsanız, gerekli olmayan zaman ayırdığınız oldukça birkaç testleri vardır.</span><span class="sxs-lookup"><span data-stu-id="c05f1-132">There are quite a few tests, taking a significant amount of time that isn't necessary if you just want to experiment with changes.</span></span>
<span data-ttu-id="c05f1-133">Ekleyerek testleri derlemeleri atlayabilirsiniz `skiptests` yapı komut bağımsız değişkeni aşağıdaki örnekteki gibi (Değiştir `.\build` ile `./build.sh` UNIX makinelerde):</span><span class="sxs-lookup"><span data-stu-id="c05f1-133">You can skip the tests builds by adding the `skiptests` argument to the build script, like in the following example (replace `.\build` with `./build.sh` on Unix machines):</span></span>

```bat
    .\build skiptests 
```

<span data-ttu-id="c05f1-134">Önceki örnekte gösterilen nasıl oluşturulacağını `Debug` geliştirme zamanı denetimleri sahip özellik (onaylar) etkin ve en iyi duruma getirme devre dışı.</span><span class="sxs-lookup"><span data-stu-id="c05f1-134">The previous example showed how to build the `Debug` flavor, which has development time checks (asserts) enabled and optimizations disabled.</span></span> <span data-ttu-id="c05f1-135">Yayın (tam hız) özellik oluşturmak için aşağıdakileri yapın:</span><span class="sxs-lookup"><span data-stu-id="c05f1-135">To build the release (full speed) flavor, do the following:</span></span>

```bat 
    .\build release skiptests
```

<span data-ttu-id="c05f1-136">Daha fazla yapı seçenekleri ile yapı kullanarak bulabilirsiniz?</span><span class="sxs-lookup"><span data-stu-id="c05f1-136">You can find more build options with build by using the -?</span></span> <span data-ttu-id="c05f1-137">ya da-niteleyici yardımcı olun.</span><span class="sxs-lookup"><span data-stu-id="c05f1-137">or -help qualifier.</span></span>   

### <a name="using-your-build"></a><span data-ttu-id="c05f1-138">Yapınızı kullanma</span><span class="sxs-lookup"><span data-stu-id="c05f1-138">Using Your Build</span></span>

<span data-ttu-id="c05f1-139">Yapı tüm altında oluşturulan dosyaları yerleştirir `bin` depo tabanında dizin.</span><span class="sxs-lookup"><span data-stu-id="c05f1-139">The build places all of its generated files under the `bin` directory at the base of the repository.</span></span>
<span data-ttu-id="c05f1-140">Var olan bir *bin\Log* (en yapı başarısız olduğunda yararlı) derleme sırasında oluşturulan günlük dosyalarını içeren dizini.</span><span class="sxs-lookup"><span data-stu-id="c05f1-140">There is a *bin\Log* directory that contains log files generated during the build (Most useful when the build fails).</span></span>
<span data-ttu-id="c05f1-141">Gerçek çıkış yerleştirilen bir *bin\Product\[platform]. [ CPU mimarisi]. [türü yapı]*  gibi dizin *bin\Product\Windows_NT.x64.Release*.</span><span class="sxs-lookup"><span data-stu-id="c05f1-141">The actual output is placed in a *bin\Product\[platform].[CPU architecture].[build type]* directory, such as *bin\Product\Windows_NT.x64.Release*.</span></span>

<span data-ttu-id="c05f1-142">Derleme 'ham' çıktısı bazen yararlı olsa da, normalde yalnızca yerleştirilir NuGet paketlerini ilgilendiğiniz `.nuget\pkg` önceki çıkış dizininin alt.</span><span class="sxs-lookup"><span data-stu-id="c05f1-142">While the 'raw' output of the build is sometimes useful, normally you're only interested in the NuGet packages, which are placed in the `.nuget\pkg` subdirectory of the previous output directory.</span></span>

<span data-ttu-id="c05f1-143">Yeni, çalışma zamanı kullanmak için iki temel teknikler şunlardır:</span><span class="sxs-lookup"><span data-stu-id="c05f1-143">There are two basic techniques for using your new runtime:</span></span>

 1. <span data-ttu-id="c05f1-144">**Dotnet.exe ve kullanma NuGet bir uygulama oluşturmak için**.</span><span class="sxs-lookup"><span data-stu-id="c05f1-144">**Use dotnet.exe and NuGet to compose an application**.</span></span>
    <span data-ttu-id="c05f1-145">Bkz: [kullanarak bilgisayarınızı yapı](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) kullanarak, yeni çalışma zamanı kullanan bir program oluşturma yönergeleri için NuGet, yeni oluşturduğunuz ve 'dotnet' komut satırı arabirimi (CLI) paketleri.</span><span class="sxs-lookup"><span data-stu-id="c05f1-145">See [Using Your Build](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingYourBuild.md) for instructions on creating a program that uses your new runtime by using the NuGet packages you just created and the 'dotnet' command-line interface (CLI).</span></span> <span data-ttu-id="c05f1-146">Beklenen şekilde çalışma zamanı olmayan geliştiriciler, yeni çalışma zamanı kullanmak büyük olasılıkla bu tekniğidir.</span><span class="sxs-lookup"><span data-stu-id="c05f1-146">This technique is the expected way non-runtime developers are likely to consume your new runtime.</span></span>    

 2. <span data-ttu-id="c05f1-147">**Corerun.exe paketlenmemiş taleplere DLL'leri kullanarak bir uygulamayı çalıştırmak için kullandığınız**.</span><span class="sxs-lookup"><span data-stu-id="c05f1-147">**Use corerun.exe to run an application using unpackaged DLLs**.</span></span>
    <span data-ttu-id="c05f1-148">Bu depo, ayrıca herhangi bir bağımlılığı NuGet üzerinde almaz corerun.exe adlı basit bir ana bilgisayar tanımlar.</span><span class="sxs-lookup"><span data-stu-id="c05f1-148">This repository also defines a simple host called corerun.exe that does NOT take any dependency on NuGet.</span></span>
    <span data-ttu-id="c05f1-149">Ana bilgisayar gerçekten gerekli DLL'leri alınacağı bildirmeniz gerekir ve el ile araya toplamak zorunda.</span><span class="sxs-lookup"><span data-stu-id="c05f1-149">You need to tell the host where to get the required DLLs you actually use, and you have to manually gather them together.</span></span>
    <span data-ttu-id="c05f1-150">Bu teknik tüm testler tarafından kullanılan [CoreCLR depoyu](https://github.com/dotnet/coreclr)ve ön birim testi gibi hızlı yerel 'düzenleme-derleme-debug' döngü için kullanışlıdır.</span><span class="sxs-lookup"><span data-stu-id="c05f1-150">This technique is used by all the tests in [the CoreCLR repo](https://github.com/dotnet/coreclr), and is useful for quick local 'edit-compile-debug' loop such as preliminary unit testing.</span></span>
    <span data-ttu-id="c05f1-151">Bkz: [yürütme .NET Core uygulamalarla CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) Bu teknik kullanımıyla ilgili ayrıntılar için.</span><span class="sxs-lookup"><span data-stu-id="c05f1-151">See [Executing .NET Core Apps with CoreRun.exe](https://github.com/dotnet/coreclr/blob/master/Documentation/workflow/UsingCoreRun.md) for details on using this technique.</span></span>

## <a name="build-the-cli-from-source"></a><span data-ttu-id="c05f1-152">CLI kaynağından derleme</span><span class="sxs-lookup"><span data-stu-id="c05f1-152">Build the CLI from source</span></span>

<span data-ttu-id="c05f1-153">.NET Core CLI için kaynak kodunu bulunabilir [ `dotnet/cli` github'daki](https://github.com/dotnet/cli/).</span><span class="sxs-lookup"><span data-stu-id="c05f1-153">The source code for the .NET Core CLI can be found in [the `dotnet/cli` repository on GitHub](https://github.com/dotnet/cli/).</span></span>

<span data-ttu-id="c05f1-154">.NET Core CLI oluşturmak için aşağıdaki makinenize yüklü gerekir.</span><span class="sxs-lookup"><span data-stu-id="c05f1-154">In order to build the .NET Core CLI, you need the following installed on your machine.</span></span>

* <span data-ttu-id="c05f1-155">Windows ve Linux:</span><span class="sxs-lookup"><span data-stu-id="c05f1-155">Windows & Linux:</span></span>
    - <span data-ttu-id="c05f1-156">YOL üzerindeki Git</span><span class="sxs-lookup"><span data-stu-id="c05f1-156">git on the PATH</span></span>
* <span data-ttu-id="c05f1-157">macOS:</span><span class="sxs-lookup"><span data-stu-id="c05f1-157">macOS:</span></span>
    - <span data-ttu-id="c05f1-158">YOL üzerindeki Git</span><span class="sxs-lookup"><span data-stu-id="c05f1-158">git on the PATH</span></span>
    - <span data-ttu-id="c05f1-159">Xcode</span><span class="sxs-lookup"><span data-stu-id="c05f1-159">Xcode</span></span>
    - <span data-ttu-id="c05f1-160">Openssl</span><span class="sxs-lookup"><span data-stu-id="c05f1-160">OpenSSL</span></span>

<span data-ttu-id="c05f1-161">Derleme için çalıştırın `build.cmd` , Windows'da veya `build.sh` Linux ve kök macOS.</span><span class="sxs-lookup"><span data-stu-id="c05f1-161">In order to build, run `build.cmd` on Windows, or `build.sh` on Linux and macOS from the root.</span></span> <span data-ttu-id="c05f1-162">Testler yürütmek istemiyorsanız, çalıştırmak `build.cmd /t:Compile` veya `./build.sh /t:Compile`.</span><span class="sxs-lookup"><span data-stu-id="c05f1-162">If you don't want to execute tests, run `build.cmd /t:Compile` or `./build.sh /t:Compile`.</span></span> <span data-ttu-id="c05f1-163">MacOS Sierra CLI oluşturmak için DOTNET_RUNTIME_ID ortam değişkeni çalıştırarak ayarlamanız gerektiğini `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span><span class="sxs-lookup"><span data-stu-id="c05f1-163">To build the CLI in macOS Sierra, you need to set the DOTNET_RUNTIME_ID environment variable by running `export DOTNET_RUNTIME_ID=osx.10.11-x64`.</span></span>

### <a name="using-your-build"></a><span data-ttu-id="c05f1-164">Yapınızı kullanma</span><span class="sxs-lookup"><span data-stu-id="c05f1-164">Using your build</span></span>

<span data-ttu-id="c05f1-165">Kullanım `dotnet` gelen yürütülebilir *yapıları / {os}-{arch} / stage2* yeni oluşturulan CLI denemek için.</span><span class="sxs-lookup"><span data-stu-id="c05f1-165">Use the `dotnet` executable from *artifacts/{os}-{arch}/stage2* to try out the newly built CLI.</span></span> <span data-ttu-id="c05f1-166">Çağrılırken, çıktı yapı kullanmak istiyorsanız, `dotnet` geçerli konsolundan de ekleyebilirsiniz *yapıları / {os}-{arch} / stage2* yolu.</span><span class="sxs-lookup"><span data-stu-id="c05f1-166">If you want to use the build output when invoking `dotnet` from the current console, you can also add *artifacts/{os}-{arch}/stage2* to the PATH.</span></span>

## <a name="see-also"></a><span data-ttu-id="c05f1-167">Ayrıca bkz.</span><span class="sxs-lookup"><span data-stu-id="c05f1-167">See also</span></span>

* [<span data-ttu-id="c05f1-168">.NET core ortak dil çalışma zamanı (CoreCLR)</span><span class="sxs-lookup"><span data-stu-id="c05f1-168">.NET Core Common Language Runtime (CoreCLR)</span></span>](https://github.com/dotnet/coreclr/blob/master/README.md)
* [<span data-ttu-id="c05f1-169">.NET core CLI Geliştirici Kılavuzu</span><span class="sxs-lookup"><span data-stu-id="c05f1-169">.NET Core CLI Developer Guide</span></span>](https://github.com/dotnet/cli/blob/master/Documentation/project-docs/developer-guide.md)
* [<span data-ttu-id="c05f1-170">.NET core dağıtım paketleme</span><span class="sxs-lookup"><span data-stu-id="c05f1-170">.NET Core distribution packaging</span></span>](./distribution-packaging.md)