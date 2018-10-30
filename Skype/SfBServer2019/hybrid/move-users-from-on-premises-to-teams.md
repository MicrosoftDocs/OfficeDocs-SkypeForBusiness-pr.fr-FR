---
title: Déplacer les utilisateurs locaux vers des équipes
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Résumé : Découvrez comment migrer les paramètres utilisateur et de déplacer les utilisateurs à des équipes.'
ms.openlocfilehash: 76baa9cdc87535e68cc0bff4e9397a91d1090439
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838716"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="ed82b-103">Déplacer les utilisateurs locaux vers des équipes</span><span class="sxs-lookup"><span data-stu-id="ed82b-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="ed82b-104">Avec Skype pour Business Server 2019, vous pouvez migrer vos utilisateurs locaux aux équipes comme décrit dans cet article.</span><span class="sxs-lookup"><span data-stu-id="ed82b-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="ed82b-105">Gardez à l’esprit qu’après le déplacement de vos utilisateurs à des équipes :</span><span class="sxs-lookup"><span data-stu-id="ed82b-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="ed82b-106">Leurs réunions sont migrées vers Skype pour Business Online, et leurs contacts sont migrés vers les équipes.</span><span class="sxs-lookup"><span data-stu-id="ed82b-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="ed82b-107">Ils peuvent participer à des réunions Skype via le Skype pour le client riche Business (les utilisateurs ne sont pas invités pour la connexion chaque fois) ou par le biais de l’application de réunions Skype (requiert un téléchargement unique et une connexion).</span><span class="sxs-lookup"><span data-stu-id="ed82b-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="ed82b-108">Lorsqu’un utilisateur clique sur un Skype pour le lien de la réunion métiers au sein des équipes, la réunion est lancé dans l’application appropriée.</span><span class="sxs-lookup"><span data-stu-id="ed82b-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="ed82b-109">Sur Mobile, vos utilisateurs pourront participer à Skype existant pour les réunions d’entreprise à l’aide de l’application native uniquement.</span><span class="sxs-lookup"><span data-stu-id="ed82b-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

