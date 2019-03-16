---
title: Déploiement de Skype Room Systems v2 avec Exchange sur site
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
description: Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 dans un environnement hybride avec Exchange sur site.
ms.openlocfilehash: a804ba6b1210efae8ed36630180f14ad367cb955
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645415"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a><span data-ttu-id="1e0e7-103">Déploiement de Skype Room Systems v2 avec Exchange sur site</span><span class="sxs-lookup"><span data-stu-id="1e0e7-103">Deploy Skype Room Systems v2 with Exchange on premises</span></span>

<span data-ttu-id="1e0e7-104">Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 dans un environnement hybride avec Exchange sur site et Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-104">Read this topic for information on how to deploy Skype Room Systems v2 in a hybrid environment with Exchange on premises and Skype for Business Online.</span></span>
  
<span data-ttu-id="1e0e7-105">Si votre organisation possède un mélange de services, avec une poignée hébergés sur site et certaines hébergées en ligne, votre configuration dépendra où se trouve chaque service.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="1e0e7-106">Cette rubrique traite des déploiements hybrides pour systèmes de salle Skype v2 avec Exchange hébergé sur site.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-106">This topic covers hybrid deployments for Skype Room Systems v2 with Exchange hosted on premises.</span></span> <span data-ttu-id="1e0e7-107">Il existe de nombreuses différentes variantes dans ce type de déploiement, il n’est pas possible de fournir des instructions détaillées pour toutes les.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="1e0e7-108">Le processus suivant fonctionnera pour de nombreuses configurations.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-108">The following process will work for many configurations.</span></span> <span data-ttu-id="1e0e7-109">Si le processus n’est pas bon choix pour votre configuration, nous vous recommandons d’utiliser Windows PowerShell pour atteindre le même résultat final, comme indiqué ici et pour d’autres options de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="1e0e7-110">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-110">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="1e0e7-111">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-111">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1e0e7-112">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="1e0e7-112">Requirements</span></span>

<span data-ttu-id="1e0e7-113">Avant de déployer des systèmes de salle Skype v2 avec Exchange sur site, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-113">Before you deploy Skype Room Systems v2 with Exchange on premises, be sure you have met the requirements.</span></span> <span data-ttu-id="1e0e7-114">Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-114">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="1e0e7-115">Si vous déployez des systèmes de salle Skype v2 avec Exchange sur site, vous utiliserez les outils d’administration Active Directory pour ajouter une adresse de messagerie pour votre compte de domaine local.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-115">If you are deploying Skype Room Systems v2 with Exchange on premises, you will be using Active Directory administrative tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="1e0e7-116">Ce compte sera synchronisé avec Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-116">This account will be synced to Office 365.</span></span> <span data-ttu-id="1e0e7-117">Vous devrez réaliser les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-117">You will need to:</span></span>
  
- <span data-ttu-id="1e0e7-118">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e0e7-118">Create an account and synchronize the account with Active Directory.</span></span>

- <span data-ttu-id="1e0e7-119">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="1e0e7-119">Enable the remote mailbox and set properties.</span></span>

- <span data-ttu-id="1e0e7-120">Attribuer une licence Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-120">Assign an Office 365 license.</span></span>

- <span data-ttu-id="1e0e7-121">Activez le compte de l’appareil avec Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-121">Enable the device account with Skype for Business Server.</span></span> <span data-ttu-id="1e0e7-122">Pour activer le compte d’appareil avec dans votre environnement, vous devez remplir les conditions préalables suivantes :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-122">To enable the device account your environment will need to meet the following prerequisites:</span></span>

  - <span data-ttu-id="1e0e7-123">Vous devez avoir Skype pour Business Online (Plan 2) ou version ultérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-123">You'll need to have Skype for Business Online (Plan 2) or higher in your Office 365 plan.</span></span> <span data-ttu-id="1e0e7-124">Le plan doit prendre en charge la fonctionnalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-124">The plan needs to support conferencing capability.</span></span>
  
  - - <span data-ttu-id="1e0e7-125">Si vous avez besoin d’Enterprise Voice (téléphonie TLS) à l’aide de fournisseurs de services de téléphonie pour les systèmes de salle Skype v2 vous devez Skype pour Business Online (Plan 3).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-125">If you need Enterprise Voice (PSTN telephony) using telephony service providers for Skype Room Systems v2 you need Skype for Business Online (Plan 3).</span></span>
  
  - - <span data-ttu-id="1e0e7-126">Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-126">Your tenant users must have Exchange mailboxes.</span></span>
  
  - - <span data-ttu-id="1e0e7-127">Votre compte v2 de systèmes de salle Skype requiert Skype pour Business Online (Plan 2) ni Skype licence entreprise Online (Plan 3), mais il ne nécessite pas une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-127">Your Skype Room Systems v2 account does require a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license, but it does not require an Exchange Online license.</span></span>

