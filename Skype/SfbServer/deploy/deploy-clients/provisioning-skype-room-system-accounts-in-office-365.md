---
title: Mise en service de comptes Skype Room System dans Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
ms.openlocfilehash: be90831eba5f16f5a3b41f4c74c26333bf728926
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="d98ea-103">Mise en service de comptes Skype Room System dans Office 365</span><span class="sxs-lookup"><span data-stu-id="d98ea-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="d98ea-104">Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d98ea-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="d98ea-105">La section suivante décrit le compte système local de Skype mise en service d’un client Office 365.</span><span class="sxs-lookup"><span data-stu-id="d98ea-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="d98ea-106">Conditions préalables Office 365</span><span class="sxs-lookup"><span data-stu-id="d98ea-106">Office 365 prerequisites</span></span>

<span data-ttu-id="d98ea-107">Votre client en ligne doit répondre aux conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="d98ea-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="d98ea-108">Le plan d’Office 365 doit inclure Skype pour Business en ligne Plan 2, Plan 3, Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="d98ea-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="d98ea-109">Votre client doit avoir la capacité de la conférence de Skype pour entreprise activé.</span><span class="sxs-lookup"><span data-stu-id="d98ea-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="d98ea-110">Votre client doit avoir Exchange Online activé.</span><span class="sxs-lookup"><span data-stu-id="d98ea-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="d98ea-111">Votre administrateur client distant doit avoir les accès PowerShell suivants :</span><span class="sxs-lookup"><span data-stu-id="d98ea-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="d98ea-112">Accès PowerShell distant Exchange</span><span class="sxs-lookup"><span data-stu-id="d98ea-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="d98ea-113">Skype pour accès de PowerShell distant de professionnels en ligne</span><span class="sxs-lookup"><span data-stu-id="d98ea-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="d98ea-114">Windows Azure Active Directory Module pour Windows PowerShell pour l’accès à l’annuaire accès Office 365</span><span class="sxs-lookup"><span data-stu-id="d98ea-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="d98ea-115">Pour le compte Skype Room, la licence suivante est requise :</span><span class="sxs-lookup"><span data-stu-id="d98ea-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="d98ea-116">Un Skype pour Business Plan en ligne de 2 ou Office 365 E1 ou E3 licence est nécessaire pour permettre de réunions Skype.</span><span class="sxs-lookup"><span data-stu-id="d98ea-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="d98ea-117">Autorisant la pièce avec la fonctionnalité Voix Entreprise afin que la pièce peut être activée avec un numéro de téléphone, un Skype pour entreprise en ligne Plan 2 avec le module complémentaire de nuage PBX ou Office 365 E5 est requise (1).</span><span class="sxs-lookup"><span data-stu-id="d98ea-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="d98ea-118">La disponibilité du droit à la conférence RTC dans une réunion donnée est déterminée par la licence de l’organisateur de la réunion.</span><span class="sxs-lookup"><span data-stu-id="d98ea-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="d98ea-119">Une licence Exchange Online n’est pas requise pour le compte Skype Room car le compte doit être configuré comme un compte de boîte aux lettres de ressource.</span><span class="sxs-lookup"><span data-stu-id="d98ea-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="d98ea-120">Vue d’ensemble de la mise en service</span><span class="sxs-lookup"><span data-stu-id="d98ea-120">Provisioning overview</span></span>

<span data-ttu-id="d98ea-121">Le diagramme suivant fournit une vue d’ensemble du compte système local de Skype mise en service de flux dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="d98ea-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Procédures de déploiement de Skype Room System pour Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="d98ea-123">Identifier une nouvelle salle de conférence</span><span class="sxs-lookup"><span data-stu-id="d98ea-123">Identify a new conference room</span></span>

<span data-ttu-id="d98ea-124">Vous disposez peut-être déjà une boîte aux lettres de salle de ressources Exchange qui fournit la fonctionnalité de planification, ou vous pouvez créer une boîte aux lettres de ressources pour la première fois afin de faciliter le déploiement d’un système de salle de Skype.</span><span class="sxs-lookup"><span data-stu-id="d98ea-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="d98ea-125">Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client.</span><span class="sxs-lookup"><span data-stu-id="d98ea-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="d98ea-126">La fourniture en ligne d’Exchange et Skype pour les sections de la disposition de l’entreprise fournissent des instructions pour les deux types de comptes.</span><span class="sxs-lookup"><span data-stu-id="d98ea-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="d98ea-127">Par exemple, supposons que vous avez deux pièces suivants, et que vous souhaitez déployer le système d’espace Skype pour les deux :</span><span class="sxs-lookup"><span data-stu-id="d98ea-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="d98ea-128">Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d98ea-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="d98ea-129">Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d98ea-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="d98ea-130">Mise en service d’Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d98ea-130">Exchange Online provisioning</span></span>

