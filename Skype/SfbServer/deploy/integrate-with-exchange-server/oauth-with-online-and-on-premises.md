---
title: Intégration de Skype entreprise Online et du serveur Exchange
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: La configuration de l’authentification OAuth entre Exchange sur site et Skype entreprise Online permet d’activer les fonctionnalités d’intégration de Skype entreprise et Exchange décrites dans la rubrique prise en charge des fonctionnalités.
ms.openlocfilehash: 1d64f8fe7b2d6dcf276ae34e74c84faf5c93f65a
ms.sourcegitcommit: 2b4fcf2561134b9f1b9a1b49401d97da1286e89d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/05/2019
ms.locfileid: "37979777"
---
# <a name="configure-integration-and-oauth-between-skype-for-business-online-and-exchange-server"></a><span data-ttu-id="8bc74-103">Configurer l’intégration et le protocole OAuth entre Skype entreprise Online et Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8bc74-103">Configure Integration and OAuth between Skype for Business Online and Exchange Server</span></span> 

<span data-ttu-id="8bc74-104">La configuration de l’intégration d’Exchange Server et de Skype entreprise Online permet d’activer les fonctionnalités d’intégration Skype entreprise et Exchange décrites dans la rubrique [prise en charge](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)des fonctionnalités.</span><span class="sxs-lookup"><span data-stu-id="8bc74-104">Configuring integration between Exchange server and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>

<span data-ttu-id="8bc74-105">Cette rubrique s’applique à l’intégration à Exchange Server 2013 à 2019.</span><span class="sxs-lookup"><span data-stu-id="8bc74-105">This topic applies to integration with Exchange Server 2013 through 2019.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="8bc74-106">Que devez-vous savoir avant de commencer ?</span><span class="sxs-lookup"><span data-stu-id="8bc74-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="8bc74-107">Temps estimé pour réaliser cette tâche : 15 minutes</span><span class="sxs-lookup"><span data-stu-id="8bc74-107">Estimated time to complete this task: 15 minutes</span></span>

-  <span data-ttu-id="8bc74-108">Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées.</span><span class="sxs-lookup"><span data-stu-id="8bc74-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="8bc74-109">Pour connaître les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et noyau](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="8bc74-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>

