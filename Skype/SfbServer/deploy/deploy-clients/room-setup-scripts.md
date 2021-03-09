---
title: Scripts de configuration de salle Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: Consultez cette rubrique pour trouver des exemples de scripts pour la mise en service des comptes Skype Room System.
ms.openlocfilehash: 93a97b42f3b800011030787ea39cfb503767e42c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569366"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="a9368-103">Scripts de configuration de salle Skype Room System</span><span class="sxs-lookup"><span data-stu-id="a9368-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="a9368-104">Consultez cette rubrique pour trouver des exemples de scripts pour la mise en service des comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="a9368-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="a9368-105">Cette section illustre des exemples de scripts qui peuvent être utilisés pour mettre en service des comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="a9368-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="a9368-106">Ces scripts sont uniquement à titre d’illustration.</span><span class="sxs-lookup"><span data-stu-id="a9368-106">These scripts are only for illustrative purposes.</span></span> <span data-ttu-id="a9368-107">Elles ne doivent être utilisées qu’après avoir consulté votre expert informatique ou votre administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="a9368-107">They should be used only after you consult with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="a9368-108">Exemple de script d’installation : Skype Entreprise et Exchange Server (local)</span><span class="sxs-lookup"><span data-stu-id="a9368-108">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```powershell
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="a9368-109">Exemple de script d’installation : Skype Entreprise et Exchange Server Online</span><span class="sxs-lookup"><span data-stu-id="a9368-109">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="a9368-110">Assurez-vous que vous avez passé en revue les conditions préalables suivantes avant d’exécutez le script :</span><span class="sxs-lookup"><span data-stu-id="a9368-110">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="a9368-111">Assistant Microsoft Online Services Sign-In pour les professionnels de l’informatique BETA</span><span class="sxs-lookup"><span data-stu-id="a9368-111">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="a9368-112">Windows Azure Module Active Directory pour Windows PowerShell (version 64 bits) ou (version 32 bits)</span><span class="sxs-lookup"><span data-stu-id="a9368-112">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="a9368-113">Teams PowerShell Module</span><span class="sxs-lookup"><span data-stu-id="a9368-113">Teams PowerShell Module</span></span>
    
- <span data-ttu-id="a9368-114">Redémarrer si nécessaire</span><span class="sxs-lookup"><span data-stu-id="a9368-114">Reboot if needed</span></span>
    
```powershell
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```

