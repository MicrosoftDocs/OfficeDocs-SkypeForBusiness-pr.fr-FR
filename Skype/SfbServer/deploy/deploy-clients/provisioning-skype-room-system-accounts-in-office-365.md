---
title: Mise en service de comptes Skype Room System dans Microsoft 365 et Office 365
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
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lisez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Microsoft 365 ou Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820844"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="95c2b-103">Mise en service de comptes Skype Room System dans Microsoft 365 et Office 365</span><span class="sxs-lookup"><span data-stu-id="95c2b-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="95c2b-104">Lisez cette rubrique pour en savoir plus sur la mise en service de comptes Skype Room System dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="95c2b-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="95c2b-105">La section suivante traite de la mise en service des comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="95c2b-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="95c2b-106">Conditions préalables pour Microsoft 365 et Office 365</span><span class="sxs-lookup"><span data-stu-id="95c2b-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="95c2b-107">Votre client en ligne doit respecter les conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="95c2b-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="95c2b-108">L’offre Microsoft 365 ou Office 365 doit inclure Skype Entreprise Online Plan 2 ou Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="95c2b-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="95c2b-109">Pour plus d’informations sur les plans Skype Entreprise Online, voir la [description du service Skype Entreprise Online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="95c2b-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="95c2b-110">La fonctionnalité de conférence de Skype Entreprise doit être activée pour votre client.</span><span class="sxs-lookup"><span data-stu-id="95c2b-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="95c2b-111">Exchange Online doit être activé pour votre client.</span><span class="sxs-lookup"><span data-stu-id="95c2b-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="95c2b-112">Votre administrateur distant client doit avoir l’accès PowerShell suivant :</span><span class="sxs-lookup"><span data-stu-id="95c2b-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="95c2b-113">Accès à PowerShell à distance Exchange</span><span class="sxs-lookup"><span data-stu-id="95c2b-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="95c2b-114">Accès PowerShell à distance Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95c2b-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="95c2b-115">Windows Azure module Active Directory pour Windows PowerShell accès à l’annuaire Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="95c2b-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="95c2b-116">Pour le compte Skype Room, les licences suivantes sont requises :</span><span class="sxs-lookup"><span data-stu-id="95c2b-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="95c2b-117">Une licence Skype Entreprise Online Plan 2 ou Office 365 E1 ou E3 est nécessaire pour activer les réunions Skype.</span><span class="sxs-lookup"><span data-stu-id="95c2b-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="95c2b-118">Pour activer la salle avec la fonctionnalité Voix Entreprise afin que la salle puisse être activée avec un numéro de téléphone, un plan Skype Entreprise Online 2 avec licence de système téléphonique ou Office 365 E5 est requis (1).</span><span class="sxs-lookup"><span data-stu-id="95c2b-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="95c2b-119">Si vous avez besoin de fonctionnalités de numérotation à partir d’une réunion, vous aurez besoin d’une audioconférence et d’une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="95c2b-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="95c2b-120">Si vous avez besoin de fonctionnalités d’appel sortant à partir d’une réunion, vous aurez besoin d’un forfait d’appels national ou national et international.</span><span class="sxs-lookup"><span data-stu-id="95c2b-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="95c2b-121">Une licence Exchange Online n’est pas requise pour le compte Skype Room, car le compte doit être configuré en tant que compte de boîte aux lettres de ressources.</span><span class="sxs-lookup"><span data-stu-id="95c2b-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="95c2b-122">Vue d’ensemble de l’approvisionnement</span><span class="sxs-lookup"><span data-stu-id="95c2b-122">Provisioning overview</span></span>

<span data-ttu-id="95c2b-123">Le diagramme suivant fournit une vue d’ensemble du flux de mise en service du compte Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="95c2b-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Étapes de mise en service de Skype Room System](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="95c2b-125">Identifier une nouvelle salle de conférence</span><span class="sxs-lookup"><span data-stu-id="95c2b-125">Identify a new conference room</span></span>

<span data-ttu-id="95c2b-126">Vous disposez peut-être déjà d’une boîte aux lettres de salle de ressources dans Exchange qui fournit la fonctionnalité de planification, ou vous créez peut-être une boîte aux lettres de ressources pour la première fois pour faciliter le déploiement de Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="95c2b-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="95c2b-127">Dans tous les cas, vous devez identifier un compte de salle à utiliser dans votre client.</span><span class="sxs-lookup"><span data-stu-id="95c2b-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="95c2b-128">Les sections Exchange Online Provision et Skype Entreprise Provision fournissent des conseils pour les deux types de comptes.</span><span class="sxs-lookup"><span data-stu-id="95c2b-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="95c2b-129">Par exemple, supposons que vous disposez des deux salles suivantes et que vous souhaitez déployer Skype Room System pour les deux salles :</span><span class="sxs-lookup"><span data-stu-id="95c2b-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="95c2b-130">Compte de boîte aux lettres de ressources existant : confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="95c2b-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="95c2b-131">Nouveau compte de boîte aux lettres de ressources : confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="95c2b-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="95c2b-132">Approvisionnement Exchange Online</span><span class="sxs-lookup"><span data-stu-id="95c2b-132">Exchange Online provisioning</span></span>

