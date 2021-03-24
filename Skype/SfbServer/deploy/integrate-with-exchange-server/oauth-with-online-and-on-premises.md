---
title: Intégration entre Skype Entreprise Online et Exchange Server
ms.reviewer: cbland
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange local et Skype Entreprise Online active les fonctionnalités Skype Entreprise et Intégration Exchange décrites dans la prise en charge des fonctionnalités.
ms.openlocfilehash: 342362926ad0af169acd6c9af4715008425e71c7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109710"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="a4235-103">Configurer l’intégration et OAuth entre Skype Entreprise Online et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="a4235-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="a4235-104">La configuration de l’intégration entre Exchange Server et Skype Entreprise Online active les fonctionnalités Skype Entreprise et Intégration Exchange décrites dans la prise en charge [des fonctionnalités.](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)</span><span class="sxs-lookup"><span data-stu-id="a4235-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="a4235-105">Cette rubrique s’applique à l’intégration Exchange Server 2013 à 2019.</span><span class="sxs-lookup"><span data-stu-id="a4235-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a4235-106">Ce qu’il faut savoir avant de commencer</span><span class="sxs-lookup"><span data-stu-id="a4235-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a4235-107">Durée d'exécution estimée de cette tâche : 15 minutes</span><span class="sxs-lookup"><span data-stu-id="a4235-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="a4235-108">Des autorisations doivent vous être attribuées avant de pouvoir exécuter cette procédure.</span><span class="sxs-lookup"><span data-stu-id="a4235-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="a4235-109">Pour voir les autorisations qui vous sont nécessaires, consultez la rubrique [Autorisations d’infrastructure Exchange et Shell.](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help)</span><span class="sxs-lookup"><span data-stu-id="a4235-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](/exchange/exchange-and-shell-infrastructure-permissions-exchange-2013-help) topic.</span></span>

