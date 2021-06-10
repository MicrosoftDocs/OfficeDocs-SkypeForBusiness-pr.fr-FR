---
title: Déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365
ms.author: v-cichur
author: cichur
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
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur la manière de déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365, où Teams, Skype Entreprise et Exchange sont tous les deux en ligne.
ms.openlocfilehash: 64567cd9925a0a11d9e9b896c522a2c4bfe13f40
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739644"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="46894-103">Déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="46894-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="46894-104">Lisez cette rubrique pour plus d’informations sur la manière de déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365, où Microsoft Teams, Skype Entreprise et Exchange sont tous les deux en ligne.</span><span class="sxs-lookup"><span data-stu-id="46894-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="46894-105">La manière la plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de la Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46894-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="46894-106">Microsoft fournit [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer de nouveaux comptes d’utilisateurs, ou à valider les comptes de ressources existants que vous avez pour vous aider à les transformer en comptes d’utilisateurs Salles Microsoft Teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="46894-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="46894-107">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer des comptes que votre Salles Microsoft Teams appareil utilisera.</span><span class="sxs-lookup"><span data-stu-id="46894-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="46894-108">Conditions requises</span><span class="sxs-lookup"><span data-stu-id="46894-108">Requirements</span></span>

<span data-ttu-id="46894-109">Avant de déployer des Salles Microsoft Teams avec Microsoft 365 ou Office 365, assurez-vous que vous avez satisfait aux exigences.</span><span class="sxs-lookup"><span data-stu-id="46894-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="46894-110">Pour plus d’informations, [voir Salles Microsoft Teams requise.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="46894-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="46894-111">Pour activer Skype Entreprise, vous devez avoir les contrôles suivants :</span><span class="sxs-lookup"><span data-stu-id="46894-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="46894-112">Skype Entreprise En ligne (plan 2 ou Enterprise plan basé sur un plan supérieur) ou version Microsoft 365 ou Office 365 plan.</span><span class="sxs-lookup"><span data-stu-id="46894-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="46894-113">Le plan doit autoriser les fonctionnalités de conférences téléphoniques.</span><span class="sxs-lookup"><span data-stu-id="46894-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="46894-114">Si vous avez besoin de fonctionnalités de rendez-vous pour une réunion, vous avez besoin d’une licence d’audioconférence et Système téléphonique conférence.</span><span class="sxs-lookup"><span data-stu-id="46894-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="46894-115">Si vous avez besoin de fonctionnalités d’appel sortant pour une réunion, vous avez besoin d’une licence d’audioconférence.</span><span class="sxs-lookup"><span data-stu-id="46894-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="46894-116">Vos utilisateurs clients doivent avoir Exchange boîtes aux lettres.</span><span class="sxs-lookup"><span data-stu-id="46894-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="46894-117">Votre Salles Microsoft Teams nécessite au minimum une licence Skype Entreprise Online (plan 2), mais ne nécessite pas de licence Exchange Online licence utilisateur.</span><span class="sxs-lookup"><span data-stu-id="46894-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="46894-118">Pour [plus d Salles Microsoft Teams, consultez](rooms-licensing.md) la liste des licences de licences en cours.</span><span class="sxs-lookup"><span data-stu-id="46894-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="46894-119">Pour plus d’informations sur Skype Entreprise de services en ligne, voir la [description Skype Entreprise service en ligne.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="46894-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="46894-120">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="46894-120">Add a device account</span></span>

1. <span data-ttu-id="46894-121">Connecter à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46894-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="46894-122">Pour obtenir des instructions à [ce Connecter, voir Exchange Online PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="46894-122">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="46894-123">Dans Exchange Online PowerShell, créez une boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="46894-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="46894-124">Par défaut, les boîtes aux lettres de salle n’ayant pas de comptes associés, vous devez ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès de Skype Room Systems v2.</span><span class="sxs-lookup"><span data-stu-id="46894-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="46894-125">Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="46894-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="46894-126">Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="46894-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="46894-127">Nom : Rigel-01</span><span class="sxs-lookup"><span data-stu-id="46894-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="46894-128">Alias : Rigel1</span><span class="sxs-lookup"><span data-stu-id="46894-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="46894-129">Compte : Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="46894-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="46894-130">Mot de passe de compte : P@$$W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="46894-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="46894-131">Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="46894-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="46894-132">Cet exemple active le compte de la boîte aux lettres de salle existante qui possède la valeur d’alias Rigel2 et définit le mot de passe sur 9898P@$$W 0rd.</span><span class="sxs-lookup"><span data-stu-id="46894-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="46894-133">Notez que le compte sera Rigel2@contoso.onmicrosoft.com en raison de la valeur d’alias existante.</span><span class="sxs-lookup"><span data-stu-id="46894-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="46894-134">Pour plus d’informations sur la syntaxe et les paramètres, voir [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox.](/powershell/module/exchange/mailboxes/set-mailbox)</span><span class="sxs-lookup"><span data-stu-id="46894-134">For detailed syntax and parameter information, see [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="46894-135">Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="46894-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="46894-136">AutomateProcessing :accept automatique (les organisateurs de réunion reçoivent directement la décision de réservation de salle sans intervention humaine : libre = accepter ; occupé = refus.)</span><span class="sxs-lookup"><span data-stu-id="46894-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="46894-137">AddOrganizerToSubject: $false (L’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="46894-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="46894-138">DeleteComments : $false (conservez tout texte dans le corps du message des demandes de réunion entrantes).)</span><span class="sxs-lookup"><span data-stu-id="46894-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="46894-139">SuppressionSubject : $false (conserver l’objet des demandes de réunion entrantes).)</span><span class="sxs-lookup"><span data-stu-id="46894-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="46894-140">RemovePrivateProperty : $false (garantit que l’indicateur privé envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste tel que spécifié.)</span><span class="sxs-lookup"><span data-stu-id="46894-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="46894-141">AddAdditionalResponse: $true (Le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="46894-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="46894-142">Réponse supplémentaire : « Il s’agit d’Réunion Skype salle de réunion ! »</span><span class="sxs-lookup"><span data-stu-id="46894-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="46894-143">(Le texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="46894-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="46894-144">Cet exemple configure ces paramètres sur la boîte aux lettres de salle rigel-01.</span><span class="sxs-lookup"><span data-stu-id="46894-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="46894-145">Pour plus d’informations sur la syntaxe et les paramètres, [voir Set-CalendarProcessing.](/powershell/module/exchange/mailboxes/set-calendarprocessing)</span><span class="sxs-lookup"><span data-stu-id="46894-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="46894-146">Connecter sur MS Online PowerShell pour définir les paramètres Active Directory en exécutant `Connect-MsolService -Credential $cred` l’cmdlet PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46894-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="46894-147">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSOnline) 1.0.](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="46894-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="46894-148">[Azure Active Directory PowerShell 2.0 n’est](/powershell/azure/active-directory/overview?view=azureadps-2.0) pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="46894-148">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="46894-149">Si vous ne souhaitez pas que le mot de passe expire, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="46894-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="46894-150">Cet exemple définit le mot de passe du compte Rigel1@contoso.onmicrosoft.com à n’expirer jamais.</span><span class="sxs-lookup"><span data-stu-id="46894-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="46894-151">Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="46894-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > <span data-ttu-id="46894-152">Si le mot de passe n’est pas réglé sur Jamais expirer, le compte ne se connecte plus sur l’appareil une fois la période d’expiration atteinte.</span><span class="sxs-lookup"><span data-stu-id="46894-152">If the password is not set to Never Expire, the account will no longer sign in on the device when the account reaches the expiry period.</span></span> <span data-ttu-id="46894-153">Le mot de passe devra alors être modifié pour le compte et mis à jour localement sur l’appareil MTR.</span><span class="sxs-lookup"><span data-stu-id="46894-153">The password will then need to be changed for the account and also updated locally on the MTR device.</span></span>

6. <span data-ttu-id="46894-154">Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide, ou Exchange et Microsoft Teams ou Skype Entreprise ne fonctionne pas.</span><span class="sxs-lookup"><span data-stu-id="46894-154">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="46894-155">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="46894-155">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="46894-156">Vous pouvez utiliser `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="46894-156">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="46894-157">pour récupérer la liste des S SKUs disponibles pour votre organisation Microsoft 365 ou Office 365 organisation comme suit :</span><span class="sxs-lookup"><span data-stu-id="46894-157">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="46894-158">Ensuite, vous pouvez ajouter une licence à l’aide du `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="46894-158">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="46894-159">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="46894-159">cmdlet.</span></span> <span data-ttu-id="46894-160">Cet exemple ajoute la licence Salle de réunion compte :</span><span class="sxs-lookup"><span data-stu-id="46894-160">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="46894-161">Pour obtenir des instructions détaillées, voir Attribuer des licences à des comptes [d’utilisateurs Office 365 PowerShell.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="46894-161">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="46894-162">Vous pouvez également ajouter Système téléphonique fonctionnalités à ce compte, mais vous devez tout d’abord le configurer.</span><span class="sxs-lookup"><span data-stu-id="46894-162">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="46894-163">Pour [plus d’Système téléphonique,](../what-is-phone-system-in-office-365.md) voir Qu’est-Système téléphonique ?</span><span class="sxs-lookup"><span data-stu-id="46894-163">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="46894-164">Cet exemple ajoute le plan Appels nationaux et internationaux PSTN :</span><span class="sxs-lookup"><span data-stu-id="46894-164">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > <span data-ttu-id="46894-165">Si vous configurez l’salles Teams de participer uniquement en natif Microsoft Teams réunions, vous ne devez pas passer à l’étape suivante.</span><span class="sxs-lookup"><span data-stu-id="46894-165">If you are configuring Teams Rooms to only natively join Microsoft Teams meetings, you should not proceed with the following step.</span></span> <span data-ttu-id="46894-166">Ce qui suit n’est nécessaire que si vous allez également activer la prise en charge de Skype Entreprise local.</span><span class="sxs-lookup"><span data-stu-id="46894-166">The following is only required if you will also be enabling support for Skype for Business on-premises.</span></span>

7. <span data-ttu-id="46894-167">Pour activer le compte d’appareil Skype Entreprise local, assurez-vous que votre environnement répond aux exigences définies dans [Salles Microsoft Teams locaux.](requirements.md)</span><span class="sxs-lookup"><span data-stu-id="46894-167">To enable the device account with Skype for Business on-premises, be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="46894-168">Démarrez une [session Windows PowerShell distance](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) comme suit (n’oubliez pas d’installer Skype Entreprise [composants PowerShell en ligne)](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector):</span><span class="sxs-lookup"><span data-stu-id="46894-168">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   > [!NOTE]
   > <span data-ttu-id="46894-169">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="46894-169">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
   >
   > <span data-ttu-id="46894-170">Si vous utilisez la dernière version [Teams public PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="46894-170">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   <span data-ttu-id="46894-171">Obtenez les informations registrarPool à partir du nouveau compte d’utilisateur en cours de configuration, comme illustré dans l’exemple ci-après :</span><span class="sxs-lookup"><span data-stu-id="46894-171">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="46894-172">Ensuite, activez ensuite votre Salles Microsoft Teams de compte Skype Entreprise Server en exécutant l’cmdlet suivante :</span><span class="sxs-lookup"><span data-stu-id="46894-172">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="46894-173">Il est possible que les nouveaux comptes d’utilisateurs ne soient pas créés dans le même pool de bureaux d’enregistrement que les comptes d’utilisateurs existants du client.</span><span class="sxs-lookup"><span data-stu-id="46894-173">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="46894-174">La commande ci-dessus permet d’éviter les erreurs de configuration de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="46894-174">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="46894-175">Validate</span><span class="sxs-lookup"><span data-stu-id="46894-175">Validate</span></span>

<span data-ttu-id="46894-176">Pour validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise vous connectez au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="46894-176">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="46894-177">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="46894-177">See also</span></span>

[<span data-ttu-id="46894-178">Configurer des comptes pour Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46894-178">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="46894-179">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46894-179">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="46894-180">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46894-180">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="46894-181">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46894-181">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="46894-182">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46894-182">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="46894-183">Salles Microsoft Teams Gestion des licences</span><span class="sxs-lookup"><span data-stu-id="46894-183">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
