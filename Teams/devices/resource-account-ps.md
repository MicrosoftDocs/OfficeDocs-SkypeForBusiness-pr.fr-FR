---
title: Création de comptes de ressources de Microsoft teams pour les barres de collaboration de Microsoft teams à l’aide de PowerShell
ms.author: mitressl
author: flinchbot
manager: ericwe
audience: ITPro
ms.reviewer: payurevi
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Consultez cette rubrique pour plus d’informations sur le déploiement de barres de collaboration pour Microsoft Teams.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 0cb8043e0530c986b9ddcaa9a1022254939adfd2
ms.sourcegitcommit: f0ccafb7e9c2d382ab4545e085657e8129024f1d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268028"
---
# <a name="create-a-microsoft-365-resource-account-using-the-powershell"></a><span data-ttu-id="4e5ab-103">Créer un compte de ressources Microsoft 365 à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e5ab-103">Create a Microsoft 365 resource account using the PowerShell</span></span>

<span data-ttu-id="4e5ab-104">Consultez cette rubrique pour plus d’informations sur la création de comptes de ressources pour les barres de collaboration de Microsoft teams à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-104">Read this topic for information on how to create resource accounts for collaboration bars for Microsoft Teams using PowerShell.</span></span>

<span data-ttu-id="4e5ab-105">Pour créer un compte de ressources, le plus simple consiste à utiliser le centre d’administration Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-105">The easiest way to create a resource account is by using the Microsoft 365 admin center.</span></span> <span data-ttu-id="4e5ab-106">[Pour plus d’informations, consultez cet article](resource-account-ui.md).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-106">[See this article on how to do this](resource-account-ui.md).</span></span>

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

## <a name="requirements"></a><span data-ttu-id="4e5ab-107">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="4e5ab-107">Requirements</span></span>

<span data-ttu-id="4e5ab-108">Avant de déployer des salles Microsoft teams avec Office 365, assurez-vous que vous remplissez les conditions requises.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-108">Before you deploy Microsoft Teams Rooms with Office 365, be sure you have met the requirements.</span></span> <span data-ttu-id="4e5ab-109">Pour plus d’informations, reportez-vous à la section [déploiement de barres de collaboration pour Microsoft teams](collab-bar-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-109">For more information, see [Deploy collaboration bars for Microsoft Teams](collab-bar-deploy.md).</span></span>

- <span data-ttu-id="4e5ab-110">Si vous avez besoin des fonctionnalités RTC pour la barre de collaboration, vous aurez besoin d’une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-110">If you need PSTN capabilities for the collaboration bar, you will need Phone System license.</span></span>

- <span data-ttu-id="4e5ab-111">Vos comptes de ressources doivent avoir des boîtes aux lettres Exchange.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-111">Your resource accounts must have Exchange mailboxes.</span></span> <span data-ttu-id="4e5ab-112">Étant donné qu’il s’agit de comptes de ressources, aucune licence Exchange n’est requise.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-112">As these are resource accounts, no Exchange license is required.</span></span> <span data-ttu-id="4e5ab-113">Nous vous recommandons d’utiliser la licence de salles de réunion pour les comptes de ressources.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-113">We recommend the usage of the Meeting Rooms license for resource accounts.</span></span>


### <a name="add-a-resource-account"></a><span data-ttu-id="4e5ab-114">Ajouter un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="4e5ab-114">Add a resource account</span></span>

1. <span data-ttu-id="4e5ab-115">Connectez-vous à Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-115">Connect to Exchange Online PowerShell.</span></span> <span data-ttu-id="4e5ab-116">Pour obtenir des instructions, voir [se connecter à Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-116">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell-v2/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exchange-online-powershell-v2-module).</span></span>

