---
title: Activation des utilisateurs pour la version en ligne de Voix Entreprise et de la messagerie vocale du Système téléphonique
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Découvrez comment activer les services vocaux du système téléphonique pour vos utilisateurs Skype Entreprise.
ms.openlocfilehash: f1c59505073a7113407f28b7ebbe3a323724782e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098570"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="d16c3-103">Activation des utilisateurs pour la version en ligne de Voix Entreprise et de la messagerie vocale du Système téléphonique</span><span class="sxs-lookup"><span data-stu-id="d16c3-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="d16c3-104">Skype Entreprise Online sera retiré le 31 juillet 2021, après quoi le service ne sera plus accessible.</span><span class="sxs-lookup"><span data-stu-id="d16c3-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="d16c3-105">En outre, la connectivité PSTN entre votre environnement local via Skype Entreprise Server ou Cloud Connector Edition et Skype Entreprise Online ne sera plus prise en charge.</span><span class="sxs-lookup"><span data-stu-id="d16c3-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="d16c3-106">Découvrez comment connecter votre réseau téléphonique local à Teams à l’aide [du routage direct.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="d16c3-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="d16c3-107">Découvrez comment activer les services vocaux du système téléphonique pour vos utilisateurs Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="d16c3-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="d16c3-108">La dernière étape du déploiement du système téléphonique avec connectivité PSTN sur site consiste à activer vos utilisateurs pour le système téléphonique et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="d16c3-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="d16c3-109">Pour activer ces fonctionnalités, vous devez être un utilisateur avec le rôle Administrateur général et être en mesure d’exécuter PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="d16c3-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="d16c3-110">Vous devez suivre les étapes de cette rubrique pour tous les comptes d’utilisateurs pour Voix Entreprise pour Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="d16c3-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="d16c3-111">Activer les services vocaux du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="d16c3-111">Enable Phone System voice services</span></span>

<span data-ttu-id="d16c3-112">Pour activer un utilisateur pour la voix et la messagerie vocale du système téléphonique, vous devez effectuer certaines étapes initiales, comme vérifier si le connecteur Skype Entreprise Online est déployé sur vos serveurs et activer vos utilisateurs pour la messagerie vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="d16c3-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="d16c3-113">Pour activer vos utilisateurs pour la messagerie vocale et la messagerie vocale du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="d16c3-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="d16c3-114">Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="d16c3-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="d16c3-115">Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.</span><span class="sxs-lookup"><span data-stu-id="d16c3-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="d16c3-116">Avant de commencer, vérifiez que le module Teams PowerShell est installé sur vos serveurs frontux.</span><span class="sxs-lookup"><span data-stu-id="d16c3-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="d16c3-117">Si ce n’est pas le cas, installez-le en suivant les instructions de l’installation du [module Teams PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="d16c3-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d16c3-118">Commencez Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="d16c3-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="d16c3-119">Tapez ce qui suit et appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="d16c3-119">Type the following and press Enter:</span></span>
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. <span data-ttu-id="d16c3-120">Utilisez la cmdlet Set-CsUser pour affecter les propriétés $EnterpriseVoiceEnabled et $HostedVoiceMail à votre utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="d16c3-120">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="d16c3-121">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d16c3-121">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="d16c3-122">Vous pouvez également spécifier un utilisateur par son adresse SIP, son nom d’utilisateur principal (UPN), son nom de domaine et son nom d’utilisateur (domaine \nom d’utilisateur) et son nom d’affichage dans Active Directory (« Bob Kelly »).</span><span class="sxs-lookup"><span data-stu-id="d16c3-122">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="d16c3-123">Mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="d16c3-123">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="d16c3-124">Cette section décrit comment mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="d16c3-124">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="d16c3-125">Pour mettre à jour l’URI de ligne</span><span class="sxs-lookup"><span data-stu-id="d16c3-125">To update the Line URI</span></span>

1. <span data-ttu-id="d16c3-126">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="d16c3-126">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="d16c3-127">Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d16c3-127">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d16c3-128">Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="d16c3-128">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="d16c3-129">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="d16c3-129">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="d16c3-130">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="d16c3-130">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="d16c3-131">Dans le tableau, cliquez sur le compte d’utilisateur Skype Entreprise que vous souhaitez modifier l’URI de ligne.</span><span class="sxs-lookup"><span data-stu-id="d16c3-131">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="d16c3-132">Cliquez **sur URI** de ligne et tapez un numéro de téléphone unique et normal (par exemple, tel:+14255550200).</span><span class="sxs-lookup"><span data-stu-id="d16c3-132">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="d16c3-133">Cliquez ensuite sur **Valider.**</span><span class="sxs-lookup"><span data-stu-id="d16c3-133">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="d16c3-134">Mettre à jour le plan de numérotation à l’aide d’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="d16c3-134">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d16c3-135">Vous pouvez affecter des plans de numérotation par utilisateur Windows PowerShell et l’cmdlet [Grant-CsDialPlan.](/powershell/module/skype/grant-csdialplan?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="d16c3-135">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="d16c3-136">Vous pouvez exécuter cette cmdlet à partir de Skype Entreprise Server 2015 ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16c3-136">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="d16c3-137">Pour affecter un plan de numérotation par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="d16c3-137">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="d16c3-138">Utilisez [l’cmdlet Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) pour affecter le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="d16c3-138">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="d16c3-139">Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d16c3-139">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="d16c3-140">La commande suivante affecte le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="d16c3-140">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d16c3-141">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir la documentation de l';cmdlet [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="d16c3-141">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="d16c3-142">Vous pouvez utiliser des plans de numérotation globaux ou utilisateur pour les utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="d16c3-142">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="d16c3-143">Les plans de numérotation de site ne peuvent pas être utilisés, car ils s’appliquent uniquement aux utilisateurs hébergés sur site et affectés à un site local.</span><span class="sxs-lookup"><span data-stu-id="d16c3-143">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="d16c3-144">Pour désattribuer un plan de numérotation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="d16c3-144">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="d16c3-145">Utilisez [l’cmdlet Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) pour supprimer l’affectation d’un plan de numérotation par utilisateur précédemment affecté à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d16c3-145">Use the [Grant-CsDialPlan](/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="d16c3-146">Une fois le plan de numérotation par utilisateur non attribué, Ken Myer est automatiquement géré à l’aide du plan de numérotation global ou du plan de numérotation d’étendue service affecté à son bureau d’enregistrement ou à sa passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="d16c3-146">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="d16c3-147">Un plan de numérotation d’étendue service est prioritaire sur le plan de numérotation global :</span><span class="sxs-lookup"><span data-stu-id="d16c3-147">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="d16c3-148">Mettre à jour les stratégies de routage des voix à l’aide d’Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="d16c3-148">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d16c3-149">Cette section décrit comment mettre à jour les stratégies de routage des voix pour les utilisateurs activés pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="d16c3-149">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="d16c3-150">Une stratégie de routage des voix doit être attribuée aux utilisateurs du système téléphonique pour que les appels se routent correctement.</span><span class="sxs-lookup"><span data-stu-id="d16c3-150">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="d16c3-151">Cela diffère des utilisateurs de voix d’entreprise locaux qui ont besoin d’être affectés à une stratégie de voix pour permettre aux appels d’être acheminés correctement.</span><span class="sxs-lookup"><span data-stu-id="d16c3-151">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="d16c3-152">La stratégie de routage des voix doit contenir des utilisations PSTN qui définissent les appels et itinéraires autorisés pour les utilisateurs du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="d16c3-152">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="d16c3-153">Vous pouvez copier ces utilisations PSTN des stratégies de voix existantes vers les nouvelles stratégies de routage des voix.</span><span class="sxs-lookup"><span data-stu-id="d16c3-153">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="d16c3-154">Pour plus d’informations, [voir New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d16c3-154">For more information, see [New-CsVoiceRoutingPolicy](/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d16c3-155">Tous les utilisateurs du système téléphonique se voit attribuer la même stratégie de voix en ligne nommée BusinessVoice qui définit les fonctionnalités d’appel autorisées . par exemple, Autoriser l’anneau simultané.</span><span class="sxs-lookup"><span data-stu-id="d16c3-155">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="d16c3-156">Pour affecter une stratégie de routage des voix par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="d16c3-156">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="d16c3-157">Utilisez [l’cmdlet Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) pour affecter la stratégie de routage des voix par utilisateur RedmondVoiceRoutingPolicy à l’utilisateur Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="d16c3-157">Use the [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="d16c3-158">Pour affecter une stratégie de routage des voix par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="d16c3-158">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="d16c3-159">La commande suivante affecte la stratégie de routage des voix par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs qui travaillent dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="d16c3-159">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d16c3-160">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d16c3-160">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="d16c3-161">Vous pouvez utiliser des stratégies de routage des voix globales ou utilisateur pour les utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="d16c3-161">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="d16c3-162">Les stratégies de routage des voix de site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés sur site et affectés à un site local.</span><span class="sxs-lookup"><span data-stu-id="d16c3-162">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="d16c3-163">Pour désattribuer une stratégie de routage des voix par utilisateur</span><span class="sxs-lookup"><span data-stu-id="d16c3-163">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="d16c3-164">Utilisez la Grant-CsVoiceRoutingPolicy pour désattribuer une stratégie de routage des voix par utilisateur précédemment affectée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="d16c3-164">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="d16c3-165">Une fois la stratégie de routage des voix par utilisateur non résignée, Ken Myer est automatiquement géré à l’aide de la stratégie globale de routage des voix.</span><span class="sxs-lookup"><span data-stu-id="d16c3-165">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="d16c3-166">Pour plus d’informations, [voir Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="d16c3-166">For more information, see [Grant-CsVoiceRoutingPolicy](/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
