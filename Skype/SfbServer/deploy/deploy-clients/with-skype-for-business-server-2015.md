---
title: Déploiement de Skype Room Systems v2 avec Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Skype pour Business Server 2015.
ms.openlocfilehash: 904835e766283791f52c0dc1d1221a0d7253e3e1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="d8a71-103">Déploiement de Skype Room Systems v2 avec Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d8a71-103">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d8a71-104">Lisez cette rubrique pour plus d’informations sur le déploiement de v2 Skype salle systèmes avec Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d8a71-104">Read this topic for information on how to deploy Skype Room Systems v2 with Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d8a71-105">Cette rubrique explique comment vous ajoutez un compte de dispositif pour systèmes de salle Skype v2 lorsque vous disposez d’un déploiement sur site de forêt unique.</span><span class="sxs-lookup"><span data-stu-id="d8a71-105">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="d8a71-106">Si vous avez une forêt unique, déploiement sur site avec Exchange 2013 SP1 ou version ultérieure et Skype pour Business Server 2015 ou version ultérieure, vous pouvez utiliser les scripts Windows PowerShell fournis pour créer les comptes de périphérique.</span><span class="sxs-lookup"><span data-stu-id="d8a71-106">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="d8a71-107">Si vous utilisez un déploiement de plusieurs forêt, vous pouvez utiliser des applets de commande équivalente qui produira les mêmes résultats.</span><span class="sxs-lookup"><span data-stu-id="d8a71-107">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="d8a71-108">Ces applets de commande sont décrites dans cette section.</span><span class="sxs-lookup"><span data-stu-id="d8a71-108">Those cmdlets are described in this section.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server-2015"></a><span data-ttu-id="d8a71-109">Déploiement de Skype Room Systems v2 avec Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d8a71-109">Deploy Skype Room Systems v2 with Skype for Business Server 2015</span></span>

<span data-ttu-id="d8a71-110">Avant de déployer v2 Skype salle systèmes avec Skype pour Business Server 2015, veillez à ce que vous avez satisfait les exigences.</span><span class="sxs-lookup"><span data-stu-id="d8a71-110">Before you deploy Skype Room Systems v2 with Skype for Business Server 2015, be sure you have met the requirements.</span></span> <span data-ttu-id="d8a71-111">Pour plus d’informations, consultez [v2 Skype pièce requise](../../plan-your-deployment/clients-and-devices/requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8a71-111">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="d8a71-112">Avant de commencer à déployer des systèmes de salle Skype v2, assurez-vous que vous disposez des autorisations appropriées pour exécuter les applets de commande associé.</span><span class="sxs-lookup"><span data-stu-id="d8a71-112">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="d8a71-113">Démarrer une session Windows PowerShell à distance à partir d’un PC et se connecter à Exchange.</span><span class="sxs-lookup"><span data-stu-id="d8a71-113">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="d8a71-114">Notez que $strExchangeServer est le nom de domaine pleinement qualifié (FQDN) de votre serveur Exchange, et $strLyncFQDN est le nom de domaine complet de votre Skype pour le déploiement de Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d8a71-114">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server 2015 deployment.</span></span>
    
2. <span data-ttu-id="d8a71-115">Après l’établissement d’une session, vous allez créer une nouvelle boîte aux lettres et activer comme un RoomMailboxAccount, soit modifier les paramètres d’une boîte aux lettres de salle existante.</span><span class="sxs-lookup"><span data-stu-id="d8a71-115">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="d8a71-116">Ainsi, le compte pour s’authentifier sur des systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="d8a71-116">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="d8a71-117">Si vous modifiez une boîte aux lettres de ressource :</span><span class="sxs-lookup"><span data-stu-id="d8a71-117">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="d8a71-118">Si vous créez une nouvelle boîte aux lettres de ressources :</span><span class="sxs-lookup"><span data-stu-id="d8a71-118">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="d8a71-119">Vous pouvez définir différentes propriétés de Exchange sur le compte de dispositif pour améliorer l’expérience de la réunion pour les personnes.</span><span class="sxs-lookup"><span data-stu-id="d8a71-119">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="d8a71-120">Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.</span><span class="sxs-lookup"><span data-stu-id="d8a71-120">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="d8a71-121">Si vous souhaitez que le mot de passe n'expire pas, vous pouvez également définir qu’avec les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d8a71-121">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="d8a71-122">Pour plus d’informations, reportez-vous à la section Gestion des mots de passe.</span><span class="sxs-lookup"><span data-stu-id="d8a71-122">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="d8a71-123">Activer le compte dans Active Directory afin qu’il va authentifier pour systèmes de salle Skype v2.</span><span class="sxs-lookup"><span data-stu-id="d8a71-123">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="d8a71-124">Activer le compte de dispositif avec Skype pour Business Server 2015 par l’activation de votre compte d’Active Directory v2 systèmes de salle Skype sur un Skype pour Business Server 2015 pool :</span><span class="sxs-lookup"><span data-stu-id="d8a71-124">Enable the device account with Skype for Business Server 2015 by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server 2015 pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="d8a71-125">Vous devrez utiliser l’adresse SIP (Session Initiation Protocol) et le contrôleur de domaine du projet.</span><span class="sxs-lookup"><span data-stu-id="d8a71-125">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="d8a71-126">**Facultatif**.</span><span class="sxs-lookup"><span data-stu-id="d8a71-126">**Optional.**</span></span> <span data-ttu-id="d8a71-127">Vous pouvez également autoriser v2 de systèmes de salle Skype à effectuer et de recevoir des appels téléphoniques de réseau téléphonique public commuté par l’activation de Voix Entreprise pour votre compte.</span><span class="sxs-lookup"><span data-stu-id="d8a71-127">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="d8a71-128">Voix Entreprise n’est pas une condition requise pour les systèmes de salle Skype v2, mais si vous souhaitez que la numérotation PSTN fonctionnalités du client v2 de systèmes de salle Skype, voici comment l’activer :</span><span class="sxs-lookup"><span data-stu-id="d8a71-128">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01

   ```

   <span data-ttu-id="d8a71-p107">Une fois encore, vous devrez remplacer les exemples de contrôleur de domaine et de numéro de téléphone fournis par vos propres informations. La valeur du paramètre $true demeure identique.</span><span class="sxs-lookup"><span data-stu-id="d8a71-p107">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-2015-on-premises"></a><span data-ttu-id="d8a71-131">Exemple : salle de compte paramétré dans Exchange et Skype pour 2015 de serveur d’entreprise dans les locaux</span><span class="sxs-lookup"><span data-stu-id="d8a71-131">Sample: room account setup in Exchange and Skype for Business Server 2015 on premises</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="d8a71-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d8a71-132">See also</span></span>

#### 

[<span data-ttu-id="d8a71-133">Plan de salle de Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="d8a71-133">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="d8a71-134">Déployer Skype salle systèmes v2</span><span class="sxs-lookup"><span data-stu-id="d8a71-134">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="d8a71-135">Configurer une console v2 de systèmes de salle de Skype</span><span class="sxs-lookup"><span data-stu-id="d8a71-135">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="d8a71-136">Gérer l’espace de Skype systèmes v2</span><span class="sxs-lookup"><span data-stu-id="d8a71-136">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

