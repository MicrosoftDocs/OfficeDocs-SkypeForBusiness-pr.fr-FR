---
title: Déploiement de salles de Microsoft teams avec Exchange en local
ms.author: v-lanac
author: lanachin
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
- seo-marvel-mar2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles de Microsoft teams dans un environnement hybride avec Exchange sur site.
ms.openlocfilehash: 0efed0a07024f0f1fcfeea7168c4f78c66fecd64
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141007"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="4c2cf-103">Déploiement de salles de Microsoft teams avec Exchange en local</span><span class="sxs-lookup"><span data-stu-id="4c2cf-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="4c2cf-104">Pour plus d’informations sur le déploiement de salles de Microsoft teams dans un environnement hybride avec Exchange en local et Microsoft teams ou Skype entreprise Online, reportez-vous à cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Microsoft Teams or Skype for Business Online.</span></span>
  
<span data-ttu-id="4c2cf-105">Si votre organisation dispose d’une combinaison de services, avec une partie hébergée en local et une partie hébergée en ligne, votre configuration dépend de l’emplacement d’hébergement de chaque service.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="4c2cf-106">Cette rubrique traite des déploiements hybrides pour les salles de Microsoft teams sur lesquelles Exchange est hébergé sur site.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="4c2cf-107">Dans la mesure où ce type de déploiement comporte autant de variations différentes, il n’est pas possible de fournir des instructions détaillées pour chacune d’elles.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="4c2cf-108">Le processus suivant fonctionne pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-108">The following process will work for many configurations.</span></span> <span data-ttu-id="4c2cf-109">Si le processus ne vous convient pas, nous vous recommandons d’utiliser Windows PowerShell pour obtenir le même résultat final qu’indiqué ici, et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="4c2cf-110">Microsoft fournit [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous permet de créer de nouveaux comptes d’utilisateur, ou de valider des comptes de ressources existants dont vous disposez pour vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="4c2cf-111">Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="4c2cf-112">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="4c2cf-112">Requirements</span></span>

<span data-ttu-id="4c2cf-113">Avant de déployer des salles Microsoft teams avec Exchange en local, assurez-vous que vous remplissez les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="4c2cf-114">Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-114">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="4c2cf-115">Si vous déployez des salles Microsoft teams avec Exchange en local, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="4c2cf-116">Ce compte sera synchronisé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="4c2cf-117">Vous devrez réaliser les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-117">You will need to:</span></span>
  
- <span data-ttu-id="4c2cf-118">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c2cf-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="4c2cf-119">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="4c2cf-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="4c2cf-120">Attribuez une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="4c2cf-121">Activez le compte de l’appareil avec Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="4c2cf-122">Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="4c2cf-123">Vous devez disposer de Skype entreprise Online (plan 2) ou d’une version ultérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="4c2cf-124">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-124">The plan needs to support conferencing capability.</span></span>
  
  - <span data-ttu-id="4c2cf-125">Si vous avez besoin d’une voix entreprise (RTC) avec des fournisseurs de service de téléphonie pour Microsoft Teams, vous avez besoin de Skype entreprise Online (plan 3).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - <span data-ttu-id="4c2cf-126">Les utilisateurs de votre client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - <span data-ttu-id="4c2cf-127">Votre compte Microsoft teams Room nécessite une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3), mais elle ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="4c2cf-128">Affectez une licence Skype entreprise Server à votre compte Microsoft teams Room.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="4c2cf-129">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="4c2cf-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="4c2cf-130">Dans l’outil **utilisateurs et ordinateurs Active Directory** , cliquez avec le bouton droit sur le dossier ou l’unité d’organisation dans lequel les comptes de Microsoft teams seront créés, cliquez sur **nouveau**, puis sur **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="4c2cf-p107">Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="4c2cf-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c2cf-136">Le fait de sélectionner un **mot de passe n’expire jamais** est requis pour Skype entreprise Server sur les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="4c2cf-137">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="4c2cf-138">Si tel est le cas, vous devez créer une exception pour chaque compte d’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="4c2cf-139">Une fois le compte créé, exécutez une synchronisation de répertoire.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="4c2cf-140">Lorsque vous avez terminé, accédez à la page utilisateurs du centre d’administration Microsoft 365 et vérifiez que le compte créé lors des étapes précédentes a été fusionné en ligne.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-140">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="4c2cf-141">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="4c2cf-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="4c2cf-142">[Ouvrez Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [Connectez-vous à votre serveur Exchange à l’aide de Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="4c2cf-143">Dans Exchange PowerShell, créez une boîte aux lettres pour le compte (activation du compte par boîte aux lettres) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-143">In Exchange PowerShell, create a mailbox for the account (mailbox-enable the account) by running the following command:</span></span>

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="4c2cf-144">Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [activer-boîte aux lettres](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="4c2cf-145">Dans Exchange PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="4c2cf-146">AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="4c2cf-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="4c2cf-147">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="4c2cf-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="4c2cf-148">DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4c2cf-149">DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4c2cf-150">RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)</span><span class="sxs-lookup"><span data-stu-id="4c2cf-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="4c2cf-151">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="4c2cf-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="4c2cf-152">AdditionalResponse : « il s’agit d’une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="4c2cf-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="4c2cf-153">(Le texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="4c2cf-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="4c2cf-154">Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="4c2cf-155">Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="4c2cf-156">Affectation d’une licence Office 365</span><span class="sxs-lookup"><span data-stu-id="4c2cf-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="4c2cf-157">Se connecter à Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-157">Connect to Azure Active Directory.</span></span> <span data-ttu-id="4c2cf-158">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-158">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="4c2cf-159">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-159">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

