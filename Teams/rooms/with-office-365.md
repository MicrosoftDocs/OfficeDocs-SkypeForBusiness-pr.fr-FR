---
title: Déploiement de salles Microsoft teams avec Microsoft 365 ou Office 365
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
description: Consultez cette rubrique pour plus d’informations sur le déploiement de salles de Microsoft teams avec Microsoft 365 ou Office 365, où teams ou Skype entreprise et Exchange sont tous deux en ligne.
ms.openlocfilehash: 4b5bd3967d3a1fcc8859cf4da8b039418819cb4e
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616888"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a><span data-ttu-id="6cfc7-103">Déploiement de salles Microsoft teams avec Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="6cfc7-103">Deploy Microsoft Teams Rooms with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="6cfc7-104">Consultez cette rubrique pour plus d’informations sur le déploiement de salles de Microsoft teams avec Microsoft 365 ou Office 365, où Microsoft teams ou Skype entreprise et Exchange sont tous deux en ligne.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, where Microsoft Teams or Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="6cfc7-105">Le moyen le plus simple de configurer des comptes d’utilisateurs consiste à les configurer à l’aide de Windows PowerShell distant.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="6cfc7-106">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script permettant de créer de nouveaux comptes d’utilisateurs, ou de valider des comptes de ressources existants dont vous avez besoin afin de vous aider à les convertir en comptes d’utilisateurs de salles Microsoft teams compatibles.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="6cfc7-107">Si vous le souhaitez, vous pouvez suivre les étapes ci-dessous afin de configurer des comptes que votre appareil de salle Microsoft teams utilisera.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-107">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="6cfc7-108">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="6cfc7-108">Requirements</span></span>

<span data-ttu-id="6cfc7-109">Avant de déployer des salles Microsoft teams avec Microsoft 365 ou Office 365, assurez-vous que vous remplissez les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-109">Before you deploy Microsoft Teams Rooms with Microsoft 365 or Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="6cfc7-110">Pour plus d’informations, voir la [Configuration requise pour Microsoft teams salles](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-110">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>

<span data-ttu-id="6cfc7-111">Pour activer Skype entreprise, vous devez disposer des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="6cfc7-112">Skype entreprise Online (plan 2 ou plan d’entreprise) ou version ultérieure dans votre plan Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Microsoft 365 or Office 365 plan.</span></span> <span data-ttu-id="6cfc7-113">Le plan doit permettre l’accès aux fonctionnalités de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="6cfc7-114">Si vous avez besoin de fonctionnalités de connexion à une réunion, vous avez besoin d’une licence de système téléphonique et de téléconférence.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-114">If you need dial-in capabilities from a meeting, you will need an Audio Conferencing and Phone System license.</span></span>  <span data-ttu-id="6cfc7-115">Si vous avez besoin de fonctionnalités de numérotation d’une réunion, vous aurez besoin d’une licence de conférence audio.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-115">If you need dial-out capabilities from a meeting, you will need an Audio Conferencing license.</span></span>

- <span data-ttu-id="6cfc7-116">Les utilisateurs de votre client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="6cfc7-117">Votre compte Microsoft teams Room nécessite au moins une licence Skype entreprise Online (plan 2), mais il ne nécessite pas de licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-117">Your Microsoft Teams Rooms account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="6cfc7-118">Pour plus d’informations, consultez la rubrique [licences Microsoft teams](rooms-licensing.md) .</span><span class="sxs-lookup"><span data-stu-id="6cfc7-118">See [Microsoft Teams Rooms licenses](rooms-licensing.md) for details.</span></span>

<span data-ttu-id="6cfc7-119">Pour plus d’informations sur les offres Skype entreprise Online, reportez-vous à la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="6cfc7-120">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="6cfc7-120">Add a device account</span></span>

