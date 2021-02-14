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
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662319"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="d1880-103">Déployer des salles Microsoft Teams avec Exchange en local</span><span class="sxs-lookup"><span data-stu-id="d1880-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="d1880-104">Lisez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft Teams dans un environnement hybride avec Exchange en local et Microsoft Teams ou Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="d1880-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="d1880-105">Si votre organisation dispose d’un mélange de services, dont certains sont hébergés en local et d’autres hébergés en ligne, votre configuration dépend de l’endroit où chaque service est hébergé.</span><span class="sxs-lookup"><span data-stu-id="d1880-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="d1880-106">Cette rubrique traite des déploiements hybrides de salles Microsoft Teams avec Exchange hébergé en local.</span><span class="sxs-lookup"><span data-stu-id="d1880-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="d1880-107">Ce type de déploiement étant très différent, il n’est pas possible de fournir des instructions détaillées pour l’ensemble d’entre eux.</span><span class="sxs-lookup"><span data-stu-id="d1880-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="d1880-108">Le processus suivant fonctionne pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="d1880-108">The following process will work for many configurations.</span></span> <span data-ttu-id="d1880-109">Si le processus n’est pas configuré pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final que celui documenté ici, ainsi que pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="d1880-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="d1880-110">Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aidera à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez afin de vous aider à les transformer en comptes d’utilisateurs de salles Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="d1880-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="d1880-111">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre appareil Microsoft Teams Rooms utilisera.</span><span class="sxs-lookup"><span data-stu-id="d1880-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="d1880-112">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="d1880-112">Requirements</span></span>

<span data-ttu-id="d1880-113">Avant de déployer des salles Microsoft Teams avec Exchange en local, assurez-vous que vous avez répondu aux exigences.</span><span class="sxs-lookup"><span data-stu-id="d1880-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="d1880-114">Pour plus d’informations, consultez [la conditions requises pour les salles Microsoft Teams.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="d1880-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="d1880-115">Si vous déployez des salles Microsoft Teams avec Exchange en local, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="d1880-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="d1880-116">Ce compte sera synchronisé avec Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1880-116">This account will be synced to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d1880-117">Vous devrez réaliser les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1880-117">You will need to:</span></span>
  
- <span data-ttu-id="d1880-118">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="d1880-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="d1880-119">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="d1880-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="d1880-120">Attribuer une licence Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1880-120">Assign an Microsoft 365 or Office 365 license.</span></span>