2. <span data-ttu-id="4c2cf-160">Le compte d’appareil doit avoir une licence Office 365 valide ou Exchange et Microsoft Teams ne fonctionneront pas.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-160">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams will not work.</span></span> <span data-ttu-id="4c2cf-161">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4c2cf-162">Vous pouvez utiliser`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="4c2cf-162">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="4c2cf-163">pour récupérer la liste des références SKU disponibles.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-163">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="4c2cf-164">Vous pouvez ensuite ajouter une licence à l’aide du`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="4c2cf-164">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="4c2cf-165">applet.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-165">cmdlet.</span></span> <span data-ttu-id="4c2cf-166">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-166">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="4c2cf-167">Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4c2cf-167">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account"></a><span data-ttu-id="4c2cf-168">Activer le compte de l’appareil</span><span class="sxs-lookup"><span data-stu-id="4c2cf-168">Enable the device account</span></span>

<span data-ttu-id="4c2cf-169">PowerShell Skype entreprise Online permet de gérer les services de Microsoft teams et de Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-169">Skype for Business Online PowerShell is used to manage services for both Microsoft Teams and Skype for Business Online.</span></span>

1. <span data-ttu-id="4c2cf-170">Créez une session Windows PowerShell distante à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-170">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="4c2cf-171">Obtenez l’adresse SIP du compte :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-171">Obtain SIP address of the account:</span></span>

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. <span data-ttu-id="4c2cf-172">Pour activer votre compte Microsoft teams Room, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-172">To enable your Microsoft Teams Rooms account, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="4c2cf-173">Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un utilisateur existant à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4c2cf-173">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing user using this command:</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="4c2cf-174">Attribution d’une licence à votre compte Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4c2cf-174">Assign a license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="4c2cf-175">Ouvrez une session en tant qu’administrateur client, ouvrez le portail d’administration Office 365, puis cliquez sur l’application Administration.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-175">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="4c2cf-176">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-176">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="4c2cf-177">Cliquez sur le compte Microsoft Teams, puis cliquez sur l’icône représentant un crayon pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-177">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="4c2cf-178">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-178">Click **Licenses**.</span></span>
5. <span data-ttu-id="4c2cf-179">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-179">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="4c2cf-180">Vous devez utiliser une licence de plan 3 Si vous souhaitez utiliser Enterprise Voice dans vos salles Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-180">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="4c2cf-181">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-181">Click **Save**.</span></span>

<span data-ttu-id="4c2cf-182">Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="4c2cf-182">For validation, you should be able to use any client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c2cf-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4c2cf-183">See also</span></span>

[<span data-ttu-id="4c2cf-184">Configurer des comptes pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4c2cf-184">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="4c2cf-185">Plan pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4c2cf-185">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="4c2cf-186">Déploiement de salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4c2cf-186">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="4c2cf-187">Configurer une console de salle Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4c2cf-187">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4c2cf-188">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="4c2cf-188">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
