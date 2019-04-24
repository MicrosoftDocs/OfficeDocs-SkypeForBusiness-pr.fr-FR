---
title: Déployer Microsoft équipes salles avec Exchange sur site
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Lisez cette rubrique pour plus d’informations sur le déploiement des salles d’équipes Microsoft dans un environnement hybride avec Exchange sur site.
ms.openlocfilehash: 664f6d210858b42591dcbb4461b858646e5cb933
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207887"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a><span data-ttu-id="67ee3-103">Déployer Microsoft équipes salles avec Exchange sur site</span><span class="sxs-lookup"><span data-stu-id="67ee3-103">Deploy Microsoft Teams Rooms with Exchange on premises</span></span>

<span data-ttu-id="67ee3-104">Lisez cette rubrique pour plus d’informations sur le déploiement des salles d’équipes Microsoft dans un environnement hybride avec Exchange sur site et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="67ee3-104">Read this topic for information on how to deploy Microsoft Teams Rooms in a hybrid environment with Exchange on premises and Skype for Business Online.</span></span>
  
<span data-ttu-id="67ee3-105">Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service.</span><span class="sxs-lookup"><span data-stu-id="67ee3-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="67ee3-106">Cette rubrique traite des déploiements hybrides pour les salles d’équipes Microsoft avec Exchange hébergé sur site.</span><span class="sxs-lookup"><span data-stu-id="67ee3-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted on premises.</span></span> <span data-ttu-id="67ee3-107">Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les.</span><span class="sxs-lookup"><span data-stu-id="67ee3-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="67ee3-108">Le processus suivant fonctionnera pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="67ee3-108">The following process will work for many configurations.</span></span> <span data-ttu-id="67ee3-109">Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="67ee3-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="67ee3-110">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs locaux des équipes Microsoft compatibles.</span><span class="sxs-lookup"><span data-stu-id="67ee3-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="67ee3-111">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre périphérique Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="67ee3-111">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="67ee3-112">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="67ee3-112">Requirements</span></span>