- <span data-ttu-id="1e0e7-128">Affecter un Skype licence Business Server à votre compte de v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-128">Assign a Skype for Business Server license to your Skype Room Systems v2 account.</span></span>

### <a name="create-an-account-and-synchronize-with-active-directory"></a><span data-ttu-id="1e0e7-129">Création d’un compte et synchronisation avec Active Directory</span><span class="sxs-lookup"><span data-stu-id="1e0e7-129">Create an account and synchronize with Active Directory</span></span>

1. <span data-ttu-id="1e0e7-130">Dans l’outil **Active Directory utilisateurs et ordinateurs Active Directory** , avec le bouton droit sur le dossier ou l’unité d’organisation que vos systèmes de salle Skype v2 comptes seront créés, cliquez sur **Nouveau**, puis cliquez sur **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-130">In the **Active Directory Users and Computers AD** tool, right-click on the folder or Organizational Unit that your Skype Room Systems v2 accounts will be created in, click **New**, and then click **User**.</span></span>

2. <span data-ttu-id="1e0e7-p107">Saisissez le nom d’affichage de l’applet de commande précédente dans le champ **Nom complet** et l’alias dans le champ **Nom d’ouverture de session de l’utilisateur**. Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-p107">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box. Click **Next**.</span></span>

3. <span data-ttu-id="1e0e7-p108">Saisissez le mot de passe de ce compte. Vous devrez le saisir à nouveau à des fins de vérification. Vérifiez que seule l’option **Le mot de passe n’expire jamais** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e0e7-136">Sélection de **mot de passe n’expire jamais** est une condition requise pour Skype pour Business Server sur les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-136">Selecting **Password never expires** is a requirement for Skype for Business Server on Skype Room Systems v2.</span></span> <span data-ttu-id="1e0e7-137">Il est possible que des règles de votre domaine interdisent la non-expiration des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-137">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="1e0e7-138">Dans ce cas, vous devez créer une exception pour chaque compte de périphérique Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-138">If so, you'll need to create an exception for each Skype Room Systems v2 device account.</span></span>
  
4. <span data-ttu-id="1e0e7-139">Une fois le compte créé, exécutez une synchronisation de répertoire.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-139">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="1e0e7-140">Lorsqu’elle est terminée, accédez à la page utilisateurs dans votre centre d’administration d’Office 365 et vérifiez que le compte créé lors des étapes précédentes a fusionné à en ligne.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-140">When it's complete, go to the users page in your Office 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

### <a name="enable-the-remote-mailbox-and-set-properties"></a><span data-ttu-id="1e0e7-141">Activation de la boîte aux lettres distante et définition des propriétés</span><span class="sxs-lookup"><span data-stu-id="1e0e7-141">Enable the remote mailbox and set properties</span></span>

