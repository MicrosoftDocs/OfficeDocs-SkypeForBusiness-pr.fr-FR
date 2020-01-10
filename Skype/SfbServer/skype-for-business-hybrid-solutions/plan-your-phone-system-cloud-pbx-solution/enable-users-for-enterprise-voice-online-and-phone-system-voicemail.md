---
title: Activation des utilisateurs pour la version en ligne de Voix Entreprise et le Système téléphonique dans la messagerie vocale Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Découvrez comment activer le système téléphonique dans les services vocaux Office 365 pour vos utilisateurs Skype entreprise.
ms.openlocfilehash: 902d2e1bad76c8275bfc8f4ce7ec7b4243b8572a
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003464"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a><span data-ttu-id="b8389-103">Activation des utilisateurs pour la version en ligne de Voix Entreprise et le Système téléphonique dans la messagerie vocale Office 365</span><span class="sxs-lookup"><span data-stu-id="b8389-103">Enable users for Enterprise Voice online and Phone System in Office 365 Voicemail</span></span>
 
<span data-ttu-id="b8389-104">Découvrez comment activer le système téléphonique dans les services vocaux Office 365 pour vos utilisateurs Skype entreprise.</span><span class="sxs-lookup"><span data-stu-id="b8389-104">Learn how to enable Phone System in Office 365 voice services for your Skype for Business users.</span></span>
  
<span data-ttu-id="b8389-105">La dernière étape du déploiement du système téléphonique dans Office 365 avec la connectivité PSTN locale consiste à activer vos utilisateurs pour le système téléphonique dans Office 365 et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="b8389-105">The final step in deploying Phone System in Office 365 with on-premises PSTN connectivity is to enable your users for Phone System in Office 365 and voicemail.</span></span> <span data-ttu-id="b8389-106">Pour activer ces fonctionnalités, vous devez disposer du rôle d’administrateur global Office 365, puis exécuter une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="b8389-106">To enable these capabilities, you must be a user with the Office 365 Global Administrator role, and be able to run remote PowerShell.</span></span> <span data-ttu-id="b8389-107">Vous devez suivre la procédure présentée dans cette rubrique pour les comptes d’utilisateur pour lesquels la fonctionnalité Voix Entreprise n’est pas activée dans Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="b8389-107">You need to follow the steps in this topic for all user accounts that do not already have Enterprise Voice enabled for Skype for Business Online.</span></span>
  
## <a name="enable-phone-system-in-office-365-voice-services"></a><span data-ttu-id="b8389-108">Activer le système téléphonique dans les services vocaux Office 365</span><span class="sxs-lookup"><span data-stu-id="b8389-108">Enable Phone System in Office 365 voice services</span></span>

<span data-ttu-id="b8389-109">Pour permettre à un utilisateur de système téléphonique dans Office 365 de voix et de boîte vocale, vous devez effectuer certaines étapes initiales, comme vérifier si le connecteur Skype entreprise Online est déployé sur vos serveurs et permettre à vos utilisateurs d’avoir une boîte vocale hébergée.</span><span class="sxs-lookup"><span data-stu-id="b8389-109">To enable a user for Phone System in Office 365 Voice and voicemail, you'll need to perform some initial steps, like checking to see if the Skype for Business Online Connector is deployed on your servers and enable your users for hosted voicemail.</span></span>
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a><span data-ttu-id="b8389-110">Pour permettre à vos utilisateurs de disposer d’un système téléphonique dans Office 365 de voix et de messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="b8389-110">To enable your users for Phone System in Office 365 voice and voicemail</span></span>

