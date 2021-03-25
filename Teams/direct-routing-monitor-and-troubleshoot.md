---
title: Contrôler et dépanner le routage direct
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment surveiller et résoudre les problèmes de configuration du routage direct, notamment les contrôleurs de bordure de session, les composants de routage direct et les ligne de télécommunications.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74a67493fa2f9647e6cd0364bb4c9d6a3c05e48a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121402"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="0e44f-103">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="0e44f-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="0e44f-104">Cet article explique comment surveiller et dépanner votre configuration de routage direct.</span><span class="sxs-lookup"><span data-stu-id="0e44f-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="0e44f-105">La possibilité d’effectuer et de recevoir des appels à l’aide du routage direct implique les composants suivants :</span><span class="sxs-lookup"><span data-stu-id="0e44f-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="0e44f-106">Contrôleurs de session en bordure (SBCs)</span><span class="sxs-lookup"><span data-stu-id="0e44f-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="0e44f-107">Composants de routage direct dans Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="0e44f-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="0e44f-108">Telecom trunks</span><span class="sxs-lookup"><span data-stu-id="0e44f-108">Telecom trunks</span></span> 

<span data-ttu-id="0e44f-109">Si vous avez des difficultés à résoudre des problèmes, vous pouvez ouvrir un cas de support auprès de votre fournisseur SBC ou de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0e44f-109">If you have difficulties troubleshooting issues, you can open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="0e44f-110">Microsoft travaille à la fourniture d’autres outils pour la résolution des problèmes et la surveillance.</span><span class="sxs-lookup"><span data-stu-id="0e44f-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="0e44f-111">Consultez régulièrement la documentation pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="0e44f-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="0e44f-112">Surveillance de la disponibilité des contrôleurs de session en bordure à l’aide des messages d’options SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="0e44f-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="0e44f-113">Le routage direct utilise les options SIP envoyées par les contrôleurs de session border pour surveiller l’état du SBC.</span><span class="sxs-lookup"><span data-stu-id="0e44f-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="0e44f-114">Aucune action n’est requise de la part de l’administrateur client pour activer la surveillance des options SIP.</span><span class="sxs-lookup"><span data-stu-id="0e44f-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="0e44f-115">Les informations collectées sont prises en compte lors des décisions de routage.</span><span class="sxs-lookup"><span data-stu-id="0e44f-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="0e44f-116">Par exemple, si, pour un utilisateur spécifique, plusieurs SBC sont disponibles pour router un appel, le routage direct examine les informations d’options SIP reçues de chaque SBC pour déterminer le routage.</span><span class="sxs-lookup"><span data-stu-id="0e44f-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="0e44f-117">Le diagramme suivant montre un exemple de configuration :</span><span class="sxs-lookup"><span data-stu-id="0e44f-117">The following diagram shows an example of the configuration:</span></span> 

![Exemple de configuration des options SIP](media/sip-options-config-example.png)

<span data-ttu-id="0e44f-119">Lorsqu’un utilisateur appelle le numéro +1 425, le \<any seven digits> routage direct évalue l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="0e44f-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="0e44f-120">Il existe deux SBCS dans l’itinéraire : sbc1.contoso.com et sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0e44f-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="0e44f-121">Les deux SBCS ont la même priorité sur l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="0e44f-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="0e44f-122">Avant de choisir un SBC, le mécanisme de routage évalue l’état des SBC en fonction de la dernière fois que le SBC a envoyé les options SIP.</span><span class="sxs-lookup"><span data-stu-id="0e44f-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="0e44f-123">Un SBC est considéré comme sain si les statistiques au moment de l’envoi de l’appel indiquent que le SBC envoie des options toutes les minutes.</span><span class="sxs-lookup"><span data-stu-id="0e44f-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends options every minute.</span></span>  

<span data-ttu-id="0e44f-124">Lorsqu’un appel est effectué, la logique suivante s’applique :</span><span class="sxs-lookup"><span data-stu-id="0e44f-124">When a call is made, the following logic applies:</span></span>

- <span data-ttu-id="0e44f-125">Le SBC a été couplé à 11:00.</span><span class="sxs-lookup"><span data-stu-id="0e44f-125">The SBC was paired at 11:00 AM.</span></span>  
- <span data-ttu-id="0e44f-126">Le SBC envoie des options à 11:01, 11:02, etc.</span><span class="sxs-lookup"><span data-stu-id="0e44f-126">The SBC sends options at 11:01 AM, 11:02 AM, and so on.</span></span>  
- <span data-ttu-id="0e44f-127">À 23:15, un utilisateur effectue un appel et le mécanisme de routage sélectionne ce SBC.</span><span class="sxs-lookup"><span data-stu-id="0e44f-127">At 11:15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="0e44f-128">Le routage direct prend les options d’intervalle régulier trois fois (l’intervalle régulier est d’une minute).</span><span class="sxs-lookup"><span data-stu-id="0e44f-128">Direct Routing takes the regular interval options three times (the regular interval is one minute).</span></span> <span data-ttu-id="0e44f-129">Si des options ont été envoyés au cours des trois dernières minutes, le SBC est considéré comme étant sain.</span><span class="sxs-lookup"><span data-stu-id="0e44f-129">If options were send during the last three minutes, the SBC is considered healthy.</span></span>

