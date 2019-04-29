---
title: Guide de démarrage rapide - Configuration des forfaits d'appels dans Microsoft Teams
author: arachmanGitHub
ms.author: Rowille
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: Rowille, lolaj
search.appverid: MET150
description: Guide de démarrage rapide pour la configuration des plans d’appel dans Microsoft Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f6c719d17938986ff6568b73864bc131667e4e7
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33401982"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="3f4b4-103">Guide de démarrage rapide : Configuration des forfaits d'appels dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f4b4-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="3f4b4-104">Ce guide vous aidera à obtenir un ensemble d’utilisateurs up et en cours d’exécution afin qu’ils peuvent Explorer appelant Plans dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="3f4b4-105">Lire l’annonce 12 décembre 2017, des Plans de l’appel dans les équipes : [Communications Intelligent prend l’étape suivante avec l’appel dans les équipes](https://aka.ms/ipyqus)</span><span class="sxs-lookup"><span data-stu-id="3f4b4-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b4-106">Nous vous recommandons, en parallèle avec ce guide de démarrage rapide, lire [Système téléphonique avec des Plans de l’appel](calling-plan-landing-page.md) et [FastTrack](https://aka.ms/cloudvoice) plan et lecteur de réussir votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="3f4b4-107">En ajoutant l’appel Plans - une fonctionnalité Office 365 par Skype pour les entreprises - vous pouvez maintenant utiliser des équipes pour émettre et recevoir des appels téléphoniques vers ou à partir des lignes terrain et téléphones mobiles via le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="3f4b4-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![L’appel dans les équipes](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="3f4b4-109">Conditions requises pour l’activation de l’onglet **appels** dans les équipes</span><span class="sxs-lookup"><span data-stu-id="3f4b4-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="3f4b4-110">Pour activer l’onglet **appels** dans les équipes, les utilisateurs doivent disposer de 1:1 appel activé dans les équipes et à l’aide d’un client équipes qui prend en charge les équipes de 1:1 appel.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="3f4b4-111">Pour savoir comment gérer l’appel de 1:1 dans les équipes, consultez [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f4b4-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="3f4b4-112">Pour savoir quels clients prennent en charge l’appel, lisez [les spécifications pour les équipes Microsoft et limites](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="3f4b4-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b4-113">Actuellement, la messagerie vocale ne sera pas disponible dans l’onglet appels, sauf si l’utilisateur est activé pour les appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="3f4b4-114">Conditions requises pour l’activation du **Pavé de numérotation** dans les équipes</span><span class="sxs-lookup"><span data-stu-id="3f4b4-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="3f4b4-115">Pour activer l’onglet **Pavé de numérotation** dans les équipes et autoriser les utilisateurs à émettre et recevoir des appels PSTN, vous devrez mettre en service des utilisateurs pour le système téléphonique et Plans de l’appel.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="3f4b4-116">Pour savoir comment configurer des Plans de l’appel, lisez [configurer des Plans de l’appel](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="3f4b4-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="3f4b4-117">Vous pouvez également utiliser le routage Direct pour autoriser les utilisateurs à émettre et recevoir des appels PSTN.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="3f4b4-118">Pour savoir comment configurer le routage Direct, consultez [Configurer le routage Direct](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="3f4b4-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="3f4b4-119">À l’aide de TeamsUpgradePolicy au contrôle où les appels atteindre</span><span class="sxs-lookup"><span data-stu-id="3f4b4-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="3f4b4-120">Pour contrôler si les appels entrants (et salles de conversation) atteindre dans des équipes ou Skype pour les entreprises, les administrateurs utilisent TeamsUpgradePolicy, à l’aide d’un [Centre d’administration de Microsoft équipes](https://aka.ms/teamsadmincenter) ou une session Windows PowerShell à distance avec la [Skype pour les entreprises](https://docs.microsoft.com/powershell/module/skype) applets de commande.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="3f4b4-121">La configuration par défaut de TeamsUpgradePolicy est le mode (îles), qui est conçu pour s’assurer que des professionnels de flux de travail n’est pas interrompu pendant un déploiement d’équipes.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="3f4b4-122">Par défaut, VoIP, PSTN et les appels fédérés à vos utilisateurs continuera à être acheminés vers Skype pour les entreprises jusqu'à ce que vous mettez à jour la stratégie pour activer les appels entrants aux équipes.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="3f4b4-123">Lorsque les destinataires sont en mode (îles) :</span><span class="sxs-lookup"><span data-stu-id="3f4b4-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="3f4b4-124">VOIP entrant appelle que Skype origine dans for Business toujours terrestre dans Skype du destinataire pour le client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="3f4b4-125">VOIP entrant appelle à l’origine de terrain d’équipes dans les équipes, *Si l’expéditeur et le destinataire sont sur le même client*.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="3f4b4-126">Entrant fédérés VOIP (quel que soit le client provient) et appels PSTN toujours terrestre dans Skype du destinataire pour le client d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="3f4b4-127">Pour vous assurer qu’entrant VOIP et PSTN appelle toujours terrestre dans un client de l’utilisateur équipes, mettre à jour en mode de coexistence de l’utilisateur pour être TeamsOnly (c'est-à-dire, les assigner l’instance de « UpgradeToTeams » de TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="3f4b4-128">Pour plus d’informations sur les modes de coexistence et de TeamsUpgradePolicy, voir [Migration et l’interopérabilité pour les organisations à l’aide des équipes avec Skype pour les entreprises](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="3f4b4-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="3f4b4-129">**NOTES**</span><span class="sxs-lookup"><span data-stu-id="3f4b4-129">**NOTES**</span></span>
 - <span data-ttu-id="3f4b4-130">Skype pour les téléphones IP Business recevra les appels, même si l’utilisateur est en mode TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="3f4b4-131">Utilisateurs qui ont été mis en service avec un système téléphonique et appel des Plans de licences pour une utilisation avec Skype pour Business Online (par exemple, ils ont été assignés une valeur de OnlineVoiceRoutingPolicy), l’onglet appels activés dans les équipes et peuvent passer des appels PSTN sortants à partir de Équipes sans avoir à aucune action d’administration des administrateurs.</span><span class="sxs-lookup"><span data-stu-id="3f4b4-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="3f4b4-132">Comment configurer les utilisateurs pour la réception de tous les VOIP et PSTN entrants des appels dans les équipes</span><span class="sxs-lookup"><span data-stu-id="3f4b4-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="3f4b4-133">Pour garantir que les utilisateurs reçoivent tous les appels entrants VOIP et PSTN dans les équipes, définit le mode de coexistence de l’utilisateur TeamsOnly dans le centre d’administration Microsoft Teams, ou bien utilisez Skype pour la session Windows PowerShell à distance Business pour mettre à jour TeamsUpgradePolicy comme suit :</span><span class="sxs-lookup"><span data-stu-id="3f4b4-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="3f4b4-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3f4b4-134">See also</span></span>
[<span data-ttu-id="3f4b4-135">Configurer des forfaits d'appels</span><span class="sxs-lookup"><span data-stu-id="3f4b4-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="3f4b4-136">Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="3f4b4-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="3f4b4-137">Système téléphonique avec les Plans d’appel</span><span class="sxs-lookup"><span data-stu-id="3f4b4-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="3f4b4-138">Skype pour référence d’applet de commande PowerShell Business</span><span class="sxs-lookup"><span data-stu-id="3f4b4-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