> [!NOTE]
> <span data-ttu-id="ed82b-110">Une fois un utilisateur est déplacé vers le mode TeamsOnly, l’utilisateur est hébergé dans Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="ed82b-110">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="ed82b-111">Conditions préalables pour le déplacement des utilisateurs locaux aux équipes</span><span class="sxs-lookup"><span data-stu-id="ed82b-111">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="ed82b-112">Cette section décrit les conditions préalables pour le déplacement de vos utilisateurs sur site aux équipes.</span><span class="sxs-lookup"><span data-stu-id="ed82b-112">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="ed82b-113">Il le faut :</span><span class="sxs-lookup"><span data-stu-id="ed82b-113">You must:</span></span>
- <span data-ttu-id="ed82b-114">[Configurer la connectivité hybride](#set-up-hybrid-connectivity) (si vous n’avez pas déjà fait)</span><span class="sxs-lookup"><span data-stu-id="ed82b-114">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="ed82b-115">[Informez les utilisateurs du déplacement aux équipes](#notify-your-users-of-the-move-to-teams) (facultatif)</span><span class="sxs-lookup"><span data-stu-id="ed82b-115">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="ed82b-116">Assurez-vous que vos utilisateurs disposent d’une licence valide</span><span class="sxs-lookup"><span data-stu-id="ed82b-116">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="ed82b-117">Prenez note des exigences de configuration vocale</span><span class="sxs-lookup"><span data-stu-id="ed82b-117">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="ed82b-118">[Attribuer une stratégie de mise à niveau des équipes](#assign-a-teams-upgrade-policy) (facultatif)</span><span class="sxs-lookup"><span data-stu-id="ed82b-118">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="ed82b-119">Configurer la connectivité hybride</span><span class="sxs-lookup"><span data-stu-id="ed82b-119">Set up hybrid connectivity</span></span>
<span data-ttu-id="ed82b-120">Avant de migrer vos utilisateurs, si vous n’avez pas déjà fait, vous devez vous assurer que vous avez configuré la connectivité hybride entre votre Skype pour l’environnement local de Business Server et le Skype pour Business Online.</span><span class="sxs-lookup"><span data-stu-id="ed82b-120">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="ed82b-121">Connectivité hybride nécessite la synchronisation Active Directory, configuration de la fédération et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="ed82b-121">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="ed82b-122">Pour plus d’informations, voir [planification de la connectivité hybride](plan-hybrid-connectivity.md) et de [connectivité de configuration hybride](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ed82b-122">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="ed82b-123">Informez les utilisateurs du déplacement aux équipes</span><span class="sxs-lookup"><span data-stu-id="ed82b-123">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="ed82b-124">Il s’agit d’une étape facultative, mais celle dont vous devez prendre en compte.</span><span class="sxs-lookup"><span data-stu-id="ed82b-124">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="ed82b-125">Pour avertir les utilisateurs de la mise à niveau d’équipes en attente, vous pouvez utiliser les applets de commande TeamsUpgradePolicy et TeamsUpgradeConfiguration du local.</span><span class="sxs-lookup"><span data-stu-id="ed82b-125">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="ed82b-126">Vous pouvez également configurer le téléchargement automatique en mode silencieux d’équipes en arrière-plan avant la mise à niveau (clients Win32 uniquement).</span><span class="sxs-lookup"><span data-stu-id="ed82b-126">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="ed82b-127">Par exemple, pour avertir les utilisateurs qu’ils sont mis à des équipes, utilisez l’applet de commande TeamsUpgradePolicy local avec le paramètre - NotifySbUser.</span><span class="sxs-lookup"><span data-stu-id="ed82b-127">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="ed82b-128">Vous pouvez définir la stratégie à un niveau global, site, de pool ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ed82b-128">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="ed82b-129">La commande suivante crée et accorde une stratégie au niveau de l’utilisateur :</span><span class="sxs-lookup"><span data-stu-id="ed82b-129">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="ed82b-130">Vous pouvez vérifier cette stratégie à l’aide de l’applet de commande Get-csTeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="ed82b-130">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="ed82b-131">Les utilisateurs verront une notification du déplacement imminente aux équipes.</span><span class="sxs-lookup"><span data-stu-id="ed82b-131">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="ed82b-132">La notification se produit Win32, Mac, Mobile et les Clients Web (avec la version de droite).</span><span class="sxs-lookup"><span data-stu-id="ed82b-132">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="ed82b-133">Vous pouvez spécifier le téléchargement automatique des équipes (pour les clients Win32) pour les utilisateurs à mettre à niveau à l’aide de l’applet de commande TeamsUpgradeConfiguration local avec le paramètre DownloadTeams.</span><span class="sxs-lookup"><span data-stu-id="ed82b-133">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="ed82b-134">Vous définissez cette stratégie au niveau du client, et il peut être appliqué à un site global et au niveau du pool.</span><span class="sxs-lookup"><span data-stu-id="ed82b-134">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="ed82b-135">Par exemple, la commande suivante définit la stratégie au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="ed82b-135">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="ed82b-136">Par défaut, la valeur de DownloadTeams a la valeur True, mais vous devez également définir NotifySfbUser sur True pour activer les équipes pour un utilisateur donné.</span><span class="sxs-lookup"><span data-stu-id="ed82b-136">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="ed82b-137">Assurez-vous que vos utilisateurs possèdent une licence valide</span><span class="sxs-lookup"><span data-stu-id="ed82b-137">Make sure your users have a valid license</span></span>  
<span data-ttu-id="ed82b-138">Avant la migration, locale doit être proposée à l’utilisateur une licence valide, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed82b-138">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="ed82b-139">Utilisateur doit avoir une licence d’équipes.</span><span class="sxs-lookup"><span data-stu-id="ed82b-139">User must have a Teams license.</span></span>
-   <span data-ttu-id="ed82b-140">Si l’utilisateur est configuré pour utiliser locale Enterprise Voice, il doivent avoir une licence vocale en ligne lors du déplacement.</span><span class="sxs-lookup"><span data-stu-id="ed82b-140">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="ed82b-141">Si l’utilisateur est configuré pour la conférence rendez-vous sur site, ils doivent possèdent une licence pour le système téléphonique (Cloud PBX).</span><span class="sxs-lookup"><span data-stu-id="ed82b-141">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="ed82b-142">Configuration requise de voix</span><span class="sxs-lookup"><span data-stu-id="ed82b-142">Voice configuration requirements</span></span>

<span data-ttu-id="ed82b-143">Si vos utilisateurs locaux ont vocal sur site, vous avez deux options :</span><span class="sxs-lookup"><span data-stu-id="ed82b-143">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="ed82b-144">**Migrer des utilisateurs grâce à des fonctionnalités de téléphonie.**</span><span class="sxs-lookup"><span data-stu-id="ed82b-144">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="ed82b-145">Les utilisateurs peuvent émettre et recevoir des appels à l’aide du client équipes.</span><span class="sxs-lookup"><span data-stu-id="ed82b-145">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="ed82b-146">Vous pouvez choisir Microsoft appelant planifier ou routage Direct pour connecter les services de téléphonie aux équipes.</span><span class="sxs-lookup"><span data-stu-id="ed82b-146">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="ed82b-147">Appel de Plan de Microsoft fournit une solution vocale tout-en nuage.</span><span class="sxs-lookup"><span data-stu-id="ed82b-147">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="ed82b-148">Pour plus d’informations sur l’appel de Plan de Microsoft, voir (lien bientôt disponible).</span><span class="sxs-lookup"><span data-stu-id="ed82b-148">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="ed82b-149">Routage direct vous permet d’utiliser pratiquement n’importe quel jonction PSTN, et vous pouvez configurer l’interopérabilité entre équipement téléphonique appartenant à un client et le système téléphonique de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed82b-149">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="ed82b-150">Pour plus d’informations, voir [Planifier le routage Direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) et [Configurer le routage Direct](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="ed82b-150">For more information, see [Plan Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="ed82b-151">**Migrer les utilisateurs sans fonctionnalités de téléphonie.**</span><span class="sxs-lookup"><span data-stu-id="ed82b-151">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="ed82b-152">Si vous migrez des utilisateurs sans conserver les fonctionnalités de téléphonie, assurez-vous que les utilisateurs ont des licences appropriés dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="ed82b-152">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="ed82b-153">Attribuer une stratégie de mise à niveau des équipes</span><span class="sxs-lookup"><span data-stu-id="ed82b-153">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="ed82b-154">Vous pouvez utiliser les outils en ligne pour gérer les stratégies d’utilisateur, telles que pour contrôler le routage des messages et les appels entrants.</span><span class="sxs-lookup"><span data-stu-id="ed82b-154">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="ed82b-155">Pour plus d’informations, consultez la rubrique (lien bientôt disponible).</span><span class="sxs-lookup"><span data-stu-id="ed82b-155">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="ed82b-156">Déplacer des utilisateurs locaux aux équipes</span><span class="sxs-lookup"><span data-stu-id="ed82b-156">Move on-premises users to Teams</span></span>

<span data-ttu-id="ed82b-157">Vous pouvez déplacer vos utilisateurs locaux aux équipes à l’aide des applets de commande PowerShell ou à l’aide de la Skype pour Business Server 2019 le panneau de configuration.</span><span class="sxs-lookup"><span data-stu-id="ed82b-157">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="ed82b-158">Déplacer les utilisateurs à l’aide de PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed82b-158">Move users by using PowerShell</span></span>
<span data-ttu-id="ed82b-159">Pour déplacer les utilisateurs vers les équipes à l’aide de PowerShell, vous allez utiliser l’applet de commande Move-CsUser avec le paramètre moveToTeams comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed82b-159">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="ed82b-160">($cred = get-informations d’identification.</span><span class="sxs-lookup"><span data-stu-id="ed82b-160">($cred = get-Credentials.</span></span> <span data-ttu-id="ed82b-161">Vous devez fournir les informations d’identification d’administration Office 365.)</span><span class="sxs-lookup"><span data-stu-id="ed82b-161">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="ed82b-162">Cette commande définit la TeamsInteropPolicy aux équipes et définit le TeamsUpgradePolicy en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="ed82b-162">This command sets the TeamsInteropPolicy to Teams and sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="ed82b-163">Après que le déplacement aux équipes se déroule correctement, Skype l’utilisateur pour client Business affichera le message suivant :</span><span class="sxs-lookup"><span data-stu-id="ed82b-163">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![Migration réussie au message d’équipes](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="ed82b-165">Notez que Skype pour les entreprises ne sera plus disponible pour les utilisateurs, sauf pour joindre une réunion.</span><span class="sxs-lookup"><span data-stu-id="ed82b-165">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="ed82b-166">Dans les cas rares, lors du déplacement de vos utilisateurs à des équipes, vous souhaiterez remplacer dans les conférences rendez-vous et à la fonctionnalité vocale en nuage.</span><span class="sxs-lookup"><span data-stu-id="ed82b-166">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="ed82b-167">Pour cela, à l’aide des paramètres suivants avec la commande Move-CsUser :</span><span class="sxs-lookup"><span data-stu-id="ed82b-167">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="ed82b-168">**BypassAudioConferencingCheck :** Si l’utilisateur a dans les conférences rendez-vous activé pour locale, l’utilisateur doit avoir également une licence AudioConf dans Office 365 avant de migrer.</span><span class="sxs-lookup"><span data-stu-id="ed82b-168">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="ed82b-169">Une fois la migration vers le nuage, l’utilisateur sera mis en service pour l’audioconférence dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="ed82b-169">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="ed82b-170">Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le nuage, mais n’utilisez pas la fonctionnalité de conférence audio, vous pouvez le substituer en spécifiant ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="ed82b-170">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="ed82b-171">**ByPassEnterpriseVoice :** Si l’utilisateur a Enterprise Voice est activé pour local, l’utilisateur doit disposer d’une licence Enterprise Voice dans Office 365 avant de migrer.</span><span class="sxs-lookup"><span data-stu-id="ed82b-171">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="ed82b-172">Après la migration vers le nuage, l’utilisateur sera mis en service pour la voix dans le nuage.</span><span class="sxs-lookup"><span data-stu-id="ed82b-172">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="ed82b-173">Si, pour une raison quelconque, vous souhaitez déplacer un utilisateur vers le nuage, mais n’utilisez pas la fonctionnalité vocale dans le nuage, vous pouvez substituer voix dans le nuage en spécifiant ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="ed82b-173">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="ed82b-174">Déplacer les utilisateurs à l’aide de la Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="ed82b-174">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="ed82b-175">Pour déplacer des utilisateurs aux équipes à l’aide de la Skype pour Business le panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="ed82b-175">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="ed82b-176">Ouvrez le Skype pour Business le panneau de configuration et se connecter à votre compte Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed82b-176">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="ed82b-177">Sélectionnez des **utilisateurs** dans le volet de navigation gauche, puis sélectionnez les utilisateurs à migrer.</span><span class="sxs-lookup"><span data-stu-id="ed82b-177">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="ed82b-178">Dans le menu **Action** , cliquez sur **déplacer les utilisateurs sélectionnés aux équipes**.</span><span class="sxs-lookup"><span data-stu-id="ed82b-178">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![Cliquez sur Suivant pour vérifier la migration](../media/migration-confirmation.png)
    
4. <span data-ttu-id="ed82b-180">Cliquez sur **suivant** pour confirmer votre migration.</span><span class="sxs-lookup"><span data-stu-id="ed82b-180">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="ed82b-181">Une fois que l’utilisateur est déplacé vers les équipes, vous verrez les confirmations comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed82b-181">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="ed82b-182">![Déplacer les utilisateurs confirmation](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="ed82b-182">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="ed82b-183">![Message que les utilisateurs ont été déplacés.](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="ed82b-183">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="ed82b-184">Si le déplacement n’a pas réussi, vous verrez un message comme suit :</span><span class="sxs-lookup"><span data-stu-id="ed82b-184">If the move was not successful, you will see a message like the following:</span></span>

![Message d’utilisateur n’a pas pu être déplacé.](../media/users-not-moved.png)
