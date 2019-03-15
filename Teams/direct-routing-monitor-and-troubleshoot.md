---
title: Contrôler et dépanner le routage direct
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Cet article décrit comment analyser et résoudre les problèmes de votre configuration de routage Direct.
ms.openlocfilehash: d4cddc98ba1ba7343d17084c3635c1fc42d5332b
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569135"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="b534f-103">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="b534f-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="b534f-104">Cet article décrit comment analyser et résoudre les problèmes de votre configuration de routage Direct.</span><span class="sxs-lookup"><span data-stu-id="b534f-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="b534f-105">La possibilité d’émettre et recevoir des appels à l’aide de routage Direct implique les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b534f-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="b534f-106">Contrôleurs de frontière de session (SBC)</span><span class="sxs-lookup"><span data-stu-id="b534f-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="b534f-107">Diriger les composants de routage dans le Cloud Microsoft</span><span class="sxs-lookup"><span data-stu-id="b534f-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="b534f-108">Jonctions de télécommunications</span><span class="sxs-lookup"><span data-stu-id="b534f-108">Telecom trunks</span></span> 

<span data-ttu-id="b534f-109">Si vous avez des problèmes de la résolution des problèmes, ouvrez une demande de support avec votre fournisseur SBC ou Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b534f-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="b534f-110">Microsoft travaille sur plusieurs outils de dépannage et d’analyse.</span><span class="sxs-lookup"><span data-stu-id="b534f-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="b534f-111">Consultez la documentation régulièrement des mises à jour.</span><span class="sxs-lookup"><span data-stu-id="b534f-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="b534f-112">Analyse de la disponibilité des contrôleurs de frontière de Session à l’aide de messages de protocole SIP (Session Initiation) Options</span><span class="sxs-lookup"><span data-stu-id="b534f-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) Options messages</span></span>

<span data-ttu-id="b534f-113">Routage direct utilise Options SIP envoyés par les contrôleurs de frontière de Session pour surveiller l’intégrité SBC.</span><span class="sxs-lookup"><span data-stu-id="b534f-113">Direct Routing uses SIP Options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="b534f-114">Il n’existe aucune action requise à partir de l’administrateur de clients pour activer la surveillance des Options SIP.</span><span class="sxs-lookup"><span data-stu-id="b534f-114">There are no actions required from the tenant administrator to enable the SIP Options monitoring.</span></span> <span data-ttu-id="b534f-115">Les informations collectées sont prises en considération lors des décisions de routage.</span><span class="sxs-lookup"><span data-stu-id="b534f-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="b534f-116">Par exemple, si, pour un utilisateur spécifique, il existe plusieurs SBCs disponibles pour un routage des appels, routage Direct considère que les informations d’Options SIP provenance de chaque SBC pour déterminer le routage.</span><span class="sxs-lookup"><span data-stu-id="b534f-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP Options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="b534f-117">Le diagramme suivant illustre un exemple de la configuration :</span><span class="sxs-lookup"><span data-stu-id="b534f-117">The following diagram shows an example of the configuration:</span></span> 

![Exemple de configuration des options SIP](media/sip-options-config-example.png)

<span data-ttu-id="b534f-119">Lorsqu’un utilisateur effectue un appel vers le numéro +1 425 \<les sept digits>, routage Direct évalue l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="b534f-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="b534f-120">Il existe deux SBCs dans l’itinéraire : sbc1.contoso.com et sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="b534f-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="b534f-121">Les deux SBCs ont une priorité équivalente dans l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="b534f-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="b534f-122">Avant de choisir un contrôleur SBC, le mécanisme d’acheminement évalue l’intégrité des SBCs basé sur lorsque le contrôleur SBC envoyé les Options SIP heure de la dernière.</span><span class="sxs-lookup"><span data-stu-id="b534f-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP Options last time.</span></span> 

<span data-ttu-id="b534f-123">Un contrôleur SBC est considéré comme sain si statistiques au moment de l’envoi de l’appel indique que le contrôleur SBC envoie les Options à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="b534f-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="b534f-124">Routage direct calcule des intervalles réguliers par deux fois la moyenne lorsque le contrôleur SBC envoie des Options avant l’appel et d’ajouter les cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="b534f-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends Options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="b534f-125">Par exemple, supposons que les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="b534f-125">For example, assume the following:</span></span> 

