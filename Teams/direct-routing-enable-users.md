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
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655481"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="0795b-103">Permettre aux utilisateurs d’utiliser le routage direct, les appels vocaux et la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="0795b-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="0795b-104">Cet article explique comment permettre aux utilisateurs de routage direct du système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="0795b-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="0795b-105">Vous trouverez ci-dessous l’étape 2 de la procédure de configuration du routage direct :</span><span class="sxs-lookup"><span data-stu-id="0795b-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="0795b-106">Étape 1.</span><span class="sxs-lookup"><span data-stu-id="0795b-106">Step 1.</span></span> [<span data-ttu-id="0795b-107">Connecter l’SBC avec un système Microsoft Phone et valider la connexion</span><span class="sxs-lookup"><span data-stu-id="0795b-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="0795b-108">**Étape 2. Permettre aux utilisateurs d’utiliser le routage direct, la voix et**   la boîte vocale (cet article)</span><span class="sxs-lookup"><span data-stu-id="0795b-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="0795b-109">Étape 3.</span><span class="sxs-lookup"><span data-stu-id="0795b-109">Step 3.</span></span> [<span data-ttu-id="0795b-110">Configurer le routage de la voix</span><span class="sxs-lookup"><span data-stu-id="0795b-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="0795b-111">Étape 4.</span><span class="sxs-lookup"><span data-stu-id="0795b-111">Step 4.</span></span> [<span data-ttu-id="0795b-112">Traduire des nombres dans un autre format</span><span class="sxs-lookup"><span data-stu-id="0795b-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="0795b-113">Pour plus d’informations sur la procédure de configuration du routage direct, voir [configurer le routage direct](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="0795b-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="0795b-114">Lorsque vous êtes prêt à activer les utilisateurs pour le routage direct, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0795b-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="0795b-115">Créez un utilisateur dans Microsoft 365 ou Office 365 et attribuez une licence de système téléphonique.</span><span class="sxs-lookup"><span data-stu-id="0795b-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="0795b-116">Assurez-vous que l’utilisateur est bien immobilier dans Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0795b-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="0795b-117">Configurez le numéro de téléphone et activez voix entreprise et boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="0795b-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="0795b-118">Affecter uniquement le mode équipe aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0795b-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="0795b-119">Créer un utilisateur et lui attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="0795b-119">Create a user and assign the license</span></span> 

<span data-ttu-id="0795b-120">Deux options s’offrent à vous pour créer un utilisateur dans Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="0795b-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="0795b-121">Toutefois, Microsoft recommande à votre organisation de choisir une option pour éviter les problèmes de routage :</span><span class="sxs-lookup"><span data-stu-id="0795b-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="0795b-122">Créer l’utilisateur dans l’annuaire Active Directory local et synchroniser l’utilisateur avec le Cloud.</span><span class="sxs-lookup"><span data-stu-id="0795b-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="0795b-123">Voir [intégrer vos annuaires locaux avec Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="0795b-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="0795b-124">Créez l’utilisateur directement dans le centre d’administration 365 Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0795b-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="0795b-125">Pour plus d' [informations, voir ajouter des utilisateurs individuellement ou en bloc à Microsoft 365 ou Office 365-aide de l’administrateur](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="0795b-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="0795b-126">Si votre déploiement de Skype entreprise Online existe avec Skype entreprise 2015 ou Lync 2010 ou 2013 sur site, la seule option prise en charge consiste à créer l’utilisateur dans l’annuaire Active Directory local et à synchroniser l’utilisateur dans le Cloud (option 1).</span><span class="sxs-lookup"><span data-stu-id="0795b-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="0795b-127">Pour plus d’informations sur la gestion des licences, voir gestion des [licences et autres exigences](direct-routing-plan.md#licensing-and-other-requirements) dans [planifier le routage direct](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0795b-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="0795b-128">Assurez-vous que l’utilisateur est en ligne et que le numéro de téléphone n’est pas synchronisé à partir de l’emplacement local (en application de la migration des utilisateurs de Skype entreprise Server entreprise vers le routage direct Teams)</span><span class="sxs-lookup"><span data-stu-id="0795b-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="0795b-129">Le routage direct nécessite que l’utilisateur soit hébergé en ligne.</span><span class="sxs-lookup"><span data-stu-id="0795b-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="0795b-130">Vous pouvez vérifier en examinant le paramètre RegistrarPool, qui doit avoir une valeur dans le domaine infra.lync.com.</span><span class="sxs-lookup"><span data-stu-id="0795b-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="0795b-131">Le paramètre OnPremLineUriManuallySet doit également être défini sur true.</span><span class="sxs-lookup"><span data-stu-id="0795b-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="0795b-132">Pour cela, il est possible de configurer le numéro de téléphone et d’activer la voix et la boîte vocale d’entreprise en utilisant PowerShell Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0795b-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="0795b-133">Connectez une session PowerShell Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0795b-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="0795b-134">Émettez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0795b-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="0795b-135">Dans le cas où OnPremLineUriManuallySet est défini sur false et que LineUri est renseigné avec un <numéro de téléphone E. 164>, nettoyez les paramètres à l’aide de Skype entreprise Online Management Shell avant de configurer le numéro de téléphone dans PowerShell Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0795b-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="0795b-136">Dans l’interpréteur de commandes de Skype entreprise, exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0795b-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="0795b-137">Une fois les modifications synchronisées avec Office 365, la sortie attendue `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` serait la suivante :</span><span class="sxs-lookup"><span data-stu-id="0795b-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="0795b-138">Configuration du numéro de téléphone et activation de la voix et de la boîte vocale entreprise</span><span class="sxs-lookup"><span data-stu-id="0795b-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="0795b-139">Une fois que vous avez créé l’utilisateur et attribué une licence, l’étape suivante consiste à configurer le numéro de téléphone de l’utilisateur et la boîte vocale.</span><span class="sxs-lookup"><span data-stu-id="0795b-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="0795b-140">Pour ajouter le numéro de téléphone et l’activer pour la boîte vocale, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0795b-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="0795b-141">Connectez une session PowerShell Skype entreprise online.</span><span class="sxs-lookup"><span data-stu-id="0795b-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="0795b-142">Émettez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="0795b-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="0795b-143">Par exemple, pour ajouter un numéro de téléphone pour l’utilisateur « Beaune Low », entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0795b-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="0795b-144">Si les utilisateurs « Beaune Low » et « Stacy Quinn » partagent le même numéro de base avec des extensions uniques, entrez ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="0795b-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="0795b-145">Nous vous conseillons de ne pas avoir besoin de configurer le numéro de téléphone avec l’indicatif du pays.</span><span class="sxs-lookup"><span data-stu-id="0795b-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="0795b-146">Il est pris en charge pour configurer des numéros de téléphone avec des extensions qui seront utilisées pour rechercher des utilisateurs lorsque la recherche par rapport au numéro de base renvoie plusieurs résultats.</span><span class="sxs-lookup"><span data-stu-id="0795b-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="0795b-147">Cela permet aux entreprises de configurer des numéros de téléphone avec les mêmes numéros de base et les mêmes extensions uniques.</span><span class="sxs-lookup"><span data-stu-id="0795b-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="0795b-148">Pour que la recherche réussisse, l’invitation doit inclure le numéro complet avec l’extension comme suit :</span><span class="sxs-lookup"><span data-stu-id="0795b-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="0795b-149">Si le numéro de téléphone de l’utilisateur est géré en local, utilisez l’interpréteur de commandes ou le panneau de configuration Skype entreprise local pour configurer le numéro de téléphone de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0795b-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="0795b-150">Configurer l’envoi d’appels directement à la boîte vocale</span><span class="sxs-lookup"><span data-stu-id="0795b-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="0795b-151">Le routage direct vous permet de mettre fin à l’appel d’un utilisateur et de l’envoyer directement à la boîte vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0795b-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="0795b-152">Si vous voulez envoyer l’appel directement à la boîte vocale, attachez opaque = application : boîte vocale dans l’en-tête de la requête.</span><span class="sxs-lookup"><span data-stu-id="0795b-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="0795b-153">Par exemple, « SIP : user@yourdomain. com ; opaque = application : boîte vocale ».</span><span class="sxs-lookup"><span data-stu-id="0795b-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="0795b-154">Dans ce cas, l’utilisateur teams n’aura pas reçu la notification d’appel, l’appel sera connecté directement à la boîte vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0795b-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="0795b-155">Attribuer le mode d’affectation uniquement aux utilisateurs pour s’assurer des appels terrestres dans Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="0795b-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="0795b-156">Le routage direct exige que les utilisateurs soient en mode d’équipe uniquement pour s’assurer que les appels entrants sont présents dans le client Teams.</span><span class="sxs-lookup"><span data-stu-id="0795b-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="0795b-157">Pour faire en sorte que les utilisateurs en mode équipes uniquement, attribuez-leur l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0795b-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="0795b-158">Pour plus d’informations, consultez la rubrique [recommandations de mise à niveau pour les administrateurs informatiques](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0795b-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="0795b-159">Si votre organisation utilise Skype entreprise Server ou Skype entreprise Online, reportez-vous à l’article suivant pour plus d’informations sur l’interopérabilité entre Skype et teams : [migration et interopérabilité avec Skype entreprise](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="0795b-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0795b-160">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0795b-160">See also</span></span>

[<span data-ttu-id="0795b-161">Planifier le routage direct</span><span class="sxs-lookup"><span data-stu-id="0795b-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="0795b-162">Configurer le routage direct</span><span class="sxs-lookup"><span data-stu-id="0795b-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
