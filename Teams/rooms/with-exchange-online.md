---
title: Déployer des salles Microsoft Teams avec Exchange Online
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
description: Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Exchange Online et Skype Entreprise Server sur site.
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662309"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="94e13-103">Déployer des salles Microsoft Teams avec Exchange Online</span><span class="sxs-lookup"><span data-stu-id="94e13-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="94e13-104">Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams avec Exchange Online et Skype Entreprise Server sur site.</span><span class="sxs-lookup"><span data-stu-id="94e13-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="94e13-105">Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé.</span><span class="sxs-lookup"><span data-stu-id="94e13-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="94e13-106">Cette rubrique traite des déploiements hybrides de salles Microsoft Teams avec Exchange hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="94e13-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="94e13-107">Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="94e13-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="94e13-108">Le processus suivant fonctionne pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="94e13-108">The following process will work for many configurations.</span></span> <span data-ttu-id="94e13-109">Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="94e13-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="94e13-110">La manière la plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de la Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94e13-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="94e13-111">Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’utilisateurs de salles Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="94e13-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="94e13-112">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre appareil Microsoft Teams Rooms utilisera.</span><span class="sxs-lookup"><span data-stu-id="94e13-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="94e13-113">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="94e13-113">Requirements</span></span>

<span data-ttu-id="94e13-114">Avant de déployer des salles Microsoft Teams avec Exchange Online, assurez-vous que vous disposez de la version requise.</span><span class="sxs-lookup"><span data-stu-id="94e13-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="94e13-115">Pour plus d’informations, consultez [la conditions requises pour les salles Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="94e13-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="94e13-116">Pour déployer des salles Microsoft Teams avec Exchange Online, suivez les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="94e13-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="94e13-117">Assurez-vous de disposer des autorisations adéquates pour exécuter les applets de commande associées.</span><span class="sxs-lookup"><span data-stu-id="94e13-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="94e13-118">Le [module Azure Active Directory](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) pour les applets de commande Windows PowerShell dans cette section (par exemple, Set-MsolUser) a été testé dans le cadre de la configuration de comptes pour les appareils Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="94e13-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="94e13-119">Il est possible que d’autres cmdlets fonctionnent, toutefois, elles n’ont pas été testées dans ce scénario particulier.</span><span class="sxs-lookup"><span data-stu-id="94e13-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="94e13-120">Si vous avez déployé les services AD FS (Active Directory Federation Services), vous deront peut-être convertir le compte d’utilisateur en utilisateur géré avant de suivre ces étapes, puis convertir l’utilisateur en utilisateur fédéré une fois ces étapes terminées.</span><span class="sxs-lookup"><span data-stu-id="94e13-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="94e13-121">Création d’un compte et définition des propriétés Exchange</span><span class="sxs-lookup"><span data-stu-id="94e13-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="94e13-122">Démarrez une session Windows PowerShell session distante sur un PC et connectez-vous à Exchange Online comme suit :</span><span class="sxs-lookup"><span data-stu-id="94e13-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="94e13-123">Après avoir établi une session, vous allez créer une boîte aux lettres et l’activer en tant que compte RoomMailboxAccount, ou modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="94e13-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="94e13-124">Cela permet au compte de s’authentifier dans Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="94e13-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="94e13-125">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="94e13-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="94e13-126">Si vous créez une boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="94e13-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="94e13-127">Pour améliorer l’expérience de réunion, vous devez définir les propriétés Exchange sur le compte d’utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="94e13-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="94e13-128">Ajout d’une adresse e-mail pour votre compte de domaine sur site</span><span class="sxs-lookup"><span data-stu-id="94e13-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="94e13-129">Dans l’outil Utilisateurs et ordinateurs **Active Directory AD,** cliquez avec le bouton droit sur le conteneur ou l’unité organisationnelle dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="94e13-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="94e13-130">Tapez le nom d’affichage (- Identité) de l’cmdlet  précédente (Set-Mailbox ou  New-Mailbox) dans la zone Nom complet et l’alias dans la zone Nom de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="94e13-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="94e13-131">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="94e13-131">Click **Next**.</span></span>
3. <span data-ttu-id="94e13-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="94e13-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94e13-135">La sélection **du mot de passe n’expire** jamais est obligatoire pour Skype Entreprise Server sur les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="94e13-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="94e13-136">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="94e13-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="94e13-137">Si c’est le cas, vous devez créer une exception pour chaque compte d’utilisateur Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="94e13-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="94e13-138">Cliquez sur **Terminer** pour créer le compte.</span><span class="sxs-lookup"><span data-stu-id="94e13-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="94e13-139">Après avoir créé le compte, exécutez une synchronisation d’annuaires.</span><span class="sxs-lookup"><span data-stu-id="94e13-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="94e13-140">Cela peut être réalisé à l’aide de la configuration [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) dans PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94e13-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="94e13-141">Une fois cette procédure terminée, allez à la page Utilisateurs et vérifiez que les deux comptes créés lors des étapes précédentes ont été fusionnés.</span><span class="sxs-lookup"><span data-stu-id="94e13-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="94e13-142">Attribuer une licence Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="94e13-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="94e13-143">Tout d’abord, connectez-vous à Azure AD pour appliquer certains paramètres de compte.</span><span class="sxs-lookup"><span data-stu-id="94e13-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="94e13-144">Pour vous connecter, vous pouvez exécuter l’applet de commande suivante.</span><span class="sxs-lookup"><span data-stu-id="94e13-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="94e13-145">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="94e13-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="94e13-146">[Azure Active Directory PowerShell 2.0 n’est](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="94e13-146">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="94e13-147">Le compte d’utilisateur doit avoir une licence Microsoft 365 ou Office 365 valide pour s’assurer qu’Exchange et Skype Entreprise Server fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="94e13-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="94e13-148">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’utilisateur ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="94e13-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="94e13-149">Vous devez effectuer le devoir dans une étape suivante.</span><span class="sxs-lookup"><span data-stu-id="94e13-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="94e13-150">Ensuite, utilisez `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="94e13-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="94e13-151">pour récupérer la liste des S SKUs disponibles pour votre organisation Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="94e13-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="94e13-152">Une fois les S SKUs répertoriées, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="94e13-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="94e13-153">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="94e13-153">cmdlet.</span></span> <span data-ttu-id="94e13-154">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="94e13-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="94e13-155">Activer le compte d’utilisateur avec Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="94e13-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="94e13-156">Créez une session Windows PowerShell distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="94e13-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="94e13-157">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="94e13-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="94e13-158">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="94e13-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="94e13-159">Pour activer votre compte Salles Microsoft Teams pour Skype Entreprise Server, exécutez la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="94e13-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="94e13-160">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur auprès d’un utilisateur existant de Skype Entreprise Server à l’aide de cette commande.</span><span class="sxs-lookup"><span data-stu-id="94e13-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="94e13-161">Affecter une licence Skype Entreprise Server à votre compte Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94e13-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="94e13-162">Connectez-vous en tant qu’administrateur client, ouvrez le Centre d’administration Microsoft 365, puis cliquez sur l’application Administrateur.</span><span class="sxs-lookup"><span data-stu-id="94e13-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="94e13-163">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="94e13-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="94e13-164">Cliquez sur le compte Salles Microsoft Teams, puis sur l’icône de stylet pour modifier les informations sur le compte.</span><span class="sxs-lookup"><span data-stu-id="94e13-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="94e13-165">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="94e13-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="94e13-166">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="94e13-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="94e13-167">Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser Voix Entreprise salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="94e13-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="94e13-168">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="94e13-168">Click **Save**.</span></span>

<span data-ttu-id="94e13-169">Pour validation, vous pouvez utiliser n’importe quel client Skype Entreprise pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="94e13-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="94e13-170">Si vous utilisez actuellement les références E1, E3, E4 ou E5 avec Skype Entreprise Plan 2 avec Audioconférence ou Phone System et un plan d’appels, celles-ci continueront de fonctionner.</span><span class="sxs-lookup"><span data-stu-id="94e13-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="94e13-171">Toutefois, vous devez envisager de passer à un modèle de licence plus simple, comme décrit dans la mise à jour des licences de salle de réunion [Teams,](rooms-licensing.md)une fois les licences actuelles expirées.</span><span class="sxs-lookup"><span data-stu-id="94e13-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="94e13-172">Si vous utilisez Le plan 2 de Skype Entreprise, vous ne pouvez utiliser que les salles Microsoft Teams en mode Skype Entreprise, ce qui signifie que toutes vos réunions seront des réunions Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="94e13-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="94e13-173">Pour activer votre salle de réunion pour les réunions Microsoft Teams, nous vous recommandons d’acheter la licence Salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="94e13-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="94e13-174">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="94e13-174">Related topics</span></span>

[<span data-ttu-id="94e13-175">Configurer des comptes pour les salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94e13-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="94e13-176">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94e13-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="94e13-177">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94e13-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="94e13-178">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94e13-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="94e13-179">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94e13-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
