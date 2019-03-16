---
title: Déploiement de Skype Room Systems v2 avec Office 365
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 avec Office 365.
ms.openlocfilehash: a931ec6cb55e654612c451f15d4a4895f61ba990
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645386"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a><span data-ttu-id="9c7f3-103">Déploiement de Skype Room Systems v2 avec Office 365 </span><span class="sxs-lookup"><span data-stu-id="9c7f3-103">Deploy Skype Room Systems v2 with Office 365</span></span>

<span data-ttu-id="9c7f3-104">Lisez cette rubrique pour plus d’informations sur le déploiement de systèmes de salle Skype v2 avec Office 365, où Skype pour les entreprises et Exchange sont en ligne.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-104">Read this topic for information on how to deploy Skype Room Systems v2 with Office 365, where Skype for Business and Exchange are both online.</span></span>

<span data-ttu-id="9c7f3-105">Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-105">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="9c7f3-106">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-106">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="9c7f3-107">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-107">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="9c7f3-108">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="9c7f3-108">Requirements</span></span>

<span data-ttu-id="9c7f3-109">Avant de déployer des systèmes de salle Skype v2 avec Office 365, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-109">Before you deploy Skype Room Systems v2 with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="9c7f3-110">Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-110">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

<span data-ttu-id="9c7f3-111">Pour activer Skype pour les entreprises, vous devez disposer les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-111">To enable Skype for Business, you must have the following:</span></span>

- <span data-ttu-id="9c7f3-112">Skype pour Business Online (Plan 2 ou un plan d’entreprise) ou supérieure dans votre plan Office 365.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-112">Skype for Business Online (Plan 2, or an Enterprise-based plan) or higher in your Office 365 plan.</span></span> <span data-ttu-id="9c7f3-113">Le plan doit autoriser les fonctions de conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-113">The plan needs to allow dial-in conferencing capabilities.</span></span>

- <span data-ttu-id="9c7f3-114">Si vous avez besoin des fonctionnalités de rendez-vous à partir d’une réunion, vous devez une conférence audio et la licence du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-114">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="9c7f3-115">Si vous avez besoin des fonctionnalités d’appel sortant à partir d’une réunion, vous devez a internes ou nationales et internationales appelant Plan.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-115">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span>

- <span data-ttu-id="9c7f3-116">Les utilisateurs de client doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-116">Your tenant users must have Exchange mailboxes.</span></span>

- <span data-ttu-id="9c7f3-117">Votre compte v2 de systèmes de salle Skype requiert au minimum un Skype pour licence entreprise Online (Plan 2), mais il ne nécessite pas une licence Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-117">Your Skype Room Systems v2 account does require at a minimum a Skype for Business Online (Plan 2) license, but it does not require an Exchange Online license.</span></span> <span data-ttu-id="9c7f3-118">Pour plus d’informations, voir [systèmes de salle Skype v2 licences](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) .</span><span class="sxs-lookup"><span data-stu-id="9c7f3-118">See [Skype Room Systems v2 Licensing](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md) for details.</span></span>