1. <span data-ttu-id="b8389-111">Avant de commencer, assurez-vous que le connecteur Skype entreprise Online (module Windows PowerShell) est déployé sur votre serveur frontal.</span><span class="sxs-lookup"><span data-stu-id="b8389-111">Before you begin, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="b8389-112">Si ce n’est pas le cas, vous pouvez le télécharger à partir [du centre de téléchargement](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="b8389-112">If it's not, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="b8389-113">Pour plus d’informations sur l’utilisation de ce module, voir [configurer votre ordinateur pour la gestion de Skype entreprise Online](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="b8389-113">You can find more information about using this module at [Configuring your computer for Skype for Business Online management](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).</span></span>
    
2. <span data-ttu-id="b8389-114">Démarrez Windows PowerShell en tant qu’administrateur.</span><span class="sxs-lookup"><span data-stu-id="b8389-114">Start Windows PowerShell as an administrator.</span></span>
    
3. <span data-ttu-id="b8389-115">Tapez la commande ci-dessous, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="b8389-115">Type the following and press Enter:</span></span>
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. <span data-ttu-id="b8389-116">Tapez la commande ci-dessous, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="b8389-116">Type the following and press Enter:</span></span>
    
   ```powershell
   $cred = Get-Credential
   ```

    <span data-ttu-id="b8389-117">Lorsque vous appuyez sur Entrée, la boîte de dialogue d’informations d’identification Windows PowerShell s’affiche.</span><span class="sxs-lookup"><span data-stu-id="b8389-117">After you press Enter, you should see the Windows PowerShell Credential dialog box.</span></span>
    
5. <span data-ttu-id="b8389-118">Tapez votre nom d’utilisateur et votre mot de passe d’administrateur des clients, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8389-118">Type your tenant admin username and password, and click **OK**.</span></span>
    
6. <span data-ttu-id="b8389-119">Dans la fenêtre PowerShell, tapez la commande ci-dessous, puis appuyez sur Entrée :</span><span class="sxs-lookup"><span data-stu-id="b8389-119">In the PowerShell window, type the following and press Enter:</span></span>
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. <span data-ttu-id="b8389-120">Importez la session en tapant l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b8389-120">Import the session by typing the following cmdlet:</span></span>
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    <span data-ttu-id="b8389-121">Lorsque vous exécutez PowerShell sur un serveur Skype entreprise, les applets de configuration Skype entreprise locales sont déjà chargées lorsque vous ouvrez PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8389-121">When running PowerShell on a Skype for Business Server, the local Skype for Business cmdlets are already loaded when you open PowerShell.</span></span> <span data-ttu-id="b8389-122">Vous devez spécifier le paramètre-AllowClobber pour permettre aux cmdlets en ligne d’écraser les applets de connexion locales portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="b8389-122">You must specify the -AllowClobber parameter to allow the online cmdlets to overwrite the on-premises cmdlets with the same name.</span></span>
    
8. <span data-ttu-id="b8389-123">Utilisez l’applet de commande Set-CsUser pour affecter les propriétés $EnterpriseVoiceEnabled et $HostedVoiceMail à votre utilisateur comme suit :</span><span class="sxs-lookup"><span data-stu-id="b8389-123">Use the Set-CsUser cmdlet to assign the $EnterpriseVoiceEnabled and $HostedVoiceMail properties to your user as follows:</span></span>
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    <span data-ttu-id="b8389-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b8389-124">For example:</span></span>
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > <span data-ttu-id="b8389-125">Vous pouvez également spécifier un utilisateur par son adresse SIP, nom d’utilisateur principal (UPN), nom de domaine et nom d’utilisateur (domaine\nom d’utilisateur) et le nom d’affichage dans Active Directory (« Bob Kelly »).</span><span class="sxs-lookup"><span data-stu-id="b8389-125">You can also specify a user by their SIP address, User Principal name (UPN), domain name and username (domain\username), and display name in Active Directory ("Bob Kelly").</span></span> 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a><span data-ttu-id="b8389-126">Mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs activés pour le système téléphonique dans Office 365</span><span class="sxs-lookup"><span data-stu-id="b8389-126">Update the Line URI and dial plan for users enabled for Phone System in Office 365</span></span>

<span data-ttu-id="b8389-127">Cette section explique comment mettre à jour l’URI de ligne et le plan de numérotation pour les utilisateurs autorisés à utiliser le système téléphonique dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8389-127">This section describes how to update the Line URI and dial plan for users enabled for Phone System in Office 365.</span></span> 
  
### <a name="to-update-the-line-uri"></a><span data-ttu-id="b8389-128">Pour mettre à jour l’URI de ligne</span><span class="sxs-lookup"><span data-stu-id="b8389-128">To update the Line URI</span></span>

1. <span data-ttu-id="b8389-129">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b8389-129">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="b8389-130">Utilisez le menu Démarrer ou le raccourci bureau pour ouvrir le Panneau de configuration de Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b8389-130">Use the Start menu or desktop shortcut to open the Skype for Business Server Control Panel.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b8389-131">Vous pouvez également ouvrir une fenêtre de navigateur, puis saisir l’URL de l’administrateur pour ouvrir le Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b8389-131">You can also open a browser window, and then enter the Administrator URL to open the Skype for Business Server Control Panel.</span></span> 
  
3. <span data-ttu-id="b8389-132">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="b8389-132">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="b8389-133">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="b8389-133">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="b8389-134">Dans le tableau, cliquez sur le compte d’utilisateur de Skype Entreprise dont vous souhaitez modifier l’URI de ligne.</span><span class="sxs-lookup"><span data-stu-id="b8389-134">In the table, click the Skype for Business user account that you want to change line URI.</span></span>
    
6. <span data-ttu-id="b8389-p104">Cliquez sur l’**URI de ligne**, puis saisissez un numéro de téléphone normalisé unique (par exemple, tél :+14255550200). Ensuite, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b8389-p104">Click **Line URI**, and type a unique, normalized phone number (for example, tel:+14255550200). Then click **Commit**.</span></span>
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="b8389-137">Mise à jour du plan de numérotation à l’aide d’applets de commande Windows PowerShell locales</span><span class="sxs-lookup"><span data-stu-id="b8389-137">Update the dial plan using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b8389-138">Vous pouvez affecter des plans de numérotation par utilisateur avec Windows PowerShell et l’applet [de connexion Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b8389-138">You can assign per-user dial plans with Windows PowerShell and the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="b8389-139">Vous pouvez exécuter cette applet de commande à partir de Skype entreprise Server 2015 ou d’une session à distance de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b8389-139">You can run this cmdlet either from the Skype for Business Server 2015 or from a remote session of Windows PowerShell.</span></span>
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="b8389-140">Pour affecter un plan de numérotation par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="b8389-140">To assign a per-user dial plan to a single user</span></span>

- <span data-ttu-id="b8389-141">Utilisez l’applet de connexion [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour attribuer le plan de numérotation de l’utilisateur RedmondDialPlan à l’utilisateur Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="b8389-141">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to assign the per-user dial plan RedmondDialPlan to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="b8389-142">Pour affecter un plan de numérotation par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b8389-142">To assign a per-user dial plan to multiple users</span></span>

- <span data-ttu-id="b8389-143">La commande suivante affecte le plan de numérotation par utilisateur RedmondDialPlan à tous les utilisateurs qui travaillent dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="b8389-143">The following command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="b8389-144">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, consultez la documentation de l’applet de commande [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :</span><span class="sxs-lookup"><span data-stu-id="b8389-144">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet:</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> <span data-ttu-id="b8389-p107">Vous pouvez utiliser les plans de numérotation de l’utilisateur ou globaux pour les utilisateurs en ligne. Les plans de numérotation du site ne peuvent pas être utilisés, car ils s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local.</span><span class="sxs-lookup"><span data-stu-id="b8389-p107">You may use either Global or User dial plans for online users. Site dial plans cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="b8389-147">Pour annuler l’affectation d’un plan de numérotation par utilisateur</span><span class="sxs-lookup"><span data-stu-id="b8389-147">To unassign a per-user dial plan</span></span>

- <span data-ttu-id="b8389-148">Utilisez l’applet de connexion [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) pour annuler l’affectation d’un plan de numérotation par utilisateur précédemment attribué à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b8389-148">Use the [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) cmdlet to unassign any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="b8389-149">Une fois l’affectation du plan de numérotation par utilisateur annulée, Ken Myer sera géré automatiquement à l’aide du plan de numérotation global ou du plan de numérotation à l’échelle du service affecté à son serveur d’inscriptions ou à sa passerelle PSTN.</span><span class="sxs-lookup"><span data-stu-id="b8389-149">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="b8389-150">Un plan de numérotation à l’échelle du service est prioritaire par rapport à tout plan de numérotation global.</span><span class="sxs-lookup"><span data-stu-id="b8389-150">A service scope dial plan takes precedence over the global dial plan:</span></span>
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a><span data-ttu-id="b8389-151">Mise à jour des stratégies de routage des communications vocales à l’aide d’applets de commande locales Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b8389-151">Update the voice routing policies using on-premises Windows PowerShell cmdlets</span></span>

<span data-ttu-id="b8389-152">Cette section explique comment mettre à jour les stratégies de routage vocal pour les utilisateurs activés pour le système téléphonique dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8389-152">This section describes how to update the voice routing policies for users enabled for Phone System in Office 365.</span></span>
  
<span data-ttu-id="b8389-153">Système téléphonique dans Office 365 les utilisateurs doivent disposer d’une stratégie de routage de la voix pour les appels vers les itinéraires réussis.</span><span class="sxs-lookup"><span data-stu-id="b8389-153">Phone System in Office 365 users must have a Voice Routing Policy assigned to them for calls to route successfully.</span></span> <span data-ttu-id="b8389-154">Cette affectation diffère de l’affectation d’une stratégie de voix aux utilisateurs professionnels de communications vocales, également nécessaire pour que les appels soient acheminés correctement.</span><span class="sxs-lookup"><span data-stu-id="b8389-154">This differs from on-premises business voice users who require a Voice Policy to be assigned to them to allow calls to route successfully.</span></span> <span data-ttu-id="b8389-155">La stratégie de routage de la voix doit contenir des utilisations PSTN qui définissent les appels et itinéraires autorisés pour le système téléphonique des utilisateurs d’Office 365.</span><span class="sxs-lookup"><span data-stu-id="b8389-155">The Voice Routing Policy should contain PSTN usages that define authorized calls and routes for Phone System in Office 365 users.</span></span> <span data-ttu-id="b8389-156">Vous pouvez copier les utilisations PSTN des stratégies de voix existantes pour les nouvelles stratégies de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="b8389-156">You can copy these PSTN usages from existing Voice Policies to new Voice Routing Policies.</span></span> <span data-ttu-id="b8389-157">Pour plus d’informations, consultez la rubrique [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b8389-157">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b8389-158">Tout le système téléphonique dans Office 365 les utilisateurs reçoivent la même stratégie vocale en ligne nommée BusinessVoice qui définit les fonctionnalités d’appel autorisées. par exemple, autorisez la sonnerie simultanée.</span><span class="sxs-lookup"><span data-stu-id="b8389-158">All Phone System in Office 365 users are assigned the same online Voice Policy named BusinessVoice which defines the calling features allowed; for example, Allow Simultaneous Ring.</span></span> 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a><span data-ttu-id="b8389-159">Pour affecter une stratégie de routage des communications vocales par utilisateur à un seul utilisateur</span><span class="sxs-lookup"><span data-stu-id="b8389-159">To assign a per-user voice routing policy to a single user</span></span>

- <span data-ttu-id="b8389-160">Utilisez l’applet de passe [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) pour affecter la stratégie de routage vocale par utilisateur RedmondVoiceRoutingPolicy à l’utilisateur Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="b8389-160">Use the [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) cmdlet to assign the per-user voice routing policy RedmondVoiceRoutingPolicy to the user Ken Myer:</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a><span data-ttu-id="b8389-161">Pour affecter une stratégie de routage des communications vocales par utilisateur à plusieurs utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b8389-161">To assign a per-user voice routing policy to multiple users</span></span>

- <span data-ttu-id="b8389-162">La commande suivante affecte la stratégie de routage des communications vocales par utilisateur RedmondVoiceRoutingPolicy à tous les utilisateurs travaillant dans la ville de Redmond.</span><span class="sxs-lookup"><span data-stu-id="b8389-162">The next command assigns the per-user voice routing policy RedmondVoiceRoutingPolicy to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="b8389-163">Pour plus d’informations sur le paramètre LdapFilter utilisé dans cette commande, voir [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b8389-163">For more information on the LdapFilter parameter used in this command, see [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).</span></span>
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > <span data-ttu-id="b8389-p111">Vous pouvez utiliser les stratégies de routage des communications vocales de l’utilisateur ou globales pour les utilisateurs en ligne. Les stratégies de routage des communications vocales du site ne peuvent pas être utilisées, car elles s’appliquent uniquement aux utilisateurs hébergés localement et affectés à un site local.</span><span class="sxs-lookup"><span data-stu-id="b8389-p111">You may use either Global or User voice routing policies for online users. Site voice routing policies cannot be used as these only apply to users who are hosted on premises and are assigned to an on-premises site.</span></span> 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a><span data-ttu-id="b8389-166">Pour annuler l’affectation d’une stratégie de routage des communications vocales par utilisateur</span><span class="sxs-lookup"><span data-stu-id="b8389-166">To unassign a per-user voice routing policy</span></span>

- <span data-ttu-id="b8389-167">Utilisez la fonction Grant-CsVoiceRoutingPolicy pour retirer toutes les stratégies de routage vocal par utilisateur précédemment affectées à Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="b8389-167">Use the Grant-CsVoiceRoutingPolicy to unassign any per-user voice routing policy previously assigned to Ken Myer.</span></span> <span data-ttu-id="b8389-168">Une fois l’affectation de la stratégie de routage des communications vocales par utilisateur annulée, Ken Myer sera automatiquement géré à l’aide de la stratégie globale de routage des communications vocales.</span><span class="sxs-lookup"><span data-stu-id="b8389-168">After the per-user voice routing policy is unassigned, Ken Myer will automatically be managed by using the global voice routing policy.</span></span>
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    <span data-ttu-id="b8389-169">Pour plus d’informations, reportez-vous à la rubrique [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b8389-169">For more information, see [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).</span></span>
    

