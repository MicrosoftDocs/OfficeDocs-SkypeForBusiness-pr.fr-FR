---
title: Déploiement de salles de Microsoft teams avec Exchange Online
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft teams avec Exchange Online et Skype entreprise Server en local.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662309"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="e2b37-103">Déploiement de salles de Microsoft teams avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e2b37-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="e2b37-104">Consultez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft teams avec Exchange Online et Skype entreprise Server en local.</span><span class="sxs-lookup"><span data-stu-id="e2b37-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="e2b37-105">Si votre organisation dispose d’une combinaison de services, avec une partie hébergée en local et une partie hébergée en ligne, votre configuration dépend de l’emplacement d’hébergement de chaque service.</span><span class="sxs-lookup"><span data-stu-id="e2b37-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="e2b37-106">Cette rubrique traite des déploiements hybrides pour les salles Microsoft teams avec Exchange hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="e2b37-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="e2b37-107">Dans la mesure où ce type de déploiement comporte autant de variations différentes, il n’est pas possible de fournir des instructions détaillées pour chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="e2b37-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="e2b37-108">Le processus suivant fonctionne pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="e2b37-108">The following process will work for many configurations.</span></span> <span data-ttu-id="e2b37-109">Si le processus ne vous convient pas, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final qu’indiqué ici, et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e2b37-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="e2b37-110">Le moyen le plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de Windows PowerShell distant.</span><span class="sxs-lookup"><span data-stu-id="e2b37-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="e2b37-111">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script permettant de créer de nouveaux comptes d’utilisateurs, ou de valider des comptes de ressources existants dont vous avez besoin afin de vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="e2b37-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="e2b37-112">Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.</span><span class="sxs-lookup"><span data-stu-id="e2b37-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="e2b37-113">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="e2b37-113">Requirements</span></span>

