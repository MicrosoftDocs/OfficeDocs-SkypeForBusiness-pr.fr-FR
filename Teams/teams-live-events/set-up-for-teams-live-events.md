---
title: Configurer des événements live dans Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Découvrez les étapes pour configurer live pour les événements dans Microsoft Teams, y compris la préparation de votre réseau, attribution de licences, activation de la planification pour les utilisateurs et configuration d’un fournisseur eCDN d’événements live.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354363"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a><span data-ttu-id="c02fe-103">Configurer des événements live dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c02fe-103">Set up for live events in Microsoft Teams</span></span>
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

<span data-ttu-id="c02fe-104">Lorsque vous configurez pour les événements en direct, il existe plusieurs étapes à suivre :</span><span class="sxs-lookup"><span data-stu-id="c02fe-104">When you are setting up for live events, there are several steps that you must take:</span></span>

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a><span data-ttu-id="c02fe-105">Étape 1 : Configurer votre réseau pour les événements live dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c02fe-105">Step 1: Set up your network for live events in Microsoft Teams</span></span>
<span data-ttu-id="c02fe-106">Les événements live démarrage rapide requièrent pour [préparer le réseau de votre organisation pour les équipes Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).</span><span class="sxs-lookup"><span data-stu-id="c02fe-106">The quick start live events require you to [prepare your organization's network for Microsoft Teams](https://docs.microsoft.com/microsoftteams/prepare-network).</span></span>  

## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="c02fe-107">Étape 2 : Obtenir et attribuer des licences</span><span class="sxs-lookup"><span data-stu-id="c02fe-107">Step 2: Get and assign licenses</span></span>
<span data-ttu-id="c02fe-108">Disposer des attributions de licence approprié pour [qui peut créer et planifier les événements live ?](#who-can-create-and-schedule-live-events) et [qui peut surveiller les événements en direct ?](#who-can-watch-live-events).</span><span class="sxs-lookup"><span data-stu-id="c02fe-108">Ensure you have correct license assignments for [Who can create and schedule live events?](#who-can-create-and-schedule-live-events) and [Who can watch live events?](#who-can-watch-live-events).</span></span>

## <a name="step-3-enable-live-event-scheduling-for-users"></a><span data-ttu-id="c02fe-109">Étape 3 : Activer la planification d’événements live pour les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c02fe-109">Step 3: Enable live event scheduling for users</span></span>
<span data-ttu-id="c02fe-110">Planification d’événements Live est activée par défaut pour les utilisateurs des équipes, mais si vous sont souhaitant aux utilisateurs de planifier des événements de codage externe des étapes supplémentaires que vous devez faire.</span><span class="sxs-lookup"><span data-stu-id="c02fe-110">Live event scheduling is enabled by default for Teams users but if you are wanting users to schedule external encoder events there are additional steps that you must do.</span></span>

### <a name="for-quick-start-events"></a><span data-ttu-id="c02fe-111">Pour les événements de démarrage rapide</span><span class="sxs-lookup"><span data-stu-id="c02fe-111">For quick start events</span></span>
<span data-ttu-id="c02fe-112">Utilisez le paramètre *AllowBroadcastScheduling* dans **TeamsMeetingBroadcastPolicy** dans PowerShell équipes pour contrôler si l’utilisateur peut créer des événements en temps réel dans les équipes ou non.</span><span class="sxs-lookup"><span data-stu-id="c02fe-112">Use the setting *AllowBroadcastScheduling* in **TeamsMeetingBroadcastPolicy** in Teams PowerShell to control whether the user can create live events in Teams or not.</span></span> <span data-ttu-id="c02fe-113">Vous en apprendrez plus sur la gestion des TeamsMeetingBroadcastPolicy [ici](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="c02fe-113">You can learn more about managing TeamsMeetingBroadcastPolicy [here](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

 <span data-ttu-id="c02fe-114">Si vous n’avez pas attribué une stratégie personnalisée assignée aux utilisateurs, les utilisateurs obtenez la stratégie *globale* , qui est activée par défaut de l’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="c02fe-114">If you haven't assigned a custom policy assigned to the users, the users will get the *Global* policy, which has recording enabled by default.</span></span>

<span data-ttu-id="c02fe-115">Vérifiez que le paramètre *AllowBroadcastScheduling* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="c02fe-115">Verify that *AllowBroadcastScheduling* parameter is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c02fe-116">Affecter l’utilisateur à la stratégie *globale* , exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-116">Then assign the user to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a><span data-ttu-id="c02fe-117">Scénarios utilisateur</span><span class="sxs-lookup"><span data-stu-id="c02fe-117">User scenarios</span></span>
<span data-ttu-id="c02fe-118">**Vous que tous les utilisateurs de votre société à être en mesure de créer des événements en direct.**</span><span class="sxs-lookup"><span data-stu-id="c02fe-118">**You want all users in your company to be able to create live events.**</span></span>

<span data-ttu-id="c02fe-119">Si les utilisateurs sont affectés à la stratégie *Glocal* , exécuter et vérifiez *AllowBroadcastScheduling* \* est défini sur *True*:</span><span class="sxs-lookup"><span data-stu-id="c02fe-119">If users are assigned the *Glocal* policy, run and verify that *AllowBroadcastScheduling* \*is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c02fe-120">Si les utilisateurs sont affectés à une stratégie de la stratégie *globale* , exécutez la commande suivante et vérifiez que l’option *-AllowBroadcastScheduling* est définie sur *True*:</span><span class="sxs-lookup"><span data-stu-id="c02fe-120">If the users are assigned a policy other than the *Global* policy, run the following and verify that *-AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

<span data-ttu-id="c02fe-121">**Vous souhaitez direct planification désactivé 100 % au sein de votre organisation.**</span><span class="sxs-lookup"><span data-stu-id="c02fe-121">**You want live event scheduling to be 100% disabled across your organization.**</span></span>

<span data-ttu-id="c02fe-122">Désactiver la planification de la diffusion, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-122">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c02fe-123">Affecter tous les utilisateurs de votre organisation à la stratégie *globale* , exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-123">Assign all users in your organization to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

<span data-ttu-id="c02fe-124">**Vous souhaitez un grand nombre d’utilisateurs à être en mesure de créer des événements en temps réel, mais souhaitez empêcher un ensemble d’utilisateurs de leur création.**</span><span class="sxs-lookup"><span data-stu-id="c02fe-124">**You want a large number of users to be able to create live events, but want to prevent a set of users from creating them.**</span></span>

<span data-ttu-id="c02fe-125">Attribuer la stratégie *globale* à l’aide de la **Grant-CsTeamsMeetingBroadcastPolicy** pour certains utilisateurs (que vous souhaitez activé), mais exécutez la commande suivante et vérifiez que *AllowBroadcastScheduling* est définie sur *True*, tout d’abord :</span><span class="sxs-lookup"><span data-stu-id="c02fe-125">Assign the *Global* policy using the **Grant-CsTeamsMeetingBroadcastPolicy** for some of the users (that you want enabled) but first run the following and verify that *AllowBroadcastScheduling* is set to *True*:</span></span>
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
<span data-ttu-id="c02fe-126">Puis affecter un ou plusieurs utilisateurs à la stratégie *globale* , exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-126">Then assign a user or users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c02fe-127">Créer et attribuer une stratégie permettant de désactiver la planification à l’aide de l’applet de commande **Grant-CsTeamsMeetingBroadcastPolicy** pour les autres utilisateurs (désactivé).</span><span class="sxs-lookup"><span data-stu-id="c02fe-127">Create and assign a policy for disabling scheduling using the  **Grant-CsTeamsMeetingBroadcastPolicy** cmdlet to the other users (you want disabled).</span></span> 

<span data-ttu-id="c02fe-128">Créer la nouvelle stratégie alors qu’il est désactivé, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-128">Create the new policy with it disabled, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
<span data-ttu-id="c02fe-129">Désactiver la planification, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-129">Disable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
<span data-ttu-id="c02fe-130">Puis affecter des utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-130">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
<span data-ttu-id="c02fe-131">**Vous live événements doivent être désactivée pour un grand nombre d’utilisateurs, mais que vous souhaitez autoriser un ensemble d’utilisateurs pour les créer.**</span><span class="sxs-lookup"><span data-stu-id="c02fe-131">**You want live events to be disabled for a large number of the users, but want to allow a set of users to create them.**</span></span>

<span data-ttu-id="c02fe-132">Désactiver la planification de la diffusion, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-132">Disable broadcast scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
<span data-ttu-id="c02fe-133">Puis affecter ces utilisateurs à la stratégie *globale* , exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-133">Then assign those users to the *Global* policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
<span data-ttu-id="c02fe-134">Créer et attribuer une stratégie d’activation de la planification, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-134">Create and assign a policy for enabling scheduling, run:</span></span>
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
<span data-ttu-id="c02fe-135">Activer la planification, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-135">Enable scheduling, run:</span></span>
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
<span data-ttu-id="c02fe-136">Puis affecter des utilisateurs à cette stratégie, exécutez :</span><span class="sxs-lookup"><span data-stu-id="c02fe-136">Then assign users to this policy, run:</span></span>
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a><span data-ttu-id="c02fe-137">Pour les événements de codage externe</span><span class="sxs-lookup"><span data-stu-id="c02fe-137">For external encoder events</span></span>
<span data-ttu-id="c02fe-138">Vous devez effectuer les opérations suivantes pour activer live événement planification pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c02fe-138">You must do the following to enable live event scheduling for those users.</span></span>

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a><span data-ttu-id="c02fe-139">Étape 1 : Activer Microsoft Stream pour les utilisateurs dans votre organisation \*\*</span><span class="sxs-lookup"><span data-stu-id="c02fe-139">Step 1: Enable Microsoft Stream for users in your organization\*\*</span></span>
<span data-ttu-id="c02fe-140">Stream Microsoft est disponible dans le cadre des abonnements Office 365 éligibles ou en tant que service autonome.</span><span class="sxs-lookup"><span data-stu-id="c02fe-140">Microsoft Stream is available as part of eligible Office 365 subscriptions or as a standalone service.</span></span> <span data-ttu-id="c02fe-141">Pour plus d’informations, voir [Présentation des flux de licences](https://docs.microsoft.com/stream/license-overview) .</span><span class="sxs-lookup"><span data-stu-id="c02fe-141">See [Stream licensing overview](https://docs.microsoft.com/stream/license-overview) for more details.</span></span>

> <span data-ttu-id="c02fe-142">! [NOTE] Stream Microsoft n’est pas inclus dans les plans Business Essentials et entreprise Premium.</span><span class="sxs-lookup"><span data-stu-id="c02fe-142">![NOTE] Microsoft Stream is not included in Business Essentials or Business Premium plans.</span></span>  

<span data-ttu-id="c02fe-143">Pour plus d’informations sur la façon dont vous pouvez [attribuer des licences aux utilisateurs dans Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) afin que les utilisateurs peuvent accéder à Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="c02fe-143">Learn more about how you can [assign licenses to users in Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) so that users can access Microsoft Stream.</span></span> <span data-ttu-id="c02fe-144">Assurez-vous que Microsoft Stream n’est pas bloqué pour les utilisateurs, comme défini dans [cet article](https://docs.microsoft.com/stream/disable-user-organization).</span><span class="sxs-lookup"><span data-stu-id="c02fe-144">Ensure Microsoft Stream is not blocked for the users as defined in [this article](https://docs.microsoft.com/stream/disable-user-organization).</span></span>

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a><span data-ttu-id="c02fe-145">Étape 2 : Vérifiez que les utilisateurs habilités à direct création de flux Microsoft \*\*</span><span class="sxs-lookup"><span data-stu-id="c02fe-145">Step 2: Ensure users have live event creation permission in Microsoft Stream\*\*</span></span>
<span data-ttu-id="c02fe-146">Par défaut, les administrateurs peuvent créer codage externe événements en direct.</span><span class="sxs-lookup"><span data-stu-id="c02fe-146">By default, administrators can create external encoder live events.</span></span> <span data-ttu-id="c02fe-147">L’administrateur Microsoft Stream peut [permettre aux utilisateurs supplémentaires pour la création de l’événement live](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) dans le flux.</span><span class="sxs-lookup"><span data-stu-id="c02fe-147">Microsoft Stream administrator can [enable additional users for live event creation](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) in Stream.</span></span>  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a><span data-ttu-id="c02fe-148">Étape 3 : Vérifiez l’événement live organisateurs souhaitez la stratégie d’entreprise définie par le flux de données d’administration \*\*</span><span class="sxs-lookup"><span data-stu-id="c02fe-148">Step 3: Ensure live event organizers have consented to the company policy set by Stream admin\*\*</span></span>
<span data-ttu-id="c02fe-149">Si un administrateur de Microsoft Stream a [configurer une stratégie d’instructions entreprise](https://docs.microsoft.com/stream/company-policy-and-consent) et exige que les employés accepter cette stratégie avant d’enregistrer le contenu, les utilisateurs doivent faire avant de créer un événement en direct (avec la production de codage externe) dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="c02fe-149">If a Microsoft Stream administrator has [set up a company guidelines policy](https://docs.microsoft.com/stream/company-policy-and-consent) and requires employees to accept this policy before saving content, then users must do so before creating a live event (with External Encoder production) in Teams.</span></span> <span data-ttu-id="c02fe-150">Avant la mise en œuvre la fonctionnalité événements en temps réel de l’organisation, assurez-vous que les utilisateurs qui créeront des ces événements en direct ont accepté à la stratégie.</span><span class="sxs-lookup"><span data-stu-id="c02fe-150">Before you rollout the live events feature in the organization, make sure users who will be creating these live events have consented to the policy.</span></span> 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a><span data-ttu-id="c02fe-151">Étape 4 : Configurer eCDN fournisseur pour les événements live dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c02fe-151">Step 4: Set up eCDN provider for live events in Microsoft Teams</span></span> 
<span data-ttu-id="c02fe-152">Lecture de vidéos direct utilise adaptive vitesse de transmission en continu (TBD), mais il s’agit d’un flux de monodiffusion, ce qui signifie que chaque visionneuse est l’obtention de leur propres flux vidéo à partir d’internet.</span><span class="sxs-lookup"><span data-stu-id="c02fe-152">Playback of live event videos uses adaptive bitrate streaming (ABR) but it is a unicast stream, meaning every viewer is getting their own video stream from the internet.</span></span> <span data-ttu-id="c02fe-153">Pour les événements en direct ou vidéos envoyés à une grande partie de votre organisation, il peut être une grande quantité de bande passante internet consommée par des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c02fe-153">For live events or videos sent out to large portions of your organization, there could be a significant amount of internet bandwidth consumed by viewers.</span></span> <span data-ttu-id="c02fe-154">Pour les organisations qui veulent réduire ce trafic internet pour les événements en direct, des événements live solutions intégrées à Microsoft approuvé partenaires de remise vidéo proposant des logiciels définis réseaux (SDNs) ou des réseaux de livraison de contenu d’entreprise (eCDNs).</span><span class="sxs-lookup"><span data-stu-id="c02fe-154">For organizations that want to reduce this internet traffic for live events, live events solutions are integrated with Microsoft's trusted video delivery partners offering software defined networks (SDNs) or enterprise content delivery networks (eCDNs).</span></span> <span data-ttu-id="c02fe-155">Ces SDN / eCDN plateformes permettent aux organisations d’optimiser la bande passante réseau sans compromettre les utilisateurs finaux une expérience de visualisation.</span><span class="sxs-lookup"><span data-stu-id="c02fe-155">These SDN / eCDN platforms enable organizations to optimize network bandwidth without sacrificing end user viewing experiences.</span></span> <span data-ttu-id="c02fe-156">Nos partenaires peuvent aider à activer une distribution vidéo plus évolutive et efficace entre votre réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c02fe-156">Our partners can help enable a more scalable and efficient video distribution across your enterprise network.</span></span>

<span data-ttu-id="c02fe-157">**Le programme d’installation & achat votre solution en dehors de Microsoft Teams** Obtenir de l’aide avec montée en puissance de diffusion vidéo en tirant parti de partenaires de Microsoft remise vidéo approuvé.</span><span class="sxs-lookup"><span data-stu-id="c02fe-157">**Purchase & setup your solution outside of Microsoft Teams** Get expert help with scaling video delivery by leveraging Microsoft’s trusted video delivery partners.</span></span> <span data-ttu-id="c02fe-158">Avant de pouvoir activer un fournisseur de remise vidéo être utilisés dans les équipes, vous devez acheter et du programme d’installation de la solution SDN/eCDN extérieur et distincte des équipes.</span><span class="sxs-lookup"><span data-stu-id="c02fe-158">Before you can enable a video delivery provider to be used with Teams you must purchase and setup the SDN/eCDN solution outside and separate from Teams.</span></span>

<span data-ttu-id="c02fe-159">Les solutions SDN/eCDN suivantes sont intégrées préalable et peuvent être le programme d’installation pour une utilisation avec Microsoft Stream.</span><span class="sxs-lookup"><span data-stu-id="c02fe-159">The following SDN/eCDN solutions are pre-integrated and can be setup to be used with Microsoft Stream.</span></span>

- <span data-ttu-id="c02fe-160">**La ruche de diffusion en continu** fournit une solution simple et puissante de distribution vidéo entreprise direct et à la demande.</span><span class="sxs-lookup"><span data-stu-id="c02fe-160">**Hive Streaming** provides a simple and powerful solution for live and on-demand enterprise video distribution.</span></span> <span data-ttu-id="c02fe-161">Ruche est une solution logicielle qui ne nécessite aucun matériel supplémentaire ou la bande passante et offre un moyen sécurisé pour activer des milliers d’utilisateurs vidéo simultanés sans impact sur votre réseau.</span><span class="sxs-lookup"><span data-stu-id="c02fe-161">Hive is a software-based solution that requires no additional hardware or bandwidth and provides a secure way to enable thousands of simultaneous video viewers without impact to your network.</span></span> <span data-ttu-id="c02fe-162">Pour les clients souhaitant pour comprendre que rencontre la vidéo de l’impact sur leur réseau avant l’achat d’une solution SDN/eCDN, la ruche de diffusion en continu fournit également une solution d’analytique basés sur navigateur pour les clients de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c02fe-162">For customers looking to understand the impact video is having on their network prior to purchasing an SDN/eCDN solution, Hive Streaming also provides a browser-based analytics solution for Microsoft customers.</span></span> <span data-ttu-id="c02fe-163">[En savoir plus](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span><span class="sxs-lookup"><span data-stu-id="c02fe-163">[Learn more](https://www.hivestreaming.com/partners/integration-partners/microsoft/).</span></span>
 
- <span data-ttu-id="c02fe-164">**Kollective** est une nuage, smart homologation distribution plateforme qui tire parti de votre infrastructure de réseau existant pour fournir un contenu, dans de nombreux écrans, (live flux vidéo, vidéo à la demande, mises à jour logicielles, les correctifs de sécurité, etc.) plus rapide, plus fiable, avec moins de bande passante.</span><span class="sxs-lookup"><span data-stu-id="c02fe-164">**Kollective** is a cloud-based, smart peering distribution platform that leverages your existing network infrastructure to deliver content, in many forms, (live streaming video, on-demand video, software updates, security patches, etc.) faster, more reliably and with less bandwidth.</span></span> <span data-ttu-id="c02fe-165">Notre plateforme sécurisée est approuvée par les institutions financières plus grandes du monde et aucun matériel supplémentaire, le programme d’installation et de maintenance faciles.</span><span class="sxs-lookup"><span data-stu-id="c02fe-165">Our secure platform is trusted by the world’s largest financial institutions and with no additional hardware, setup and maintenance are easy.</span></span> <span data-ttu-id="c02fe-166">[En savoir plus](http://www.kollective.com).</span><span class="sxs-lookup"><span data-stu-id="c02fe-166">[Learn more](http://www.kollective.com).</span></span>
 
- <span data-ttu-id="c02fe-167">**Ramp OmniCache** assure la distribution réseau nouvelle génération et transparente livraison de contenu vidéo sur des réseaux étendus globaux, aider les producteurs événement optimiser la bande passante réseau et prend en charge les diffusions événement réussie en direct et à la demande diffusion en continu.</span><span class="sxs-lookup"><span data-stu-id="c02fe-167">**Ramp OmniCache** provides next-generation network distribution and ensures seamless delivery of video content across global WANs, helping event producers optimize network bandwidth and support successful live event broadcasts and on-demand streaming.</span></span> <span data-ttu-id="c02fe-168">La prise en charge pour Ramp OmniCache pour les événements de démarrage rapide live seront prochainement disponibles.</span><span class="sxs-lookup"><span data-stu-id="c02fe-168">The support for Ramp OmniCache for quick start live events is coming soon.</span></span>  <span data-ttu-id="c02fe-169">[En savoir plus](http://www.ramp.com).</span><span class="sxs-lookup"><span data-stu-id="c02fe-169">[Learn more](http://www.ramp.com).</span></span> 
 
> [!NOTE] 
> <span data-ttu-id="c02fe-170">Sélectionnées **termes du fournisseur 3e partie de la stratégie de confidentialité et de service**, qui régit l’utilisation de la solution du fournisseur eCDN sujette à votre solution eCDN que vous avez choisie.</span><span class="sxs-lookup"><span data-stu-id="c02fe-170">Your chosen eCDN solution is subject to the selected **3rd party provider’s terms of service and privacy policy**, which will governs your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="c02fe-171">L’utilisation de la solution du fournisseur eCDN ne sera pas soumis aux conditions de licence en volume Microsoft ou des termes du contrat de Services en ligne.</span><span class="sxs-lookup"><span data-stu-id="c02fe-171">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="c02fe-172">Si vous n’acceptez pas les **termes du contrat de 3 fournisseur tiers**, puis n’activez pas la solution eCDN dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="c02fe-172">If you do not agree to the **3rd party provider’s terms**, then don't enable the eCDN solution in Teams.</span></span> 

<span data-ttu-id="c02fe-173">**Configurer un eCDN pour « Démarrage rapide » des événements en direct** Vous pouvez configurer le fournisseur eCDN pour les événements live dans les équipes à l’aide de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c02fe-173">**Set up an eCDN for "Quick start" live events** You can configure eCDN provider for live events in Teams using PowerShell.</span></span> 

> [!NOTE] 
> <span data-ttu-id="c02fe-174">Un fournisseur unique eCDN peut être configuré pour votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c02fe-174">A single eCDN provider can be configured for your organization.</span></span> 

<span data-ttu-id="c02fe-175">***La ruche*** Vous pouvez utiliser l’applet de commande [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell pour configurer eCDN fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c02fe-175">***Hive*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="c02fe-176">Tout d’abord obtenir l’URL de modèle de code et les API de licence de votre contact ruche puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c02fe-176">First obtain the license ID and API template URL from your Hive contact then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="c02fe-177">***Kollective*** Vous pouvez utiliser l’applet de commande [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell pour configurer eCDN fournisseur.</span><span class="sxs-lookup"><span data-stu-id="c02fe-177">***Kollective*** You can use [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) PowerShell cmdlet to configure eCDN provider.</span></span> <span data-ttu-id="c02fe-178">Tout d’abord obtenir le jeton d’API et l’URL de modèle API à partir de votre contact Kollective, puis exécutez la commande suivante :</span><span class="sxs-lookup"><span data-stu-id="c02fe-178">First obtain the API token and the API template URL from your Kollective contact, then run the following:</span></span>
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="c02fe-179">**Configurer un eCDN pour les événements live « Codage externe »**</span><span class="sxs-lookup"><span data-stu-id="c02fe-179">**Set up an eCDN for "External encoder" live events**</span></span> 

<span data-ttu-id="c02fe-180">Si vous envisagez de créer des événements en temps réel qui utilisent des encodeurs externes, vous devrez également [configurer votre fournisseur eCDN avec flux de données Microsoft](https://docs.microsoft.com/stream/network-caching) .</span><span class="sxs-lookup"><span data-stu-id="c02fe-180">If you plan to create live events that use external encoders, you will need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching) as well.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="c02fe-181">Étapes suivantes</span><span class="sxs-lookup"><span data-stu-id="c02fe-181">Next steps</span></span>
<span data-ttu-id="c02fe-182">Accédez à [Confgure équipes événements en direct](configure-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="c02fe-182">Go to [Confgure Teams live events](configure-teams-live-events.md).</span></span>
