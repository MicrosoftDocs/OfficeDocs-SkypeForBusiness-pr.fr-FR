---
title: Mise en service des comptes Skype Room System dans Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Consultez cette rubrique pour en savoir plus sur la mise en service des comptes Skype Room System dans Office 365.
ms.openlocfilehash: 141c833bcbdd744a7577c0762cb8ba55dd3d5c54
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037724"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="4557b-103">Mise en service des comptes Skype Room System dans Office 365</span><span class="sxs-lookup"><span data-stu-id="4557b-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="4557b-104">Consultez cette rubrique pour en savoir plus sur la mise en service des comptes Skype Room System dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="4557b-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="4557b-105">La section suivante traite de la mise en service des comptes Skype Room System pour un client Office 365.</span><span class="sxs-lookup"><span data-stu-id="4557b-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="4557b-106">Conditions préalables pour Office 365</span><span class="sxs-lookup"><span data-stu-id="4557b-106">Office 365 prerequisites</span></span>

<span data-ttu-id="4557b-107">Votre client en ligne doit remplir les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="4557b-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="4557b-108">Le plan Office 365 doit inclure Skype entreprise Online plan 2 ou Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="4557b-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="4557b-109">Pour plus d’informations sur les offres Skype entreprise Online, voir la [Description du service Skype entreprise Online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="4557b-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="4557b-110">La fonctionnalité de conférence de Skype entreprise doit être activée pour votre client.</span><span class="sxs-lookup"><span data-stu-id="4557b-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="4557b-111">Votre client doit avoir Exchange Online activé.</span><span class="sxs-lookup"><span data-stu-id="4557b-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="4557b-112">L’administrateur distant de votre client doit disposer de l’accès PowerShell suivant :</span><span class="sxs-lookup"><span data-stu-id="4557b-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="4557b-113">Accès à PowerShell à distance Exchange</span><span class="sxs-lookup"><span data-stu-id="4557b-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="4557b-114">Accès PowerShell à distance Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4557b-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="4557b-115">Module Windows Azure Active Directory pour Windows PowerShell pour accéder à l’accès à l’annuaire Office 365</span><span class="sxs-lookup"><span data-stu-id="4557b-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="4557b-116">Pour le compte Skype Room, la licence suivante est requise :</span><span class="sxs-lookup"><span data-stu-id="4557b-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="4557b-117">Une licence Skype entreprise Online plan 2 ou Office 365 E1 ou E3 est requise pour activer les réunions Skype.</span><span class="sxs-lookup"><span data-stu-id="4557b-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="4557b-118">Pour permettre à la salle de prendre en charge la fonctionnalité voix entreprise de sorte que la salle puisse être activée avec un numéro de téléphone, un site Skype entreprise Online plan 2 avec la licence du système téléphonique ou Office 365 E5 est requis (1).</span><span class="sxs-lookup"><span data-stu-id="4557b-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="4557b-119">Si vous avez besoin de fonctionnalités de rendez-vous à partir d’une réunion, vous aurez besoin d’une licence d’audioconférence et de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="4557b-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="4557b-120">Si vous avez besoin de fonctionnalités d’appels sortants à partir d’une réunion, vous aurez besoin d’un forfait d’appels nationaux ou internationaux.</span><span class="sxs-lookup"><span data-stu-id="4557b-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="4557b-121">Une licence Exchange Online n’est pas requise pour le compte de la salle Skype car le compte doit être configuré en tant que compte de boîte aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="4557b-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="4557b-122">Vue d’ensemble de la mise en service</span><span class="sxs-lookup"><span data-stu-id="4557b-122">Provisioning overview</span></span>

<span data-ttu-id="4557b-123">Le diagramme suivant fournit une vue d’ensemble du flux de mise en service du compte Skype Room System dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="4557b-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Étapes de mise en service de Skype Room System pour O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="4557b-125">Identifier une nouvelle salle de conférence</span><span class="sxs-lookup"><span data-stu-id="4557b-125">Identify a new conference room</span></span>

<span data-ttu-id="4557b-126">Vous disposez peut-être déjà d’une boîte aux lettres de salle de ressources dans Exchange qui fournit la fonctionnalité de planification, ou vous pouvez créer une boîte aux lettres de ressources pour la première fois afin de faciliter le déploiement de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4557b-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="4557b-127">Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client.</span><span class="sxs-lookup"><span data-stu-id="4557b-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="4557b-128">Les sections Exchange Online provision and Skype for Business provision fournissent des conseils pour les deux types de comptes.</span><span class="sxs-lookup"><span data-stu-id="4557b-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="4557b-129">Par exemple, supposons que vous disposez des deux salles suivantes et que vous souhaitez déployer Skype Room System pour les deux :</span><span class="sxs-lookup"><span data-stu-id="4557b-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="4557b-130">Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4557b-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="4557b-131">Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4557b-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="4557b-132">Mise en service d’Exchange Online</span><span class="sxs-lookup"><span data-stu-id="4557b-132">Exchange Online provisioning</span></span>

<span data-ttu-id="4557b-133">Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions de la rubrique, [Connectez-vous à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="4557b-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="4557b-134">Pour définir un compte de boîte aux lettres de salle de ressources existant pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="4557b-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="4557b-135">Pour créer un nouveau compte de boîte aux lettres de ressource Exchange pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="4557b-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="4557b-136">Les commandes précédentes configurent ou créent un nouveau compte de boîte aux lettres de ressources Exchange pour l’utilisation de Skype Room System en activant le compte.</span><span class="sxs-lookup"><span data-stu-id="4557b-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="4557b-137">Après avoir créé la boîte aux lettres, vous pouvez utiliser la cmdlet Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="4557b-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="4557b-138">Reportez-vous aux étapes 3 à 6 sous déploiements locaux d’une forêt unique pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="4557b-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="4557b-139">Affectation d’une licence Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4557b-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="4557b-140">À présent, vous pouvez attribuer une licence Skype entreprise Online (plan 2) ou Skype entreprise Online (plan 3) à l’aide du portail d’administration Office 365, comme décrit dans la rubrique [attribuer ou supprimer des licences pour office 365 pour les entreprises](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou dans les [licences de module complémentaire Skype entreprise](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="4557b-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="4557b-141">Après avoir attribué une licence pour Skype entreprise Online, vous serez en mesure de vous connecter et de confirmer que le compte est actif à l’aide de n’importe quel client Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="4557b-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="4557b-142">Mise en service de Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="4557b-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="4557b-143">Une fois qu’un compte de boîte aux lettres de salle de ressources a été créé et activé comme indiqué précédemment, et que vous disposez d’une licence pour le compte de Skype entreprise Online, le compte sera synchronisé entre la forêt Exchange Online et la forêt Skype entreprise Online à l’aide du Forêt Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="4557b-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="4557b-144">Les étapes suivantes sont nécessaires pour mettre en service le compte Skype Room System dans le pool Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="4557b-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="4557b-145">Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressource existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’elles sont activées dans Exchange Online, ces deux comptes sont synchronisés avec Skype entreprise Online de la même manière :</span><span class="sxs-lookup"><span data-stu-id="4557b-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="4557b-146">Créez une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="4557b-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="4557b-147">Notez que vous devrez télécharger le module du connecteur Skype entreprise Online et l’Assistant de connexion Microsoft Online Services et vous assurer que votre ordinateur est configuré.</span><span class="sxs-lookup"><span data-stu-id="4557b-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="4557b-148">Pour plus d’informations, reportez-vous à [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4557b-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="4557b-149">Pour activer un compte Skype Room System pour Skype entreprise, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4557b-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="4557b-150">Vous pouvez obtenir l’adresse RegistrarPool où vos utilisateurs Skype entreprise sont hébergés à partir de l’un de vos comptes existants à l’aide de la commande suivante pour renvoyer cette propriété :</span><span class="sxs-lookup"><span data-stu-id="4557b-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="4557b-151">L’authentification multifacteur (MFA) n’est pas prise en charge pour les comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="4557b-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="4557b-152">Expiration du mot de passe</span><span class="sxs-lookup"><span data-stu-id="4557b-152">Password expiration</span></span>

<span data-ttu-id="4557b-153">Dans Office 365, la stratégie d’expiration de mot de passe par défaut pour tous vos comptes d’utilisateur est de 90 jours, sauf si vous configurez une stratégie d’expiration de mot de passe différente.</span><span class="sxs-lookup"><span data-stu-id="4557b-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="4557b-154">Pour les comptes Skype Room System, vous pouvez sélectionner le paramètre le mot de passe n’expire jamais en suivant les étapes ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="4557b-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="4557b-155">Créez une session Windows Azure Active Directory à l’aide de vos informations d’identification d’administrateur général de client.</span><span class="sxs-lookup"><span data-stu-id="4557b-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="4557b-156">Définissez le paramètre le mot de passe n’expire jamais pour le compte de la salle des salles Skype créé précédemment à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="4557b-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="4557b-157">Pour plus d’informations, reportez-vous à [configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="4557b-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="4557b-158">Valider</span><span class="sxs-lookup"><span data-stu-id="4557b-158">Validate</span></span>

<span data-ttu-id="4557b-159">Pour la validation, vous devriez être en mesure d’utiliser n’importe quel client Skype entreprise pour vous connecter au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="4557b-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