<span data-ttu-id="d98ea-131">Tout d’abord se connecter à Exchange Online PowerShell en suivant les instructions de la rubrique, [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="d98ea-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="d98ea-132">Pour définir un compte de boîte aux lettres de salle ressource existant pour système de salle Skype, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d98ea-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="d98ea-133">Pour créer un nouveau compte de boîte aux lettres de ressources Exchange pour système de salle Skype, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d98ea-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="d98ea-134">Les commandes précédentes définir ou créer un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation du système de salle de Skype en activant le compte.</span><span class="sxs-lookup"><span data-stu-id="d98ea-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="d98ea-135">Après avoir créé la boîte aux lettres, vous pouvez utiliser l’applet de commande Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="d98ea-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="d98ea-136">Reportez-vous aux étapes 3 à 6 sous Déploiements locaux d’une forêt unique pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="d98ea-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="d98ea-137">Mise en service de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d98ea-137">Skype for Business Online provisioning</span></span>

<span data-ttu-id="d98ea-138">Une fois un compte de boîte aux lettres de salle de ressource a été créé et activé comme indiqué précédemment, le compte est synchronisées à partir de la forêt Exchange Online dans Skype pour Business Online de la forêt à l’aide de la forêt Active Directory de Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="d98ea-138">After a resource room mailbox account has been created and enabled as shown previously, the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="d98ea-139">Les étapes suivantes sont nécessaires pour mettre en service le compte système de salle de Skype dans le Skype pour le pool d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="d98ea-139">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="d98ea-140">Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), étant donné que lorsqu’elles sont activées dans Exchange en ligne, les deux de ces comptes seront synchronisés avec Skype pour l’activité en ligne de la même manière :</span><span class="sxs-lookup"><span data-stu-id="d98ea-140">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="d98ea-141">Créez une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="d98ea-141">Create a Remote PowerShell session.</span></span> <span data-ttu-id="d98ea-142">Notez que vous devrez télécharger Skype pour Module de connecteur Business en ligne et Assistant Microsoft Online Services Sign-In et vous assurer que votre ordinateur est configuré.</span><span class="sxs-lookup"><span data-stu-id="d98ea-142">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="d98ea-143">Pour plus d’informations, consultez [Configuration de votre ordinateur pour la gestion de Lync Online](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span><span class="sxs-lookup"><span data-stu-id="d98ea-143">For more information, see [Configuring Your Computer for Lync Online Management](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="d98ea-144">Pour activer un compte système local de Skype pour Skype pour entreprise, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d98ea-144">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="d98ea-145">Vous pouvez obtenir le RegistrarPool renvoie de l’adresse où votre Skype pour les utilisateurs professionnels sont hébergés à partir d’un de vos comptes existants à l’aide de la commande suivante pour cette propriété :</span><span class="sxs-lookup"><span data-stu-id="d98ea-145">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="d98ea-146">Attribution d’une licence Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="d98ea-146">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="d98ea-147">Après avoir activé un compte système local de Skype dans Skype pour les entreprises, vous pouvez affecter un Skype pour Business Online (Plan 2) ou Skype pour licence Business Online (Plan 3) à l’aide du portail d’administration d’Office 365, comme décrit dans [affecter ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou dans [Skype pour la licence de module complémentaire Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="d98ea-147">After you enable a Skype Room System account in Skype for Business, you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="d98ea-148">Après avoir attribué une licence pour Skype pour professionnels en ligne, vous serez en mesure de se connecter et valider que le compte est actif à l’aide de n’importe quel Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="d98ea-148">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="password-expiration"></a><span data-ttu-id="d98ea-149">Expiration du mot de passe</span><span class="sxs-lookup"><span data-stu-id="d98ea-149">Password expiration</span></span>

<span data-ttu-id="d98ea-150">Dans Office 365, la stratégie d’expiration du mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie différente d’expiration du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="d98ea-150">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="d98ea-151">Pour les comptes du système de salle de Skype, vous pouvez sélectionner le mot de passe n’expire jamais paramètre avec les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="d98ea-151">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="d98ea-152">Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur client global.</span><span class="sxs-lookup"><span data-stu-id="d98ea-152">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="d98ea-153">Définir le mot de passe n’expire jamais paramètre pour le compte de salle Skype espace système créé précédemment à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d98ea-153">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="d98ea-154">Pour plus d’informations, consultez [L’aide de Windows PowerShell pour gérer Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="d98ea-154">For more information, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  

