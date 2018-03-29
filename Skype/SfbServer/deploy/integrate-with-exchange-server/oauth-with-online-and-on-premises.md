---
title: Configurer OAuth entre Skype pour Business Online et Exchange sur site
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configuration OAuth authentification entre Exchange sur site et Skype pour Business Online permet le Skype pour les fonctionnalités d’entreprise et d’intégration d’Exchange décrites dans prise en charge de la fonctionnalité.
ms.openlocfilehash: adb811a8934fdc6ea574dc934efa57ee28e6fba6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-oauth-between-skype-for-business-online-and-exchange-on-premises"></a><span data-ttu-id="b20ac-103">Configurer OAuth entre Skype pour Business Online et Exchange sur site</span><span class="sxs-lookup"><span data-stu-id="b20ac-103">Configure OAuth between Skype for Business Online and Exchange on premises</span></span>
 
<span data-ttu-id="b20ac-104">Configuration OAuth authentification entre Exchange sur site et Skype pour Business Online permet le Skype pour les fonctions commerciales et d’intégration d’Exchange décrites dans [prise en charge de la fonctionnalité](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="b20ac-104">Configuring OAuth authentication between Exchange on premises and Skype for Business Online enables the Skype for Business and Exchange Integration features described in [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span>
  
<span data-ttu-id="b20ac-105">Cette rubrique s’applique aux 2016 d’Exchange Server et Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b20ac-105">This topic applies to Exchange Server 2016 and Exchange Server 2013.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b20ac-106">Que devez-vous savoir avant de commencer ?</span><span class="sxs-lookup"><span data-stu-id="b20ac-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b20ac-107">Temps estimé pour réaliser cette tâche : 15 minutes</span><span class="sxs-lookup"><span data-stu-id="b20ac-107">Estimated time to complete this task: 15 minutes</span></span>
    
-  <span data-ttu-id="b20ac-108">Avant de pouvoir réaliser cette (ces) procédure(s), des autorisations doivent vous avoir été attribuées.</span><span class="sxs-lookup"><span data-stu-id="b20ac-108">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="b20ac-109">Pour voir quelles sont les autorisations dont vous avez besoin, consultez la rubrique [autorisations d’infrastructure Exchange et du Shell](https://go.microsoft.com/fwlink/p/?LinkId=746511) .</span><span class="sxs-lookup"><span data-stu-id="b20ac-109">To see what permissions you need, see the [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) topic.</span></span>
    
- <span data-ttu-id="b20ac-110">Pour plus d’informations sur les raccourcis clavier qui peuvent s’appliquer aux procédures de cette rubrique, consultez [raccourcis clavier dans le centre d’administration Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span><span class="sxs-lookup"><span data-stu-id="b20ac-110">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts in the Exchange admin center]( https://go.microsoft.com/fwlink/p/?LinkId=746512).</span></span>
    
## <a name="configure-oauth-authentication-between-your-on-premises-exchange-and-skype-for-business-organizations"></a><span data-ttu-id="b20ac-111">Configurer l’authentification OAuth entre vos organisations Exchange et Skype Entreprise locales.</span><span class="sxs-lookup"><span data-stu-id="b20ac-111">Configure OAuth authentication between your on-premises Exchange and Skype for Business organizations</span></span>

### <a name="step-1-create-an-authorization-server-object-for-your-skype-for-business-online-organization"></a><span data-ttu-id="b20ac-112">Étape 1 : Créer un objet d’autorisation du serveur pour votre Skype pour une organisation commerciale en ligne</span><span class="sxs-lookup"><span data-stu-id="b20ac-112">Step 1: Create an authorization server object for your Skype for Business Online organization</span></span>

<span data-ttu-id="b20ac-113">Spécifiez un domaine vérifié pour votre Skype pour une organisation commerciale en ligne.</span><span class="sxs-lookup"><span data-stu-id="b20ac-113">Specify a verified domain for your Skype for Business Online organization.</span></span> <span data-ttu-id="b20ac-114">Ce domaine doit être le même domaine que celui utilisé comme domaine SIP principal pour les comptes sur le cloud.</span><span class="sxs-lookup"><span data-stu-id="b20ac-114">This domain should be the same domain used as the primary SIP domain used for the cloud-based accounts.</span></span> <span data-ttu-id="b20ac-115">Ce domaine est désigné en tant que \<votre domaine vérifié\> dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="b20ac-115">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>
  
<span data-ttu-id="b20ac-116">Exécutez la commande suivante dans Exchange Management Shell (Exchange PowerShell) dans vos locaux sur organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="b20ac-116">Run the following command in the Exchange Management Shell (the Exchange PowerShell) in your on-premises Exchange organization.</span></span>
  
```
New-AuthServer -Name "WindowsAzureACS" -AuthMetadataUrl "https://accounts.accesscontrol.windows.net/<your Verified Domain>/metadata/json/1" 
```

### <a name="step-2-enable-the-partner-application-for-your-skype-for-business-online-organization"></a><span data-ttu-id="b20ac-117">Étape 2 : Activer l’application partenaire pour votre Skype pour une organisation commerciale en ligne</span><span class="sxs-lookup"><span data-stu-id="b20ac-117">Step 2: Enable the partner application for your Skype for Business Online organization</span></span>

<span data-ttu-id="b20ac-118">Exécutez la commande suivante dans Exchange PowerShell dans vos locaux sur organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="b20ac-118">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span>
  
```
Get-PartnerApplication | ?{$_.ApplicationIdentifier -eq "00000002-0000-0ff1-ce00-000000000000" -and $_.Realm -eq ""} | Set-PartnerApplication -Enabled $true
```

### <a name="step-3-create-a-new-mail-user-account-for-the-skype-for-business-online-partner-application"></a><span data-ttu-id="b20ac-119">Étape 3 : Créer un nouveau compte d’utilisateur de messagerie pour le Skype pour Application de partenaire commerciale en ligne</span><span class="sxs-lookup"><span data-stu-id="b20ac-119">Step 3: Create a new Mail User account for the Skype for Business Online Partner Application</span></span>

<span data-ttu-id="b20ac-p103">Cette étape est effectuée en local. Elle crée un utilisateur de messagerie et lui attribue les droits de rôle de gestion adaptés. Ce compte sera alors utilisé lors de l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="b20ac-p103">This step is done on-premises. It will create a mail user and assign it the appropriate management role rights. This account will then be used in the next step.</span></span>
  
<span data-ttu-id="b20ac-123">Spécifiez un domaine vérifié pour votre organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="b20ac-123">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="b20ac-124">Ce domaine doit être le même domaine que celui utilisé comme le domaine SMTP principal utilisé pour les comptes Exchange sur site.</span><span class="sxs-lookup"><span data-stu-id="b20ac-124">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="b20ac-125">Ce domaine est désigné en tant que \<votre domaine vérifié\> dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="b20ac-125">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span> <span data-ttu-id="b20ac-126">En outre, les \<DomainControllerFQDN\> doit être le nom de domaine complet d’un contrôleur de domaine.</span><span class="sxs-lookup"><span data-stu-id="b20ac-126">Also, the \<DomainControllerFQDN\> should be the FQDN of a domain controller.</span></span> 
  
```
$user = New-MailUser -Name SfBOnline-ApplicationAccount -ExternalEmailAddress SfBOnline-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN> 
```

<span data-ttu-id="b20ac-127">Cette commande masquera le nouvel utilisateur de messagerie dans les listes d’adresses.</span><span class="sxs-lookup"><span data-stu-id="b20ac-127">This command will hide the new mail user from address lists.</span></span>
  
```
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN> 
```

<span data-ttu-id="b20ac-128">Les deux commandes qui suivent permettront d’attribuer les rôles de gestion ArchiveApplication et UserApplication à ce nouveau compte.</span><span class="sxs-lookup"><span data-stu-id="b20ac-128">These next two commands will assign the UserApplication and ArchiveApplication management role to this new account.</span></span>
  
```
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN> 

```

```
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN> 
```

### <a name="step-4-create-and-enable-a-partner-application-for-skype-for-business-online"></a><span data-ttu-id="b20ac-129">Étape 4 : Créer et permettent à une Application du partenaire pour Skype pour professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="b20ac-129">Step 4: Create and enable a Partner Application for Skype for Business Online</span></span>

<span data-ttu-id="b20ac-130">Créez une nouvelle application partenaire et utilisez le compte que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="b20ac-130">Create a new partner application and will use the account you just created.</span></span> <span data-ttu-id="b20ac-131">Exécutez la commande suivante dans Exchange PowerShell dans vos locaux sur organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="b20ac-131">Run the following command in the Exchange PowerShell in your on-premises Exchange organization.</span></span> 
  
```
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="step-5-export-the-on-premises-authorization-certificate"></a><span data-ttu-id="b20ac-132">Étape 5 : exportez le certificat d’autorisation locale</span><span class="sxs-lookup"><span data-stu-id="b20ac-132">Step 5: Export the on-premises authorization certificate</span></span>

<span data-ttu-id="b20ac-133">Exécuter un script PowerShell pour exporter le certificat d’autorisation en local, vous l’importez dans votre Skype pour une organisation commerciale en ligne à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="b20ac-133">Run a PowerShell script to export the on-premises authorization certificate, which you will import to your Skype for Business Online organization in the next step.</span></span>
  
<span data-ttu-id="b20ac-134">Enregistrez le texte suivant dans un fichier de script PowerShell appelé, par exemple, ExportAuthCert.ps1.</span><span class="sxs-lookup"><span data-stu-id="b20ac-134">Save the following text to a PowerShell script file named, for example, ExportAuthCert.ps1.</span></span>
  
```
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

<span data-ttu-id="b20ac-135">Dans Exchange PowerShell dans votre organisation Exchange sur site, exécutez le script PowerShell que vous venez de créer.</span><span class="sxs-lookup"><span data-stu-id="b20ac-135">In Exchange PowerShell in your on-premises Exchange organization, run the PowerShell script that you just created.</span></span> <span data-ttu-id="b20ac-136">Par exemple :.\ExportAuthCert.ps1</span><span class="sxs-lookup"><span data-stu-id="b20ac-136">For example: .\ExportAuthCert.ps1</span></span>
  
### <a name="step-6-upload-the-on-premises-authorization-certificate-to-azure-active-directory-acs"></a><span data-ttu-id="b20ac-137">Étape 6 : chargez le certificat d’autorisation locale dans Azure Active Directory ACS</span><span class="sxs-lookup"><span data-stu-id="b20ac-137">Step 6: Upload the on-premises authorization certificate to Azure Active Directory ACS</span></span>

<span data-ttu-id="b20ac-138">Utilisez ensuite Windows PowerShell pour télécharger le certificat d’autorisation locale que vous avez exporté au cours de l’étape précédente pour Azure Active Directory Access Control Services (ACS).</span><span class="sxs-lookup"><span data-stu-id="b20ac-138">Next, use Windows PowerShell to upload the on-premises authorization certificate that you exported in the previous step to Azure Active Directory Access Control Services (ACS).</span></span> <span data-ttu-id="b20ac-139">Pour ce faire, le module Azure Active Directory pour applets de commande Windows PowerShell doit déjà être installé.</span><span class="sxs-lookup"><span data-stu-id="b20ac-139">To do this, the Azure Active Directory Module for Windows PowerShell cmdlets must already be installed.</span></span> <span data-ttu-id="b20ac-140">S’il n’est pas installé, accédez à [https://aka.ms/aadposh](https://aka.ms/aadposh) pour installer le Module Azure pour annuaire Active pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b20ac-140">If it's not installed, go to [https://aka.ms/aadposh](https://aka.ms/aadposh) to install the Azure Active Directory Module for Windows PowerShell.</span></span> <span data-ttu-id="b20ac-141">Complétez les étapes suivantes après avoir installé le module Azure Active Directory pour Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b20ac-141">Complete the following steps after the Azure Active Directory Module for Windows PowerShell is installed.</span></span>
  
1. <span data-ttu-id="b20ac-p108">Cliquez sur le raccourci du **module Azure Active Directory pour Windows PowerShell** pour ouvrir un espace de travail Windows PowerShell qui contient les applets Azure AD installées. Dans cette étape, toutes les commandes seront exécutées au moyen de la console Windows PowerShell pour Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b20ac-p108">Click the **Azure Active Directory Module for Windows PowerShell** shortcut to open a Windows PowerShell workspace that has the Azure AD cmdlets installed. All commands in this step will be run using the Windows PowerShell for Azure Active Directory console.</span></span>
    
2. <span data-ttu-id="b20ac-144">Enregistrer le texte suivant dans un fichier de script PowerShell nommé, par exemple, `UploadAuthCert.ps1`.</span><span class="sxs-lookup"><span data-stu-id="b20ac-144">Save the following text to a PowerShell script file named, for example,  `UploadAuthCert.ps1`.</span></span>
    
  ```
  Connect-MsolService; 
Import-Module msonlineextended; 
$CertFile = "$env:SYSTEMDRIVE\OAuthConfig\OAuthCert.cer" 
$objFSO = New-Object -ComObject Scripting.FileSystemObject; 
$CertFile = $objFSO.GetAbsolutePathName($CertFile); 
$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate 
$cer.Import($CertFile); 
$binCert = $cer.GetRawCertData(); 
$credValue = [System.Convert]::ToBase64String($binCert); 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName 
New-MsolServicePrincipalCredential -AppPrincipalId $p.AppPrincipalId -Type asymmetric -Usage Verify -Value $credValue 
  ```

3. <span data-ttu-id="b20ac-145">Exécutez le script PowerShell que vous avez créé lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="b20ac-145">Run the PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="b20ac-146">Par exemple :`.\UploadAuthCert.ps1`</span><span class="sxs-lookup"><span data-stu-id="b20ac-146">For example:  `.\UploadAuthCert.ps1`</span></span>
    
4. <span data-ttu-id="b20ac-p110">Une fois que vous avez lancé le script, une boîte de dialogue d’informations d’identification s’affiche. Entrez les données d’identification du compte d’administrateur client de votre organisation Microsoft Online Azure AD. Après avoir exécuté le script, laissez la session Windows PowerShell pour Azure AD ouverte. Vous l’utiliserez pour exécuter un script PowerShell à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="b20ac-p110">After you start the script, a credentials dialog box is displayed. Enter the credentials for the tenant administrator account of your Microsoft Online Azure AD organization. After running the script, leave the Windows PowerShell for Azure AD session open. You will use this to run a PowerShell script in the next step.</span></span>
    
### <a name="step-7-register-the-hostname-authorities-for-the-smtp-domain"></a><span data-ttu-id="b20ac-151">Étape 7 : inscrivez les autorités de nom d’hôte pour le domaine SMTP</span><span class="sxs-lookup"><span data-stu-id="b20ac-151">Step 7: Register the hostname authorities for the SMTP domain</span></span>

<span data-ttu-id="b20ac-152">Spécifiez un domaine vérifié pour votre organisation Exchange.</span><span class="sxs-lookup"><span data-stu-id="b20ac-152">Specify a verified domain for your Exchange organization.</span></span> <span data-ttu-id="b20ac-153">Ce domaine doit être le même domaine que celui utilisé comme le domaine SMTP principal utilisé pour les comptes Exchange sur site.</span><span class="sxs-lookup"><span data-stu-id="b20ac-153">This domain should be the same domain used as the primary SMTP domain used for the on-premises Exchange accounts.</span></span> <span data-ttu-id="b20ac-154">Ce domaine est désigné en tant que \<votre domaine vérifié\> dans la procédure suivante.</span><span class="sxs-lookup"><span data-stu-id="b20ac-154">This domain is referred as \<your Verified Domain\> in the following procedure.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b20ac-155">Pour exécuter correctement le script suivant, Windows PowerShell pour Azure Active Directory doit être connecté à votre client Microsoft Online Azure AD, comme expliqué dans l’étape 4 de la section précédente.</span><span class="sxs-lookup"><span data-stu-id="b20ac-155">Successfully running the following script requires that the Windows PowerShell for Azure Active Directory is connected to your Microsoft Online Azure AD tenant, as explained in step 4 in the previous section.</span></span> 
  
1. <span data-ttu-id="b20ac-156">Enregistrez le texte suivant dans un fichier de script PowerShell appelé, par exemple, RegisterEndpoints.ps1.</span><span class="sxs-lookup"><span data-stu-id="b20ac-156">Save the following text to a PowerShell script file named, for example, RegisterEndpoints.ps1.</span></span> <span data-ttu-id="b20ac-157">Cet exemple utilise un caractère générique pour inscrire tous les points de terminaison pour contoso.com. Remplacer contoso.com avec une autorité de nom d’hôte de votre organisation d’Exchange en local</span><span class="sxs-lookup"><span data-stu-id="b20ac-157">This example uses a wildcard to register all endpoints for contoso.com. Replace contoso.com with a hostname authority for your on-premises Exchange organization</span></span>
    
  ```
  $externalAuthority="*.<your Verified Domain>" 
$ServiceName = "00000002-0000-0ff1-ce00-000000000000"; 
$p = Get-MsolServicePrincipal -ServicePrincipalName $ServiceName; 
$spn = [string]::Format("{0}/{1}", $ServiceName, $externalAuthority); 
$p.ServicePrincipalNames.Add($spn); 
Set-MsolServicePrincipal -ObjectID $p.ObjectId -ServicePrincipalNames $p.ServicePrincipalNames; 
  ```

2.  <span data-ttu-id="b20ac-158">Dans Windows PowerShell pour Azure Active Directory, exécutez le script Windows PowerShell que vous avez créé lors de l’étape précédente.</span><span class="sxs-lookup"><span data-stu-id="b20ac-158">In Windows PowerShell for Azure Active Directory, run the Windows PowerShell script that you created in the previous step.</span></span> <span data-ttu-id="b20ac-159">Par exemple : `.\RegisterEndpoints.ps1`</span><span class="sxs-lookup"><span data-stu-id="b20ac-159">For example: `.\RegisterEndpoints.ps1`</span></span>
    
### <a name="verify-your-success"></a><span data-ttu-id="b20ac-160">Vérifiez que tout fonctionne correctement</span><span class="sxs-lookup"><span data-stu-id="b20ac-160">Verify your success</span></span>

<span data-ttu-id="b20ac-161">Vérifiez que la configuration OAuth est correcte en vous assurant que certaines des fonctionnalités fonctionnent correctement (par exemple, l’historique des conversations pour les clients mobiles doit être visible dans l’historique des conversations d’Outlook).</span><span class="sxs-lookup"><span data-stu-id="b20ac-161">Verify that the OAuth configuration is correct by verifying some of the features are working successfully, such as having conversation history for mobile clients visible in the Outlook Conversation History folder.</span></span>
  
1. <span data-ttu-id="b20ac-162">Démarrer le Skype pour l’application mobile d’entreprise sur votre Windows Phone ou le périphérique d’e/s et connectez-vous en tant qu’un Skype pour l’utilisateur professionnel en ligne avec un 2016 d’Exchange ou d’une boîte aux lettres de Exchange 2013 sur site.</span><span class="sxs-lookup"><span data-stu-id="b20ac-162">Start the Skype for Business mobile app on your Windows Phone or iOS device and sign in as a Skype for Business Online user with an Exchange 2016 or Exchange 2013 on-premises mailbox.</span></span>
    
2. <span data-ttu-id="b20ac-163">Avoir une conversation par messagerie instantanée avec un autre Skype pour des utilisateurs professionnels en ligne.</span><span class="sxs-lookup"><span data-stu-id="b20ac-163">Have an instant messaging conversation with another Skype for Business Online user.</span></span>
    
3. <span data-ttu-id="b20ac-164">Fermez la fenêtre de conversation de la messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="b20ac-164">Close the IM conversation window.</span></span>
    
4. <span data-ttu-id="b20ac-165">Démarrez Outlook pour cet utilisateur et vérifiez que la conversation est visible dans l’historique des conversations d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="b20ac-165">Start Outlook for this user and verify that the conversation is visible in the Outlook Conversation history folder.</span></span>
    

