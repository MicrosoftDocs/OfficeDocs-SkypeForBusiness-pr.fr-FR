---
title: Déployer des salles Microsoft Teams avec Exchange sur site
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
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams dans un environnement hybride avec Exchange en local.
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117352"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="e439f-103">Déployer des salles Microsoft Teams avec Exchange en local</span><span class="sxs-lookup"><span data-stu-id="e439f-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="e439f-104">Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams dans un environnement hybride avec Exchange en local et Microsoft Teams ou Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="e439f-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="e439f-105">Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé.</span><span class="sxs-lookup"><span data-stu-id="e439f-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="e439f-106">Cette rubrique traite des déploiements hybrides de salles Microsoft Teams avec Exchange hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="e439f-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="e439f-107">Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="e439f-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="e439f-108">Le processus suivant fonctionne pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="e439f-108">The following process will work for many configurations.</span></span> <span data-ttu-id="e439f-109">Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="e439f-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="e439f-110">Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aidera à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’utilisateurs de salles Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="e439f-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="e439f-111">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre appareil Microsoft Teams Rooms utilisera.</span><span class="sxs-lookup"><span data-stu-id="e439f-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="e439f-112">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="e439f-112">Requirements</span></span>

<span data-ttu-id="e439f-113">Avant de déployer des salles Microsoft Teams avec Exchange en local, assurez-vous que vous avez répondu à la exigences.</span><span class="sxs-lookup"><span data-stu-id="e439f-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="e439f-114">Pour plus d’informations, consultez [la conditions requises pour les salles Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="e439f-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="e439f-115">Si vous déployez des salles Microsoft Teams avec Exchange en local, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="e439f-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="e439f-116">Ce compte sera synchronisé avec Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e439f-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e439f-117">Vous devrez réaliser les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e439f-117">You will need to:</span></span>
  
