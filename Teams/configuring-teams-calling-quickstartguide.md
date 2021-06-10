---
title: Guide de démarrage rapide - Configuration des forfaits d’appels
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Guide de démarrage rapide pour configurer des plans d’appel Microsoft Teams vous pouvez rendre un ensemble d’utilisateurs opérationnel.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6420fdff102533c44bdd3ccb2ab503a646c354b8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101180"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="1569d-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1569d-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="1569d-104">Ce guide vous aide à rendre un ensemble d’utilisateurs opérationnels pour leur permettre d’explorer les forfaits d’appels Teams.</span><span class="sxs-lookup"><span data-stu-id="1569d-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="1569d-105">Lire l’annonce des plans d’appels du 12 décembre 2017 dans Teams : Intelligent [Communications passe](https://aka.ms/ipyqus) à l’étape suivante avec les appels dans Teams</span><span class="sxs-lookup"><span data-stu-id="1569d-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="1569d-106">Nous vous recommandons, en parallèle de ce guide de démarrage rapide, de lire les Système téléphonique avec les [plans](calling-plan-landing-page.md) d’appel et [FastTrack](https://aka.ms/cloudvoice) pour planifier et conduire un déploiement réussi.</span><span class="sxs-lookup"><span data-stu-id="1569d-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="1569d-107">En ajoutant des forfaits d’appels, une fonctionnalité de Microsoft 365 et de Office 365 optimisée par Skype Entreprise, vous pouvez désormais utiliser Teams pour passer et recevoir des appels vers ou depuis des lignes fixes et mobiles via le réseau téléphonique commuté (PSTN).</span><span class="sxs-lookup"><span data-stu-id="1569d-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Capture d’écran montrant la page Contacts dans Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="1569d-109">Conditions préalables à l’activation **de l’onglet** Appels dans Teams</span><span class="sxs-lookup"><span data-stu-id="1569d-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="1569d-110">Pour activer  l’onglet Appels dans Teams les utilisateurs doivent avoir activé les appels en face à face dans Teams et utiliser un client Teams qui prend en charge les appels Teams en deux temps.</span><span class="sxs-lookup"><span data-stu-id="1569d-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="1569d-111">Pour découvrir comment gérer les appels 1:1 dans Teams, lisez [Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="1569d-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="1569d-112">Pour savoir quels clients prendre en charge les appels, consultez les [limites et spécifications pour Microsoft Teams.](./limits-specifications-teams.md)</span><span class="sxs-lookup"><span data-stu-id="1569d-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](./limits-specifications-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1569d-113">Pour l’instant, la messagerie vocale ne sera pas disponible dans l’onglet Appels, sauf si l’utilisateur est activé pour les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="1569d-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="1569d-114">Conditions préalables à l’activation **du pavé de numérotation** Teams</span><span class="sxs-lookup"><span data-stu-id="1569d-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="1569d-115">Pour activer  l’onglet Pavé de numérotation dans Teams et permettre à vos utilisateurs d’effectuer et de recevoir des appels PSTN, vous devez mettre en service les utilisateurs pour les plans de Système téléphonique et d’appel.</span><span class="sxs-lookup"><span data-stu-id="1569d-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="1569d-116">Pour découvrir comment configurer des forfaits d’appels, lisez [Configurer les forfaits d’appels.](./set-up-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="1569d-116">To learn how to set up Calling Plans, read [Set up Calling Plans](./set-up-calling-plans.md).</span></span>
<span data-ttu-id="1569d-117">De plus, pour Teams utilisateurs uniquement, vous devez vous assurer que la stratégie « Autoriser les appels privés » est activée dans la Teams d’appel.</span><span class="sxs-lookup"><span data-stu-id="1569d-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="1569d-118">Pour [plus d Teams informations, voir](./manage-teams-skypeforbusiness-admin-center.md) Gérer les Teams pendant la transition vers le nouveau centre Microsoft Teams’administration.</span><span class="sxs-lookup"><span data-stu-id="1569d-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](./manage-teams-skypeforbusiness-admin-center.md) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="1569d-119">Vous pouvez également utiliser le routage direct pour permettre à vos utilisateurs d’effectuer et de recevoir des appels RSTN.</span><span class="sxs-lookup"><span data-stu-id="1569d-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="1569d-120">Pour découvrir comment configurer le routage direct, lisez [Configurer le routage direct.](./direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="1569d-120">To learn how to set up Direct Routing, read [Configure Direct Routing](./direct-routing-configure.md).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="1569d-121">Utilisation de TeamsUpgradePolicy pour contrôler la place des appels</span><span class="sxs-lookup"><span data-stu-id="1569d-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="1569d-122">Pour contrôler l’accès aux appels entrants (et aux conversations) dans Teams ou Skype Entreprise, les administrateurs utilisent TeamsUpgradePolicy, à l’aide du Centre d’administration [Microsoft Teams](https://aka.ms/teamsadmincenter) ou d’une session de Windows PowerShell distante avec les [cmdlets Skype Entreprise.](/powershell/module/skype)</span><span class="sxs-lookup"><span data-stu-id="1569d-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="1569d-123">La configuration par défaut de TeamsUpgradePolicy est le mode Îles, qui est conçu pour garantir que les flux de travail existants d’entreprise ne soient pas interrompus pendant un Teams automatique.</span><span class="sxs-lookup"><span data-stu-id="1569d-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="1569d-124">Par défaut, les appels VoIP, PSTN et fédérés vers vos utilisateurs continueront d’être acheminés vers Skype Entreprise jusqu’à ce que vous mettez à jour la stratégie pour activer les appels entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="1569d-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="1569d-125">Lorsque les destinataires sont en mode îles :</span><span class="sxs-lookup"><span data-stu-id="1569d-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="1569d-126">Les appels VOIP entrants provenant de Skype Entreprise arrivent toujours dans le client de Skype Entreprise destinataire.</span><span class="sxs-lookup"><span data-stu-id="1569d-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="1569d-127">Appels VOIP entrants provenant d’un Teams entrants sur Teams, si l’expéditeur et le destinataire se *trouvent dans le même client.*</span><span class="sxs-lookup"><span data-stu-id="1569d-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="1569d-128">Les appels VOIP fédérés entrants (quel que soit l’origine du client) et les appels PSTN arrivent toujours dans le client Skype Entreprise destinataire.</span><span class="sxs-lookup"><span data-stu-id="1569d-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="1569d-129">Pour vous assurer que les appels VOIP et PSTN entrants arrivent toujours dans le client Teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (c’est-à-dire, affectez-lui l’instance « UpgradeToTeams » de TeamsUpgradePolicy).</span><span class="sxs-lookup"><span data-stu-id="1569d-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="1569d-130">Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, consultez les conseils sur la migration et l’interopérabilité pour les organisations qui utilisent Teams avec [d Skype Entreprise](./migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="1569d-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)</span></span>

<span data-ttu-id="1569d-131">**NOTES**</span><span class="sxs-lookup"><span data-stu-id="1569d-131">**NOTES**</span></span>
 - <span data-ttu-id="1569d-132">Skype Entreprise Les téléphones IP recevront des appels, même si l’utilisateur est en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="1569d-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="1569d-133">Les utilisateurs qui ont été mis en service avec des licences Système téléphonique et Forfaits d’appels pour une utilisation avec Skype Entreprise Online (par exemple, une valeur de OnlineVoiceRoutingPolicy) verront l’onglet Appels activé dans Teams et pourront passer des appels RSTN sortants à partir d’Teams sans que les administrateurs n’ont à prendre d’mesures administratives.</span><span class="sxs-lookup"><span data-stu-id="1569d-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="1569d-134">Comment configurer les utilisateurs pour recevoir tous les appels VOIP et PSTN entrants dans Teams</span><span class="sxs-lookup"><span data-stu-id="1569d-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="1569d-135">Pour vous assurer que les utilisateurs reçoivent tous les appels VOIP et PSTN entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le Centre d’administration Microsoft Teams Skype Entreprise ou utilisez une session de Windows PowerShell distante pour mettre à jour TeamsUpgradePolicy comme suit :</span><span class="sxs-lookup"><span data-stu-id="1569d-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

```powershell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com
```

## <a name="see-also"></a><span data-ttu-id="1569d-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1569d-136">See also</span></span>
[<span data-ttu-id="1569d-137">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="1569d-137">Set up Calling Plans</span></span>](/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="1569d-138">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1569d-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](./migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="1569d-139">Système téléphonique avec Forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="1569d-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="1569d-140">Skype Entreprise Référence de l’cmdlet PowerShell</span><span class="sxs-lookup"><span data-stu-id="1569d-140">Skype for Business PowerShell cmdlet reference</span></span>](/powershell/module/skype)