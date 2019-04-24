---
title: Déployer les équipes Microsoft salles avec Skype pour Business Server
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer des salles d’équipes Microsoft avec Skype pour Business Server.
ms.openlocfilehash: e5ba372a5990f7c63827f1f8b0426e67ae48b620
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207873"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="6d3d3-103">Déployer les équipes Microsoft salles avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="6d3d3-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="6d3d3-104">Cette rubrique explique comment vous ajoutez un compte de périphérique pour les salles d’équipes Microsoft lorsque vous avez un déploiement local de forêt unique.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="6d3d3-105">Si vous avez une forêt unique, le déploiement local avec Exchange 2013 SP1 ou version ultérieure et le Skype pour Business Server 2015 ou version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="6d3d3-106">Si vous utilisez un déploiement à forêts multiples, vous pouvez utiliser les applets de commande équivalente qui produit le même résultat.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="6d3d3-107">Ces applets de commande sont décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="6d3d3-108">Avant de commencer à déployer Microsoft équipes salles, assurez-vous que les autorisations appropriées pour exécuter les applets de commande associée.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="6d3d3-109">Notez que $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange et $strLyncFQDN est le nom de domaine complet de votre Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="6d3d3-110">Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="6d3d3-111">Ainsi, le compte de s’authentifier auprès de salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="6d3d3-112">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="6d3d3-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="6d3d3-113">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="6d3d3-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="6d3d3-114">Vous pouvez définir diverses propriétés Exchange sur le compte de l’appareil pour améliorer l’expérience des personnes.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="6d3d3-115">Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="6d3d3-116">Si vous décidez d’avoir le mot de passe n'expire pas, vous pouvez également définir qui avec les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="6d3d3-117">Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="6d3d3-118">Activez le compte dans Active Directory pour authentifie salles d’équipes Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="6d3d3-119">Activer le compte de l’appareil avec Skype pour Business Server grâce à votre compte Microsoft équipes salles Active Directory sur un Skype pour le pool de serveurs d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="6d3d3-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="6d3d3-120">Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="6d3d3-121">**Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-121">**Optional.**</span></span> <span data-ttu-id="6d3d3-122">Vous pouvez également permettre salles d’équipes Microsoft émettre et recevoir des appels téléphoniques de réseau téléphonique commuté public en activant Enterprise Voice de votre compte.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="6d3d3-123">Enterprise Voice n’est pas une condition requise pour les salles d’équipes Microsoft, mais si vous souhaitez composer le numéro PSTN pour le client Microsoft équipes salles, voici comment l’activer :</span><span class="sxs-lookup"><span data-stu-id="6d3d3-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="6d3d3-p106">Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.</span><span class="sxs-lookup"><span data-stu-id="6d3d3-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="6d3d3-126">Exemple : configuration de compte salle dans Exchange et Skype pour Business Server sur site</span><span class="sxs-lookup"><span data-stu-id="6d3d3-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="6d3d3-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6d3d3-127">See also</span></span>

[<span data-ttu-id="6d3d3-128">Configurer des comptes pour les salles d’équipes Microsoft</span><span class="sxs-lookup"><span data-stu-id="6d3d3-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="6d3d3-129">Planifier des équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="6d3d3-129">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="6d3d3-130">Déployer les équipes Microsoft salles</span><span class="sxs-lookup"><span data-stu-id="6d3d3-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="6d3d3-131">Configurer une console Microsoft équipes salles</span><span class="sxs-lookup"><span data-stu-id="6d3d3-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="6d3d3-132">Gérer Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="6d3d3-132">Manage Microsoft Teams Rooms</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)