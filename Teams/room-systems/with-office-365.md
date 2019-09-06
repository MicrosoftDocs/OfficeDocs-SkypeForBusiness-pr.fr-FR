---
title: Déployer des Salles Microsoft Teams avec Office 365 ProPlus
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles Microsoft teams avec Office 365.
ms.openlocfilehash: 8e41b06b8f5cf76a45fd09f4b8820fb2fcaaa6d5
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775029"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a><span data-ttu-id="36c13-103">Déployer des Salles Microsoft Teams avec Office 365 ProPlus</span><span class="sxs-lookup"><span data-stu-id="36c13-103">Deploy Microsoft Teams Rooms with Office 365</span></span>

<span data-ttu-id="36c13-104">Pour plus d’informations sur le déploiement de salles de Microsoft teams avec Office 365, vous pouvez consulter la rubrique Microsoft teams ou Skype entreprise et Exchange en ligne.</span><span class="sxs-lookup"><span data-stu-id="36c13-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="36c13-105">Le moyen le plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de Windows PowerShell distant.</span><span class="sxs-lookup"><span data-stu-id="36c13-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="36c13-106">Microsoft fournit [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous permet de créer de nouveaux comptes d’utilisateur, ou de valider des comptes de ressources existants dont vous disposez pour vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="36c13-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="36c13-107">Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.</span><span class="sxs-lookup"><span data-stu-id="36c13-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="36c13-108">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="36c13-108">Requirements</span></span>

<span data-ttu-id="36c13-109">Avant de déployer des salles Microsoft teams avec Office 365, assurez-vous que vous remplissez les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="36c13-109">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="36c13-110">Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c13-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="36c13-111">Pour activer Skype entreprise, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="36c13-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="36c13-112">Skype entreprise Online (plan 2 ou plan d’entreprise) ou une version ultérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="36c13-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="36c13-113">Le plan doit permettre l’accès aux fonctionnalités de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="36c13-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="36c13-114">Si vous avez besoin de fonctionnalités de connexion à une réunion, vous avez besoin d’une licence de système téléphonique et de téléconférence.</span><span class="sxs-lookup"><span data-stu-id="36c13-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="36c13-115">Si vous avez besoin de fonctionnalités de numérotation d’une réunion, vous aurez besoin d’un forfait d’appels nationaux ou internationaux.</span><span class="sxs-lookup"><span data-stu-id="36c13-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="36c13-116">Les utilisateurs de votre client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="36c13-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="36c13-117">Votre compte Microsoft teams Room nécessite au moins une licence Skype entreprise Online (plan 2), mais il ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="36c13-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="36c13-118">Pour plus d’informations, consultez la rubrique [licences Microsoft teams](skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="36c13-118">See [Microsoft Teams Rooms licenses](skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="36c13-119">Pour plus d’informations sur les offres Skype entreprise Online, reportez-vous à la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="36c13-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="36c13-120">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="36c13-120">Add a device account</span></span>

1. <span data-ttu-id="36c13-121">Connectez-vous à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36c13-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="36c13-122">Pour obtenir des instructions, voir [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="36c13-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="36c13-123">Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="36c13-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="36c13-124">Par défaut, les boîtes aux lettres de salle n’ont pas de compte associé, vous devez donc ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="36c13-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="36c13-125">Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="36c13-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="36c13-126">Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="36c13-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="36c13-127">Nom : projet-Rigel-01</span><span class="sxs-lookup"><span data-stu-id="36c13-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="36c13-128">Alias : ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="36c13-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="36c13-129">Compte : ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="36c13-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="36c13-130">Mot de passe du compte : P @ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="36c13-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="36c13-131">Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="36c13-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="36c13-132">Dans cet exemple, le compte de la boîte aux lettres de salle existante possède la valeur alias ProjectRigel02 et définit le mot de passe sur 9898P @ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="36c13-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="36c13-133">Notez que le compte sera ProjectRigel02@contoso.onmicrosoft.com en raison de la valeur de l’alias existant.</span><span class="sxs-lookup"><span data-stu-id="36c13-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="36c13-134">Pour plus d’informations sur les paramètres de syntaxe et de paramètre, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="36c13-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="36c13-135">Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="36c13-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="36c13-136">AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="36c13-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="36c13-137">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="36c13-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="36c13-138">DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="36c13-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="36c13-139">DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="36c13-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="36c13-140">RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)</span><span class="sxs-lookup"><span data-stu-id="36c13-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="36c13-141">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="36c13-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="36c13-142">AdditionalResponse : « il s’agit d’une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="36c13-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="36c13-143">(Le texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="36c13-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="36c13-144">Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="36c13-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="36c13-145">Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="36c13-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="36c13-146">Connectez-vous à MS Online PowerShell pour créer des paramètres Active Directory `Connect-MsolService -Credential $cred` en exécutant l’applet de contrôle PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36c13-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="36c13-147">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="36c13-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="36c13-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="36c13-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="36c13-149">Si vous ne souhaitez pas que le mot de passe expire, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="36c13-149">If you do not want the password to expire, use the following syntax:</span></span>

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="36c13-150">Cet exemple définit le mot de passe du compte ProjectRigel01@contoso.onmicrosoft.com pour qu’il n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="36c13-150">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="36c13-151">Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="36c13-151">You can also set a phone number for the account by running the following command:</span></span>

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="36c13-152">Le compte d’appareil doit avoir une licence Office 365 valide ou Exchange et Microsoft teams ou Skype entreprise ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="36c13-152">The device account needs to have a valid Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="36c13-153">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="36c13-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="36c13-154">Vous pouvez utiliser`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="36c13-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="36c13-155">pour récupérer la liste des références (SKU) disponibles pour votre client 365 Office, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="36c13-155">to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="36c13-156">Vous pouvez ensuite ajouter une licence à l’aide du`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="36c13-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="36c13-157">applet.</span><span class="sxs-lookup"><span data-stu-id="36c13-157">cmdlet.</span></span> <span data-ttu-id="36c13-158">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="36c13-158">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

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

   <span data-ttu-id="36c13-159">Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="36c13-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="36c13-160">Ensuite, vous devez activer le compte de l’appareil avec Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="36c13-160">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="36c13-161">Assurez-vous que votre environnement répond à la configuration requise définie dans les [exigences de Microsoft teams salles](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c13-161">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="36c13-162">Démarrez une [session Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) distante comme suit (veillez à [installer les composants PowerShell de Skype entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) :</span><span class="sxs-lookup"><span data-stu-id="36c13-162">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="36c13-163">Activez ensuite votre compte Microsoft teams pour Skype entreprise Server en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="36c13-163">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="36c13-164">Obtenez les informations RegistrarPool à partir du nouveau compte d’utilisateur configuré, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="36c13-164">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="36c13-165">Les nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de bureau d’enregistrement que les comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="36c13-165">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="36c13-166">Dans le cas présent, la commande ci-dessus empêche les erreurs dans la configuration du compte.</span><span class="sxs-lookup"><span data-stu-id="36c13-166">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="36c13-167">Après avoir suivi les étapes ci-dessous pour activer votre compte Microsoft teams dans Microsoft teams ou Skype entreprise Online, vous devez attribuer une licence à l’appareil Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36c13-167">After you've completed the preceding steps to enable your Microsoft Teams Rooms account in Microsoft Teams or Skype for Business Online, you need to assign a license to Microsoft Teams Rooms device.</span></span> <span data-ttu-id="36c13-168">À l’aide du portail d’administration Office 365, attribuez une licence Skype entreprise Online (plan 2) ou une licence Skype entreprise Online (plan 3) à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="36c13-168">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="36c13-169">Affectation d’une licence à votre compte</span><span class="sxs-lookup"><span data-stu-id="36c13-169">Assign a license to your account</span></span>

1. <span data-ttu-id="36c13-170">Connectez-vous en tant qu’administrateur client, ouvrez le portail d’administration Office 365, puis cliquez sur l’application Administration.</span><span class="sxs-lookup"><span data-stu-id="36c13-170">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="36c13-171">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="36c13-171">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="36c13-172">Sélectionnez le compte Microsoft teams Room, puis cliquez ou appuyez sur l’icône de stylet, c’est-à-dire modifier.</span><span class="sxs-lookup"><span data-stu-id="36c13-172">Select the Microsoft Teams Rooms account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="36c13-173">Cliquez sur l’option **Licences**.</span><span class="sxs-lookup"><span data-stu-id="36c13-173">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="36c13-174">Dans la section **attribuer des licences** , vous devez sélectionner Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3), en fonction de votre licence et de ce que vous avez choisi pour l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="36c13-174">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="36c13-175">Vous devez utiliser une licence de plan 3 Si vous souhaitez utiliser PBX Cloud sur les salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36c13-175">You'll have to use a Plan 3 license if you want to use Cloud PBX on Microsoft Teams Rooms.</span></span> <span data-ttu-id="36c13-176">Vous aurez au moins besoin de CloudPBX pour la connectivité vocale.</span><span class="sxs-lookup"><span data-stu-id="36c13-176">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="36c13-177">Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC.</span><span class="sxs-lookup"><span data-stu-id="36c13-177">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="36c13-178">Pour plus d’informations, consultez la rubrique [licences Microsoft teams](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)</span><span class="sxs-lookup"><span data-stu-id="36c13-178">See [Microsoft Teams Rooms licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="36c13-179">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="36c13-179">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="36c13-180">Exemple : configuration de compte salle dans Exchange Online et Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="36c13-180">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="36c13-181">Commandes PowerShell Exchange Online :</span><span class="sxs-lookup"><span data-stu-id="36c13-181">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="36c13-182">Commandes PowerShell d’Azure Active Directory :</span><span class="sxs-lookup"><span data-stu-id="36c13-182">Azure Active Directory PowerShell commands:</span></span>

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

<span data-ttu-id="36c13-183">Commande PowerShell Skype entreprise :</span><span class="sxs-lookup"><span data-stu-id="36c13-183">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="36c13-184">Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="36c13-184">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="36c13-185">Par ailleurs, vous devez utiliser l’interface administrateur pour attribuer un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="36c13-185">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="36c13-186">Invalidé</span><span class="sxs-lookup"><span data-stu-id="36c13-186">Validate</span></span>

<span data-ttu-id="36c13-187">Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="36c13-187">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="36c13-188">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="36c13-188">See also</span></span>

[<span data-ttu-id="36c13-189">Configurer des comptes pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="36c13-189">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="36c13-190">Plan pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="36c13-190">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="36c13-191">Déploiement de salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="36c13-191">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="36c13-192">Configurer une console de salle Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="36c13-192">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="36c13-193">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="36c13-193">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)

[<span data-ttu-id="36c13-194">Gestion des licences Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="36c13-194">Microsoft Teams Rooms Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
