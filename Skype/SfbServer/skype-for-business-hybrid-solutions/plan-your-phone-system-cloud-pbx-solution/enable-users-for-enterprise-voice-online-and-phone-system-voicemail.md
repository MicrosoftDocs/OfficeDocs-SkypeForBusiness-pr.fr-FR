---
title: Activer la messagerie vocale pour les utilisateurs de la messagerie vocale Enterprise Online et du système téléphonique
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
description: Découvrez comment activer les services vocaux de téléphonie pour vos utilisateurs de Skype entreprise.
ms.openlocfilehash: 76fbc20b11c0ec91685479d768b88abf71b65d21
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625110"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a><span data-ttu-id="f06f7-103">Activer la messagerie vocale pour les utilisateurs de la messagerie vocale Enterprise Online et du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f06f7-103">Enable users for Enterprise Voice online and Phone System Voicemail</span></span>
 
> [!Important]
> <span data-ttu-id="f06f7-104">Skype entreprise Online sera supprimé le 31 juillet 2021 après lequel le service ne sera plus accessible.</span><span class="sxs-lookup"><span data-stu-id="f06f7-104">Skype for Business Online will be retired on July 31, 2021 after which the service will no longer be accessible.</span></span>  <span data-ttu-id="f06f7-105">De plus, la connectivité PSTN entre votre environnement local, que ce soit via Skype entreprise Server ou Cloud Connector Edition et Skype entreprise Online, ne sera plus prise en charge.</span><span class="sxs-lookup"><span data-stu-id="f06f7-105">In addition, PSTN connectivity between your on-premises environment whether through Skype for Business Server or Cloud Connector Edition and Skype for Business Online will no longer be supported.</span></span>  <span data-ttu-id="f06f7-106">Découvrez comment connecter votre réseau téléphonique local à teams à l’aide du [routage direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="f06f7-106">Learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="f06f7-107">Découvrez comment activer les services vocaux de téléphonie pour vos utilisateurs de Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="f06f7-107">Learn how to enable Phone System voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="f06f7-108">La dernière étape du déploiement d’un système téléphonique avec une connectivité RTC sur site consiste à activer vos utilisateurs pour le système téléphonique et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="f06f7-108">The final step in deploying Phone System with on-premises PSTN connectivity is to enable your users for Phone System and voicemail.</span></span> <span data-ttu-id="f06f7-109">Pour activer ces fonctionnalités, vous devez être un utilisateur doté du rôle d’administrateur général et être en mesure d’exécuter PowerShell à distance.</span><span class="sxs-lookup"><span data-stu-id="f06f7-109">To enable these capabilities, you must be a user with the Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="f06f7-110">Vous devez suivre les étapes décrites dans cette rubrique pour tous les comptes d’utilisateur pour lesquels la fonctionnalité voix entreprise n’est pas encore activée pour Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="f06f7-110">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-voice-services"></a><span data-ttu-id="f06f7-111">Activer les services vocaux de système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f06f7-111">Enable Phone System voice services</span></span>

<span data-ttu-id="f06f7-112">Pour activer un utilisateur pour la voix et la messagerie vocale du système téléphonique, vous devez effectuer certaines opérations initiales, comme vérifier si le connecteur Skype entreprise Online est déployé sur vos serveurs et activer la messagerie vocale hébergée pour vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="f06f7-112">To enable a user for Phone System Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a><span data-ttu-id="f06f7-113">Pour activer les utilisateurs pour la voix et la messagerie vocale du système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f06f7-113">To enable your users for Phone System voice and voicemail</span></span>

> [!NOTE]
> <span data-ttu-id="f06f7-114">Le connecteur Skype entreprise Online fait actuellement partie du dernier module PowerShell Teams.</span><span class="sxs-lookup"><span data-stu-id="f06f7-114">Skype for Business Online Connector is currently part of latest Teams PowerShell Module.</span></span>
> <span data-ttu-id="f06f7-115">Si vous utilisez la version publique la plus récente [PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams/), vous n’avez pas besoin d’installer le connecteur Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="f06f7-115">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

1. <span data-ttu-id="f06f7-116">Avant de commencer, vérifiez que le module PowerShell teams est installé sur vos serveurs frontaux.</span><span class="sxs-lookup"><span data-stu-id="f06f7-116">Before you begin, check that the Teams PowerShell module is installed on your Front End Servers.</span></span> <span data-ttu-id="f06f7-117">Si ce n’est pas le cas, procédez à l’installation en utilisant les instructions de l' [installation du module PowerShell teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="f06f7-117">If it's not, please  install using the instructions in [Teams PowerShell Module Installation](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="f06f7-118">Démarrez Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="f06f7-118">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="f06f7-119">Tapez la commande ci-dessous, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="f06f7-119">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module MicrosoftTeams
   ```

4. <span data-ttu-id="f06f7-120">Tapez la commande ci-dessous, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="f06f7-120">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="f06f7-121">Une fois que vous avez appuyé sur entrée, la boîte de dialogue informations d’identification Windows PowerShell doit s’afficher.</span><span class="sxs-lookup"><span data-stu-id="f06f7-121">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="f06f7-122">Tapez le nom d’utilisateur et le mot de passe de votre administrateur client, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="f06f7-122">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="f06f7-123">Dans la fenêtre PowerShell, tapez la commande suivante, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="f06f7-123">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="f06f7-124">Importez la session en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="f06f7-124">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="f06f7-125">Lors de l’exécution de PowerShell sur un serveur Skype entreprise, les applets de commande locales de Skype entreprise sont déjà chargées lorsque vous ouvrez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f06f7-125">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="f06f7-126">Vous devez spécifier le paramètre-AllowClobber pour permettre aux cmdlets en ligne de remplacer les applets de commande locales portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="f06f7-126">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="f06f7-127">Utilisez l’applet de commande Set-CsUser pour attribuer les propriétés $EnterpriseVoiceEnabled et $HostedVoiceMail à votre utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="f06f7-127">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="f06f7-128">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="f06f7-128">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="f06f7-129">Vous pouvez également spécifier un utilisateur par son adresse SIP, nom d’utilisateur principal (UPN), nom de domaine et nom d’utilisateur (domaine\nom_utilisateur), et le nom d’affichage dans Active Directory (« Bob Kelly »).</span><span class="sxs-lookup"><span data-stu-id="f06f7-129">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a><span data-ttu-id="f06f7-130">Mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique</span><span class="sxs-lookup"><span data-stu-id="f06f7-130">Update the Line URI and dial plan for users enabled for Phone System</span></span>

<span data-ttu-id="f06f7-131">Cette section décrit comment mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="f06f7-131">This section describes how to update the Line URI and dial plan for users enabled for Phone System.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="f06f7-132">Pour mettre à jour l’URI de ligne</span><span class="sxs-lookup"><span data-stu-id="f06f7-132">To update the Line URI</span></span>

1. <span data-ttu-id="f06f7-133">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="f06f7-133">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="f06f7-134">Utilisez le menu Démarrer ou le raccourci Bureau pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f06f7-134">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f06f7-135">Vous pouvez également ouvrir une fenêtre de navigateur, puis entrer l’URL de l’administrateur pour ouvrir le panneau de configuration de Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="f06f7-135">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="f06f7-136">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="f06f7-136">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="f06f7-137">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="f06f7-137">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="f06f7-138">Dans le tableau, cliquez sur le compte d’utilisateur Skype entreprise dont vous souhaitez modifier l’URI de ligne.</span><span class="sxs-lookup"><span data-stu-id="f06f7-138">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="f06f7-139">Cliquez sur **URI de ligne**, puis tapez un numéro de téléphone normalisé unique (par exemple, tel : + 14255550200).</span><span class="sxs-lookup"><span data-stu-id="f06f7-139">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200).</span></span> <span data-ttu-id="f06f7-140">Ensuite, cliquez sur **valider**.</span><span class="sxs-lookup"><span data-stu-id="f06f7-140">Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="f06f7-141">Mettre à jour le plan de numérotation à l’aide des applets de commande Windows PowerShell locales</span><span class="sxs-lookup"><span data-stu-id="f06f7-141">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f06f7-142">Vous pouvez attribuer des plans de numérotation par utilisateur avec Windows PowerShell et l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="f06f7-142">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="f06f7-143">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server 2015 ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f06f7-143">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="f06f7-144">Pour affecter un plan de numérotation par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="f06f7-144">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="f06f7-145">Utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour affecter le plan de numérotation par utilisateur RedmondDialPlan à l’utilisateur Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="f06f7-145">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="f06f7-146">Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f06f7-146">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="f06f7-147">La commande suivante attribue le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="f06f7-147">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="f06f7-148">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, reportez-vous à la documentation de l’applet de commande [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="f06f7-148">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="f06f7-149">Vous pouvez utiliser des plans de numérotation de type utilisateur ou global pour les utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="f06f7-149">You may use either Global or User dial plans for online users.</span></span> <span data-ttu-id="f06f7-150">Les plans de numérotation de site ne peuvent pas être utilisés car ils s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local.</span><span class="sxs-lookup"><span data-stu-id="f06f7-150">Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="f06f7-151">Pour annuler l’affectation d’un plan de numérotation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="f06f7-151">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="f06f7-152">Utilisez l’applet de commande [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour annuler l’affectation d’un plan de numérotation par utilisateur précédemment affecté à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f06f7-152">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="f06f7-153">Une fois que le plan de numérotation par utilisateur n’est pas affecté, Ken Myer est automatiquement géré à l’aide du plan de numérotation global ou du plan de numérotation de l’étendue service affecté à son serveur d’inscriptions ou à sa passerelle RTC.</span><span class="sxs-lookup"><span data-stu-id="f06f7-153">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="f06f7-154">Un plan de numérotation d’étendue de service est prioritaire sur le plan de numérotation global :</span><span class="sxs-lookup"><span data-stu-id="f06f7-154">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="f06f7-155">Mettre à jour les stratégies de routage des communications vocales à l’aide des applets de commande locales Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f06f7-155">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="f06f7-156">Cette section décrit comment mettre à jour les stratégies de routage des communications vocales pour les utilisateurs activés pour le système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="f06f7-156">This section describes how to update the voice routing policies for users enabled for Phone System.</span></span>
  
<span data-ttu-id="f06f7-157">Les utilisateurs du système téléphonique doivent disposer d’une stratégie de routage des communications vocales pour que les appels soient acheminés correctement.</span><span class="sxs-lookup"><span data-stu-id="f06f7-157">Phone System users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="f06f7-158">Il en est de même pour les utilisateurs de voix entreprise sur site qui nécessitent une stratégie de voix qui leur est attribuée pour permettre l’acheminement des appels.</span><span class="sxs-lookup"><span data-stu-id="f06f7-158">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="f06f7-159">La stratégie de routage des communications vocales doit contenir des utilisations PSTN qui définissent les appels et itinéraires autorisés pour les utilisateurs du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="f06f7-159">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System users.</span></span> <span data-ttu-id="f06f7-160">Vous pouvez copier ces utilisations RTC à partir des stratégies de voix existantes vers les nouvelles stratégies de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="f06f7-160">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="f06f7-161">Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f06f7-161">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f06f7-162">Tous les utilisateurs du système téléphonique sont affectés à la même stratégie de voix en ligne nommée BusinessVoice qui définit les fonctionnalités d’appel autorisées ; par exemple, autoriser les sonneries simultanées.</span><span class="sxs-lookup"><span data-stu-id="f06f7-162">All Phone System users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="f06f7-163">Pour affecter une stratégie de routage des communications vocales par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="f06f7-163">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="f06f7-164">Utilisez l’applet de commande [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) pour affecter la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à l’utilisateur Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="f06f7-164">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="f06f7-165">Pour affecter une stratégie de routage des communications vocales par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="f06f7-165">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="f06f7-166">La commande suivante attribue la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs travaillant dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="f06f7-166">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="f06f7-167">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, consultez la rubrique [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f06f7-167">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="f06f7-168">Vous pouvez utiliser des stratégies de routage des communications vocales ou globales pour les utilisateurs en ligne.</span><span class="sxs-lookup"><span data-stu-id="f06f7-168">You may use either Global or User voice routing policies for online users.</span></span> <span data-ttu-id="f06f7-169">Les stratégies de routage des communications vocales du site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local.</span><span class="sxs-lookup"><span data-stu-id="f06f7-169">Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="f06f7-170">Pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur</span><span class="sxs-lookup"><span data-stu-id="f06f7-170">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="f06f7-171">Utilisez le Grant-CsVoiceRoutingPolicy pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur précédemment affectée à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="f06f7-171">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="f06f7-172">Une fois la stratégie de routage des communications vocales par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="f06f7-172">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="f06f7-173">Pour plus d’informations, consultez la rubrique [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f06f7-173">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

