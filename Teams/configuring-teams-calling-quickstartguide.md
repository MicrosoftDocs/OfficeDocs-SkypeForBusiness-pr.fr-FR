---
title: Guide de démarrage rapide - Configuration des forfaits d'appels dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Guide de mise en route pour la configuration des offres d’appel dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87670ea398150e4895f2d87ccc48f60aba2d1377
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516479"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="4aaf8-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4aaf8-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="4aaf8-104">Ce guide va vous aider à mettre en route un ensemble d’utilisateurs afin qu’ils puissent explorer les plans d’appel dans Teams.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="4aaf8-105">Lire le 12 décembre 2017, annonce des plans d’appel dans teams : [les communications intelligentes prennent l’étape suivante avec les appels dans teams](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="4aaf8-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="4aaf8-106">Dans le cas d’un guide de démarrage rapide, nous vous conseillons de lire le [système téléphonique avec les offres d’appel](calling-plan-landing-page.md) et [FastTrack](https://aka.ms/cloudvoice) pour planifier et conduire un déploiement réussi.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="4aaf8-107">En ajoutant des plans d’appel, une fonctionnalité de 365 Office gérée par Skype entreprise, vous pouvez désormais utiliser les équipes pour passer et recevoir des appels téléphoniques vers des lignes fixes et mobiles via le réseau téléphonique public commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="4aaf8-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Capture d’écran montrant la page contacts dans teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="4aaf8-109">Conditions préalables à l’activation de l’onglet **appels** dans teams</span><span class="sxs-lookup"><span data-stu-id="4aaf8-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="4aaf8-110">Pour activer l’onglet **appels** dans équipes, les utilisateurs doivent avoir activé l’appel 1:1 dans teams et utiliser un client teams prenant en charge les appels d’équipes 1:1.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="4aaf8-111">Pour savoir comment gérer les appels 1:1 dans Teams, voir [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4aaf8-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="4aaf8-112">Pour savoir quels clients prennent en charge les appels, prenez connaissance des [limites et des caractéristiques de Microsoft teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="4aaf8-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="4aaf8-113">Pour le moment, la boîte vocale n’est pas disponible sous l’onglet appels, sauf si l’utilisateur est autorisé à utiliser les appels RTC.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="4aaf8-114">Conditions préalables à l’activation du **pavé de numérotation** dans teams</span><span class="sxs-lookup"><span data-stu-id="4aaf8-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="4aaf8-115">Pour activer l’onglet **pavé de numérotation** dans teams et permettre aux utilisateurs de passer et de recevoir des appels RTC, vous devez configurer les utilisateurs pour le système téléphonique et les offres d’appels.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="4aaf8-116">Pour plus d’informations sur la configuration des forfaits d’appel, consultez la rubrique [configurer les offres d’appels](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="4aaf8-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="4aaf8-117">Vous pouvez également utiliser le routage direct pour autoriser vos utilisateurs à passer et à recevoir des appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="4aaf8-118">Pour savoir comment configurer le routage direct, voir [configurer le routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="4aaf8-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="4aaf8-119">Utilisation de TeamsUpgradePolicy pour contrôler les appels terrestres</span><span class="sxs-lookup"><span data-stu-id="4aaf8-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="4aaf8-120">Pour contrôler si les appels entrants (et les discussions) dans teams ou Skype entreprise, les administrateurs utilisent TeamsUpgradePolicy, à l’aide du [Centre d’administration Microsoft teams](https://aka.ms/teamsadmincenter) ou d’une session Windows PowerShell distante avec [Skype entreprise](https://docs.microsoft.com/powershell/module/skype) applets.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="4aaf8-121">La configuration par défaut de TeamsUpgradePolicy est le mode îlot, qui est conçu pour garantir que les flux de travail d’entreprise existants ne sont pas interrompus lors du déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="4aaf8-122">Par défaut, les appels VoIP, RTC et fédérés vers vos utilisateurs continuent d’être routés vers Skype entreprise tant que vous n’avez pas mis à jour la stratégie pour autoriser les appels entrants vers Teams.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="4aaf8-123">Lorsque les destinataires sont en mode îlot :</span><span class="sxs-lookup"><span data-stu-id="4aaf8-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="4aaf8-124">Les appels VOIP entrants à l’origine de Skype entreprise sont toujours terrains dans le client Skype entreprise du destinataire.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="4aaf8-125">Appels VOIP entrants à l’origine dans teams en équipe, *si l’expéditeur et le destinataire se trouvent dans le même client*.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="4aaf8-126">Le VOIP fédéré entrant (quel que soit le client qu’il contient) et les appels RTC sont toujours terrains dans le client Skype entreprise du destinataire.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="4aaf8-127">Pour vous assurer que les appels VOIP et PSTN entrants restent toujours dans le client teams d’un utilisateur, mettez à jour le mode de coexistence de l’utilisateur pour qu’il soit TeamsOnly (c’est-à-dire, attribuez-lui l’instance « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="4aaf8-128">Pour plus d’informations sur les modes de coexistence et TeamsUpgradePolicy, voir [conseils de migration et d’interopérabilité pour les organisations qui utilisent des équipes dans Skype entreprise](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype) .</span><span class="sxs-lookup"><span data-stu-id="4aaf8-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="4aaf8-129">**NOTES**</span><span class="sxs-lookup"><span data-stu-id="4aaf8-129">**NOTES**</span></span>
 - <span data-ttu-id="4aaf8-130">Les téléphones IP Skype entreprise recevront des appels, même s’ils sont en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="4aaf8-131">Les utilisateurs qui ont été configurés avec un système téléphonique et des offres d’appels d’offres pour une utilisation avec Skype entreprise Online (par exemple, une valeur de OnlineVoiceRoutingPolicy), l’onglet appels est activé dans teams et peuvent passer des appels RTC Équipes sans qu’ils aient à effectuer d’action administrative.</span><span class="sxs-lookup"><span data-stu-id="4aaf8-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="4aaf8-132">Comment configurer les utilisateurs pour qu’ils reçoivent tous les appels VOIP et PSTN entrants dans teams</span><span class="sxs-lookup"><span data-stu-id="4aaf8-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="4aaf8-133">Pour garantir que les utilisateurs reçoivent tous les appels VOIP et PSTN entrants dans Teams, définissez le mode de coexistence de l’utilisateur sur TeamsOnly dans le centre d’administration de Microsoft Teams, ou utilisez la session Windows PowerShell Skype entreprise à distance pour mettre à jour TeamsUpgradePolicy comme suit :</span><span class="sxs-lookup"><span data-stu-id="4aaf8-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="4aaf8-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4aaf8-134">See also</span></span>
[<span data-ttu-id="4aaf8-135">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="4aaf8-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="4aaf8-136">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="4aaf8-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="4aaf8-137">Système téléphonique avec forfaits d’appels</span><span class="sxs-lookup"><span data-stu-id="4aaf8-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="4aaf8-138">Référence sur les applets de passe Skype entreprise PowerShell</span><span class="sxs-lookup"><span data-stu-id="4aaf8-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