<span data-ttu-id="0e44f-130">Si le SBC de l’exemple a été envoyé à des options à n’importe quel moment entre 11:12 et 11:15 (heure à l’heure de l’appel), il est considéré comme étant sain.</span><span class="sxs-lookup"><span data-stu-id="0e44f-130">If the SBC in the example sent options at any period between 11:12 AM and 11:15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="0e44f-131">Si ce n’est pas le cas, le SBC est rétrogradé de l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="0e44f-131">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="0e44f-132">Demotion signifie que le SBC ne sera pas tenté en premier.</span><span class="sxs-lookup"><span data-stu-id="0e44f-132">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="0e44f-133">Par exemple, nous avons des sbc1.contoso.com et sbc2.contoso.com priorité égale.</span><span class="sxs-lookup"><span data-stu-id="0e44f-133">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="0e44f-134">Si sbc1.contoso.com n’envoie pas les options SIP à intervalles réguliers comme décrit précédemment, elle est rétrogradée.</span><span class="sxs-lookup"><span data-stu-id="0e44f-134">If sbc1.contoso.com does not send SIP options on a regular interval as previously described, it is demoted.</span></span> <span data-ttu-id="0e44f-135">Ensuite, sbc2.contoso.com pour l’appel.</span><span class="sxs-lookup"><span data-stu-id="0e44f-135">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="0e44f-136">Si sbc2.contoso.con ne peut pas donner l’appel, l’sbc1.contoso.com (rétrogradé) fait l’appel à nouveau avant qu’un échec ne soit généré.</span><span class="sxs-lookup"><span data-stu-id="0e44f-136">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

<span data-ttu-id="0e44f-137">Si deux (ou plusieurs) SBCs dans un même itinéraire sont considérés comme sains et égaux, un mélange Fisher-Yates est appliqué pour distribuer les appels entre les SBCs.</span><span class="sxs-lookup"><span data-stu-id="0e44f-137">If two (or more) SBCs in one route are considered healthy and equal, Fisher-Yates shuffle is applied to distribute the calls between the SBCs.</span></span>

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="0e44f-138">Surveiller le tableau de bord d’analyse de la qualité des appels et les journaux SBC</span><span class="sxs-lookup"><span data-stu-id="0e44f-138">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="0e44f-139">Dans certains cas, en particulier lors du coupage initial, des problèmes peuvent se trouver liés à une configuration mal configurée des SCS ou du service de routage direct.</span><span class="sxs-lookup"><span data-stu-id="0e44f-139">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs or the Direct Routing service.</span></span> 

<span data-ttu-id="0e44f-140">Vous pouvez utiliser les outils suivants pour surveiller votre configuration :</span><span class="sxs-lookup"><span data-stu-id="0e44f-140">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="0e44f-141">Tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="0e44f-141">Call Quality Dashboard</span></span> 
- <span data-ttu-id="0e44f-142">Journaux SBC</span><span class="sxs-lookup"><span data-stu-id="0e44f-142">SBC logs</span></span> 

<span data-ttu-id="0e44f-143">Les codes d’erreur très descriptifs du service de routage direct sont signalés aux journaux d’analyse des appels ou SBC.</span><span class="sxs-lookup"><span data-stu-id="0e44f-143">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="0e44f-144">Le tableau de bord de qualité des appels fournit des informations sur la qualité et la fiabilité des appels.</span><span class="sxs-lookup"><span data-stu-id="0e44f-144">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="0e44f-145">Pour en savoir plus sur la résolution des problèmes à l’aide de l’analyse des appels, voir Mise en place et utilisation du tableau de bord de qualité des appels pour [Microsoft Teams](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et Skype Entreprise Online et Utiliser l’analyse des appels pour résoudre les problèmes de qualité des [appels.](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality)</span><span class="sxs-lookup"><span data-stu-id="0e44f-145">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="0e44f-146">En cas d’échec d’appel, l’analyse des appels fournit des codes SIP standard pour vous aider à résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="0e44f-146">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Exemple de code SIP pour l’échec d’appel](media/failed-response-code.png)

<span data-ttu-id="0e44f-148">Toutefois, l’analyse des appels ne peut vous aider que lorsque les appels atteignent les composants internes du routage direct et échouent.</span><span class="sxs-lookup"><span data-stu-id="0e44f-148">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="0e44f-149">En cas de problèmes de jumelage SBC ou de problèmes de rejet de l’invitation siP (par exemple, le nom de la ligne de nom de domaine complet n’est pas configuré de façon configurée), l’analyse des appels n’est pas utile.</span><span class="sxs-lookup"><span data-stu-id="0e44f-149">In case of issues with SBC pairing or issues where SIP "Invite" was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="0e44f-150">Dans ce cas, consultez les journaux SBC.</span><span class="sxs-lookup"><span data-stu-id="0e44f-150">In this case, refer to the SBC logs.</span></span> <span data-ttu-id="0e44f-151">Le routage direct envoie une description détaillée des problèmes aux SCS. ces problèmes peuvent être lus à partir des journaux SBC.</span><span class="sxs-lookup"><span data-stu-id="0e44f-151">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span>