- <span data-ttu-id="a4235-110">Pour obtenir des informations sur les raccourcis clavier applicables aux procédures de cette rubrique, reportez-vous à l’article [Raccourcis clavier dans le Centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="a4235-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="a4235-111">Pour plus d’informations sur la compatibilité, voir Compatibilité de Skype Entreprise [avec les applications Office.](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md)</span><span class="sxs-lookup"><span data-stu-id="a4235-111">For information about compatibility, see [Skype for Business compatibility with Office apps](../../plan-your-deployment/clients-and-devices/compatibility-with-office.md).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="a4235-112">Configurer l’intégration entre Exchange Server et O365</span><span class="sxs-lookup"><span data-stu-id="a4235-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="a4235-113">Étape 1 : Configurer l’authentification OAuth entre Exchange Server et O365</span><span class="sxs-lookup"><span data-stu-id="a4235-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="a4235-114">Effectuez les étapes de l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="a4235-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="a4235-115">Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a4235-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="a4235-116">Étape 2 : Créer un compte d’utilisateur de messagerie pour l’application partenaire Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a4235-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="a4235-117">Cette étape est effectuée sur le serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4235-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="a4235-118">Il crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion appropriés.</span><span class="sxs-lookup"><span data-stu-id="a4235-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="a4235-119">Ce compte sera ensuite utilisé à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="a4235-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="a4235-120">Spécifiez un domaine vérifié pour votre organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="a4235-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="a4235-121">Ce domaine doit être le même domaine que celui utilisé comme domaine SMTP principal pour les comptes Exchange locaux.</span><span class="sxs-lookup"><span data-stu-id="a4235-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="a4235-122">Ce domaine est appelé dans \<your Verified Domain\> la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="a4235-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="a4235-123">En outre, \<DomainControllerFQDN\> il doit s’agit du nom de domaine (FQDN) d’un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="a4235-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

```powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="a4235-124">Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a4235-124">This command will hide the new mail user from address lists.</span></span>

```powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="a4235-125">Les deux commandes suivantes affecteront le rôle de gestion UserApplication et ArchiveApplication à ce nouveau compte.</span><span class="sxs-lookup"><span data-stu-id="a4235-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

```powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

```powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="a4235-126">Étape 3 : Créer et activer une application partenaire pour Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="a4235-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="a4235-127">Créez une application partenaire et utilisez le compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="a4235-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="a4235-128">Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="a4235-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

```powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="a4235-129">Étape 4 : Exporter le certificat d’autorisation local</span><span class="sxs-lookup"><span data-stu-id="a4235-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="a4235-130">Exécutez un script PowerShell pour exporter le certificat d’autorisation local, que vous importez dans votre organisation Skype Entreprise Online à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="a4235-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="a4235-131">Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="a4235-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

```powershell
$thumbprint = (Get-AuthConfig).CurrentCertificateThumbprint
if((test-path $env:SYSTEMDRIVE\OAuthConfig) -eq $false)
{
md $env:SYSTEMDRIVE\OAuthConfig
}
cd $env:SYSTEMDRIVE\OAuthConfig
$oAuthCert = (dir Cert:\LocalMachine\My) | where {$_.Thumbprint -match $thumbprint}
$certType = [System.Security.Cryptography.X509Certificates.X509ContentType]::Cert
$certBytes = $oAuthCert.Export($certType)
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
[System.IO.File]::WriteAllBytes($CertFile, $certBytes)
```

<span data-ttu-id="a4235-132">Dans Exchange PowerShell dans votre organisation Exchange sur site, exécutez le script PowerShell que vous vient de créer.</span><span class="sxs-lookup"><span data-stu-id="a4235-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="a4235-133">Par exemple : .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="a4235-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="a4235-134">Étape 5 : Télécharger le certificat d’autorisation local vers Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="a4235-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="a4235-135">Ensuite, utilisez Windows PowerShell pour télécharger le certificat d’autorisation local que vous avez exporté à l’étape précédente vers Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="a4235-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="a4235-136">Pour ce faire, le module Azure Active Directory pour Windows PowerShell cmdlets doivent déjà être installés.</span><span class="sxs-lookup"><span data-stu-id="a4235-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="a4235-137">Si elle n'est pas installée, accédez à [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) pour installer la cmdlet Module Azure Active Directory pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a4235-137">If it's not installed, go to [https://aka.ms/aadposh](/previous-versions/azure/jj151815(v=azure.100)) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="a4235-138">Effectuez les étapes suivantes une fois que la cmdlet Module Azure Active Directory pour Windows PowerShell est installée.</span><span class="sxs-lookup"><span data-stu-id="a4235-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="a4235-p107">Cliquez sur le raccourci **Module Windows Azure Active Directory pour Windows PowerShell** afin d'ouvrir un espace de travail Windows PowerShell pour lequel les cmdlets Azure AD sont installées. Dans cette étape, toutes les commandes seront exécutées à l'aide de la console Windows PowerShell pour Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a4235-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="a4235-141">Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple,  `UploadAuthCert.ps1` .</span><span class="sxs-lookup"><span data-stu-id="a4235-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ```powershell
   Connect-MsolService;
   Import-Module msonlineextended;
   $CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer"
   $objFSO = New-Object -ComObject Scripting.FileSystemObject;
   $CertFile = $objFSO.GetAbsolutePathName($CertFile);
   $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
   $cer.Import($CertFile);
   $binCert = $cer.GetRawCertData();
   $credValue = [System.Convert]::ToBase64String($binCert);
   $ServiceName = "00000004-0000-0ff1-ce00-000000000000";
   $p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName
   New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue
   ```

3. <span data-ttu-id="a4235-142">Exécutez le script PowerShell que vous avez créé à l'étape précédente.</span><span class="sxs-lookup"><span data-stu-id="a4235-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="a4235-143">Par exemple :  `.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="a4235-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="a4235-144">Une fois le script lancé, une boîte de dialogue d'informations d'identification s'affiche.</span><span class="sxs-lookup"><span data-stu-id="a4235-144">After you start the script, a credentials dialog box is displayed.</span></span> <span data-ttu-id="a4235-145">Entrez les informations d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a4235-145">Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization.</span></span> <span data-ttu-id="a4235-146">Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte.</span><span class="sxs-lookup"><span data-stu-id="a4235-146">After running the script, leave the Windows PowerShell for Azure AD session open.</span></span> <span data-ttu-id="a4235-147">Vous l'utiliserez pour exécuter un script PowerShell à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="a4235-147">You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="a4235-148">Étape 6 : Vérifier que le certificat a été téléchargé vers le principal de service Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="a4235-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="a4235-149">Dans PowerShell ouvert et authentifié sur Azure Active Directory, exécutez la méthode suivante :</span><span class="sxs-lookup"><span data-stu-id="a4235-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```powershell
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="a4235-150">Appuyez sur Entrée lorsque vous y invitez ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="a4235-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="a4235-151">Confirmez que vous voyez une clé avec des données de date de début et de fin qui correspond à vos dates de début et de fin de certificat Oauth Exchange</span><span class="sxs-lookup"><span data-stu-id="a4235-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="a4235-152">Vérifier votre réussite</span><span class="sxs-lookup"><span data-stu-id="a4235-152">Verify your success</span></span>

<span data-ttu-id="a4235-153">Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="a4235-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="a4235-154">Confirmez que les utilisateurs De Skype Entreprise avec le service de messagerie vocale cloud, dans une organisation avec une configuration Exchange Server hybride, peuvent modifier correctement leurs messages d’accueil de messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="a4235-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="a4235-155">Confirmez que l’historique des conversations pour les clients mobiles est visible dans le dossier Historique des conversations Outlook.</span><span class="sxs-lookup"><span data-stu-id="a4235-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="a4235-156">Confirmez que les messages de conversation archivés sont déposés dans la boîte aux lettres sur site de l’utilisateur dans le dossier Purges à l’aide [d’EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).</span><span class="sxs-lookup"><span data-stu-id="a4235-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](/archive/blogs/webdav_101/where-to-get-ewseditor).</span></span>