<span data-ttu-id="67ee3-113">Avant de déployer Microsoft équipes salles avec Exchange sur site, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="67ee3-113">Before you deploy Microsoft Teams Rooms with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="67ee3-114">Pour plus d’informations, consultez [Configuration requise de salles d’équipes Microsoft](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67ee3-114">For more information, see [Microsoft Teams Rooms requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="67ee3-115">Si vous déployez Microsoft équipes salles avec Exchange sur site, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="67ee3-115">If you are deploying Microsoft Teams Rooms with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="67ee3-116">Ce compte sera synchronisé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="67ee3-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="67ee3-117">Vous devrez réaliser les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="67ee3-117">You will need to:</span></span>
  
- <span data-ttu-id="67ee3-118">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="67ee3-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="67ee3-119">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="67ee3-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="67ee3-120">Attribuer une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="67ee3-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="67ee3-121">Activez le compte de l’appareil avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="67ee3-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="67ee3-122">Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="67ee3-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="67ee3-123">Vous devez avoir Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="67ee3-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="67ee3-124">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="67ee3-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="67ee3-125">Si vous avez besoin d’Enterprise Voice (téléphonie TLS) à l’aide de fournisseurs de services de téléphonie pour les salles d’équipes Microsoft vous devez Skype pour Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="67ee3-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Microsoft Teams Rooms you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="67ee3-126">Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="67ee3-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="67ee3-127">Votre compte Microsoft équipes salles requiert Skype pour Business Online (Plan 2) ni Skype licence entreprise Online (Plan 3), mais il ne requiert pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="67ee3-127">Your Microsoft Teams Rooms account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="67ee3-128">Affecter un Skype licence Business Server à votre compte Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="67ee3-128">Assign a Skype for Business Server license to your Microsoft Teams Rooms account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="67ee3-129">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="67ee3-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="67ee3-130">Dans l’outil **utilisateurs et ordinateurs** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos salles d’équipes Microsoft comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="67ee3-130">In the **Active Directory Users and Computers** tool, right-click on the folder or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="67ee3-p107">Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="67ee3-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="67ee3-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67ee3-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="67ee3-136">Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server dans les salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67ee3-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="67ee3-137">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="67ee3-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="67ee3-138">Dans ce cas, vous devez créer une exception pour chaque compte de périphérique salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67ee3-138">If so, you'll need to create an exception for each Microsoft Teams Rooms device account.</span></span>
  
4. <span data-ttu-id="67ee3-139">Une fois le compte créé, exécutez une synchronisation de répertoire.</span><span class="sxs-lookup"><span data-stu-id="67ee3-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="67ee3-140">Lorsqu’elle est terminée, accédez à la page utilisateurs dans votre centre d’administration d’Office 365 et vérifiez que le compte créé lors des étapes précédentes a fusionné à en ligne.</span><span class="sxs-lookup"><span data-stu-id="67ee3-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="67ee3-141">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="67ee3-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="67ee3-142">[Ouvrez Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [vous connecter à votre serveur Exchange à l’aide de PowerShell à distance](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="67ee3-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="67ee3-143">Dans Exchange PowerShell, créer une boîte aux lettres pour le compte de (boîte aux lettres activer le compte) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="67ee3-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="67ee3-144">Pour détaillées sur la syntaxe et les informations sur les paramètres, consultez la rubrique [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="67ee3-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="67ee3-145">Dans Exchange PowerShell, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="67ee3-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="67ee3-146">AutomateProcessing : AutoAccept (organisateurs de réunion recevoir la décision de réservation de salles directement sans intervention humaine : libre = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="67ee3-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="67ee3-147">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion).</span><span class="sxs-lookup"><span data-stu-id="67ee3-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="67ee3-148">DeleteComments : $false (conserver le texte dans le corps du message de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="67ee3-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="67ee3-149">DeleteSubject : $false (conserver l’objet de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="67ee3-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="67ee3-150">RemovePrivateProperty : $false (garantit la demande de l’indicateur privé qui a été envoyé par l’organisateur de la réunion d’origine reste comme indiqué).</span><span class="sxs-lookup"><span data-stu-id="67ee3-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="67ee3-151">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion).</span><span class="sxs-lookup"><span data-stu-id="67ee3-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="67ee3-152">AdditionalResponse : « Ceci est une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="67ee3-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="67ee3-153">(Texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="67ee3-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="67ee3-154">Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommé Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="67ee3-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="67ee3-155">Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="67ee3-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="67ee3-156">Affectation d’une licence Office 365</span><span class="sxs-lookup"><span data-stu-id="67ee3-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="67ee3-157">Se connecter à Active Directory Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="67ee3-157">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="67ee3-158">Pour obtenir des instructions, consultez la rubrique [Connect avec Azure Active Directory PowerShell pour le module de graphique](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="67ee3-158">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

2. <span data-ttu-id="67ee3-159">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="67ee3-159">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="67ee3-160">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="67ee3-160">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="67ee3-161">Vous pouvez utiliser`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="67ee3-161">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="67ee3-162">pour récupérer une liste de références disponibles.</span><span class="sxs-lookup"><span data-stu-id="67ee3-162">to retrieve a list of available SKUs.</span></span>

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. <span data-ttu-id="67ee3-163">Ensuite, vous pouvez ajouter une licence à l’aide du`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="67ee3-163">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense --> <span data-ttu-id="67ee3-164">applet de commande.</span><span class="sxs-lookup"><span data-stu-id="67ee3-164">cmdlet.</span></span> <span data-ttu-id="67ee3-165">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="67ee3-165">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="67ee3-166">Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="67ee3-166">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="67ee3-167">Activation du compte de l’appareil avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="67ee3-167">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="67ee3-168">Créez une session Windows PowerShell à distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="67ee3-168">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="67ee3-169">Pour activer votre compte Microsoft équipes salles pour Skype pour Business Server, exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="67ee3-169">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="67ee3-170">Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante</span><span class="sxs-lookup"><span data-stu-id="67ee3-170">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="67ee3-171">Affecter un Skype licence entreprise à votre compte Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="67ee3-171">Assign a Skype for Business license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="67ee3-172">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="67ee3-172">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="67ee3-173">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="67ee3-173">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="67ee3-174">Cliquez sur le compte de salles d’équipes Microsoft, puis cliquez sur l’icône du crayon pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="67ee3-174">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="67ee3-175">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="67ee3-175">Click **Licenses**.</span></span>
5. <span data-ttu-id="67ee3-176">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="67ee3-176">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="67ee3-177">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice sur vos salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="67ee3-177">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="67ee3-178">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="67ee3-178">Click **Save**.</span></span>

<span data-ttu-id="67ee3-179">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="67ee3-179">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="67ee3-180">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67ee3-180">See also</span></span>

[<span data-ttu-id="67ee3-181">Configurer des comptes pour les salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="67ee3-181">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="67ee3-182">Planifier des équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="67ee3-182">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="67ee3-183">Déployer les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="67ee3-183">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="67ee3-184">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="67ee3-184">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="67ee3-185">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="67ee3-185">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)