<span data-ttu-id="e2b37-114">Avant de déployer des salles Microsoft teams avec Exchange Online, assurez-vous que vous remplissez les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="e2b37-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="e2b37-115">Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2b37-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="e2b37-116">Pour déployer des salles Microsoft teams avec Exchange Online, suivez les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="e2b37-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="e2b37-117">Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="e2b37-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="e2b37-118">Le [module Azure Active Directory pour les applets de contrôle Windows PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) de cette section (par exemple, Set-MsolUser) a été testé dans la configuration de comptes pour les appareils Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2b37-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="e2b37-119">Il est possible que d’autres cmdlets puissent fonctionner, mais qui n’ont pas été testées dans ce scénario spécifique.</span><span class="sxs-lookup"><span data-stu-id="e2b37-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="e2b37-120">Si vous avez déployé les services AD FS (Active Directory Federation Services), il est possible que vous deviez convertir le compte d’utilisateur en utilisateur géré avant de suivre ces étapes, puis de reconvertir l’utilisateur en utilisateur fédéré une fois ces étapes terminées.</span><span class="sxs-lookup"><span data-stu-id="e2b37-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="e2b37-121">Création d’un compte et définition des propriétés Exchange</span><span class="sxs-lookup"><span data-stu-id="e2b37-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="e2b37-122">Démarrez une session Windows PowerShell distante sur un PC et connectez-vous à Exchange Online en procédant comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2b37-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="e2b37-123">Après avoir établi une session, vous pouvez créer une nouvelle boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou changer les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="e2b37-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="e2b37-124">Cela permettra au compte d’s’authentifier dans les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2b37-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="e2b37-125">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="e2b37-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="e2b37-126">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="e2b37-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="e2b37-127">Pour améliorer l’utilisation de la réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2b37-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="e2b37-128">Ajout d’une adresse e-mail pour votre compte de domaine sur site</span><span class="sxs-lookup"><span data-stu-id="e2b37-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="e2b37-129">Dans l’outil d' **annonce utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le conteneur ou l’unité d’organisation dans lequel vos comptes Microsoft teams seront créés, cliquez sur **nouveau**, puis sur **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="e2b37-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="e2b37-130">Entrez le nom d’affichage (-identité) à partir de l’applet de connexion précédente (Set-Mailbox ou New-Mailbox) dans la zone **nom complet** et l’alias dans la zone nom **d’utilisateur** de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e2b37-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="e2b37-131">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e2b37-131">Click **Next**.</span></span>
3. <span data-ttu-id="e2b37-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e2b37-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e2b37-135">Le fait de sélectionner un **mot de passe n’expire jamais** est requis pour Skype entreprise Server sur les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2b37-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="e2b37-136">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="e2b37-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="e2b37-137">Si tel est le cas, vous devez créer une exception pour chaque compte d’utilisateur de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2b37-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="e2b37-138">Cliquez sur **Terminer** pour créer le compte.</span><span class="sxs-lookup"><span data-stu-id="e2b37-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="e2b37-139">Une fois le compte créé, effectuez une synchronisation d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="e2b37-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="e2b37-140">Pour ce faire, vous pouvez utiliser [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2b37-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="e2b37-141">Lorsque vous avez terminé, accédez à la page utilisateurs et vérifiez que les deux comptes créés aux étapes précédentes ont été fusionnés.</span><span class="sxs-lookup"><span data-stu-id="e2b37-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="e2b37-142">Attribution d’une licence Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="e2b37-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="e2b37-143">Tout d’abord, connectez-vous à Azure AD pour appliquer des paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="e2b37-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="e2b37-144">Pour vous connecter, vous pouvez exécuter l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="e2b37-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="e2b37-145">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e2b37-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="e2b37-146">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e2b37-146">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="e2b37-147">Le compte d’utilisateur doit avoir une licence Microsoft 365 ou Office 365 valide pour garantir le bon fonctionnement d’Exchange et de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e2b37-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="e2b37-148">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="e2b37-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e2b37-149">Vous devez créer le devoir à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="e2b37-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="e2b37-150">Utilisez ensuite `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="e2b37-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="e2b37-151">pour récupérer la liste des références SKU disponibles pour votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e2b37-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="e2b37-152">Une fois que vous avez répertorié les références (SKU), vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="e2b37-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="e2b37-153">applet.</span><span class="sxs-lookup"><span data-stu-id="e2b37-153">cmdlet.</span></span> <span data-ttu-id="e2b37-154">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="e2b37-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-MsolAccountSku
     Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="e2b37-155">Activer le compte utilisateur avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="e2b37-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="e2b37-156">Créez une session Windows PowerShell distante à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="e2b37-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="e2b37-157">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="e2b37-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="e2b37-158">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="e2b37-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="e2b37-159">Pour activer votre compte Microsoft teams pour Skype entreprise Server, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e2b37-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="e2b37-160">Si vous n’êtes pas sûr de la valeur à utiliser pour le paramètre RegistrarPool de votre environnement, vous pouvez obtenir la valeur d’un utilisateur Skype entreprise Server existant à l’aide de la commande suivante</span><span class="sxs-lookup"><span data-stu-id="e2b37-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="e2b37-161">Affectation d’une licence Skype entreprise Server à votre compte Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e2b37-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="e2b37-162">Connectez-vous en tant qu’administrateur client, ouvrez le centre d’administration Microsoft 365, puis cliquez sur l’application Administration.</span><span class="sxs-lookup"><span data-stu-id="e2b37-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="e2b37-163">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="e2b37-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="e2b37-164">Cliquez sur le compte Microsoft Teams, puis cliquez sur l’icône représentant un crayon pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="e2b37-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="e2b37-165">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="e2b37-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="e2b37-166">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2b37-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="e2b37-167">Vous devez utiliser une licence de plan 3 Si vous souhaitez utiliser Enterprise Voice sur les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e2b37-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="e2b37-168">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e2b37-168">Click **Save**.</span></span>

<span data-ttu-id="e2b37-169">Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="e2b37-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="e2b37-170">Si vous utilisez actuellement E1, E3, E4 ou E5 avec Skype entreprise plan 2 avec audioconférence ou avec un système téléphonique et un plan d’appels, ces références continuent de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="e2b37-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="e2b37-171">Néanmoins, vous devez envisager de migrer vers un modèle de licence plus simple, comme décrit dans la rubrique mise à jour de la gestion des licences de la [salle de réunion teams](rooms-licensing.md), après l’expiration des licences actuelles.</span><span class="sxs-lookup"><span data-stu-id="e2b37-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2b37-172">Si vous utilisez le plan 2 de Skype entreprise, vous ne pouvez utiliser que le mode Skype entreprise uniquement en mode Skype entreprise, ce qui signifie que toutes vos réunions seront des réunions Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="e2b37-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="e2b37-173">Pour pouvoir activer la salle de réunion pour les réunions Microsoft Teams, nous vous recommandons d’acheter la licence de salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="e2b37-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e2b37-174">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="e2b37-174">Related topics</span></span>

[<span data-ttu-id="e2b37-175">Configurer des comptes pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="e2b37-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="e2b37-176">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2b37-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="e2b37-177">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2b37-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="e2b37-178">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2b37-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="e2b37-179">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2b37-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