<span data-ttu-id="a4235-157">Vous pourz également examiner votre trafic.</span><span class="sxs-lookup"><span data-stu-id="a4235-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="a4235-158">Le trafic dans une poignée de main OAuth est vraiment distinct (et ne ressemble pas à l’authentification de base), en particulier autour des domaines, où vous allez commencer à voir le trafic de l’émetteur qui ressemble à ceci : 00000004-0000-0ff1-ce00-000000000000@ (parfois avec un / avant le signe @), dans les jetons transmis.</span><span class="sxs-lookup"><span data-stu-id="a4235-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="a4235-159">Vous ne verrez pas de nom d’utilisateur ou de mot de passe, qui est le point d’OAuth.</span><span class="sxs-lookup"><span data-stu-id="a4235-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="a4235-160">Mais vous verrez l’émetteur « Office » (dans ce cas, « 4 » est Skype Entreprise) et le domaine de votre abonnement.</span><span class="sxs-lookup"><span data-stu-id="a4235-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="a4235-161">Si vous voulez être sûr d’utiliser OAuth avec succès, assurez-vous que vous savez à quoi vous attendre et à quoi le trafic doit ressembler.</span><span class="sxs-lookup"><span data-stu-id="a4235-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="a4235-162">Voici donc ce à quoi vous devez vous attendre, voici un exemple assez standard de trafic [OAuth](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) dans une application Microsoft (vraiment utile pour lire, bien [qu’il](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)n’utilise pas de jetons d’actualisation), et il existe des extensions Fiddler qui vous permet d’examiner votre JWT OAuth (jeton web JSON).</span><span class="sxs-lookup"><span data-stu-id="a4235-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="a4235-163">Voici un exemple de [configuration](/archive/blogs/kaevans/updated-fiddler-oauth-inspector)d’un outil de suivi réseau, mais vous pouvez utiliser n’importe quel outil de suivi réseau pour effectuer ce processus.</span><span class="sxs-lookup"><span data-stu-id="a4235-163">Here's an [example of setting one up](/archive/blogs/kaevans/updated-fiddler-oauth-inspector), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a4235-164">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a4235-164">Related topics</span></span>

[<span data-ttu-id="a4235-165">Configurer l’authentification OAuth entre des organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a4235-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)