1. <span data-ttu-id="6cfc7-121">Connectez-vous à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="6cfc7-122">Pour obtenir des instructions, voir [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="6cfc7-123">Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="6cfc7-124">Par défaut, les boîtes aux lettres de salle n’ont pas de compte associé, vous devez donc ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier auprès des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="6cfc7-125">Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="6cfc7-126">Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="6cfc7-127">Nom : Rigel-01</span><span class="sxs-lookup"><span data-stu-id="6cfc7-127">Name: Rigel-01</span></span>

     - <span data-ttu-id="6cfc7-128">Alias : Rigel1</span><span class="sxs-lookup"><span data-stu-id="6cfc7-128">Alias: Rigel1</span></span>

     - <span data-ttu-id="6cfc7-129">Compte : Rigel1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="6cfc7-129">Account: Rigel1@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="6cfc7-130">Mot de passe du compte : P@ $ $W 0rd5959</span><span class="sxs-lookup"><span data-stu-id="6cfc7-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="6cfc7-131">Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="6cfc7-132">Dans cet exemple, le compte de la boîte aux lettres de salle existante possède la valeur alias Rigel2 et le mot de passe est défini sur 9898P@ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-132">This example enables the account for the existing room mailbox that has the alias value Rigel2, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="6cfc7-133">Notez que le compte sera Rigel2@contoso.onmicrosoft.com en raison de la valeur de l’alias existant.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-133">Note that the account will be Rigel2@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="6cfc7-134">Pour plus d’informations sur les paramètres de syntaxe et de paramètre, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>

3. <span data-ttu-id="6cfc7-135">Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="6cfc7-136">AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="6cfc7-137">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="6cfc7-138">DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6cfc7-139">DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="6cfc7-140">RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="6cfc7-141">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="6cfc7-142">AdditionalResponse : « il s’agit d’une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="6cfc7-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="6cfc7-143">(Le texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="6cfc7-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="6cfc7-144">Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-144">This example configures these settings on the room mailbox named Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="6cfc7-145">Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="6cfc7-146">Connectez-vous à MS Online PowerShell pour créer des paramètres Active Directory en exécutant l’applet de contrôle `Connect-MsolService -Credential $cred` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-146">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` PowerShell cmdlet.</span></span> <span data-ttu-id="6cfc7-147">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-147">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="6cfc7-148">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-148">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

5. <span data-ttu-id="6cfc7-149">Si vous ne souhaitez pas que le mot de passe expire, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-149">If you do not want the password to expire, use the following syntax:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   <span data-ttu-id="6cfc7-150">Cet exemple définit le mot de passe du compte Rigel1@contoso.onmicrosoft.com pour qu’il n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-150">This example sets the password for the account Rigel1@contoso.onmicrosoft.com to never expire.</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   <span data-ttu-id="6cfc7-151">Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-151">You can also set a phone number for the account by running the following command:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. <span data-ttu-id="6cfc7-152">Le compte d’appareil doit avoir une licence Microsoft 365 ou Office 365 valide ou Exchange et Microsoft teams ou Skype entreprise ne fonctionnera pas.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-152">The device account needs to have a valid Microsoft 365 or Office 365 license, or Exchange and Microsoft Teams or Skype for Business will not work.</span></span> <span data-ttu-id="6cfc7-153">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-153">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="6cfc7-154">Vous pouvez utiliser `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="6cfc7-154">You can use `Get-MsolAccountSku`</span></span> <!-- Get-AzureADSubscribedSku --> <span data-ttu-id="6cfc7-155">pour récupérer la liste des références SKU disponibles pour votre organisation Microsoft 365 ou Office 365, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-155">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization as follows:</span></span>

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   <span data-ttu-id="6cfc7-156">Vous pouvez ensuite ajouter une licence à l’aide du `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="6cfc7-156">Next, you can add a license using the `Set-MsolUserLicense`</span></span> <!--Set-AzureADUserLicense --> <span data-ttu-id="6cfc7-157">applet.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-157">cmdlet.</span></span> <span data-ttu-id="6cfc7-158">Dans cet exemple, la licence de salle de réunion est ajoutée au compte :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-158">This example adds the Meeting Room license to the account:</span></span>

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   <span data-ttu-id="6cfc7-159">Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-159">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

   <span data-ttu-id="6cfc7-160">Vous pouvez également ajouter des fonctionnalités de système téléphonique à ce compte, mais vous devez d’abord le configurer.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-160">You can also add Phone System capabilities to this account, but you have to configure it first.</span></span> <span data-ttu-id="6cfc7-161">Pour en savoir plus, voir [qu’est-ce que le système téléphonique ?](../what-is-phone-system-in-office-365.md) .</span><span class="sxs-lookup"><span data-stu-id="6cfc7-161">See [What is Phone System?](../what-is-phone-system-in-office-365.md) for more details.</span></span> <span data-ttu-id="6cfc7-162">Cet exemple ajoute le forfait d’appels RTC nationaux et internationaux :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-162">This example adds the PSTN Domestic and International Calling Plan:</span></span>

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. <span data-ttu-id="6cfc7-163">Ensuite, vous devez activer le compte de l’appareil avec Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-163">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="6cfc7-164">Assurez-vous que votre environnement répond à la configuration requise définie dans les [exigences de Microsoft teams salles](requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cfc7-164">Be sure your environment meets the requirements defined in [Microsoft Teams Rooms requirements](requirements.md).</span></span>

   <span data-ttu-id="6cfc7-165">Démarrez une [session Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) distante comme suit (veillez à [installer les composants PowerShell de Skype entreprise Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-165">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

> [!NOTE]
> <span data-ttu-id="6cfc7-166">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-166">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="6cfc7-167">Si vous utilisez la dernière [version publique de teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-167">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess = New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="6cfc7-168">Obtenez les informations RegistrarPool à partir du nouveau compte d’utilisateur configuré, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-168">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   <span data-ttu-id="6cfc7-169">Activez ensuite votre compte Microsoft teams pour Skype entreprise Server en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="6cfc7-169">Next, enable your Microsoft Teams Rooms account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > <span data-ttu-id="6cfc7-170">Les nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de bureau d’enregistrement que les comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-170">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="6cfc7-171">Dans le cas présent, la commande ci-dessus empêche les erreurs dans la configuration du compte.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-171">The command above will prevent errors in account setup due to this situation.</span></span>

## <a name="validate"></a><span data-ttu-id="6cfc7-172">Invalidé</span><span class="sxs-lookup"><span data-stu-id="6cfc7-172">Validate</span></span>

<span data-ttu-id="6cfc7-173">Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="6cfc7-173">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cfc7-174">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6cfc7-174">See also</span></span>

[<span data-ttu-id="6cfc7-175">Configurer des comptes pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="6cfc7-176">Planifier les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)

[<span data-ttu-id="6cfc7-177">Déployer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)

[<span data-ttu-id="6cfc7-178">Configurer une console des salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="6cfc7-179">Gérer les Salles Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)

[<span data-ttu-id="6cfc7-180">Gestion des licences Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="6cfc7-180">Microsoft Teams Rooms Licensing</span></span>](rooms-licensing.md)