1. <span data-ttu-id="1e0e7-142">[Ouvrez Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [vous connecter à votre serveur Exchange à l’aide de PowerShell à distance](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-142">[Open the Exchange Management Shell](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) or [connect to your Exchange server using remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="1e0e7-143">Dans Exchange PowerShell, créer une boîte aux lettres pour le compte de (boîte aux lettres activer le compte) en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-143">In Exchange PowerShell, crate a mailbox for the account (mailbox-enable the account)by running the following command:</span></span>

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   <span data-ttu-id="1e0e7-144">Pour détaillées sur la syntaxe et les informations sur les paramètres, consultez la rubrique [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-144">For detailed syntax and parameter information, see [Enable-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox).</span></span>

3. <span data-ttu-id="1e0e7-145">Dans Exchange PowerShell, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-145">In Exchange PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="1e0e7-146">AutomateProcessing : AutoAccept (organisateurs de réunion recevoir la décision de réservation de salles directement sans intervention humaine : libre = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="1e0e7-146">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="1e0e7-147">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-147">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="1e0e7-148">DeleteComments : $false (conserver le texte dans le corps du message de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-148">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="1e0e7-149">DeleteSubject : $false (conserver l’objet de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-149">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="1e0e7-150">RemovePrivateProperty : $false (garantit la demande de l’indicateur privé qui a été envoyé par l’organisateur de la réunion d’origine reste comme indiqué).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-150">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="1e0e7-151">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-151">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="1e0e7-152">AdditionalResponse : « Ceci est une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="1e0e7-152">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="1e0e7-153">(Texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="1e0e7-153">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="1e0e7-154">Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommé Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-154">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="1e0e7-155">Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-155">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="1e0e7-156">Affectation d’une licence Office 365</span><span class="sxs-lookup"><span data-stu-id="1e0e7-156">Assign an Office 365 license</span></span>

1. <span data-ttu-id="1e0e7-157">Se connecter à Active Directory Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-157">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="1e0e7-158">Pour obtenir des instructions, consultez la rubrique [Connect avec Azure Active Directory PowerShell pour le module de graphique](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="1e0e7-158">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

2. <span data-ttu-id="1e0e7-159">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-159">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="1e0e7-160">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-160">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="1e0e7-161">Vous pouvez utiliser Get-AzureADSubscribedSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-161">You can use Get-AzureADSubscribedSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   <span data-ttu-id="1e0e7-162">Ensuite, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-AzureADUserLicense.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-162">Next, you can add a license using the Set-AzureADUserLicense cmdlet.</span></span> <span data-ttu-id="1e0e7-163">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-163">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   <span data-ttu-id="1e0e7-164">Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e0e7-164">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="enable-the-device-account-with-skype-for-business"></a><span data-ttu-id="1e0e7-165">Activation du compte de l’appareil avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1e0e7-165">Enable the device account with Skype for Business</span></span>

1. <span data-ttu-id="1e0e7-166">Créez une session Windows PowerShell à distance à partir d’un PC comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-166">Create a remote Windows PowerShell session from a PC as follows:</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="1e0e7-167">Pour activer votre compte v2 de systèmes de salle Skype pour Skype pour Business Server, exécutez cette commande :</span><span class="sxs-lookup"><span data-stu-id="1e0e7-167">To enable your Skype Room Systems v2 account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   <span data-ttu-id="1e0e7-168">Si vous ne savez pas quelle valeur utiliser pour le paramètre RegistrarPool dans votre environnement, vous pouvez obtenir la valeur d’un Skype pour utilisateur Business Server à l’aide de cette commande existante</span><span class="sxs-lookup"><span data-stu-id="1e0e7-168">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a><span data-ttu-id="1e0e7-169">Affectation d’une licence Skype Entreprise à votre compte Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="1e0e7-169">Assign a Skype for Business license to your Skype Room Systems v2 account</span></span>

1. <span data-ttu-id="1e0e7-170">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration d’Office 365 et cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-170">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="1e0e7-171">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-171">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="1e0e7-172">Cliquez sur le compte de v2 Skype salle systèmes, puis cliquez sur l’icône du crayon pour modifier les informations de compte.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-172">Click the Skype Room Systems v2 account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="1e0e7-173">Cliquez sur **Licences**.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-173">Click **Licenses**.</span></span>
5. <span data-ttu-id="1e0e7-174">Dans la zone **Attribuer des licences**, sélectionnez Skype Entreprise (Plan 2) ou Skype Entreprise (Plan 3), en fonction de vos conditions de licence et Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-174">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="1e0e7-175">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser Enterprise Voice sur votre v2 Skype salle systèmes.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-175">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Skype Room Systems v2.</span></span>
6. <span data-ttu-id="1e0e7-176">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-176">Click **Save**.</span></span>

<span data-ttu-id="1e0e7-177">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter à ce compte.</span><span class="sxs-lookup"><span data-stu-id="1e0e7-177">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1e0e7-178">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e0e7-178">See also</span></span>

[<span data-ttu-id="1e0e7-179">Configurer des comptes pour les systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="1e0e7-179">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="1e0e7-180">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="1e0e7-180">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="1e0e7-181">Déploiement des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="1e0e7-181">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="1e0e7-182">Configuration d’une console pour les systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="1e0e7-182">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="1e0e7-183">Gestion des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="1e0e7-183">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)