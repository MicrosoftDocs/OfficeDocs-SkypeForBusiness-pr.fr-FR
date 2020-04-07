---
title: Activer les utilisateurs pour le routage direct
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
description: Découvrez comment permettre aux utilisateurs du routage direct du système Microsoft Phone.
ms.openlocfilehash: 10c62d14f283d565765a47e4c07504bc9bffa720
ms.sourcegitcommit: 0fdc60840f45ff5b0a39a8ec4a21138f6cab49c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43160058"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="b64f0-103">Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="b64f0-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="b64f0-104">Cet article explique comment permettre aux utilisateurs de routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="b64f0-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="b64f0-105">Vous trouverez ci-dessous l’étape 2 de la procédure de configuration du routage direct :</span><span class="sxs-lookup"><span data-stu-id="b64f0-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="b64f0-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="b64f0-106">Step 1.</span></span> [<span data-ttu-id="b64f0-107">Connecter l’SBC avec un système Microsoft Phone et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="b64f0-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="b64f0-108">**Étape 2. Permettre aux utilisateurs d’utiliser le routage direct, la voix et** la boîte vocale (cet article)</span><span class="sxs-lookup"><span data-stu-id="b64f0-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="b64f0-109">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="b64f0-109">Step 3.</span></span> [<span data-ttu-id="b64f0-110">Configurer le routage de la voix</span><span class="sxs-lookup"><span data-stu-id="b64f0-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="b64f0-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="b64f0-111">Step 4.</span></span> [<span data-ttu-id="b64f0-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="b64f0-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="b64f0-113">Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b64f0-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="b64f0-114">Lorsque vous êtes prêt à activer les utilisateurs pour le routage direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b64f0-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="b64f0-115">Créez un utilisateur dans Office 365 et attribuez une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="b64f0-115">Create a user in Office 365 and assign a phone system license.</span></span> 
2. <span data-ttu-id="b64f0-116">Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="b64f0-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="b64f0-117">Configurez le numéro de téléphone et activez voix entreprise et boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="b64f0-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="b64f0-118">Affecter uniquement le mode équipe aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b64f0-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-in-office-365-and-assign-the-license"></a><span data-ttu-id="b64f0-119">Créer un utilisateur dans Office 365 et affecter la licence</span><span class="sxs-lookup"><span data-stu-id="b64f0-119">Create a user in Office 365 and assign the license</span></span> 

<span data-ttu-id="b64f0-120">Deux options s’offrent à vous pour créer un utilisateur dans Office 365.</span><span class="sxs-lookup"><span data-stu-id="b64f0-120">There are two options for creating a new user in Office 365.</span></span> <span data-ttu-id="b64f0-121">Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="b64f0-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="b64f0-122">Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud.</span><span class="sxs-lookup"><span data-stu-id="b64f0-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="b64f0-123">Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="b64f0-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="b64f0-124">Créer l’utilisateur directement dans le portail d’administration Office 365.</span><span class="sxs-lookup"><span data-stu-id="b64f0-124">Create the user directly in the Office 365 Administrator Portal.</span></span> <span data-ttu-id="b64f0-125">Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="b64f0-125">See [Add users individually or in bulk to Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="b64f0-126">Si votre déploiement de Skype entreprise Online existe avec Skype entreprise 2015 ou Lync 2010 ou 2013 sur site, la seule option prise en charge consiste à créer l’utilisateur dans l’annuaire Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1).</span><span class="sxs-lookup"><span data-stu-id="b64f0-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="b64f0-127">Pour plus d’informations sur la gestion des licences, voir gestion des [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements) dans [planifier le routage direct](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="b64f0-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="b64f0-128">Vérifier que l’utilisateur est bien immobilier dans Skype entreprise Online</span><span class="sxs-lookup"><span data-stu-id="b64f0-128">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="b64f0-129">Le routage direct nécessite que l’utilisateur soit hébergé dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="b64f0-129">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="b64f0-130">Vous pouvez vérifier en examinant le paramètre RegistrarPool, qui doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="b64f0-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="b64f0-131">Connectez-vous à Remote PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b64f0-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="b64f0-132">Émettez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b64f0-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="b64f0-133">Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise</span><span class="sxs-lookup"><span data-stu-id="b64f0-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="b64f0-134">Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer le numéro de téléphone de l’utilisateur et la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="b64f0-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="b64f0-135">Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b64f0-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="b64f0-136">Se connecter à une session PowerShell distante.</span><span class="sxs-lookup"><span data-stu-id="b64f0-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="b64f0-137">Entrez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="b64f0-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="b64f0-138">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Beaune Low », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="b64f0-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="b64f0-139">Le numéro de téléphone utilisé doit être configuré en tant que numéro de téléphone avec l’indicatif du pays.</span><span class="sxs-lookup"><span data-stu-id="b64f0-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="b64f0-140">Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b64f0-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="b64f0-141">Configurer l’envoi d’appels directement à la boîte vocale</span><span class="sxs-lookup"><span data-stu-id="b64f0-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="b64f0-142">Le routage direct vous permet de mettre fin à l’appel d’un utilisateur et de l’envoyer directement à la boîte vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b64f0-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="b64f0-143">Si vous voulez envoyer l’appel directement à la boîte vocale, attachez opaque = application : boîte vocale dans l’en-tête de la requête.</span><span class="sxs-lookup"><span data-stu-id="b64f0-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="b64f0-144">Par exemple, « SIP : user@yourdomain. com ; opaque = application : boîte vocale ».</span><span class="sxs-lookup"><span data-stu-id="b64f0-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="b64f0-145">Dans ce cas, l’utilisateur teams n’aura pas reçu la notification d’appel, l’appel sera connecté directement à la boîte vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="b64f0-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="b64f0-146">Attribuer le mode d’affectation uniquement aux utilisateurs pour s’assurer des appels terrestres dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="b64f0-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="b64f0-147">Le routage direct exige que les utilisateurs soient en mode d’équipe uniquement pour s’assurer que les appels entrants sont présents dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="b64f0-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="b64f0-148">Pour faire en sorte que les utilisateurs en mode équipes uniquement, attribuez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="b64f0-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="b64f0-149">Pour plus d’informations, consultez la rubrique [recommandations de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b64f0-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="b64f0-150">Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et teams : [migration et interopérabilité avec Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="b64f0-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b64f0-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b64f0-151">See also</span></span>

[<span data-ttu-id="b64f0-152">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="b64f0-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="b64f0-153">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="b64f0-153">Configure Direct Routing</span></span>](direct-routing-configure.md)