<span data-ttu-id="95c2b-133">Tout d’abord, connectez-vous à Exchange Online PowerShell en suivant les instructions de la rubrique, [Connectez-vous à Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="95c2b-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="95c2b-134">Pour définir un compte de boîte aux lettres de salle de ressources existant pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="95c2b-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="95c2b-135">Pour créer un compte de boîte aux lettres de ressources Exchange pour Skype Room System, exécutez les commandes suivantes dans Exchange Online PowerShell :</span><span class="sxs-lookup"><span data-stu-id="95c2b-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="95c2b-136">Les commandes précédentes permettent de configurer ou de créer un compte de boîte aux lettres de ressources Exchange pour l’utilisation de Skype Room System en activant le compte.</span><span class="sxs-lookup"><span data-stu-id="95c2b-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="95c2b-137">Après avoir créé la boîte aux lettres, vous pouvez utiliser la cmdlet Set-CalendarProcessing dans Exchange Online PowerShell pour configurer la boîte aux lettres.</span><span class="sxs-lookup"><span data-stu-id="95c2b-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="95c2b-138">Reportez-vous aux étapes 3 à 6 sous Déploiements locaux à forêt unique pour plus d’informations</span><span class="sxs-lookup"><span data-stu-id="95c2b-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="95c2b-139">Attribution d’une licence Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95c2b-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="95c2b-140">Vous pouvez à présent attribuer une licence Skype Entreprise Online (Plan 2) ou Skype Entreprise Online (Plan 3) à l’aide du portail d’administration Microsoft 365, comme décrit dans La procédure d’attribution ou de suppression de licences pour [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) entreprise ou dans la gestion des licences de modules [add-on Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Entreprise.</span><span class="sxs-lookup"><span data-stu-id="95c2b-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="95c2b-141">Après avoir attribué une licence pour Skype Entreprise Online, vous pourrez vous connecter et vérifier que le compte est actif à l’aide de n’importe quel client Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="95c2b-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="95c2b-142">Mise en service de Skype Entreprise Online</span><span class="sxs-lookup"><span data-stu-id="95c2b-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="95c2b-143">Une fois qu’un compte de boîte aux lettres de salle de ressources a été créé et activé comme indiqué précédemment, et que vous avez sous licence le compte pour Skype Entreprise Online, le compte sera synchronisé à partir de la forêt Exchange Online avec la forêt Skype Entreprise Online à l’aide de la forêt Active Directory Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="95c2b-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="95c2b-144">Les étapes suivantes sont nécessaires pour mettre en service le compte Skype Room System dans le pool Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="95c2b-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="95c2b-145">Ces étapes sont les mêmes pour un compte de boîte aux lettres de ressources existant ou un compte nouvellement créé (confrm1 ou confrm2), car une fois qu’ils sont activés dans Exchange Online, ces deux comptes seront synchronisés avec Skype Entreprise Online de la même manière :</span><span class="sxs-lookup"><span data-stu-id="95c2b-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="95c2b-146">Créez une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="95c2b-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="95c2b-147">Notez que vous devrez télécharger le module Connecteur Skype Entreprise Online et l’Assistant Microsoft Online Services Sign-In et vous assurer que votre ordinateur est configuré.</span><span class="sxs-lookup"><span data-stu-id="95c2b-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="95c2b-148">Pour plus d’informations, voir [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="95c2b-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="95c2b-149">Pour activer un compte Skype Room System pour Skype Entreprise, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="95c2b-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="95c2b-150">Vous pouvez obtenir l’adresse RegistrarPool dans laquelle vos utilisateurs Skype Entreprise sont homed à partir de l’un de vos comptes existants à l’aide de la commande suivante pour retourner cette propriété :</span><span class="sxs-lookup"><span data-stu-id="95c2b-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="95c2b-151">L’authentification multifacteur (MFA) n’est pas prise en charge pour les comptes Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="95c2b-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="95c2b-152">Expiration du mot de passe</span><span class="sxs-lookup"><span data-stu-id="95c2b-152">Password expiration</span></span>

<span data-ttu-id="95c2b-153">Dans Microsoft 365 ou Office 365, la stratégie d’expiration de mot de passe par défaut pour tous vos comptes d’utilisateurs est de 90 jours, sauf si vous configurez une stratégie d’expiration de mot de passe différente.</span><span class="sxs-lookup"><span data-stu-id="95c2b-153">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="95c2b-154">Pour les comptes Skype Room System, vous pouvez sélectionner le paramètre Mot de passe n’expire jamais en suivant les étapes ci-après.</span><span class="sxs-lookup"><span data-stu-id="95c2b-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="95c2b-155">Créez une session Active Directory Windows Azure à l’aide de vos informations d’identification d’administrateur général client.</span><span class="sxs-lookup"><span data-stu-id="95c2b-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="95c2b-156">Définissez le paramètre Mot de passe n’expire jamais pour le compte de salle Skype Room System créé précédemment à l’aide de la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="95c2b-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="95c2b-157">Pour plus d’informations, voir [Configurer votre ordinateur pour Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="95c2b-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="95c2b-158">Valider</span><span class="sxs-lookup"><span data-stu-id="95c2b-158">Validate</span></span>

<span data-ttu-id="95c2b-159">Pour la validation, vous devez être en mesure d’utiliser n’importe quel client Skype Entreprise pour vous inscrire au compte que vous avez créé.</span><span class="sxs-lookup"><span data-stu-id="95c2b-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