- <span data-ttu-id="d1880-121">Activez le compte d’appareil avec Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d1880-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="d1880-122">Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="d1880-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="d1880-123">Vous devez avoir Skype Entreprise Online (plan 2) ou une version supérieure dans votre offre Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="d1880-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="d1880-124">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="d1880-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="d1880-125">Si vous avez besoin Voix Entreprise (téléphonie PSTN) en utilisant des fournisseurs de services téléphoniques pour les salles Microsoft Teams, vous avez besoin de Skype Entreprise Online (plan 3).</span><span class="sxs-lookup"><span data-stu-id="d1880-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="d1880-126">Vos utilisateurs clients doivent avoir une boîte aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="d1880-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="d1880-127">Votre compte Salles Microsoft Teams ne nécessite pas de licence Skype Entreprise Online (plan 2) ou Skype Entreprise Online (plan 3), mais pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d1880-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="d1880-128">Affectez une licence Skype Entreprise Server à votre compte Salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1880-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="d1880-129">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="d1880-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="d1880-130">Dans l’outil Utilisateurs et ordinateurs **Active Directory,** cliquez avec le bouton droit sur le dossier ou l’unité d’organisation dans qui vos comptes Salles Microsoft Teams seront créés, cliquez sur **Nouveau,** puis sur **Utilisateur.**</span><span class="sxs-lookup"><span data-stu-id="d1880-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="d1880-p107">Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="d1880-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="d1880-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d1880-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d1880-136">La sélection **du mot de passe n’expire** jamais est obligatoire pour Skype Entreprise Server sur les salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1880-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="d1880-137">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="d1880-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="d1880-138">Si c’est le cas, vous devez créer une exception pour chaque compte d’appareil Microsoft Teams Rooms.</span><span class="sxs-lookup"><span data-stu-id="d1880-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="d1880-139">Une fois le compte créé, exécutez une synchronisation de répertoire.</span><span class="sxs-lookup"><span data-stu-id="d1880-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="d1880-140">Une fois l’étape terminée, dans la page utilisateurs de votre Centre d’administration Microsoft 365, vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.</span><span class="sxs-lookup"><span data-stu-id="d1880-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="d1880-141">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="d1880-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="d1880-142">[Ouvrez Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [connectez-vous à votre serveur Exchange à l’aide de Remote PowerShell.](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)</span><span class="sxs-lookup"><span data-stu-id="d1880-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="d1880-143">Dans Exchange PowerShell, créez une boîte aux lettres pour le compte (activez-le avec la boîte aux lettres) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d1880-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="d1880-144">Pour plus d’informations sur la syntaxe et les paramètres, voir [Enable-Mailbox.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)</span><span class="sxs-lookup"><span data-stu-id="d1880-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="d1880-145">Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="d1880-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="d1880-146">AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent la décision de réservation de salle directement sans intervention humaine : libre = accepter ; occupé = refus.)</span><span class="sxs-lookup"><span data-stu-id="d1880-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="d1880-147">AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="d1880-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="d1880-148">DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)</span><span class="sxs-lookup"><span data-stu-id="d1880-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="d1880-149">SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)</span><span class="sxs-lookup"><span data-stu-id="d1880-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="d1880-150">RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion initiale reste tel que spécifié.)</span><span class="sxs-lookup"><span data-stu-id="d1880-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="d1880-151">AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="d1880-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="d1880-152">Réponse supplémentaire : « Il s’agit d’une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="d1880-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="d1880-153">(Texte supplémentaire à ajouter à la demande de réunion.</span><span class="sxs-lookup"><span data-stu-id="d1880-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="d1880-154">Cet exemple configure ces paramètres sur la boîte aux lettres de salle project-rigel-01.</span><span class="sxs-lookup"><span data-stu-id="d1880-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="d1880-155">Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="d1880-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="d1880-156">Attribuer une licence Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="d1880-156">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="d1880-157">Connectez-vous à Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d1880-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="d1880-158">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="d1880-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="d1880-159">[Azure Active Directory PowerShell 2.0 n’est](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="d1880-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="d1880-160">Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide, sinon Exchange et Microsoft Teams ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="d1880-160">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="d1880-161">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="d1880-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="d1880-162">Vous pouvez utiliser `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="d1880-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="d1880-163">pour récupérer la liste des S SKUs disponibles.</span><span class="sxs-lookup"><span data-stu-id="d1880-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="d1880-164">Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="d1880-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="d1880-165">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d1880-165">cmdlet.</span></span> <span data-ttu-id="d1880-166">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="d1880-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="d1880-167">Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes d’utilisateurs [avec PowerShell Office 365.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="d1880-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="d1880-168">Activer le compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="d1880-168">Enable the device account</span></span>

<span data-ttu-id="d1880-169">Skype Entreprise Online PowerShell est utilisé pour gérer les services pour Microsoft Teams et Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="d1880-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="d1880-170">Créez une session Windows PowerShell distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="d1880-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>
> [!NOTE]
> <span data-ttu-id="d1880-171">Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.</span><span class="sxs-lookup"><span data-stu-id="d1880-171">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="d1880-172">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d1880-172">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="d1880-173">Obtenez l’adresse SIP du compte :</span><span class="sxs-lookup"><span data-stu-id="d1880-173">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="d1880-174">Pour activer votre compte Salles Microsoft Teams, exécutez la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="d1880-174">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="d1880-175">Si vous n’êtes pas certain de la valeur à utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur auprès d’un utilisateur existant à l’aide de la commande ci-après :</span><span class="sxs-lookup"><span data-stu-id="d1880-175">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="d1880-176">Attribuer une licence à votre compte Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1880-176">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="d1880-177">Connectez-vous en tant qu’administrateur client, ouvrez le Centre d’administration Microsoft 365, puis cliquez sur l’application Administrateur.</span><span class="sxs-lookup"><span data-stu-id="d1880-177">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="d1880-178">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="d1880-178">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="d1880-179">Cliquez sur le compte Salles Microsoft Teams, puis sur l’icône de stylet pour modifier les informations sur le compte.</span><span class="sxs-lookup"><span data-stu-id="d1880-179">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="d1880-180">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="d1880-180">Click **Licenses**.</span></span>
5. <span data-ttu-id="d1880-181">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d1880-181">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="d1880-182">Vous devez utiliser une licence Plan 3 si vous souhaitez utiliser des Voix Entreprise dans vos salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d1880-182">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="d1880-183">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="d1880-183">Click **Save**.</span></span>

<span data-ttu-id="d1880-184">Pour validation, vous pouvez utiliser n’importe quel client pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="d1880-184">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d1880-185">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="d1880-185">Related topics</span></span>

[<span data-ttu-id="d1880-186">Configurer des comptes pour les salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1880-186">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="d1880-187">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1880-187">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="d1880-188">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1880-188">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="d1880-189">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1880-189">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="d1880-190">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d1880-190">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