- <span data-ttu-id="8bc74-110">Pour plus d’informations sur les raccourcis clavier susceptibles d’être appliqués aux procédures décrites dans cette rubrique, voir [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="8bc74-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>

- <span data-ttu-id="8bc74-111">Pour plus d’informations sur la compatibilité, reportez-vous à la rubrique [compatibilité de Skype entreprise avec les applications Office](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span><span class="sxs-lookup"><span data-stu-id="8bc74-111">For information about compatibility, see [Skype for Business compatibility with Office apps](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/compatibility-with-office).</span></span>

## <a name="configure-integration-between-exchange-server-and-o365"></a><span data-ttu-id="8bc74-112">Configurer l’intégration entre Exchange Server et O365</span><span class="sxs-lookup"><span data-stu-id="8bc74-112">Configure integration between Exchange Server and O365</span></span>

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a><span data-ttu-id="8bc74-113">Étape 1 : configuration de l’authentification OAuth entre Exchange Server et O365</span><span class="sxs-lookup"><span data-stu-id="8bc74-113">Step 1: Configure OAuth authentication between Exchange Server and O365</span></span>

<span data-ttu-id="8bc74-114">Suivez les étapes décrites dans l’article suivant :</span><span class="sxs-lookup"><span data-stu-id="8bc74-114">Perform the steps in the following article:</span></span>

[<span data-ttu-id="8bc74-115">Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8bc74-115">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="8bc74-116">Étape 2 : créer un compte d’utilisateur de messagerie pour l’application partenaire de Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8bc74-116">Step 2: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="8bc74-117">Cette étape est exécutée sur le serveur Exchange.</span><span class="sxs-lookup"><span data-stu-id="8bc74-117">This step is done on the Exchange server.</span></span> <span data-ttu-id="8bc74-118">Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés.</span><span class="sxs-lookup"><span data-stu-id="8bc74-118">It will create a mail user and assign it the appropriate management role rights.</span></span> <span data-ttu-id="8bc74-119">Ce compte sera alors utilisé lors de l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="8bc74-119">This account will then be used in the next step.</span></span>

<span data-ttu-id="8bc74-120">Spécifiez un domaine vérifié pour votre organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="8bc74-120">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="8bc74-121">Ce domaine doit être identique à celui utilisé pour le domaine SMTP principal utilisé pour les comptes Exchange locaux.</span><span class="sxs-lookup"><span data-stu-id="8bc74-121">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="8bc74-122">Ce domaine est connu sous \<le nom de\> domaine vérifié dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="8bc74-122">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="8bc74-123">Par ailleurs, \<le\> DomainControllerFQDN doit être le nom de domaine complet d’un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="8bc74-123">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span>

``` Powershell
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="8bc74-124">Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.</span><span class="sxs-lookup"><span data-stu-id="8bc74-124">This command will hide the new mail user from address lists.</span></span>

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

<span data-ttu-id="8bc74-125">Les deux commandes qui suivent permettront d’attribuer les rôles de gestion ArchiveApplication et UserApplication à ce nouveau compte.</span><span class="sxs-lookup"><span data-stu-id="8bc74-125">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="8bc74-126">Étape 3 : créer et activer une application partenaire pour Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="8bc74-126">Step 3: Create and enable a Partner Application for Skype for Business Online</span></span> 

<span data-ttu-id="8bc74-127">Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="8bc74-127">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="8bc74-128">Exécutez la commande suivante dans Exchange PowerShell dans votre organisation Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="8bc74-128">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-4-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="8bc74-129">Étape 4 : exporter le certificat d’autorisation local</span><span class="sxs-lookup"><span data-stu-id="8bc74-129">Step 4: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="8bc74-130">Exécutez un script PowerShell pour exporter le certificat d’autorisation local que vous allez importer vers votre organisation Skype entreprise Online à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="8bc74-130">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>

<span data-ttu-id="8bc74-131">Enregistrez le texte suivant dans un fichier de script PowerShell appelé, par exemple, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="8bc74-131">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>

``` Powershell
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

<span data-ttu-id="8bc74-132">Dans Exchange PowerShell dans votre organisation Exchange locale, exécutez le script PowerShell que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="8bc74-132">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="8bc74-133">Par exemple : .\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="8bc74-133">For example: .\ExportAuthCert.ps1</span></span>

### <a name="step-5-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="8bc74-134">Étape 5 : Télécharger le certificat d’autorisation local auprès d’Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="8bc74-134">Step 5: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="8bc74-135">Utilisez ensuite Windows PowerShell pour télécharger le certificat d’autorisation locale que vous avez exporté au cours de l’étape précédente pour Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="8bc74-135">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="8bc74-136">Pour ce faire, le module Azure Active Directory pour applets de commande Windows PowerShell doit déjà être installé.</span><span class="sxs-lookup"><span data-stu-id="8bc74-136">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="8bc74-137">Si ce n’est pas le cas, [https://aka.ms/aadposh](https://aka.ms/aadposh) accédez à l’installation du module Azure Active Directory pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bc74-137">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="8bc74-138">Complétez les étapes suivantes après avoir installé le module Azure Active Directory pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8bc74-138">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>

1. <span data-ttu-id="8bc74-p107">Cliquez sur le raccourci du **module Azure Active Directory pour Windows PowerShell** pour ouvrir un espace de travail Windows PowerShell qui contient les applets Azure AD installées. Dans cette étape, toutes les commandes seront exécutées au moyen de la console Windows PowerShell pour Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8bc74-p107">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>

2. <span data-ttu-id="8bc74-141">Enregistrez le texte suivant dans un fichier de script PowerShell nommé, par exemple `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="8bc74-141">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>

   ``` Powershell
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

3. <span data-ttu-id="8bc74-142">Exécutez le script PowerShell que vous avez créé lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="8bc74-142">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="8bc74-143">Par exemple :`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="8bc74-143">For example:  `.\UploadAuthCert.ps1`</span></span>

4. <span data-ttu-id="8bc74-p109">Une fois que vous avez lancé le script, une boîte de dialogue d’informations d’identification s’affiche. Entrez les données d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD. Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte. Vous l’utiliserez pour exécuter un script PowerShell à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="8bc74-p109">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>

### <a name="step-6-verify-that-the-certificate-has-uploaded-to-the-skype-for-business-service-principal"></a><span data-ttu-id="8bc74-148">Étape 6 : vérifier que le certificat a été téléchargé pour le principal du service Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="8bc74-148">Step 6: Verify that the Certificate has Uploaded to the Skype for Business Service Principal</span></span>
1. <span data-ttu-id="8bc74-149">Dans PowerShell ouvert et authentifié dans Azure Active Directory, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="8bc74-149">In the PowerShell opened and authenticated to Azure Active Directory, run the following</span></span>
```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```
2. <span data-ttu-id="8bc74-150">Appuyez sur entrée lorsque vous êtes invité à ReturnKeyValues</span><span class="sxs-lookup"><span data-stu-id="8bc74-150">Press Enter when prompted for ReturnKeyValues</span></span>
3. <span data-ttu-id="8bc74-151">Confirmez que vous voyez une clé qui correspond à la date de début et aux données de fin correspondant aux dates de début et de fin de votre certificat OAuth Exchange.</span><span class="sxs-lookup"><span data-stu-id="8bc74-151">Confirm you see a key listed with start date and end data that matches your Exchange Oauth certificate start and end dates</span></span>

### <a name="verify-your-success"></a><span data-ttu-id="8bc74-152">Vérifiez que tout fonctionne correctement</span><span class="sxs-lookup"><span data-stu-id="8bc74-152">Verify your success</span></span>

<span data-ttu-id="8bc74-153">Vérifiez que la configuration est correcte en vérifiant que certaines fonctionnalités fonctionnent correctement.</span><span class="sxs-lookup"><span data-stu-id="8bc74-153">Verify that the configuration is correct by verifying some of the features are working successfully.</span></span> 

1. <span data-ttu-id="8bc74-154">Assurez-vous que les utilisateurs de Skype entreprise avec le service de messagerie vocale Cloud, au sein d’une organisation qui dispose d’une configuration Exchange Server hybride, peuvent modifier les messages d’accueil de la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="8bc74-154">Confirm that Skype for Business users with Cloud Voicemail service, in an organization with a Hybrid Exchange Server configuration, can successfully change their voicemail greetings.</span></span>

2. <span data-ttu-id="8bc74-155">L’historique des conversations pour les clients mobiles est visible dans le dossier historique des conversations Outlook.</span><span class="sxs-lookup"><span data-stu-id="8bc74-155">Confirm conversation history for mobile clients is visible in the Outlook Conversation History folder.</span></span>

3. <span data-ttu-id="8bc74-156">Vérifiez que les messages archivés sont déposés dans la boîte aux lettres locale de l’utilisateur dans le dossier purges à l’aide de [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span><span class="sxs-lookup"><span data-stu-id="8bc74-156">Confirm that archived chat messages are deposited in the user's on-premises mailbox in the Purges folder using [EWSEditor](https://blogs.msdn.microsoft.com/webdav_101/2018/03/12/where-to-get-ewseditor/).</span></span>

<span data-ttu-id="8bc74-157">Vous pouvez également examiner votre trafic.</span><span class="sxs-lookup"><span data-stu-id="8bc74-157">Alternately, look at your traffic.</span></span> <span data-ttu-id="8bc74-158">Le trafic d’une connexion OAuth est réellement distinctif (et ne ressemble pas à l’authentification de base), en particulier par rapport aux domaines, où vous allez commencer à voir le trafic de l’émetteur qui ressemble à ce qui suit : 00000004-0000-0ff1-CE00-000000000000 @ (parfois avec un/avant). le signe @), dans les jetons transmis.</span><span class="sxs-lookup"><span data-stu-id="8bc74-158">The traffic in an OAuth handshake is really distinctive (and doesn't look like Basic authentication), particularly around realms, where you’ll begin to see issuer traffic that looks like this: 00000004-0000-0ff1-ce00-000000000000@ (sometimes with a / before the @ sign), in the tokens that are being passed.</span></span> <span data-ttu-id="8bc74-159">Aucun nom d’utilisateur ou mot de passe ne s’affiche, qui est le point de OAuth.</span><span class="sxs-lookup"><span data-stu-id="8bc74-159">You won’t see a username or password, which is the point of OAuth.</span></span> <span data-ttu-id="8bc74-160">Néanmoins, vous verrez l’émetteur’Office', dans le cas où « 4 » est Skype entreprise, ainsi que le domaine de votre abonnement.</span><span class="sxs-lookup"><span data-stu-id="8bc74-160">But you will see   the ‘Office’ issuer – in this case ‘4’ is Skype for Business – and the realm of your subscription.</span></span>

<span data-ttu-id="8bc74-161">Si vous voulez vous assurer que vous utilisez correctement OAuth, assurez-vous que vous savez à quoi il doit s’attendre et que vous savez à quoi ressemble le trafic.</span><span class="sxs-lookup"><span data-stu-id="8bc74-161">If you want to be sure you’re successfully using OAuth, make certain you know what to expect and know what the traffic should look like.</span></span> <span data-ttu-id="8bc74-162">Voici [ce à quoi vous pouvez vous attendre, vous](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34)trouverez ci-dessous un [exemple standard de trafic OAuth dans une application Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (il est réellement utile de lire, même si elle n’utilise pas de jeton d’actualisation), et il existe des extensions Fiddler qui vous permettront d’accéder à votre JWT OAuth (JSON). Jeton Web).</span><span class="sxs-lookup"><span data-stu-id="8bc74-162">So [here’s what to expect](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), here’s a pretty standard [example of OAuth traffic in a Microsoft application](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf)  (really helpful to read, though it doesn't use Refresh tokens), and there are Fiddler extensions that will let you look into your OAuth JWT (JSON Web Token).</span></span>

<span data-ttu-id="8bc74-163">Voici un [exemple de configuration d’une valeur unique](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mais vous pouvez utiliser n’importe quel outil de suivi réseau qui vous plaît pour engager ce processus.</span><span class="sxs-lookup"><span data-stu-id="8bc74-163">Here's an [example of setting one up](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), but you can use any network tracing tool you like to undertake this process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8bc74-164">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="8bc74-164">Related topics</span></span>

[<span data-ttu-id="8bc74-165">Configurer l’authentification OAuth entre les organisations Exchange et Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8bc74-165">Configure OAuth authentication between Exchange and Exchange Online organizations</span></span>](https://docs.microsoft.com/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
