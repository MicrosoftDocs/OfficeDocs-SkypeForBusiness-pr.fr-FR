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
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 86a4862a547df6f50d0831616a42824d9f8c3287
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882097"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="83ff9-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83ff9-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="83ff9-104">Ce guide vous aidera à définir un ensemble d'utilisateurs prêts à utiliser les forfaits d'appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="83ff9-105">Lisez l'annonce du 12 décembre 2017 sur les forfaits d'appels dans Teams : [Les communications intelligentes passent la vitesse supérieure avec les appels dans Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="83ff9-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="83ff9-106">En parallèle de ce guide de démarrage rapide, nous vous recommandons de consulter notre [guide pratique](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) et [FastTrack](https://aka.ms/cloudvoice) pour planifier et réaliser un lancement réussi.</span><span class="sxs-lookup"><span data-stu-id="83ff9-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="83ff9-107">En ajoutant les forfaits d'appels (une fonction Office 365 avec Skype Entreprise), vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques de ou vers des lignes fixes et mobiles via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="83ff9-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Appel dans Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="83ff9-109">Prérequis à l'activation de l'onglet **Appels** dans Teams</span><span class="sxs-lookup"><span data-stu-id="83ff9-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="83ff9-110">Pour activer l'onglet **Appels** dans Teams et permettre à vos utilisateurs de passer et recevoir des appels PSTN, vous devez leur fournir un système téléphonique et un forfait d'appels.</span><span class="sxs-lookup"><span data-stu-id="83ff9-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="83ff9-111">Pour savoir comment les configurer, reportez-vous à la section [Configurer des forfaits d'appels](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="83ff9-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="83ff9-112">Configuration de la stratégie d'interopérabilité de Teams</span><span class="sxs-lookup"><span data-stu-id="83ff9-112">Teams interop policy configuration</span></span>
<span data-ttu-id="83ff9-113">Pour permettre à Teams de commencer à recevoir des appels, vous devez mettre à jour la stratégie de mise à niveau de Teams et la stratégie d'interopérabilité de Teams à l’aide du [Centre d’administration de Microsoft Teams et Skype Entreprise](https://aka.ms/teamsadmincenter), ou d'une session Windows PowerShell avec les applets de commande de Skype Entreprise [`*-CsTeamsUpgradePolicy` et `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) afin de rediriger les appels vers Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="83ff9-114">Pour plus d’informations sur la stratégie de mise à niveau de Teams et la stratégie d’interopérabilité de Teams, reportez-vous à la rubrique [Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="83ff9-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="83ff9-115">Pour rechercher les applets de commande PowerShell dont vous avez besoin, entrez « CsTeamsUpgradePolicy » ou « CsTeamsInteropPolicy » dans la zone **Filtre** de la [documentation des applets de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="83ff9-115">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="83ff9-116">Stratégies de mise à niveau et d’interopérabilité de Teams par défaut</span><span class="sxs-lookup"><span data-stu-id="83ff9-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="83ff9-117">Teams intègre une configuration de stratégie par défaut conçue pour garantir que les flux de travail de l’entreprise existants ne soient pas interrompus pendant un déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="83ff9-118">Par défaut, les appels de type Voix sur IP, RTC et fédérés vers vos utilisateurs continuent d'être acheminés vers Skype Entreprise jusqu'à la mise à jour de la stratégie permettant d'activer les appels entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="83ff9-119">Vous avez ainsi la garantie que les services vocaux ne seront pas interrompus de manière imprévue lors de la phase pilote et du déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="83ff9-120">La stratégie de mise à niveau de Teams par défaut est laissée en mode hérité qui respectera la stratégie d’interopérabilité de Teams pour déterminer où les conversations et appels sont dirigés - Teams ou Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="83ff9-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="83ff9-121">Les comportements de la stratégie de mise à niveau de Teams et de la stratégie d’interopérabilité de Teams seront modifiés prochainement. Reportez-vous à la rubrique [Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="83ff9-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="83ff9-122">La stratégie d'interopérabilité de Teams a la configuration par défaut suivante :</span><span class="sxs-lookup"><span data-stu-id="83ff9-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="83ff9-123">Comportements de la configuration par défaut :</span><span class="sxs-lookup"><span data-stu-id="83ff9-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="83ff9-124">**Pour les clients de Skype Entreprise existants**, cette stratégie vise à garantir que les appels Skype Entreprise sont dirigés vers Skype Entreprise et les appels Teams vers Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="83ff9-125">Les appels PSTN et fédérés seront dirigés vers Skype Entreprise une fois cette stratégie en place.</span><span class="sxs-lookup"><span data-stu-id="83ff9-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="83ff9-126">**Pour les clients sans Skype Entreprise**, une fois la stratégie en place, outre les appels entre utilisateurs de Teams, seuls les appels PSTN sortants seront disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="83ff9-127">Vous devrez modifier la stratégie d'interopérabilité de Teams attribuée à vos utilisateurs pour recevoir des appels PSTN dans Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="83ff9-128">Les utilisateurs ayant reçu une licence de système téléphonique et de forfait d'appels pour Skype Entreprise Online et utilisant la stratégie d'interopérabilité générale par défaut de Teams auront accès à l'onglet Appels dans Teams et pourront passer des appels RTC sortants à partir de Teams sans intervention des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="83ff9-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="83ff9-129">Configuration de Teams pour recevoir des appels PSTN entrants</span><span class="sxs-lookup"><span data-stu-id="83ff9-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="83ff9-130">Pour recevoir des appels PSTN entrants dans Teams, vous devez configurer Teams en tant qu'application d'appel par défaut en appliquant la stratégie de mise à niveau de Teams avec la stratégie d'interopérabilité de Teams correspondante qui définit le paramètre `CallingDefaultClient` sur Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83ff9-131">Nous vous recommandons d'appliquer cette configuration à l'ensemble initial des utilisateurs pour découvrir ces nouvelles fonctionnalités d'appel dans Teams avant d'apporter des modifications à plus grande échelle ou dans l'ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="83ff9-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="83ff9-132">Si vous choisissez de continuer à utiliser la stratégie de mise à niveau de Teams héritée, utilisez la stratégie d’interopérabilité de Teams préconfigurée suivante pour acheminer les appels PSTN entrants vers Teams :</span><span class="sxs-lookup"><span data-stu-id="83ff9-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="83ff9-133">Si vous choisissez d’utiliser la stratégie de mise à niveau de Teams mise à jour, vous devez attribuer le mode TeamsOnly à vos utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="83ff9-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="83ff9-134">Les comportements de la stratégie ci-dessus sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="83ff9-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="83ff9-135">**Pour les clients Skype Entreprise existants**, cette stratégie est conçue pour rediriger les appels vers Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="83ff9-136">Elle inclut les appels Voix sur IP (depuis Teams et Skype Entreprise) et les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="83ff9-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="83ff9-137">**Pour les clients sans Skype Entreprise**, le cas échéant, les appels PSTN seront reçus dans Teams.</span><span class="sxs-lookup"><span data-stu-id="83ff9-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="83ff9-138">Actuellement, si basculer `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="83ff9-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="83ff9-139">Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie.</span><span class="sxs-lookup"><span data-stu-id="83ff9-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="83ff9-140">Consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap) pour en savoir plus sur la prise en charge des téléphones SIP certifiés existants.</span><span class="sxs-lookup"><span data-stu-id="83ff9-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="83ff9-141">Configuration des utilisateurs pour qu'ils reçoivent les appels PSTN dans Teams</span><span class="sxs-lookup"><span data-stu-id="83ff9-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="83ff9-142">Si vous utilisez la stratégie de mise à niveau de Teams héritée, appliquez la stratégie d'interopérabilité de Teams comme indiqué ci-dessus via la session Windows PowerShell distante de Skype Entreprise pour rediriger les appels vers Teams :</span><span class="sxs-lookup"><span data-stu-id="83ff9-142">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="83ff9-143">Si vous choisissez d’utiliser le mode TeamsOnly, vous pouvez modifier le mode de coexistence des utilisateurs sur TeamsOnly via le Centre d’administration de Microsoft Teams et Skype Entreprise, ou via la session Windows PowerShell de Skype Entreprise pour rediriger les appels vers Teams :</span><span class="sxs-lookup"><span data-stu-id="83ff9-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="83ff9-144">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="83ff9-144">See also</span></span>
[<span data-ttu-id="83ff9-145">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="83ff9-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="83ff9-146">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="83ff9-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="83ff9-147">Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83ff9-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="83ff9-148">Référence de l'applet de commande PowerShell de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="83ff9-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="83ff9-149">Référence de l'applet de commande PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="83ff9-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
