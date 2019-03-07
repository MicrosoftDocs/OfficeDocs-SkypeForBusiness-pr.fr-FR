---
title: "Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Guide de démarrage rapide pour la configuration des forfaits d'appels dans Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e1d2fd7a9b999d98109e732b3bdbbba16f26e3bf
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30460571"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="115e2-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="115e2-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="115e2-104">Ce guide vous aidera à définir un ensemble d'utilisateurs prêts à utiliser les forfaits d'appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="115e2-105">Lisez l'annonce du 12 décembre 2017 sur les forfaits d'appels dans Teams : [Les communications intelligentes passent la vitesse supérieure avec les appels dans Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="115e2-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="115e2-106">Nous vous recommandons, en parallèle avec ce guide de démarrage rapide, lire [Système téléphonique avec des Plans de l’appel](calling-plan-landing-page.md) et [FastTrack](https://aka.ms/cloudvoice) plan et lecteur de réussir votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="115e2-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="115e2-107">En ajoutant les forfaits d'appels (une fonction Office 365 avec Skype Entreprise), vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques de ou vers des lignes fixes et mobiles via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="115e2-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Appel dans Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="115e2-109">Prérequis à l'activation de l'onglet **Appels** dans Teams</span><span class="sxs-lookup"><span data-stu-id="115e2-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="115e2-110">Pour activer l’onglet **appels** dans les équipes, les utilisateurs doivent disposer de 1:1 appel activé dans les équipes et à l’aide d’un client équipes qui prend en charge les équipes de 1:1 appel.</span><span class="sxs-lookup"><span data-stu-id="115e2-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="115e2-111">Pour savoir comment gérer l’appel de 1:1 dans les équipes, consultez [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="115e2-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="115e2-112">Pour savoir quels clients prennent en charge l’appel, lisez [les spécifications pour les équipes Microsoft et limites](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="115e2-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="115e2-113">Actuellement, la messagerie vocale ne sera pas disponible dans l’onglet appels, sauf si l’utilisateur est activé pour les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="115e2-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="115e2-114">Conditions requises pour l’activation du **Pavé de numérotation** dans les équipes</span><span class="sxs-lookup"><span data-stu-id="115e2-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="115e2-115">Pour activer l’onglet **Pavé de numérotation** dans les équipes et autoriser les utilisateurs à émettre et recevoir des appels PSTN, vous devrez mettre en service des utilisateurs pour le système téléphonique et Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="115e2-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="115e2-116">Pour savoir comment configurer des Plans de l’appel, lisez [configurer des Plans de l’appel](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="115e2-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="115e2-117">Vous pouvez également utiliser le routage Direct pour autoriser les utilisateurs à ext et de recevoir des appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="115e2-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="115e2-118">Pour savoir comment configurer le routage Direct, consultez [Configurer le routage Direct](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="115e2-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="115e2-119">Configuration de la stratégie d'interopérabilité de Teams</span><span class="sxs-lookup"><span data-stu-id="115e2-119">Teams interop policy configuration</span></span>
<span data-ttu-id="115e2-120">Pour activer les équipes commencer à recevoir des appels, vous devez mettre à jour la stratégie de mise à niveau d’équipes et équipes interopérabilité la stratégie, à l’aide du [Centre d’administration de Microsoft équipes](https://aka.ms/teamsadmincenter) ou à l’aide d’une session Windows PowerShell à distance avec le Skype pour les entreprises [ `*-CsTeamsUpgradePolicy` et `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) applets de commande, pour rediriger les appels vers les équipes.</span><span class="sxs-lookup"><span data-stu-id="115e2-120">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="115e2-121">Pour plus d’informations sur la stratégie de mise à niveau équipes et équipes PIA, voir [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="115e2-121">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="115e2-122">Pour rechercher les applets de commande PowerShell que vous avez besoin, tapez « CsTeamsUpgradePolicy » ou « CsTeamsInteropPolicy » dans la zone **filtre** dans la [Skype pour la documentation d’applet de commande PowerShell Business](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="115e2-122">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="115e2-123">Par défaut des équipes de stratégies de mise à niveau et interopérabilités</span><span class="sxs-lookup"><span data-stu-id="115e2-123">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="115e2-124">Teams intègre une configuration de stratégie par défaut conçue pour garantir l'ininterruption des flux de travail professionnels existants pendant le déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-124">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="115e2-125">Par défaut, les appels de type Voix sur IP, RTC et fédérés vers vos utilisateurs continuent d'être acheminés vers Skype Entreprise jusqu'à la mise à jour de la stratégie permettant d'activer les appels entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-125">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="115e2-126">Vous avez ainsi la garantie que les services vocaux ne seront pas interrompus de manière imprévue à la mise en place et au déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-126">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="115e2-127">Mise à niveau de stratégie par défaut est conservée au mode hérité qui respecte la stratégie d’interopérabilité de base équipes pour déterminer où des conversations et les appels sont routés--les équipes des équipes ou Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="115e2-127">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="115e2-128">Stratégie de mise à niveau les comportements d’équipes et stratégie interopérabilité équipes change bientôt comme décrit dans la [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="115e2-128">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="115e2-129">La stratégie d'interopérabilité de Teams possède la configuration par défaut suivante :</span><span class="sxs-lookup"><span data-stu-id="115e2-129">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="115e2-130">Comportements de la configuration par défaut :</span><span class="sxs-lookup"><span data-stu-id="115e2-130">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="115e2-131">**Pour les clients de Skype Entreprise existants**, cette stratégie vise à garantir que les appels Skype Entreprise sont dirigés vers Skype Entreprise et les appels Teams vers Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-131">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="115e2-132">Les appels PSTN et fédérés seront dirigés vers Skype Entreprise une fois cette stratégie en place.</span><span class="sxs-lookup"><span data-stu-id="115e2-132">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="115e2-133">**Pour les clients sans Skype Entreprise**, une fois la stratégie en place, outre les appels entre utilisateurs de Teams, seuls les appels PSTN sortants seront disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-133">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="115e2-134">Vous devrez modifier la stratégie d'interopérabilité de Teams attribuée à vos utilisateurs pour recevoir des appels PSTN dans Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-134">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="115e2-135">Les utilisateurs ayant reçu une licence de système téléphonique et de forfait d'appels pour Skype Entreprise Online et utilisant la stratégie d'interopérabilité générale par défaut de Teams auront accès à l'onglet Appels dans Teams et pourront passer des appels RTC sortants à partir de Teams sans intervention des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="115e2-135">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="115e2-136">Configuration de Teams pour recevoir des appels PSTN entrants</span><span class="sxs-lookup"><span data-stu-id="115e2-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="115e2-137">Pour recevoir des appels entrants de PSTN dans les équipes, vous devez configurer des équipes par défaut appelant en appliquant une stratégie de mise à niveau équipes avec la stratégie d’interopérabilité de base équipes correspondante qui définit l’application `CallingDefaultClient` paramètre aux équipes.</span><span class="sxs-lookup"><span data-stu-id="115e2-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="115e2-138">Nous vous recommandons d'appliquer cette configuration à l'ensemble initial des utilisateurs pour découvrir ces nouvelles fonctionnalités d'appel dans Teams avant d'apporter des modifications à plus grande échelle ou dans l'ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="115e2-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="115e2-139">Si vous choisissez de continuer à utiliser la stratégie de mise à niveau équipes héritée, permet de la stratégie d’interopérabilité de base équipes préconfigurée suivante pour acheminer des appels PSTN entrants aux équipes :</span><span class="sxs-lookup"><span data-stu-id="115e2-139">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="115e2-140">Si vous choisissez d’utiliser la stratégie de mise à niveau équipes mis à jour, vous devez affecter des équipes uniquement en mode à vos utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="115e2-140">If you choose to use the updated Teams upgrade policy, you need to assign Teams Only mode to your users.</span></span>

<span data-ttu-id="115e2-141">Comportements de la stratégie ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="115e2-141">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="115e2-142">**Pour les clients Skype Entreprise existants**, cette stratégie est conçue pour rediriger les appels vers Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-142">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="115e2-143">Elle comprend les appels de type Voix sur IP (de Teams et Skype Entreprise) et les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="115e2-143">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="115e2-144">**Pour les clients sans Skype Entreprise**, le cas échéant, les appels PSTN seront reçus dans Teams.</span><span class="sxs-lookup"><span data-stu-id="115e2-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="115e2-145">Basculer de `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="115e2-145">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="115e2-146">Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie.</span><span class="sxs-lookup"><span data-stu-id="115e2-146">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="115e2-147">Veuillez consulter la [Feuille de route 365 Microsoft](https://aka.ms/O365Roadmap) pour plus d’informations sur la prise en charge pour les téléphones SIP certifiés existants.</span><span class="sxs-lookup"><span data-stu-id="115e2-147">Please consult the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="115e2-148">Comment configurer les utilisateurs pour la réception de PSTN des appels dans les équipes</span><span class="sxs-lookup"><span data-stu-id="115e2-148">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="115e2-149">Lorsque vous utilisez la stratégie de mise à niveau équipes héritée, appliquer la stratégie de PIA équipes comme indiqué ci-dessus par le biais de Skype pour la session Windows PowerShell à distance Business pour rediriger les appels vers les équipes :</span><span class="sxs-lookup"><span data-stu-id="115e2-149">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="115e2-150">Si vous choisissez d’utiliser le mode équipes uniquement, vous pouvez modifier en mode de coexistence de l’utilisateur aux équipes uniquement via le centre d’acmin Microsoft Teams ou un Skype pour la session Windows PowerShell à distance Business pour rediriger les appels vers les équipes :</span><span class="sxs-lookup"><span data-stu-id="115e2-150">If you choose to use Teams Only mode, you can change the user's coexistence mode to Teams Only via the Microsoft Teams acmin center or via a Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="115e2-151">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="115e2-151">See also</span></span>
[<span data-ttu-id="115e2-152">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="115e2-152">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="115e2-153">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="115e2-153">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="115e2-154">Système téléphonique avec forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="115e2-154">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="115e2-155">Référence de l'applet de commande PowerShell de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="115e2-155">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="115e2-156">Référence de l'applet de commande PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="115e2-156">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
