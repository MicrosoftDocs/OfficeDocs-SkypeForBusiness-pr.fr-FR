---
title: Activer le routage direct pour les utilisateurs
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment permettre aux utilisateurs d Téléphone Microsoft routage direct du système.
ms.openlocfilehash: 858b9073106945d414c2dbe56a16e6cecd104ee7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122218"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="0c8d7-103">Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="0c8d7-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="0c8d7-104">Cet article explique comment permettre aux utilisateurs d’obtenir Système téléphonique routage direct.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="0c8d7-105">Voici l’étape 2 de la procédure de configuration du routage direct :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="0c8d7-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-106">Step 1.</span></span> [<span data-ttu-id="0c8d7-107">Connecter SBC avec Téléphone Microsoft et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="0c8d7-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="0c8d7-108">**Étape 2. Activer les utilisateurs pour le routage direct, la voix et la messagerie vocale**   (cet article)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="0c8d7-109">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-109">Step 3.</span></span> [<span data-ttu-id="0c8d7-110">Configurer le routage vocal</span><span class="sxs-lookup"><span data-stu-id="0c8d7-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="0c8d7-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-111">Step 4.</span></span> [<span data-ttu-id="0c8d7-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="0c8d7-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="0c8d7-113">Pour plus d’informations sur les étapes requises pour configurer le routage direct, voir [Configurer le routage direct.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="0c8d7-114">Lorsque vous êtes prêt à activer le routage direct pour les utilisateurs, suivez ces étapes :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="0c8d7-115">Créez un utilisateur dans Microsoft 365 ou Office 365 et attribuez une licence Système téléphonique utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="0c8d7-116">Assurez-vous que l’utilisateur est bien familialement Skype Entreprise Online.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="0c8d7-117">Configurez le numéro de téléphone et activez la voix entreprise et la messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="0c8d7-118">Affectez Teams mode uniquement aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="0c8d7-119">Créer un utilisateur et attribuer la licence</span><span class="sxs-lookup"><span data-stu-id="0c8d7-119">Create a user and assign the license</span></span> 

<span data-ttu-id="0c8d7-120">Deux options s’offrent à vous pour créer un utilisateur dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0c8d7-121">Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="0c8d7-122">Créez l’utilisateur dans Active Directory local et synchronisez l’utilisateur avec le cloud.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="0c8d7-123">Consultez [Intégrer vos annuaires locaux à Azure Active Directory.](/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="0c8d7-124">Créez l’utilisateur directement dans le Microsoft 365 d’administration.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0c8d7-125">Voir [Ajouter des utilisateurs individuellement ou en bloc Microsoft 365 ou Office 365 - Aide de l’administrateur.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="0c8d7-126">Si votre déploiement Skype Entreprise Online coexiste avec Skype Entreprise 2015 ou Lync 2010 ou 2013 en local, la seule option prise en charge consiste à créer l’utilisateur dans l’Active Directory local et à le synchroniser avec le cloud (option 1).</span><span class="sxs-lookup"><span data-stu-id="0c8d7-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="0c8d7-127">Pour plus d’informations sur les conditions de licence, voir licences et [autres conditions requises](direct-routing-plan.md#licensing-and-other-requirements) dans [Planifier le routage direct.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="0c8d7-128">Vérifier que l’utilisateur est domicile en ligne et que le numéro de téléphone n’est pas synchronisé à partir de l’ordinateur local (applicable aux utilisateurs Skype Entreprise Server Voix Entreprise en cours de migration vers Teams Routage direct)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="0c8d7-129">Le routage direct nécessite que l’utilisateur soit domicile en ligne.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="0c8d7-130">Vous pouvez vérifier le paramètre RegistrarPool, qui doit avoir une valeur dans infra.lync.com domaine.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="0c8d7-131">Le paramètre OnPremLineUriManuallySet doit également être réglé sur True.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="0c8d7-132">Pour ce faire, configurez le numéro de téléphone et activez la voix entreprise et la messagerie vocale à l’aide de Skype Entreprise PowerShell en ligne.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="0c8d7-133">Connecter une session Skype Entreprise PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="0c8d7-134">Émettre la commande :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="0c8d7-135">Si OnPremLineUriManuallySet est configuré sur False et LineUri est rempli avec un> de numéro de téléphone <E.164, nettoyez les paramètres à l’aide de l’environnement de ligne Skype Entreprise Management Shell local avant de configurer le numéro de téléphone à l’aide de Skype Entreprise Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="0c8d7-136">À partir Skype Entreprise Management Shell, émettre la commande :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="0c8d7-137">Une fois les modifications synchronisées sur Office 365 la sortie `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` attendue serait :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="0c8d7-138">Configurer le numéro de téléphone et activer la messagerie vocale et la messagerie vocale d’entreprise</span><span class="sxs-lookup"><span data-stu-id="0c8d7-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="0c8d7-139">Après avoir créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer son numéro de téléphone et sa messagerie vocale.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="0c8d7-140">Pour ajouter le numéro de téléphone et activer la messagerie vocale :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="0c8d7-141">Connecter une session Skype Entreprise PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="0c8d7-142">Émettre la commande :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="0c8d7-143">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Contrôle faible », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="0c8d7-144">Si les utilisateurs « Sont petits » et « Qu’ils partagent le même numéro de base avec des extensions uniques », entrez les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="0c8d7-145">Il est recommandé, mais pas obligatoire, que le numéro de téléphone utilisé soit configuré comme numéro de téléphone E.164 complet avec l’code du pays.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="0c8d7-146">Il est pris en charge pour configurer des numéros de téléphone avec des extensions qui seront utilisés pour rechercher des utilisateurs lorsque la recherche par rapport au numéro de base renvoie plusieurs résultats.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="0c8d7-147">Cela permet aux entreprises de configurer des numéros de téléphone avec le même numéro de base et des extensions uniques.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="0c8d7-148">Pour que la recherche soit réussie, l’invitation doit inclure le numéro complet avec l’extension suivante :</span><span class="sxs-lookup"><span data-stu-id="0c8d7-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="0c8d7-149">Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’shell de gestion Skype Entreprise local ou le Panneau de configuration pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="0c8d7-150">Configuration de l’envoi d’appels directement sur la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="0c8d7-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="0c8d7-151">Le routage direct vous permet de mettre fin à l’appel à un utilisateur et de l’envoyer directement à la messagerie vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="0c8d7-152">Si vous voulez envoyer l’appel directement sur la messagerie vocale, joignez opaque=application:voicemail à l’en-tête URI de demande.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="0c8d7-153">Par exemple, « sip:user@yourdomain.com;opaque=app:voicemail ».</span><span class="sxs-lookup"><span data-stu-id="0c8d7-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="0c8d7-154">Dans ce cas, l Teams de l’utilisateur ne reçoit pas la notification d’appel, l’appel est connecté directement à la messagerie vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="0c8d7-155">Affecter Teams mode uniquement aux utilisateurs pour s’assurer que les appels sont bien Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0c8d7-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="0c8d7-156">Le routage direct nécessite que les utilisateurs soient en Teams uniquement pour s’assurer que les appels entrants arrivent dans Teams client.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="0c8d7-157">Pour mettre les utilisateurs en Teams mode Uniquement, affectez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="0c8d7-158">Pour plus d’informations, voir [Stratégies de mise à niveau pour les administrateurs informatiques.](upgrade-to-teams-on-prem-implement.md)</span><span class="sxs-lookup"><span data-stu-id="0c8d7-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="0c8d7-159">Si votre organisation utilise Skype Entreprise Server ou Skype Entreprise Online, consultez l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et Teams : [migration](migration-interop-guidance-for-teams-with-skype.md)et interopérabilité avec Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c8d7-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0c8d7-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0c8d7-160">See also</span></span>

[<span data-ttu-id="0c8d7-161">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="0c8d7-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="0c8d7-162">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="0c8d7-162">Configure Direct Routing</span></span>](direct-routing-configure.md)