- <span data-ttu-id="b534f-126">Un contrôleur SBC est configuré pour envoyer les Options de toutes les minutes.</span><span class="sxs-lookup"><span data-stu-id="b534f-126">An SBC is configured to send Options every minute.</span></span> 
- <span data-ttu-id="b534f-127">Le contrôleur SBC a été associé à 11 h 00.</span><span class="sxs-lookup"><span data-stu-id="b534f-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="b534f-128">Le contrôleur SBC envoie options 11.01 AM, 11.02 AM, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="b534f-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="b534f-129">11.15, un utilisateur effectue un appel et le mécanisme de routage sélectionne cet SBC.</span><span class="sxs-lookup"><span data-stu-id="b534f-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="b534f-130">La logique suivante est appliquée : deux fois l’intervalle moyen lorsque le contrôleur SBC envoie Options (une minute plus une minute = deux minutes) plus de cinq minutes = sept minutes.</span><span class="sxs-lookup"><span data-stu-id="b534f-130">The following logic is applied: Two times the average interval when the SBC sends Options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="b534f-131">Il s’agit de la valeur de l’intervalle régulier pour le contrôleur SBC.</span><span class="sxs-lookup"><span data-stu-id="b534f-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="b534f-132">Si le contrôleur SBC dans notre exemple envoyé options à tout délai entre 11 h 08 et 11 h 15 (l’heure de l’appel a été effectué), il est considéré comme sain.</span><span class="sxs-lookup"><span data-stu-id="b534f-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="b534f-133">Si ce n’est pas le cas, le contrôleur SBC sera rétrogradé à partir de l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="b534f-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="b534f-134">La rétrogradation des propriétés signifie que le contrôleur SBC ne sera pas essayé en premier.</span><span class="sxs-lookup"><span data-stu-id="b534f-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="b534f-135">Par exemple, nous avons sbc1.contoso.com et sbc2.contoso.com avec une priorité équivalente.</span><span class="sxs-lookup"><span data-stu-id="b534f-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="b534f-136">Si sbc1.contoso.com n’envoie pas les Options de SIP à intervalles réguliers comme décrit plus haut, il est rétrogradé.</span><span class="sxs-lookup"><span data-stu-id="b534f-136">If sbc1.contoso.com does not send SIP Options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="b534f-137">Ensuite, sbc2.contoso.com tente de l’appel.</span><span class="sxs-lookup"><span data-stu-id="b534f-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="b534f-138">Si sbc2.contoso.con ne peut pas remettre l’appel, le sbc1.contoso.com (rétrogradé) est tentée de nouveau avant qu’une défaillance est générée.</span><span class="sxs-lookup"><span data-stu-id="b534f-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="b534f-139">Surveiller le tableau de bord Analytique de qualité des appels et des journaux SBC</span><span class="sxs-lookup"><span data-stu-id="b534f-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="b534f-140">Dans certains cas, en particulier pendant l’appariement initiale, il peut exister des problèmes liés à une mauvaise configuration des SBCs et/ou le service de routage Direct.</span><span class="sxs-lookup"><span data-stu-id="b534f-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="b534f-141">Vous pouvez utiliser les outils suivants pour analyser votre configuration :</span><span class="sxs-lookup"><span data-stu-id="b534f-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="b534f-142">Tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="b534f-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="b534f-143">Journaux SBC</span><span class="sxs-lookup"><span data-stu-id="b534f-143">SBC logs</span></span> 

<span data-ttu-id="b534f-144">Le service de routage Direct a des codes d’erreur descriptif très signalés Analytique appeler ou les journaux SBC.</span><span class="sxs-lookup"><span data-stu-id="b534f-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="b534f-145">Le tableau de bord qualité d’appel fournit des informations sur la qualité des appels et la fiabilité.</span><span class="sxs-lookup"><span data-stu-id="b534f-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="b534f-146">Pour savoir comment résoudre les problèmes à l’aide d’appel d’Analytique, voir [activation et à l’aide d’appels de tableau de bord qualité pour les équipes Microsoft et Skype pour Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et [Utiliser appel Analytique pour résoudre les problèmes d’appel de mauvaise qualité](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="b534f-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="b534f-147">En cas d’échec de l’appel, Analytique appel fournit des codes SIP standard pour vous aider à résoudre.</span><span class="sxs-lookup"><span data-stu-id="b534f-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Exemple de code SIP de l’échec d’appel](media/failed-response-code.png)

<span data-ttu-id="b534f-149">Toutefois, Analytique appel peuvent aider à uniquement quand les appels atteint les composants internes du routage Direct échouent.</span><span class="sxs-lookup"><span data-stu-id="b534f-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="b534f-150">En cas de problèmes liés au jumelage SBC ou où SIP « Inviter » a été rejeté (par exemple, le nom de la jonction de que nom de domaine complet est mal configuré), appelez l’Analytique ne permettra pas.</span><span class="sxs-lookup"><span data-stu-id="b534f-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="b534f-151">Dans ce cas, consultez les journaux SBC.</span><span class="sxs-lookup"><span data-stu-id="b534f-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="b534f-152">Routage direct envoie une description détaillée des problèmes à le SBCs ; Ces problèmes peuvent être lus à partir des journaux SBC.</span><span class="sxs-lookup"><span data-stu-id="b534f-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