- <span data-ttu-id="e439f-118">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="e439f-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="e439f-119">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="e439f-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="e439f-120">Attribuer une licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e439f-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="e439f-121">Activez le compte d’appareil avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e439f-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="e439f-122">Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="e439f-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="e439f-123">Vous devez avoir Skype Entreprise Online (plan 2) ou une version supérieure dans votre offre Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e439f-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="e439f-124">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="e439f-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="e439f-125">Si vous avez besoin Voix Entreprise (téléphonie PSTN) en utilisant des fournisseurs de services téléphoniques pour les salles Microsoft Teams, vous avez besoin de Skype Entreprise Online (plan 3).</span><span class="sxs-lookup"><span data-stu-id="e439f-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>

  - <span data-ttu-id="e439f-126">Lors de la configuration d’un compte de salle avec Microsoft Teams ou Skype Entreprise Online, le numéro de téléphone doit être affecté avant que le compte soit activé en tant que compte de salle.</span><span class="sxs-lookup"><span data-stu-id="e439f-126">When configuring a room account with Microsoft Teams or Skype for Business Online, the phone number should be assigned prior to the account being enabled as a room account.</span></span>
  
  - <span data-ttu-id="e439f-127">Vos utilisateurs clients doivent avoir une boîte aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="e439f-127">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="e439f-128">Votre compte Salles Microsoft Teams ne nécessite pas de licence Skype Entreprise Online (plan 2) ou Skype Entreprise Online (plan 3), mais pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="e439f-128">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="e439f-129">Affectez une licence Skype Entreprise Server à votre compte Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e439f-129">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="e439f-130">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="e439f-130">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="e439f-131">Dans l’outil Utilisateurs et ordinateurs **Active Directory,** cliquez avec le bouton droit sur le dossier ou l’unité de l’organisation dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="e439f-131">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="e439f-p107">Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e439f-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="e439f-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="e439f-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e439f-137">La sélection **du mot de passe n’expire** jamais est obligatoire pour Skype Entreprise Server sur les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e439f-137">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="e439f-138">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="e439f-138">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="e439f-139">Si c’est le cas, vous devez créer une exception pour chaque compte d’appareil Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="e439f-139">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="e439f-140">Une fois le compte créé, exécutez une synchronisation de répertoire.</span><span class="sxs-lookup"><span data-stu-id="e439f-140">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="e439f-141">Une fois l’étape terminée, dans la page utilisateurs de votre Centre d’administration Microsoft 365, vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.</span><span class="sxs-lookup"><span data-stu-id="e439f-141">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="e439f-142">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="e439f-142">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="e439f-143">[Ouvrez Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [connectez-vous à votre serveur Exchange à l’aide de Remote PowerShell.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="e439f-143">[Open the Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="e439f-144">Dans Exchange PowerShell, créez une boîte aux lettres pour le compte (activez-le avec la boîte aux lettres) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="e439f-144">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="e439f-145">Pour plus d’informations sur la syntaxe et les paramètres, [voir Enable-Mailbox.](/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="e439f-145">For detailed syntax and parameter information, see [Enable-Mailbox](/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="e439f-146">Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="e439f-146">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="e439f-147">AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention humaine : libre = accepter ; occupé = refus.)</span><span class="sxs-lookup"><span data-stu-id="e439f-147">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="e439f-148">AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="e439f-148">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="e439f-149">DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)</span><span class="sxs-lookup"><span data-stu-id="e439f-149">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="e439f-150">SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)</span><span class="sxs-lookup"><span data-stu-id="e439f-150">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="e439f-151">RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.)</span><span class="sxs-lookup"><span data-stu-id="e439f-151">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="e439f-152">AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="e439f-152">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="e439f-153">Réponse supplémentaire : « Il s’agit d’une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="e439f-153">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="e439f-154">(Le texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="e439f-154">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="e439f-155">Cet exemple configure ces paramètres sur la boîte aux lettres de salle project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="e439f-155">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="e439f-156">Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="e439f-156">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="e439f-157">Attribuer une licence Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="e439f-157">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="e439f-158">Connectez-vous à Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e439f-158">Connect to Azure Active Directory.</span></span> <span data-ttu-id="e439f-159">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="e439f-159">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="e439f-160">[Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="e439f-160">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="e439f-161">Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide, sinon Exchange et Microsoft Teams ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="e439f-161">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="e439f-162">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="e439f-162">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="e439f-163">Vous pouvez utiliser `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="e439f-163">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="e439f-164">pour récupérer la liste des S SKUs disponibles.</span><span class="sxs-lookup"><span data-stu-id="e439f-164">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="e439f-165">Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="e439f-165">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="e439f-166">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e439f-166">cmdlet.</span></span> <span data-ttu-id="e439f-167">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="e439f-167">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   <span data-ttu-id="e439f-168">Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes d’utilisateurs [avec PowerShell Office 365.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e439f-168">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="e439f-169">Activer le compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="e439f-169">Enable the device account</span></span>

<span data-ttu-id="e439f-170">Skype Entreprise Online PowerShell est utilisé pour gérer les services pour Microsoft Teams et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="e439f-170">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="e439f-171">Créez une session Windows PowerShell distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="e439f-171">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="e439f-172">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="e439f-172">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="e439f-173">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="e439f-173">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. <span data-ttu-id="e439f-174">Obtenez l’adresse SIP du compte :</span><span class="sxs-lookup"><span data-stu-id="e439f-174">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="e439f-175">**Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="e439f-175">**Optional.**</span></span> <span data-ttu-id="e439f-176">Si vous voulez attribuer un numéro de téléphone au compte, l’opération doit être effectuée à ce stade.</span><span class="sxs-lookup"><span data-stu-id="e439f-176">If you want to assign a phone number to the account, the operation should be performed at this point.</span></span> <span data-ttu-id="e439f-177">Si vous souhaitez affecter un numéro de téléphone de routage direct :</span><span class="sxs-lookup"><span data-stu-id="e439f-177">If you want to assign a Direct Routing phone number:</span></span>

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    <span data-ttu-id="e439f-178">Si vous affectez un numéro de téléphone fourni par Microsoft, utilisez l’cmdlet ci-dessous après avoir fourni à l’utilisateur une licence forfait d’appels :</span><span class="sxs-lookup"><span data-stu-id="e439f-178">If you're assigning a Microsoft provided phone number, use the cmdlet below after having provisioned the user with a Calling Plan license:</span></span>
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. <span data-ttu-id="e439f-179">Pour activer votre compte Salles Microsoft Teams, exécutez la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="e439f-179">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="e439f-180">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur auprès d’un utilisateur existant à l’aide de la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="e439f-180">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="e439f-181">Attribuer une licence à votre compte Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e439f-181">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="e439f-182">Connectez-vous en tant qu’administrateur client, ouvrez le Centre d’administration Microsoft 365, puis cliquez sur l’application Administrateur.</span><span class="sxs-lookup"><span data-stu-id="e439f-182">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="e439f-183">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="e439f-183">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="e439f-184">Cliquez sur le compte Salles Microsoft Teams, puis sur l’icône de stylet pour modifier les informations sur le compte.</span><span class="sxs-lookup"><span data-stu-id="e439f-184">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="e439f-185">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="e439f-185">Click **Licenses**.</span></span>
5. <span data-ttu-id="e439f-186">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="e439f-186">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="e439f-187">Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser des Voix Entreprise dans vos salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e439f-187">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="e439f-188">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e439f-188">Click **Save**.</span></span>

<span data-ttu-id="e439f-189">Pour validation, vous pouvez utiliser n’importe quel client pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="e439f-189">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e439f-190">Rubriques connexes</span><span class="sxs-lookup"><span data-stu-id="e439f-190">Related topics</span></span>

[<span data-ttu-id="e439f-191">Configurer des comptes pour les salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e439f-191">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="e439f-192">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e439f-192">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="e439f-193">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e439f-193">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="e439f-194">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e439f-194">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="e439f-195">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e439f-195">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)