<span data-ttu-id="9c7f3-119">Pour plus d’informations sur Skype pour Business Online Plans, voir le [Skype pour Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-119">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>

### <a name="add-a-device-account"></a><span data-ttu-id="9c7f3-120">Ajout d’un compte d’appareil</span><span class="sxs-lookup"><span data-stu-id="9c7f3-120">Add a device account</span></span>

https://docs.microsoft.com/en-us/powershell/module/msonline/?view=azureadps-1.0

https://docs.microsoft.com/en-us/powershell/module/Azuread/?view=azureadps-2.0 


1. <span data-ttu-id="9c7f3-121">Connexion à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-121">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="9c7f3-122">Pour plus d’informations, voir [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-122">For instructions, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

2. <span data-ttu-id="9c7f3-123">Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifier une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-123">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span> <span data-ttu-id="9c7f3-124">Par défaut, les boîtes aux lettres de salle ne disposent pas des comptes associés, afin que vous aurez besoin d’ajouter un compte lorsque vous créez ou modifiez une boîte aux lettres de salle qui lui permet de s’authentifier avec des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-124">By default, room mailboxes don't have associated accounts, so you'll need to add an account when you create or modify a room mailbox that allows it to authenticate with Skype Room Systems v2.</span></span>

   - <span data-ttu-id="9c7f3-125">Pour créer une nouvelle boîte aux lettres de salle, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-125">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9c7f3-126">Cet exemple crée une nouvelle boîte aux lettres de salle avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-126">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="9c7f3-127">Nom : Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-127">Name: Project-Rigel-01</span></span>

     - <span data-ttu-id="9c7f3-128">Alias : ProjectRigel01</span><span class="sxs-lookup"><span data-stu-id="9c7f3-128">Alias: ProjectRigel01</span></span>

     - <span data-ttu-id="9c7f3-129">Compte : ProjectRigel01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="9c7f3-129">Account: ProjectRigel01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="9c7f3-130">Mot de passe de compte : P@$$W0rd5959</span><span class="sxs-lookup"><span data-stu-id="9c7f3-130">Account password: P@$$W0rd5959</span></span>

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - <span data-ttu-id="9c7f3-131">Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-131">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="9c7f3-132">Cet exemple active le compte pour la boîte aux lettres de salle existante qui a la valeur d’alias ProjectRigel02 et définit le mot de passe 9898P@$$W0rd.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-132">This example enables the account for the existing room mailbox that has the alias value ProjectRigel02, and sets the password to 9898P@$$W0rd.</span></span> <span data-ttu-id="9c7f3-133">Notez que le compte sera ProjectRigel02@contoso.onmicrosoft.com en raison de la valeur d’alias existante.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-133">Note that the account will be ProjectRigel02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="9c7f3-134">Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-134">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="9c7f3-135">Dans Exchange Online PowerShell, configurez les paramètres suivants dans la boîte aux lettres de salle pour améliorer l’expérience de réunion :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-135">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="9c7f3-136">AutomateProcessing : AutoAccept (organisateurs de réunion recevoir la décision de réservation de salles directement sans intervention humaine : libre = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="9c7f3-136">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="9c7f3-137">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté à l’objet de la demande de réunion).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-137">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="9c7f3-138">DeleteComments : $false (conserver le texte dans le corps du message de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-138">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9c7f3-139">DeleteSubject : $false (conserver l’objet de demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-139">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="9c7f3-140">RemovePrivateProperty : $false (garantit la demande de l’indicateur privé qui a été envoyé par l’organisateur de la réunion d’origine reste comme indiqué).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-140">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="9c7f3-141">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-141">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="9c7f3-142">AdditionalResponse : « Ceci est une salle de réunion Skype ! »</span><span class="sxs-lookup"><span data-stu-id="9c7f3-142">AdditionalResponse: "This is a Skype Meeting room!"</span></span> <span data-ttu-id="9c7f3-143">(Texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="9c7f3-143">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="9c7f3-144">Cet exemple configure ces paramètres dans la boîte aux lettres de salle nommé Project-Rigel-01.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-144">This example configures these settings on the room mailbox named Project-Rigel-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   <span data-ttu-id="9c7f3-145">Pour détaillées sur la syntaxe et les informations sur les paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-145">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="9c7f3-146">Se connecter à Active Directory Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-146">Connect to Azure Active Directory PowerShell.</span></span> <span data-ttu-id="9c7f3-147">Pour obtenir des instructions, consultez la rubrique [Connect avec Azure Active Directory PowerShell pour le module de graphique](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="9c7f3-147">For instructions, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span></span>

5. <span data-ttu-id="9c7f3-148">Si vous ne souhaitez pas que le mot de passe à expiration, utilisez la syntaxe suivante dans Windows Azure Active Directory PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-148">If you do not want the password to expire, use the following syntax in Azure Active Directory PowerShell:</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="9c7f3-149">Cet exemple montre comment définir le mot de passe pour le compte ProjectRigel01@contoso.onmicrosoft.com n’expire jamais.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-149">This example sets the password for the account ProjectRigel01@contoso.onmicrosoft.com to never expire.</span></span>

   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ```

   <span data-ttu-id="9c7f3-150">Vous pouvez également définir un numéro de téléphone pour le compte en exécutant la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-150">You can also set a phone number for the account by running the following command:</span></span>

   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```

6. <span data-ttu-id="9c7f3-151">Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-151">The device account needs to have a valid Office 365 license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="9c7f3-152">Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-152">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="9c7f3-153">Vous pouvez utiliser Get-AzureADSubscribedSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-153">You can use Get-AzureADSubscribedSku to retrieve a list of available SKUs for your Office 365 tenant as follows:</span></span>

   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```

   <span data-ttu-id="9c7f3-154">Ensuite, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-AzureADUserLicense.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-154">Next, you can add a license using the Set-AzureADUserLicense cmdlet.</span></span> <span data-ttu-id="9c7f3-155">Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-155">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span>

   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```

   <span data-ttu-id="9c7f3-156">Pour obtenir des instructions détaillées, consultez la rubrique [attribution de licences pour les comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-156">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

7. <span data-ttu-id="9c7f3-157">Ensuite, vous devez activer le compte de l’appareil avec Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-157">Next, you need to enable the device account with Skype for Business.</span></span> <span data-ttu-id="9c7f3-158">Assurez-vous que votre environnement est conforme à la configuration définie dans [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c7f3-158">Be sure your environment meets the requirements defined in [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>

   <span data-ttu-id="9c7f3-159">Démarrer une [session Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) à distance comme suit (veillez à [installer Skype pour les composants Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-159">Start a remote [Windows PowerShell session](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) as follows (be sure to [install Skype for Business Online PowerShell components](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)):</span></span>

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   <span data-ttu-id="9c7f3-160">Ensuite, activer votre compte v2 de systèmes de salle Skype pour Skype pour Business Server en exécutant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-160">Next, enable your Skype Room Systems v2 account for Skype for Business Server by running the following cmdlet:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   <span data-ttu-id="9c7f3-161">Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-161">Obtain the RegistrarPool information from the new user account being setup, as shown in this example:</span></span>

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > <span data-ttu-id="9c7f3-162">Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-162">New user accounts might not be created on the same registrar pool as existing user accounts in the tenant.</span></span> <span data-ttu-id="9c7f3-163">La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-163">The command above will prevent errors in account setup due to this situation.</span></span>

<span data-ttu-id="9c7f3-164">Une fois que vous avez terminé les étapes précédentes pour activer votre compte Skype salle systèmes v2 Skype pour Business Online, vous devez attribuer une licence à un appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-164">After you've completed the preceding steps to enable your Skype Room Systems v2 account in Skype for Business Online, you need to assign a license to Skype Room Systems v2 device.</span></span> <span data-ttu-id="9c7f3-165">À l’aide du portail d’administration d’Office 365, assignez un soit Skype Business Online (Plan 2) ou une Skype licence entreprise Online (Plan 3) à l’appareil.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-165">Using the Office 365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

### <a name="assign-a-license-to-your-account"></a><span data-ttu-id="9c7f3-166">Affectation d’une licence à votre compte</span><span class="sxs-lookup"><span data-stu-id="9c7f3-166">Assign a license to your account</span></span>

1. <span data-ttu-id="9c7f3-167">Ouverture de session en tant qu’un administrateur client, ouvrez le portail d’administration d’Office 365, puis cliquez sur l’application d’administration.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-167">Login as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>

2. <span data-ttu-id="9c7f3-168">Cliquez sur **Utilisateurs et groupes**, puis sur **Ajoutez des utilisateurs, réinitialisez les mots de passe, et plus encore**.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-168">Click **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>

3. <span data-ttu-id="9c7f3-169">Sélectionnez le compte v2 Skype salle systèmes, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-169">Select the Skype Room Systems v2 account, and then click or tap the pen icon, which means edit.</span></span>

4. <span data-ttu-id="9c7f3-170">Cliquez sur l’option **Licences**.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-170">Click on the **Licenses** option.</span></span>

5. <span data-ttu-id="9c7f3-171">Dans la section **attribution de licences** , vous devez sélectionner Skype pour Business Online (Plan 2) ou Skype pour Business Online (Plan 3), en fonction de vos licences et vous avez décidé en termes de devoir Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-171">In the **Assign licenses** section, you need to select Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3), depending on your licensing and what you've decided in terms of needing Enterprise Voice.</span></span> <span data-ttu-id="9c7f3-172">Vous devrez utiliser une licence 3 planifier si vous souhaitez utiliser dans le nuage PBX sur Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-172">You'll have to use a Plan 3 license if you want to use Cloud PBX on Skype Room Systems v2.</span></span> <span data-ttu-id="9c7f3-173">Vous aurez au moins besoin de CloudPBX pour la connectivité vocale.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-173">Minimally you will need CloudPBX for voice connectivity.</span></span> <span data-ttu-id="9c7f3-174">Puis, configurez la voix hybride ou la fonction d’appel RTC sur la méthode de connectivité RTC.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-174">Then configure hybrid voice or PSTN calling based on the PSTN connectivity method.</span></span> <span data-ttu-id="9c7f3-175">Pour plus d’informations, voir [systèmes de salle Skype v2 licences](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) .</span><span class="sxs-lookup"><span data-stu-id="9c7f3-175">See [Skype Room Systems v2 licenses](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2) for more details.</span></span>

6. <span data-ttu-id="9c7f3-176">Cliquez sur **Enregistrer** pour terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-176">Click **Save** to complete the task.</span></span>

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a><span data-ttu-id="9c7f3-177">Exemple : Compte salle du programme d’installation dans Exchange Online et Skype pour Business Online</span><span class="sxs-lookup"><span data-stu-id="9c7f3-177">Sample: Room account setup in Exchange Online and Skype for Business Online</span></span>

<span data-ttu-id="9c7f3-178">Commandes Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-178">Exchange Online PowerShell commands:</span></span>

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

<span data-ttu-id="9c7f3-179">Commandes Azure Active Directory PowerShell :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-179">Azure Active Directory PowerShell commands:</span></span>

``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<span data-ttu-id="9c7f3-180">Skype pour commande PowerShell d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="9c7f3-180">Skype for Business PowerShell command:</span></span>

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> <span data-ttu-id="9c7f3-181">Ceci ajoute CloudPBX et PSTNCallingDomesticAndInternational.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-181">This adds CloudPBX and PSTNCallingDomesticAndInternational.</span></span> <span data-ttu-id="9c7f3-182">En outre, vous devez utiliser l’interface d’administration pour affecter un numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-182">Additionally, you will need to use the Admin interface to assign a phone number.</span></span>

## <a name="validate"></a><span data-ttu-id="9c7f3-183">Valider</span><span class="sxs-lookup"><span data-stu-id="9c7f3-183">Validate</span></span>

<span data-ttu-id="9c7f3-184">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="9c7f3-184">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c7f3-185">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c7f3-185">See also</span></span>

[<span data-ttu-id="9c7f3-186">Configurer des comptes pour les systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="9c7f3-186">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="9c7f3-187">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="9c7f3-187">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="9c7f3-188">Déploiement des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="9c7f3-188">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)

[<span data-ttu-id="9c7f3-189">Configuration d’une console pour les systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="9c7f3-189">Configure a Skype Room Systems v2 console</span></span>](console.md)

[<span data-ttu-id="9c7f3-190">Gestion des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="9c7f3-190">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[<span data-ttu-id="9c7f3-191">Gestion des licences de salle Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="9c7f3-191">Skype Room Systems v2 Licensing</span></span>](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
