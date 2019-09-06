---
title: Déploiement de salles de Microsoft teams avec Skype entreprise Server
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Pour plus d’informations sur le déploiement de salles de Microsoft teams avec Skype entreprise Server, reportez-vous à cette rubrique.
ms.openlocfilehash: 0661a19b3569cbfde5edfb5ceb631fab7282d302
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774945"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="76daf-103">Déploiement de salles de Microsoft teams avec Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="76daf-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="76daf-104">Cette rubrique explique comment ajouter un compte d’appareil pour les salles Microsoft teams lorsque vous disposez d’un déploiement local de forêt et de forêt unique.</span><span class="sxs-lookup"><span data-stu-id="76daf-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="76daf-105">Si vous avez un déploiement local de forêt unique avec Exchange 2013 SP1 ou une version ultérieure et Skype entreprise Server 2015 ou une version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes d’appareil.</span><span class="sxs-lookup"><span data-stu-id="76daf-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="76daf-106">Si vous utilisez un déploiement à plusieurs forêts, vous pouvez utiliser les applets de requête équivalentes qui produisent les mêmes résultats.</span><span class="sxs-lookup"><span data-stu-id="76daf-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="76daf-107">Ces applets de commande sont décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="76daf-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="76daf-108">Avant de commencer à déployer des salles de Microsoft Teams, vérifiez que vous disposez des autorisations appropriées pour exécuter les applets de cmdlet associées.</span><span class="sxs-lookup"><span data-stu-id="76daf-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="76daf-109">Notez que $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange, et que $strLyncFQDN est le FQDN du déploiement de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="76daf-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="76daf-110">Après avoir établi une session, vous pouvez créer une nouvelle boîte aux lettres et l’activer en tant que RoomMailboxAccount, ou changer les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="76daf-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="76daf-111">Cela permettra au compte d’s’authentifier auprès des salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76daf-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="76daf-112">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="76daf-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="76daf-113">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="76daf-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="76daf-114">Vous pouvez définir diverses propriétés Exchange sur le compte de l’appareil pour améliorer l’interface utilisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="76daf-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="76daf-115">Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="76daf-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="76daf-116">Si vous décidez que le mot de passe n’expire pas, vous pouvez également définir ce comportement avec les applets de cmdlet Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="76daf-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="76daf-117">Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="76daf-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="76daf-118">Activez le compte dans Active Directory de manière à ce qu’il s’authentifie aux salles de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76daf-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="76daf-119">Activez le compte de l’appareil avec Skype entreprise Server en activant votre compte Active Directory de Microsoft teams sur un pool Skype entreprise Server :</span><span class="sxs-lookup"><span data-stu-id="76daf-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="76daf-120">Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet.</span><span class="sxs-lookup"><span data-stu-id="76daf-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="76daf-121">**Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="76daf-121">**Optional.**</span></span> <span data-ttu-id="76daf-122">Vous pouvez également permettre aux salles de Microsoft teams de passer et de recevoir des appels téléphoniques du réseau téléphonique commuté (PSTN) en activant Enterprise Voice pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="76daf-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="76daf-123">L’application voix entreprise n’est pas obligatoire pour les salles de Microsoft Teams, mais si vous voulez utiliser la fonctionnalité de numérotation PSTN pour le client Microsoft Teams, voici comment l’activer :</span><span class="sxs-lookup"><span data-stu-id="76daf-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="76daf-p106">Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.</span><span class="sxs-lookup"><span data-stu-id="76daf-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="76daf-126">Exemple : configuration de compte salle dans Exchange et Skype entreprise Server en local</span><span class="sxs-lookup"><span data-stu-id="76daf-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="76daf-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76daf-127">See also</span></span>

[<span data-ttu-id="76daf-128">Configurer des comptes pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="76daf-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="76daf-129">Plan pour les salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="76daf-129">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="76daf-130">Déploiement de salles de Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="76daf-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="76daf-131">Configurer une console de salle Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="76daf-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="76daf-132">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="76daf-132">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