2. <span data-ttu-id="4e5ab-117">Dans Exchange Online PowerShell, créez une nouvelle boîte aux lettres de salle ou modifiez une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-117">In Exchange Online PowerShell, create a new room mailbox or modify an existing room mailbox.</span></span>

   - <span data-ttu-id="4e5ab-118">Pour créer une boîte aux lettres de salle, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="4e5ab-118">To create a new room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="4e5ab-119">Cet exemple crée une boîte aux lettres de salle avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="4e5ab-119">This example creates a new room mailbox with the following settings:</span></span>

     - <span data-ttu-id="4e5ab-120">Nom : Huddle-salle-01</span><span class="sxs-lookup"><span data-stu-id="4e5ab-120">Name: Huddle-Room-01</span></span>

     - <span data-ttu-id="4e5ab-121">Alias : HuddleRoom01</span><span class="sxs-lookup"><span data-stu-id="4e5ab-121">Alias: HuddleRoom01</span></span>

     - <span data-ttu-id="4e5ab-122">Compte : huddleroom01@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4e5ab-122">Account: huddleroom01@contoso.onmicrosoft.com</span></span>

     - <span data-ttu-id="4e5ab-123">Mot de passe du compte : P@ $ $W 0rd242</span><span class="sxs-lookup"><span data-stu-id="4e5ab-123">Account password: P@$$W0rd242</span></span>

     ``` PowerShell
     New-Mailbox -Name "Huddle-Room-01" -Alias HuddleRoom01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID HuddleRoom01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd242' -AsPlainText -Force)
     ```

   - <span data-ttu-id="4e5ab-124">Pour modifier une boîte aux lettres de salle existante, utilisez la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="4e5ab-124">To modify an existing room mailbox, use the following syntax:</span></span>

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     <span data-ttu-id="4e5ab-125">Dans cet exemple, le compte de la boîte aux lettres de salle existante possède la valeur alias HuddleRoom02 et le mot de passe est défini sur 808P@ $ $W 0rd.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-125">This example enables the account for the existing room mailbox that has the alias value HuddleRoom02, and sets the password to 808P@$$W0rd.</span></span> <span data-ttu-id="4e5ab-126">Notez que le compte sera HuddleRoom02@contoso.onmicrosoft.com en raison de la valeur de l’alias existant.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-126">Note that the account will be HuddleRoom02@contoso.onmicrosoft.com because of the existing alias value.</span></span>

     ``` PowerShell
     Set-Mailbox -Identity HuddleRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '808P@$$W0rd' -AsPlainText -Force)
     ```

   <span data-ttu-id="4e5ab-127">Pour plus d’informations sur les paramètres de syntaxe et de paramètre, voir [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) et [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-127">For detailed syntax and parameter information, see [New-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox) and [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).</span></span>


3. <span data-ttu-id="4e5ab-128">Dans Exchange Online PowerShell, configurez les paramètres suivants sur la boîte aux lettres de salle pour améliorer l’interface utilisateur :</span><span class="sxs-lookup"><span data-stu-id="4e5ab-128">In Exchange Online PowerShell, configure the following settings on the room mailbox to improve the meeting experience:</span></span>

   - <span data-ttu-id="4e5ab-129">AutomateProcessing : l’acceptation automatique (les organisateurs de la réunion reçoivent la décision de réservation de salle directement sans intervention humaine : gratuit = accepter ; occupé = refuser.)</span><span class="sxs-lookup"><span data-stu-id="4e5ab-129">AutomateProcessing: AutoAccept (Meeting organizers receive the room reservation decision directly without human intervention: free = accept; busy = decline.)</span></span>

   - <span data-ttu-id="4e5ab-130">AddOrganizerToSubject : $false (l’organisateur de la réunion n’est pas ajouté au sujet de la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="4e5ab-130">AddOrganizerToSubject: $false (The meeting organizer is not added to the subject of the meeting request.)</span></span>

   - <span data-ttu-id="4e5ab-131">DeleteComments : $false (conservez le texte dans le corps des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-131">DeleteComments: $false (Keep any text in the message body of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4e5ab-132">DeleteSubject : $false (conserver le sujet des demandes de réunion entrantes).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-132">DeleteSubject: $false (Keep the subject of incoming meeting requests.)</span></span>

   - <span data-ttu-id="4e5ab-133">RemovePrivateProperty : $false (vérifie que l’indicateur privé qui a été envoyé par l’organisateur de la réunion dans la demande de réunion d’origine reste indiqué.)</span><span class="sxs-lookup"><span data-stu-id="4e5ab-133">RemovePrivateProperty: $false (Ensures the private flag that was sent by the meeting organizer in the original meeting request remains as specified.)</span></span>

   - <span data-ttu-id="4e5ab-134">AddAdditionalResponse : $true (le texte spécifié par le paramètre AdditionalResponse est ajouté aux demandes de réunion.)</span><span class="sxs-lookup"><span data-stu-id="4e5ab-134">AddAdditionalResponse: $true (The text specified by the AdditionalResponse parameter is added to meeting requests.)</span></span>

   - <span data-ttu-id="4e5ab-135">AdditionalResponse : « cette salle possède une barre de collaboration pour Microsoft teams ! »</span><span class="sxs-lookup"><span data-stu-id="4e5ab-135">AdditionalResponse: "This room has a collaboration bar for Microsoft Teams!"</span></span> <span data-ttu-id="4e5ab-136">(Le texte supplémentaire à ajouter à la demande de réunion.)</span><span class="sxs-lookup"><span data-stu-id="4e5ab-136">(The additional text to add to the meeting request.)</span></span>

   <span data-ttu-id="4e5ab-137">Cet exemple configure ces paramètres sur la boîte aux lettres de salle nommée Huddle-salle-01.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-137">This example configures these settings on the room mailbox named Huddle-Room-01.</span></span>

   ``` PowerShell
   Set-CalendarProcessing -Identity "Huddle-Room-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room has a collaboration bar for Microsoft Teams!"
   ```

   <span data-ttu-id="4e5ab-138">Pour obtenir une syntaxe détaillée et des informations relatives aux paramètres, voir [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-138">For detailed syntax and parameter information, see [Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing).</span></span>

4. <span data-ttu-id="4e5ab-139">Connectez-vous à MS Online PowerShell pour créer des paramètres Active Directory en exécutant l’applet de contrôle `Connect-MsolService -Credential $cred` PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-139">Connect to MS Online PowerShell to make Active Directory settings by running the `Connect-MsolService -Credential $cred` powershell cmdlet.</span></span>   <span data-ttu-id="4e5ab-140">Pour plus d’informations sur Active Directory, voir [Azure ActiveDirectory (MSONLINE,) 1,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-140">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="4e5ab-141">[Azure Active Directory PowerShell 2,0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) n’est pas pris en charge.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-141">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

5. <span data-ttu-id="4e5ab-142">Définissez le mot de passe pour huddleroom01@contoso.onmicrosoft.com pour qu’il n’expire pas en utilisant la syntaxe suivante :</span><span class="sxs-lookup"><span data-stu-id="4e5ab-142">Set the password for huddleroom01@contoso.onmicrosoft.com to not expire using the following syntax:</span></span>

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -PasswordNeverExpires $true
      ```
    
6. <span data-ttu-id="4e5ab-143">Le compte de ressource doit disposer d’une licence Office 365 valide, de préférence du SKU de la salle de réunion.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-143">The resource account needs to have a valid Office 365 license, preferably the Meeting Room SKU.</span></span> <span data-ttu-id="4e5ab-144">Vous devez également attribuer un emplacement d’utilisation à votre compte d’appareil : cela détermine les références SKU de licence disponibles pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-144">You also need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4e5ab-145">Vous pouvez utiliser `Get-MsolAccountSku` pour récupérer la liste des références SKU disponibles pour votre client Office 365.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-145">You can use `Get-MsolAccountSku` to retrieve a list of available SKUs for your Office 365 tenant.</span></span>

      ``` Powershell
      Get-MsolAccountSku
      ```
    
    <span data-ttu-id="4e5ab-146">Vous pouvez attribuer la licence à l’aide de Set-MsolUserLicense.</span><span class="sxs-lookup"><span data-stu-id="4e5ab-146">You can assign the license using Set-MsolUserLicense.</span></span> 

      ``` Powershell
      Set-MsolUser -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -UsageLocation "US"
      Set-MsolUserLicense -UserPrincipalName huddleroom01@contoso.onmicrosoft.com -AddLicenses contoso:meeting_room
      ```
   <span data-ttu-id="4e5ab-147">Pour obtenir des instructions détaillées, voir [attribuer des licences à des comptes d’utilisateurs avec Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4e5ab-147">For detailed instructions, see [Assign licenses to user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>




[<span data-ttu-id="4e5ab-148">Configurer les comptes pour les barres de collaboration de Microsoft teams à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="4e5ab-148">Configure accounts for collaboration bars for Microsoft Teams using PowerShell</span></span>](resource-account-ps.md)

[<span data-ttu-id="4e5ab-149">Déploiement de barres de collaboration pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4e5ab-149">Deploy collaboration bars for Microsoft Teams</span></span>](collab-bar-deploy.md)

[<span data-ttu-id="4e5ab-150">Barres de collaboration pour la gestion des licences Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="4e5ab-150">Collaboration bars for Microsoft Teams Licensing</span></span>](../rooms/rooms-licensing.md)


