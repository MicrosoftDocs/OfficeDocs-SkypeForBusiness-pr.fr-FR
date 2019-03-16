---
title: Déployer la salle Skype systèmes v2 avec Skype pour Business Server
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur la façon de déployer des systèmes de salle Skype v2 avec Skype pour Business Server.
ms.openlocfilehash: 5159d9cc8835ebe2b6e1d74e2f7644ee11232b63
ms.sourcegitcommit: a589b86520028d8751653386265f6ce1e066818b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2019
ms.locfileid: "30645393"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="31ca1-103">Déployer la salle Skype systèmes v2 avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="31ca1-103">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>
  
<span data-ttu-id="31ca1-104">Cette rubrique explique comment vous ajoutez un compte de périphériques pour les systèmes de salle Skype v2 lorsque vous avez un déploiement local de forêt unique.</span><span class="sxs-lookup"><span data-stu-id="31ca1-104">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="31ca1-105">Si vous avez une forêt unique, le déploiement local avec Exchange 2013 SP1 ou version ultérieure et le Skype pour Business Server 2015 ou version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer des comptes de l’appareil.</span><span class="sxs-lookup"><span data-stu-id="31ca1-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="31ca1-106">Si vous utilisez un déploiement à forêts multiples, vous pouvez utiliser les applets de commande équivalente qui produit le même résultat.</span><span class="sxs-lookup"><span data-stu-id="31ca1-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="31ca1-107">Ces applets de commande sont décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="31ca1-107">Those cmdlets are described in this section.</span></span>

<span data-ttu-id="31ca1-108">Pour configurer des comptes d’utilisateurs, la plus simple consiste à configurer à l’aide de Windows PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="31ca1-108">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="31ca1-109">Microsoft propose [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), un script qui vous aide à créer des comptes d’utilisateur ou de valider les comptes de ressource existant dont vous disposez afin de vous aider à les transformer en comptes d’utilisateurs v2 Skype salle systèmes compatibles.</span><span class="sxs-lookup"><span data-stu-id="31ca1-109">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="31ca1-110">Si vous préférez, vous pouvez suivre les étapes ci-dessous pour configurer les comptes utilisés par votre appareil v2 de systèmes de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="31ca1-110">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="31ca1-111">Configuration requise</span><span class="sxs-lookup"><span data-stu-id="31ca1-111">Requirements</span></span>

<span data-ttu-id="31ca1-112">Avant de déployer des systèmes de salle Skype v2 avec Skype pour Business Server, assurez-vous que vous remplissez les conditions.</span><span class="sxs-lookup"><span data-stu-id="31ca1-112">Before you deploy Skype Room Systems v2 with Skype for Business Server, be sure you have met the requirements.</span></span> <span data-ttu-id="31ca1-113">Pour plus d’informations, reportez-vous à la rubrique [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31ca1-113">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="31ca1-114">Avant de commencer à déployer des systèmes de salle Skype v2, assurez-vous que les autorisations appropriées pour exécuter les applets de commande associée.</span><span class="sxs-lookup"><span data-stu-id="31ca1-114">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="31ca1-115">Démarrer une session Windows PowerShell à distance à partir d’un PC et se connecter à Exchange.</span><span class="sxs-lookup"><span data-stu-id="31ca1-115">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span>

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

   <span data-ttu-id="31ca1-116">Notez que $strExchangeServer est le nom de domaine complet (FQDN) de votre serveur Exchange et $strLyncFQDN est le nom de domaine complet de votre Skype pour le déploiement de serveur d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="31ca1-116">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="31ca1-117">Après avoir établi une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="31ca1-117">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="31ca1-118">Ainsi, le compte de s’authentifier sur les systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="31ca1-118">This will allow the account to authenticate to Skype Room Systems v2.</span></span>

    <span data-ttu-id="31ca1-119">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="31ca1-119">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="31ca1-120">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="31ca1-120">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="31ca1-121">Vous pouvez définir diverses propriétés Exchange sur le compte de l’appareil pour améliorer l’expérience des personnes.</span><span class="sxs-lookup"><span data-stu-id="31ca1-121">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="31ca1-122">Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="31ca1-122">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="31ca1-123">Si vous décidez d’avoir le mot de passe n'expire pas, vous pouvez également définir qui avec les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="31ca1-123">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="31ca1-124">Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="31ca1-124">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="31ca1-125">Activez le compte dans Active Directory pour authentifie à Skype salle systèmes v2.</span><span class="sxs-lookup"><span data-stu-id="31ca1-125">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="31ca1-126">Activer le compte de l’appareil avec Skype pour Business Server grâce à votre compte d’Active Directory v2 Skype salle systèmes sur un Skype pour le pool de serveurs d’entreprise :</span><span class="sxs-lookup"><span data-stu-id="31ca1-126">Enable the device account with Skype for Business Server by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="31ca1-127">Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet.</span><span class="sxs-lookup"><span data-stu-id="31ca1-127">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="31ca1-128">**Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="31ca1-128">**Optional.**</span></span> <span data-ttu-id="31ca1-129">Vous pouvez également permettre Skype salle systèmes v2 émettre et recevoir des appels téléphoniques de réseau téléphonique commuté public en activant Enterprise Voice de votre compte.</span><span class="sxs-lookup"><span data-stu-id="31ca1-129">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="31ca1-130">Enterprise Voice n’est pas une condition requise pour les systèmes de salle Skype v2, mais si vous souhaitez composer le numéro PSTN pour le client de v2 Skype salle systèmes, voici comment l’activer :</span><span class="sxs-lookup"><span data-stu-id="31ca1-130">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="31ca1-p108">Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.</span><span class="sxs-lookup"><span data-stu-id="31ca1-p108">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="31ca1-133">Exemple : configuration de compte salle dans Exchange et Skype pour Business Server sur site</span><span class="sxs-lookup"><span data-stu-id="31ca1-133">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="31ca1-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="31ca1-134">See also</span></span>

[<span data-ttu-id="31ca1-135">Configurer des comptes pour les systèmes de salle Skype v2</span><span class="sxs-lookup"><span data-stu-id="31ca1-135">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="31ca1-136">Planification de Skype Room Systems v2</span><span class="sxs-lookup"><span data-stu-id="31ca1-136">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="31ca1-137">Déploiement des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="31ca1-137">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="31ca1-138">Configuration d’une console pour les systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="31ca1-138">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="31ca1-139">Gestion des systèmes Skype Room version 2</span><span class="sxs-lookup"><span data-stu-id="31ca1-139">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)