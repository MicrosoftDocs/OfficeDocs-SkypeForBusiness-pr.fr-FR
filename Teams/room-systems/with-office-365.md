---
title: Déployer les équipes Microsoft salles avec Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer Microsoft équipes salles avec Office 365.
ms.openlocfilehash: 462f5a6727a3c67e221b0d7ac019849ed3eb6f52
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362775"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="9c788-103">Déployer les équipes Microsoft salles avec Office 365</span><span class="sxs-lookup"><span data-stu-id="9c788-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="9c788-104">Lisez cette rubrique pour plus d’informations sur la façon de déployer Microsoft équipes salles avec Office 365, où Microsoft Teams ou Skype pour les entreprises et Exchange sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="9c788-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="9c788-105">Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="9c788-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="9c788-106">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs locaux des équipes Microsoft compatibles.</span><span class="sxs-lookup"><span data-stu-id="9c788-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="9c788-107">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre périphérique Microsoft équipes salles.</span><span class="sxs-lookup"><span data-stu-id="9c788-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c788-108">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9c788-108">Requirements</span></span>

<span data-ttu-id="9c788-109">Avant de déployer Microsoft équipes salles avec Office 365, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="9c788-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="9c788-110">Pour plus d’informations, consultez [Configuration requise de salles d’équipes Microsoft](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c788-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="9c788-111">Pour activer Skype pour les entreprises, vous devez disposer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9c788-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="9c788-112">Skype pour Business Online (Plan 2 ou un plan d’entreprise) ou supérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c788-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="9c788-113">Le plan doit autoriser les fonctions de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9c788-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="9c788-114">Si vous avez besoin des fonctionnalités de rendez-vous à partir d’une réunion, vous devez une conférence audio et la licence du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="9c788-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="9c788-115">Si vous avez besoin des fonctionnalités d’appel sortant à partir d’une réunion, vous devez a internes ou nationales et internationales appelant Plan.</span><span class="sxs-lookup"><span data-stu-id="9c788-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="9c788-116">Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="9c788-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="9c788-117">Votre compte Microsoft équipes salles requiert au minimum un Skype pour la licence entreprise Online (Plan 2), mais il ne nécessite pas une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9c788-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="9c788-118">Pour plus d’informations, voir [Gestion des licences salles d’équipes Microsoft](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="9c788-118">See [Microsoft Teams Rooms Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="9c788-119">Pour plus d’informations sur Skype pour Business Online Plans, voir le [Skype pour Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="9c788-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="9c788-120">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="9c788-120">Add a device account</span></span>

1. <span data-ttu-id="9c788-121">Connexion à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c788-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="9c788-122">Pour plus d’informations, voir [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="9c788-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="9c788-123">Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifier une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="9c788-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="9c788-124">Par défaut, les boîtes aux lettres de salle ne disposent pas des comptes associés, afin que vous aurez besoin d’ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier avec des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="9c788-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="9c788-125">Pour créer une nouvelle boîte aux lettres de salle, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9c788-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9c788-126">Cet exemple crée une nouvelle boîte aux lettres de salle avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="9c788-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="9c788-127">Nom : Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="9c788-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="9c788-128">Alias : ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="9c788-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="9c788-129">Compte : ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9c788-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="9c788-130">Mot de passe de compte : P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="9c788-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="9c788-131">Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9c788-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9c788-132">Cet exemple active le compte pour la boîte aux lettres de salle existante qui a la valeur d’alias ProjectRigel02 et définit le mot de passe 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="9c788-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="9c788-133">Notez que le compte sera ProjectRigel02@contoso.onmicrosoft.com en raison de la valeur d’alias existante.</span><span class="sxs-lookup"><span data-stu-id="9c788-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="9c788-134">Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9c788-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="9c788-135">Dans Exchange Online PowerShell, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="9c788-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="9c788-136">AutomateProcessing : AutoAccept (organisateurs de réunion recevoir la décision de réservation de salles directement sans intervention humaine : libre = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="9c788-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="9c788-137">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion).</span><span class="sxs-lookup"><span data-stu-id="9c788-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="9c788-138">DeleteComments : $false (conserver le texte dans le corps du message de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="9c788-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9c788-139">DeleteSubject : $false (conserver l’objet de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="9c788-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9c788-140">RemovePrivateProperty : $false (garantit la demande de l’indicateur privé qui a été envoyé par l’organisateur de la réunion d’origine reste comme indiqué).</span><span class="sxs-lookup"><span data-stu-id="9c788-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="9c788-141">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion).</span><span class="sxs-lookup"><span data-stu-id="9c788-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="9c788-142">AdditionalResponse : « Ceci est une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="9c788-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="9c788-143">(Texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="9c788-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="9c788-144">Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommé Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="9c788-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="9c788-145">Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="9c788-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="9c788-146">Se connecter à MS Online PowerShell pour rendre les paramètres Active Directory en exécutant la `Connect-MsolService -Credential $cred` applet de commande powershell.</span><span class="sxs-lookup"><span data-stu-id="9c788-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="9c788-147">Pour plus d’informations sur Active Directory, voir [Azure Active Directory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="9c788-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. <span data-ttu-id="9c788-148">Si vous ne souhaitez pas que le mot de passe à expiration, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9c788-148">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="9c788-149">Cet exemple montre comment définir le mot de passe pour le compte ProjectRigel01@contoso.onmicrosoft.com n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="9c788-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="9c788-150">Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9c788-150">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="9c788-151">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Microsoft Teams ou Skype pour les entreprises ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="9c788-151">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="9c788-152">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="9c788-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="9c788-153">Vous pouvez utiliser`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="9c788-153">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="9c788-154">pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :</span><span class="sxs-lookup"><span data-stu-id="9c788-154">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="9c788-155">Ensuite, vous pouvez ajouter une licence à l’aide du`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="9c788-155">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="9c788-156">applet de commande.</span><span class="sxs-lookup"><span data-stu-id="9c788-156">cmdlet.</span></span> <span data-ttu-id="9c788-157">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="9c788-157">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   <span data-ttu-id="9c788-158">Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9c788-158">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="9c788-159">Ensuite, vous devez activer le compte de l’appareil avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="9c788-159">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="9c788-160">Assurez-vous que votre environnement répond aux exigences définies dans les [salles d’équipes Microsoft requise](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c788-160">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="9c788-161">Démarrer une [session Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) à distance comme suit (veillez à [installer Skype pour les composants Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) :</span><span class="sxs-lookup"><span data-stu-id="9c788-161">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="9c788-162">Ensuite, activer votre compte Microsoft équipes salles pour Skype pour Business Server en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9c788-162">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="9c788-163">Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="9c788-163">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="9c788-164">Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="9c788-164">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="9c788-165">La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="9c788-165">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="9c788-166">Une fois que vous avez terminé les étapes précédentes pour activer votre compte Microsoft équipes salles dans Microsoft Teams ou Skype pour Business Online, vous devez attribuer une licence à un périphérique de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9c788-166">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="9c788-167">À l’aide du portail d’administration d’Office 365, assignez un soit Skype Business Online (Plan 2) ou une Skype licence entreprise Online (Plan 3) à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9c788-167">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="9c788-168">Affectation d’une licence à votre compte</span><span class="sxs-lookup"><span data-stu-id="9c788-168">Assign a license to your account</span></span>

1. <span data-ttu-id="9c788-169">Ouverture de session en tant qu’un administrateur client, ouvrez le portail d’administration d’Office 365, puis cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="9c788-169">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="9c788-170">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="9c788-170">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="9c788-171">Sélectionnez le compte Microsoft équipes locaux, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.</span><span class="sxs-lookup"><span data-stu-id="9c788-171">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="9c788-172">Cliquez sur l’option **Licences**.</span><span class="sxs-lookup"><span data-stu-id="9c788-172">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="9c788-173">Dans la section **attribution de licences** , vous devez sélectionner Skype pour Business Online (Plan 2) ou Skype pour Business Online (Plan 3), en fonction de vos licences et vous avez décidé en termes de devoir Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9c788-173">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="9c788-174">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser dans le nuage PBX sur salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9c788-174">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="9c788-175">Vous aurez au moins besoin de CloudPBX pour la connectivité vocale.</span><span class="sxs-lookup"><span data-stu-id="9c788-175">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="9c788-176">Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC.</span><span class="sxs-lookup"><span data-stu-id="9c788-176">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="9c788-177">Pour plus d’informations, voir [licences salles d’équipes Microsoft](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .</span><span class="sxs-lookup"><span data-stu-id="9c788-177">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="9c788-178">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="9c788-178">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="9c788-179">Exemple : Compte salle du programme d’installation dans Exchange Online et Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="9c788-179">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="9c788-180">Commandes Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9c788-180">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="9c788-181">Commandes Azure Active Directory PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9c788-181">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

<span data-ttu-id="9c788-182">Skype pour commande PowerShell d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="9c788-182">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="9c788-183">Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="9c788-183">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="9c788-184">En outre, vous devez utiliser l’interface d’administration pour affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="9c788-184">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="9c788-185">Valider</span><span class="sxs-lookup"><span data-stu-id="9c788-185">Validate</span></span>

<span data-ttu-id="9c788-186">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="9c788-186">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c788-187">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c788-187">See also</span></span>

[<span data-ttu-id="9c788-188">Configurer des comptes pour les salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c788-188">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="9c788-189">Planifier des équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="9c788-189">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="9c788-190">Déployer les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="9c788-190">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="9c788-191">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="9c788-191">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="9c788-192">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="9c788-192">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="9c788-193">Salles de gestion des licences des équipes de Microsoft</span><span class="sxs-lookup"><span data-stu-id="9c788-193">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
