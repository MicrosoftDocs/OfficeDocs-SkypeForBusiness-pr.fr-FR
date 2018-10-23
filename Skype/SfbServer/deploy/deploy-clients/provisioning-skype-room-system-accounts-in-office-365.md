---
title: Mise en service de comptes Skype Room System dans Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.
ms.openlocfilehash: 74512be2d097ca5f43fbd6a22ff17bba8040dd36
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699608"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="7959a-103">Mise en service de comptes Skype Room System dans Office 365</span><span class="sxs-lookup"><span data-stu-id="7959a-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="7959a-104">Consultez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="7959a-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="7959a-105">La section suivante traite de compte Skype salle système de mise en service pour un client Office 365.</span><span class="sxs-lookup"><span data-stu-id="7959a-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="7959a-106">Conditions préalables Office 365</span><span class="sxs-lookup"><span data-stu-id="7959a-106">Office 365 prerequisites</span></span>

<span data-ttu-id="7959a-107">Votre client en ligne doit répondre aux conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="7959a-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="7959a-108">Le plan Office 365 doit inclure Skype pour Business Online Plan 2, ou Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="7959a-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="7959a-109">Pour plus d’informations sur Skype pour Business Online Plans, voir le [Skype pour Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="7959a-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="7959a-110">Votre client doit avoir la fonctionnalité de conférence de Skype pour les entreprises activé.</span><span class="sxs-lookup"><span data-stu-id="7959a-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="7959a-111">Votre client doit avoir Exchange Online activé.</span><span class="sxs-lookup"><span data-stu-id="7959a-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="7959a-112">Votre administrateur client distant doit avoir les accès PowerShell suivants :</span><span class="sxs-lookup"><span data-stu-id="7959a-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="7959a-113">Accès PowerShell distant Exchange</span><span class="sxs-lookup"><span data-stu-id="7959a-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7959a-114">Skype pour l’accès Business Online PowerShell à distance</span><span class="sxs-lookup"><span data-stu-id="7959a-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="7959a-115">Windows Azure Active Directory Module pour Windows PowerShell à l’accès à l’annuaire access Office 365</span><span class="sxs-lookup"><span data-stu-id="7959a-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="7959a-116">Pour le compte Skype Room, la licence suivante est requise :</span><span class="sxs-lookup"><span data-stu-id="7959a-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="7959a-117">Un Skype pour Business Online Plan 2 ou Office 365 E1 ou E3 licence est nécessaire pour activer les réunions Skype.</span><span class="sxs-lookup"><span data-stu-id="7959a-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="7959a-118">Autorisant la salle avec la fonctionnalité voix entreprise afin que la salle peut être activée avec un numéro de téléphone, un Skype pour Business Online Plan 2 avec la licence de système téléphonique ou Office 365 E5 est requise (1).</span><span class="sxs-lookup"><span data-stu-id="7959a-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="7959a-119">Si vous avez besoin des fonctionnalités de rendez-vous à partir d’une réunion, vous devez une conférence audio et la licence du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="7959a-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="7959a-120">Si vous avez besoin des fonctionnalités d’appel sortant à partir d’une réunion, vous devez a internes ou nationales et internationales appelant Plan.</span><span class="sxs-lookup"><span data-stu-id="7959a-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="7959a-121">Une licence Exchange Online n’est pas requise pour le compte Skype Room car le compte doit être configuré comme un compte de boîte aux lettres de ressource.</span><span class="sxs-lookup"><span data-stu-id="7959a-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="7959a-122">Vue d’ensemble de la mise en service</span><span class="sxs-lookup"><span data-stu-id="7959a-122">Provisioning overview</span></span>

<span data-ttu-id="7959a-123">Le diagramme suivant fournit une vue d’ensemble du compte Skype salle système mise en service des flux dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="7959a-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Procédures de déploiement de Skype Room System pour Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="7959a-125">Identifier une nouvelle salle de conférence</span><span class="sxs-lookup"><span data-stu-id="7959a-125">Identify a new conference room</span></span>

<span data-ttu-id="7959a-126">Est peut-être déjà une boîte aux lettres de salle de ressource dans Exchange qui fournit la fonctionnalité de planification, ou vous pouvez créer une boîte aux lettres de ressources pour la première fois faciliter le déploiement du système de salle Skype.</span><span class="sxs-lookup"><span data-stu-id="7959a-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="7959a-127">Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client.</span><span class="sxs-lookup"><span data-stu-id="7959a-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="7959a-128">La mise en service en ligne Exchange et Skype pour les sections de la mise en service de l’entreprise fournissent des instructions pour les deux types de comptes.</span><span class="sxs-lookup"><span data-stu-id="7959a-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="7959a-129">Par exemple, supposons que vous avez les deux locaux suivants, et vous souhaitez déployer salle Skype pour chacun d'entre eux :</span><span class="sxs-lookup"><span data-stu-id="7959a-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="7959a-130">Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7959a-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="7959a-131">Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="7959a-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="7959a-132">Mise en service d’Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7959a-132">Exchange Online provisioning</span></span>

<span data-ttu-id="7959a-133">Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions fournies dans la rubrique, [se connecter à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="7959a-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="7959a-134">Pour configurer un compte de boîte aux lettres de salle ressource existant pour Skype salle système, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="7959a-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7959a-135">Pour créer un nouveau compte de boîte aux lettres de ressources Exchange pour Skype salle système, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="7959a-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="7959a-136">Les commandes précédentes définir ou créer un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation du système de salle Skype à l’activation du compte.</span><span class="sxs-lookup"><span data-stu-id="7959a-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="7959a-137">Après avoir créé la boîte aux lettres, vous pouvez utiliser l’applet de commande Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="7959a-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="7959a-138">Reportez-vous aux étapes 3 à 6 sous Déploiements locaux d’une forêt unique pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="7959a-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="7959a-139">Attribution d’une licence Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7959a-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="7959a-140">Maintenant vous pouvez assigner un Skype pour Business Online (Plan 2) ou Skype licence entreprise Online (Plan 3) à l’aide du portail d’administration d’Office 365, comme décrit dans [affecter ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou [Skype pour le module complémentaire Business gestion des licences](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="7959a-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="7959a-141">Après avoir attribué une licence pour Skype pour Business Online, vous serez en mesure de se connecter et vérifier que le compte est actif à l’aide de n’importe quel Skype pour client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="7959a-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="7959a-142">Mise en service de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="7959a-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="7959a-143">Après une salle de ressource compte de boîte aux lettres a été créé et activé comme indiqué précédemment, et le compte d’avoir une licence pour Skype pour Business Online le compte seront synchronisées à partir de la forêt Exchange Online dans Skype pour la forêt Business Online à l’aide de la Forêt de Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7959a-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="7959a-144">Les étapes suivantes sont nécessaires pour mettre en service le compte de système de salle Skype dans le Skype pour le pool d’entreprise en ligne.</span><span class="sxs-lookup"><span data-stu-id="7959a-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="7959a-145">Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’ils sont activés dans Exchange Online, les deux de ces comptes seront synchronisés avec Skype pour Business Online de la même manière :</span><span class="sxs-lookup"><span data-stu-id="7959a-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="7959a-146">Créez une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="7959a-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="7959a-147">Notez que vous devrez télécharger Skype pour Module connecteur en ligne d’entreprise et Microsoft Online Services Assistant de connexion et assurez-vous que votre ordinateur est configuré.</span><span class="sxs-lookup"><span data-stu-id="7959a-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="7959a-148">Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7959a-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="7959a-149">Pour activer un compte de système de salle Skype pour Skype pour les entreprises, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7959a-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="7959a-150">Vous pouvez obtenir RegistrarPool renvoie adresse où votre Skype pour les utilisateurs sont hébergés à partir d’un de vos comptes existants à l’aide de la commande suivante pour cette propriété :</span><span class="sxs-lookup"><span data-stu-id="7959a-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="7959a-151">Expiration du mot de passe</span><span class="sxs-lookup"><span data-stu-id="7959a-151">Password expiration</span></span>

<span data-ttu-id="7959a-152">Dans Office 365, la stratégie d’expiration du mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie différente d’expiration du mot de passe.</span><span class="sxs-lookup"><span data-stu-id="7959a-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="7959a-153">Pour les comptes Skype salle système, vous pouvez sélectionner le mot de passe n’expire jamais paramètre avec les étapes suivantes.</span><span class="sxs-lookup"><span data-stu-id="7959a-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="7959a-154">Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur client global.</span><span class="sxs-lookup"><span data-stu-id="7959a-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="7959a-155">Définir le mot de passe n’expire jamais paramètre pour le compte de salle Skype salle système précédemment créé à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="7959a-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="7959a-156">Pour plus d’informations, voir [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="7959a-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="7959a-157">Valider</span><span class="sxs-lookup"><span data-stu-id="7959a-157">Validate</span></span>

<span data-ttu-id="7959a-158">Pour la validation, vous devez être en mesure d’utiliser n’importe quel Skype pour client d’entreprise pour vous connecter au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="7959a-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

