---
title: "Gizli üretim aynı anda korumak için Azure anahtar kasası kullanma"
description: "Kapsayıcılı .NET uygulamaları için .NET mikro mimarisi | Gizli üretim aynı anda korumak için Azure anahtar kasası kullanma"
keywords: "Docker, mikro, ASP.NET, kapsayıcı"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="b4382-104">Gizli üretim aynı anda korumak için Azure anahtar kasası kullanma</span><span class="sxs-lookup"><span data-stu-id="b4382-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="b4382-105">Ortam değişkenleri olarak depolanır veya gizli anahtarı Yöneticisi aracı tarafından depolanan gizli hala yerel olarak depolanan ve makinede şifrelenmemiş.</span><span class="sxs-lookup"><span data-stu-id="b4382-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="b4382-106">Parolaları depolamak için daha güvenli bir seçenektir; [Azure anahtar kasası](https://azure.microsoft.com/services/key-vault/), anahtarları ve parolaları saklamak için güvenli, merkezi bir konum sağlar.</span><span class="sxs-lookup"><span data-stu-id="b4382-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="b4382-107">Azure anahtar Kasası'nı yapılandırma bilgilerini okumak bir ASP.NET Core uygulama Microsoft.Extensions.Configuration.AzureKeyVault paketi sağlar.</span><span class="sxs-lookup"><span data-stu-id="b4382-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="b4382-108">Gizli anahtarları Azure anahtar Kasası'ndan kullanmaya başlamak için aşağıdaki adımları izleyin:</span><span class="sxs-lookup"><span data-stu-id="b4382-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="b4382-109">İlk olarak, uygulamanızı Azure AD uygulaması kaydedin.</span><span class="sxs-lookup"><span data-stu-id="b4382-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="b4382-110">(Anahtar kasalarını erişimi Azure AD tarafından yönetilir.) Bu, Azure Yönetim Portalı aracılığıyla yapılabilir.</span><span class="sxs-lookup"><span data-stu-id="b4382-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="b4382-111">Alternatif olarak, bir parola veya istemci gizli anahtarı yerine bir sertifika kullanarak kimlik doğrulaması için uygulamanızın istiyorsanız kullanabileceğiniz [yeni AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet'i.</span><span class="sxs-lookup"><span data-stu-id="b4382-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="b4382-112">Azure anahtar kasası ile kaydettiğiniz sertifika, ortak anahtar gerekir.</span><span class="sxs-lookup"><span data-stu-id="b4382-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="b4382-113">(Uygulamanızın özel anahtarı kullanır.)</span><span class="sxs-lookup"><span data-stu-id="b4382-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="b4382-114">İkinci olarak, yeni bir hizmet sorumlusu oluşturarak anahtar Kasası'na kayıtlı uygulama erişimi verin.</span><span class="sxs-lookup"><span data-stu-id="b4382-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="b4382-115">Aşağıdaki PowerShell komutlarını kullanarak bunu yapabilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b4382-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="b4382-116">Üçüncü anahtar kasası, uygulamanızda yapılandırma kaynağı olarak bir IConfigurationRoot örneği oluşturduğunuzda IConfigurationBuilder.AddAzureKeyVault genişletme yöntemi çağrılarak içerir.</span><span class="sxs-lookup"><span data-stu-id="b4382-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="b4382-117">AddAzureKeyVault çağrılırken, kayıtlı ve önceki adımları anahtar kasasına erişim verilen uygulama kimliği gerektirecektir unutmayın.</span><span class="sxs-lookup"><span data-stu-id="b4382-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="b4382-118">Şu anda .NET standart ve .NET Core Azure anahtar Kasası'ndan yapılandırma bilgileri alınırken bir istemci kimliği ve istemci gizli anahtarı kullanarak destekler.</span><span class="sxs-lookup"><span data-stu-id="b4382-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="b4382-119">.NET framework uygulamaları bir aşırı yüklemesini bir sertifika istemci gizli anahtarı yerine geçen IConfigurationBuilder.AddAzureKeyVault kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="b4382-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="b4382-120">Bu makalenin yazıldığı sırada iştir [devam eden](https://github.com/aspnet/Configuration/issues/605) Bu aşırı .NET standart ve .NET Core yapmak için.</span><span class="sxs-lookup"><span data-stu-id="b4382-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="b4382-121">Bir sertifika kullanılabilir kabul AddAzureKeyVault aşırı kadar ASP.NET Core uygulamaları bir Azure anahtar kasası sertifika tabanlı kimlik doğrulaması ile açıkça bir KeyVaultClient nesnesi oluşturarak aşağıdaki örnekte gösterildiği gibi erişebilirsiniz:</span><span class="sxs-lookup"><span data-stu-id="b4382-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

<span data-ttu-id="b4382-122">Bu örnekte, yapılandırma sağlayıcısı kaydını sonunda AddAzureKeyVault çağrısı gelir.</span><span class="sxs-lookup"><span data-stu-id="b4382-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="b4382-123">Azure anahtar kasası önceki sağlayıcılardan yapılandırma değerleri geçersiz kılmak fırsatına sahip olması ve böylece hiçbir yapılandırma değerlerini diğer kaynaklardan anahtar Kasası'ndan geçersiz kılabilir son yapılandırma sağlayıcısı olarak kaydetmek için en iyi bir uygulamadır.</span><span class="sxs-lookup"><span data-stu-id="b4382-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4382-124">Ek kaynaklar</span><span class="sxs-lookup"><span data-stu-id="b4382-124">Additional resources</span></span>

-   <span data-ttu-id="b4382-125">**Uygulama parolaları korumak için Azure anahtar kasası kullanarak**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="b4382-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="b4382-126">**Geliştirme sırasında uygulama sırrı güvenli depolama**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="b4382-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="b4382-127">**Veri korumasını yapılandırma**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="b4382-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="b4382-128">**Anahtar Yönetimi ve yaşam süresi**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#veri koruması varsayılan ayarları*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="b4382-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="b4382-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="b4382-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="b4382-130">GitHub depo.</span><span class="sxs-lookup"><span data-stu-id="b4382-130">GitHub repo.</span></span>
    [<span data-ttu-id="b4382-131">*https://github.com/ASPNET/Configuration/Tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="b4382-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="b4382-132">[Önceki] (Geliştirici-app-gizli-storage.md) [sonraki] (.. / anahtar takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="b4382-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>