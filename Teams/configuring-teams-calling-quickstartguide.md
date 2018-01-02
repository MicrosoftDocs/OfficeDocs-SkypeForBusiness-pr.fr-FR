---
title: "Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Guide de démarrage rapide pour la configuration des forfaits d'appels dans Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bf2aa9b698516882ed5e48b4d9b7b639b74af40e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="30cb9-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30cb9-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="30cb9-104">Ce guide vous aidera à définir un ensemble d'utilisateurs prêts à utiliser les forfaits d'appels dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="30cb9-105">Lisez l'annonce du 12 décembre 2017 sur les forfaits d'appels dans Teams : [Les communications intelligentes passent la vitesse supérieure avec les appels dans Teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="30cb9-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="30cb9-106">En parallèle de ce guide de démarrage rapide, nous vous recommandons de consulter notre [guide pratique](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) et [FastTrack](https://aka.ms/cloudvoice) pour planifier et réaliser un lancement réussi.</span><span class="sxs-lookup"><span data-stu-id="30cb9-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="30cb9-107">En ajoutant les forfaits d'appels (une fonction Office 365 avec Skype Entreprise), vous pouvez désormais utiliser Teams pour passer et recevoir des appels téléphoniques de ou vers des lignes fixes et mobiles via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="30cb9-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Appel dans Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="30cb9-109">Prérequis à l'activation de l'onglet **Appels** dans Teams</span><span class="sxs-lookup"><span data-stu-id="30cb9-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="30cb9-110">Pour activer l'onglet **Appels** dans Teams et permettre à vos utilisateurs de passer et recevoir des appels PSTN, vous devez leur fournir un système téléphonique et un forfait d'appels.</span><span class="sxs-lookup"><span data-stu-id="30cb9-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="30cb9-111">Pour en savoir plus à ce sujet, lisez [Configurer des forfaits d'appels](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span><span class="sxs-lookup"><span data-stu-id="30cb9-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30cb9-112">Avant de configurer des forfaits d'appels dans Teams, tenez compte des restrictions suivantes :</span><span class="sxs-lookup"><span data-stu-id="30cb9-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="30cb9-113">**La fonction Voix Hybride n'est pas prise en charge dans Teams** - Teams ne prend pas en charge la fonction Voix hybride pour le moment.</span><span class="sxs-lookup"><span data-stu-id="30cb9-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="30cb9-114">Il n'est pas conseillé aux clients qui utilisent la Voix hybride de modifier les stratégies de réception des appels dans Teams, ceci pouvant engendrer des interruptions de service.</span><span class="sxs-lookup"><span data-stu-id="30cb9-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="30cb9-115">**Les appels fédérés ne sont pas pris en charge dans Teams** - Teams ne prend pas en charge les appels fédérés (appels entre clients/entreprises) pour le moment.</span><span class="sxs-lookup"><span data-stu-id="30cb9-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="30cb9-116">Les appels fédérés seront toujours acheminés vers Skype Entreprise indépendamment de la configuration de l'appel jusqu'à la prise en charge de cette fonction dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="30cb9-117">Configuration de la stratégie d'interopérabilité de Teams</span><span class="sxs-lookup"><span data-stu-id="30cb9-117">Teams interop policy configuration</span></span>
<span data-ttu-id="30cb9-118">Pour activer la réception des appels dans Teams, vous devez mettre à jour la stratégie d'interopérabilité de Teams à l'aide d'une session Windows PowerShell distante avec les applets de commande [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) de Skype Entreprise, afin de rediriger les appels vers Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="30cb9-119">Pour en savoir plus sur la fonction d'interopérabilité de Teams, consultez [Interopérabilité entre Microsoft Teams et Skype Entreprise](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span><span class="sxs-lookup"><span data-stu-id="30cb9-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="30cb9-120">Pour rechercher les applets de commande PowerShell dont vous avez besoin, entrez CsTeamsInteropPolicy dans le champ **Filtre** de la [documentation des applets de commande PowerShell de Skype Entreprise](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="30cb9-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="30cb9-121">Stratégie d'interopérabilité de Teams par défaut</span><span class="sxs-lookup"><span data-stu-id="30cb9-121">Default Teams interop policy</span></span>
<span data-ttu-id="30cb9-122">Teams intègre une configuration de stratégie par défaut conçue pour garantir l'ininterruption des flux de travail professionnels existants pendant le déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="30cb9-123">Par défaut, les appels de type Voix sur IP, RTC et fédérés vers vos utilisateurs continuent d'être acheminés vers Skype Entreprise jusqu'à la mise à jour de la stratégie permettant d'activer les appels entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="30cb9-124">Vous avez ainsi la garantie que les services vocaux ne seront pas interrompus de manière imprévue à la mise en place et au déploiement de Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="30cb9-125">La stratégie d'interopérabilité de Teams possède la configuration par défaut suivante :</span><span class="sxs-lookup"><span data-stu-id="30cb9-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="30cb9-126">Comportements de la configuration par défaut :</span><span class="sxs-lookup"><span data-stu-id="30cb9-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="30cb9-127">**Pour les clients de Skype Entreprise existants**, cette stratégie vise à garantir que les appels Skype Entreprise sont dirigés vers Skype Entreprise et les appels Teams vers Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="30cb9-128">Les appels PSTN et fédérés seront dirigés vers Skype Entreprise une fois cette stratégie en place.</span><span class="sxs-lookup"><span data-stu-id="30cb9-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="30cb9-129">**Pour les clients sans Skype Entreprise**, une fois la stratégie en place, outre les appels entre utilisateurs de Teams, seuls les appels PSTN sortants seront disponibles dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="30cb9-130">Vous devrez modifier la stratégie d'interopérabilité de Teams attribuée à vos utilisateurs pour recevoir des appels PSTN dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="30cb9-131">Les utilisateurs ayant reçu une licence de système téléphonique et de forfait d'appels pour Skype Entreprise Online et utilisant la stratégie d'interopérabilité générale par défaut de Teams auront accès à l'onglet Appels dans Teams et pourront passer des appels RTC sortants à partir de Teams sans intervention des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="30cb9-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="30cb9-132">Procédure de configuration de Teams pour utiliser la stratégie par défaut</span><span class="sxs-lookup"><span data-stu-id="30cb9-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="30cb9-133">Par défaut, la stratégie d'interopérabilité générale de Teams est appliquée à tous les utilisateurs de votre client et configurée avec les paramètres standard décrits ci-après.</span><span class="sxs-lookup"><span data-stu-id="30cb9-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="30cb9-134">Si pour un motif quelconque vous avez octroyé des stratégies différentes à vos utilisateurs et souhaitez rétablir les paramètres par défaut, vous devrez appliquer la stratégie d'interopérabilité générale de Teams via la session Windows PowerShell distante de Skype Entreprise :</span><span class="sxs-lookup"><span data-stu-id="30cb9-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="30cb9-135">Bien qu'il soit possible de modifier la stratégie d'interopérabilité générale de Teams à partir des valeurs par défaut, nous vous déconseillons fortement de le faire.</span><span class="sxs-lookup"><span data-stu-id="30cb9-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="30cb9-136">Configuration de Teams pour recevoir des appels PSTN entrants</span><span class="sxs-lookup"><span data-stu-id="30cb9-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="30cb9-137">Pour recevoir des appels RTC entrants dans Teams, vous devez configurer Teams en tant qu'application d'appel par défaut en appliquant la stratégie d'interopérabilité de Teams après avoir défini le paramètre `CallingDefaultClient` sur Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="30cb9-138">Nous vous recommandons d'appliquer cette configuration à l'ensemble initial des utilisateurs pour découvrir ces nouvelles fonctionnalités d'appel dans Teams avant d'apporter des modifications à plus grande échelle ou dans l'ensemble de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30cb9-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="30cb9-139">Considérez l'utilisation de la stratégie d'interopérabilité de Teams préconfigurée suivante pour acheminer les appels RTC entrants vers Teams :</span><span class="sxs-lookup"><span data-stu-id="30cb9-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="30cb9-140">Comportements de la stratégie ci-dessus :</span><span class="sxs-lookup"><span data-stu-id="30cb9-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="30cb9-141">**Pour les clients Skype Entreprise existants**, cette stratégie est conçue pour rediriger les appels vers Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="30cb9-142">Elle comprend les appels de type Voix sur IP (de Teams et Skype Entreprise) et les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="30cb9-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="30cb9-143">Les appels fédérés continueront d'être reçus dans Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="30cb9-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="30cb9-144">**Pour les clients sans Skype Entreprise**, le cas échéant, les appels PSTN seront reçus dans Teams.</span><span class="sxs-lookup"><span data-stu-id="30cb9-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="30cb9-145">Teams **ne prend pas encore en charge** les appels fédérés.</span><span class="sxs-lookup"><span data-stu-id="30cb9-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="30cb9-146">Basculer de `CallingDefaultClient` vers Teams affectera également les appels vers les téléphones IP Skype Entreprise.</span><span class="sxs-lookup"><span data-stu-id="30cb9-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="30cb9-147">Les appels entrants ne seront pas reçus sur les téléphones et seuls les clients Teams entendront la sonnerie.</span><span class="sxs-lookup"><span data-stu-id="30cb9-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="30cb9-148">Consultez la [Feuille de route de l'évolution des fonctionnalités entre Skype Entreprise et Microsoft Teams](https://aka.ms/skype2teamsroadmap) pour en savoir plus sur la prise en charge des téléphones SIP certifiés existants.</span><span class="sxs-lookup"><span data-stu-id="30cb9-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="30cb9-149">Procédure de configuration de Teams pour recevoir des appels RTC</span><span class="sxs-lookup"><span data-stu-id="30cb9-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="30cb9-150">Appliquez la stratégie d'interopérabilité de Teams comme indiqué ci-dessus via la session Windows PowerShell distante de Skype Entreprise pour rediriger les appels vers Teams :</span><span class="sxs-lookup"><span data-stu-id="30cb9-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="30cb9-151">Configuration de Teams pour permettre aux utilisateurs de modifier leur application d'appel préférée</span><span class="sxs-lookup"><span data-stu-id="30cb9-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="30cb9-152">Pour laisser les utilisateurs choisir leur application d'appel préférée et de recevoir les appels dans Teams ou Skype Entreprise, vous devez créer une stratégie d'interopérabilité personnalisée de Teams dans laquelle le paramètre `AllowEndUserClientOverride` est activé.</span><span class="sxs-lookup"><span data-stu-id="30cb9-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="30cb9-153">Voici un exemple de stratégie d'interopérabilité de Teams permettant à l'utilisateur de choisir son application d'appel préférée :</span><span class="sxs-lookup"><span data-stu-id="30cb9-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="30cb9-154">Une fois cette stratégie personnalisée appliquée aux utilisateurs, l'option de modification de l'application d'appel préférée sera disponible sur le client Teams permettant ainsi aux utilisateurs d'effectuer la modification eux-mêmes.</span><span class="sxs-lookup"><span data-stu-id="30cb9-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![Option d'application d'appel préférée](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="30cb9-156">Il est recommandé d'appliquer cette configuration à un ensemble initial d'utilisateurs avant d'apporter des modifications à plus grande échelle ou dans toute votre organisation.</span><span class="sxs-lookup"><span data-stu-id="30cb9-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="30cb9-157">Procédure de création et d'application d'une stratégie d'interopérabilité personnalisée de Teams</span><span class="sxs-lookup"><span data-stu-id="30cb9-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="30cb9-158">Pour créer la stratégie d'interopérabilité de Teams comme indiqué ci-dessus via la session Windows PowerShell distante de Skype Entreprise, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="30cb9-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="30cb9-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30cb9-159">See also</span></span>
[<span data-ttu-id="30cb9-160">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="30cb9-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="30cb9-161">Interopérabilité entre Microsoft Teams et Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="30cb9-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="30cb9-162">Guide pratique des systèmes téléphoniques avec forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="30cb9-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="30cb9-163">Référence de l'applet de commande PowerShell de Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="30cb9-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="30cb9-164">Référence de l'applet de commande PowerShell de Teams</span><span class="sxs-lookup"><span data-stu-id="30cb9-164">PowerShell cmdlet reference for Teams</span></span>](https://docs.microsoft.com/powershell/module/teams)
