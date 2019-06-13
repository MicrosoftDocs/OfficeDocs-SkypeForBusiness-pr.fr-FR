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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Cet article décrit comment surveiller et résoudre les problèmes de votre configuration de routage direct.
ms.openlocfilehash: eeae12aafba87d9af210138f546ed82b12acbbd7
ms.sourcegitcommit: 1a768e470a9509139eeb24034def12630acb7914
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2019
ms.locfileid: "34915155"
---
# <a name="monitor-and-troubleshoot-direct-routing"></a><span data-ttu-id="7e512-103">Contrôler et dépanner le routage direct</span><span class="sxs-lookup"><span data-stu-id="7e512-103">Monitor and troubleshoot Direct Routing</span></span>

<span data-ttu-id="7e512-104">Cet article décrit comment surveiller et résoudre les problèmes de votre configuration de routage direct.</span><span class="sxs-lookup"><span data-stu-id="7e512-104">This article describes how to monitor and troubleshoot your Direct Routing configuration.</span></span> 

<span data-ttu-id="7e512-105">La possibilité de passer et de recevoir des appels à l’aide du routage direct implique les composants suivants:</span><span class="sxs-lookup"><span data-stu-id="7e512-105">The ability to make and receive calls by using Direct Routing involves the following components:</span></span> 

- <span data-ttu-id="7e512-106">Contrôleurs de frontière de session (SBCs)</span><span class="sxs-lookup"><span data-stu-id="7e512-106">Session Border Controllers (SBCs)</span></span> 
- <span data-ttu-id="7e512-107">Composants de routage directs dans Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="7e512-107">Direct Routing components in the Microsoft Cloud</span></span> 
- <span data-ttu-id="7e512-108">Circuits de télécoms</span><span class="sxs-lookup"><span data-stu-id="7e512-108">Telecom trunks</span></span> 

<span data-ttu-id="7e512-109">Si vous éprouvez des difficultés à résoudre le problème, ouvrez un dossier de support auprès de votre fournisseur de SBC ou de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7e512-109">If you have difficulties troubleshooting issues, please open a support case with your SBC vendor or Microsoft.</span></span> 

<span data-ttu-id="7e512-110">Microsoft travaille actuellement à la fourniture de plus d’outils de résolution des problèmes et de surveillance.</span><span class="sxs-lookup"><span data-stu-id="7e512-110">Microsoft is working on providing more tools for troubleshooting and monitoring.</span></span> <span data-ttu-id="7e512-111">Consultez régulièrement la documentation pour les mises à jour.</span><span class="sxs-lookup"><span data-stu-id="7e512-111">Please check the documentation periodically for updates.</span></span> 

## <a name="monitoring-availability-of-session-border-controllers-using-session-initiation-protocol-sip-options-messages"></a><span data-ttu-id="7e512-112">Surveiller la disponibilité des contrôleurs de bordure de session à l’aide de messages d’options SIP (Session Initiation Protocol)</span><span class="sxs-lookup"><span data-stu-id="7e512-112">Monitoring availability of Session Border Controllers using Session Initiation Protocol (SIP) options messages</span></span>

<span data-ttu-id="7e512-113">Le routage direct utilise les options SIP envoyées par les contrôleurs en bordure de session pour contrôler l’intégrité des SBC.</span><span class="sxs-lookup"><span data-stu-id="7e512-113">Direct Routing uses SIP options sent by the Session Border Controllers to monitor SBC health.</span></span> <span data-ttu-id="7e512-114">Aucune action n’est requise de la part de l’administrateur client pour activer la surveillance des options SIP.</span><span class="sxs-lookup"><span data-stu-id="7e512-114">There are no actions required from the tenant administrator to enable the SIP options monitoring.</span></span> <span data-ttu-id="7e512-115">Les informations collectées sont prises en compte lors de la prise de décisions de routage.</span><span class="sxs-lookup"><span data-stu-id="7e512-115">The collected information is taken into consideration when routing decisions are made.</span></span> 

<span data-ttu-id="7e512-116">Par exemple, si pour un utilisateur spécifique, il existe plusieurs SBCs disponibles pour diriger un appel, le routage direct considère les informations d’options SIP reçues de chaque SBC pour déterminer le routage.</span><span class="sxs-lookup"><span data-stu-id="7e512-116">For example, if, for a specific user, there are several SBCs available to route a call, Direct Routing considers the SIP options information received from each SBC to determine routing.</span></span> 

<span data-ttu-id="7e512-117">Le schéma suivant illustre un exemple de configuration:</span><span class="sxs-lookup"><span data-stu-id="7e512-117">The following diagram shows an example of the configuration:</span></span> 

![Exemple de configuration des options SIP](media/sip-options-config-example.png)

<span data-ttu-id="7e512-119">Lorsqu’un utilisateur effectue un appel vers le numéro + \<1 425 de sept chiffres>, le routage direct évalue l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="7e512-119">When a user makes a call to number +1 425 \<any seven digits>, Direct Routing evaluates the route.</span></span> <span data-ttu-id="7e512-120">Il existe deux éléments SBCs dans l’itinéraire: sbc1.contoso.com et sbc2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="7e512-120">There are two SBCs in the route: sbc1.contoso.com and sbc2.contoso.com.</span></span> <span data-ttu-id="7e512-121">Les deux SBCs ont une priorité égale dans l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="7e512-121">Both SBCs have equal priority in the route.</span></span> <span data-ttu-id="7e512-122">Avant de sélectionner un SBC, le mécanisme de routage évalue l’état de l’SBCs en fonction du moment où l’SBC a envoyé les options SIP pour la dernière fois.</span><span class="sxs-lookup"><span data-stu-id="7e512-122">Before picking an SBC, the routing mechanism evaluates the health of the SBCs based on when the SBC sent the SIP options last time.</span></span> 

<span data-ttu-id="7e512-123">Un SBC est considéré comme sain si les statistiques lors de l’envoi de l’appel indiquent que la ligne SBC envoie des options sur un intervalle régulier.</span><span class="sxs-lookup"><span data-stu-id="7e512-123">An SBC is considered healthy if statistics at the moment of sending the call shows that the SBC sends Options on a regular interval.</span></span>  

<span data-ttu-id="7e512-124">Le routage direct calcule les intervalles réguliers en prenant deux fois la moyenne lorsque l’SBC envoie les options avant de passer l’appel et d’ajouter cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="7e512-124">Direct Routing calculates regular intervals by taking two times the average when the SBC sends options before making the call and adding five minutes.</span></span> 

<span data-ttu-id="7e512-125">Par exemple, supposons que vous ayez les informations suivantes:</span><span class="sxs-lookup"><span data-stu-id="7e512-125">For example, assume the following:</span></span> 

- <span data-ttu-id="7e512-126">Un SBC est configuré pour envoyer des options toutes les minutes.</span><span class="sxs-lookup"><span data-stu-id="7e512-126">An SBC is configured to send options every minute.</span></span> 
- <span data-ttu-id="7e512-127">L’SBC a été couplé à 11,00 AM.</span><span class="sxs-lookup"><span data-stu-id="7e512-127">The SBC was paired at 11.00 AM.</span></span>  
- <span data-ttu-id="7e512-128">Les options d’envoi de SBC envoient à 11,01 AM, 11,02 AM, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="7e512-128">The SBC sends options at 11.01 AM, 11.02 AM, and so on.</span></span>  
- <span data-ttu-id="7e512-129">Dans 11,15, un utilisateur effectue un appel et le mécanisme de routage sélectionne cet SBC.</span><span class="sxs-lookup"><span data-stu-id="7e512-129">At 11.15, a user makes a call and the routing mechanism selects this SBC.</span></span> 

<span data-ttu-id="7e512-130">La logique suivante est appliquée: deux fois l’intervalle moyen lorsque l’SBC envoie les options (une minute plus une minute = 2 minutes) + cinq minutes = sept minutes.</span><span class="sxs-lookup"><span data-stu-id="7e512-130">The following logic is applied: Two times the average interval when the SBC sends options (one minute plus one minute = two minutes) plus five minutes = seven minutes.</span></span> <span data-ttu-id="7e512-131">Il s’agit de la valeur de l’intervalle régulier pour l’SBC.</span><span class="sxs-lookup"><span data-stu-id="7e512-131">This is the value of the regular interval for the SBC.</span></span>
 
<span data-ttu-id="7e512-132">Si l’SBC dans notre exemple a envoyé des options à n’importe quelle période entre 11,08 et 11,15 AM (l’heure de l’appel), il est considéré comme sain.</span><span class="sxs-lookup"><span data-stu-id="7e512-132">If the SBC in our example sent options at any period between 11.08 AM and 11.15 AM (the time the call was made), it is considered healthy.</span></span> <span data-ttu-id="7e512-133">Si ce n’est pas le cas, l’SBC sera abaissé de l’itinéraire.</span><span class="sxs-lookup"><span data-stu-id="7e512-133">If not, the SBC will be demoted from the route.</span></span> 

<span data-ttu-id="7e512-134">La rétrogradation signifie que l’SBC ne sera pas essayé en premier.</span><span class="sxs-lookup"><span data-stu-id="7e512-134">Demotion means that the SBC will not be tried first.</span></span> <span data-ttu-id="7e512-135">Par exemple, nous avons sbc1.contoso.com et sbc2.contoso.com avec une priorité égale.</span><span class="sxs-lookup"><span data-stu-id="7e512-135">For example, we have sbc1.contoso.com and sbc2.contoso.com with equal priority.</span></span>  

<span data-ttu-id="7e512-136">Si sbc1.contoso.com n’envoie pas d’options SIP à un intervalle régulier comme décrit ci-dessus, il est abaissé.</span><span class="sxs-lookup"><span data-stu-id="7e512-136">If sbc1.contoso.com does not send SIP options on a regular interval as described above, it is demoted.</span></span> <span data-ttu-id="7e512-137">Ensuite, sbc2.contoso.com tente d’appeler.</span><span class="sxs-lookup"><span data-stu-id="7e512-137">Next, sbc2.contoso.com tries for the call.</span></span> <span data-ttu-id="7e512-138">Si sbc2. contoso. con ne peut pas répondre à l’appel, le sbc1.contoso.com (rétrogradé) est essayé de nouveau avant la génération d’une erreur.</span><span class="sxs-lookup"><span data-stu-id="7e512-138">If sbc2.contoso.con cannot deliver the call, the sbc1.contoso.com (demoted) is tried again before a failure is generated.</span></span> 

## <a name="monitor-call-quality-analytics-dashboard-and-sbc-logs"></a><span data-ttu-id="7e512-139">Surveiller les journaux de tableau de bord d’analyse de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="7e512-139">Monitor Call Quality Analytics dashboard and SBC logs</span></span> 
 
<span data-ttu-id="7e512-140">Dans certains cas, en particulier lors du jumelage initial, il est possible qu’il y ait des problèmes liés à la configuration du service de routage SBCs et/ou du service de routage direct.</span><span class="sxs-lookup"><span data-stu-id="7e512-140">In some cases, especially during the initial pairing, there might be issues related to misconfiguration of the SBCs and/or the Direct Routing service.</span></span> 

<span data-ttu-id="7e512-141">Vous pouvez utiliser les outils suivants pour contrôler votre configuration:</span><span class="sxs-lookup"><span data-stu-id="7e512-141">You can use the following tools to monitor your configuration:</span></span>  
 
- <span data-ttu-id="7e512-142">Tableau de bord de la qualité des appels</span><span class="sxs-lookup"><span data-stu-id="7e512-142">Call Quality Dashboard</span></span> 
- <span data-ttu-id="7e512-143">Journaux de SBC</span><span class="sxs-lookup"><span data-stu-id="7e512-143">SBC logs</span></span> 

<span data-ttu-id="7e512-144">Le service de routage direct possède des codes d’erreur très descriptifs signalés aux analyses d’appel ou aux journaux de SBC.</span><span class="sxs-lookup"><span data-stu-id="7e512-144">The Direct Routing service has very descriptive error codes reported to either Call Analytics or the SBC logs.</span></span> 

<span data-ttu-id="7e512-145">Le tableau de bord de qualité des appels fournit des informations sur la qualité et la fiabilité des appels.</span><span class="sxs-lookup"><span data-stu-id="7e512-145">The Call Quality Dashboard provides information about call quality and reliability.</span></span> <span data-ttu-id="7e512-146">Pour en savoir plus sur la résolution des problèmes d’analyse des appels, reportez-vous à [activation et utilisation du tableau de bord de qualité des appels pour Microsoft teams et Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) et [utilisation de l’analyse des appels pour résoudre les problèmes de mauvaise qualité des appels](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span><span class="sxs-lookup"><span data-stu-id="7e512-146">To learn more about how to troubleshoot issues using Call Analytics, see [Turning on and using Call Quality Dashboard for Microsoft Teams and Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard) and [Use Call Analytics to troubleshoot poor call quality](https://docs.microsoft.com/SkypeForBusiness/using-call-quality-in-your-organization/use-call-analytics-to-troubleshoot-poor-call-quality).</span></span> 

<span data-ttu-id="7e512-147">En cas d’échecs d’appel, l’analyse des appels fournit des codes SIP standard pour vous aider à résoudre les problèmes.</span><span class="sxs-lookup"><span data-stu-id="7e512-147">In case of call failures, Call Analytics provides standard SIP codes to help you with troubleshooting.</span></span> 

![Exemple de code SIP pour l’échec d’un appel](media/failed-response-code.png)

<span data-ttu-id="7e512-149">Toutefois, l’analyse des appels ne peut vous aider qu’à accéder aux composants internes du routage direct et à l’échec.</span><span class="sxs-lookup"><span data-stu-id="7e512-149">However, Call Analytics can only help when calls reach the internal components of Direct Routing and fail.</span></span> <span data-ttu-id="7e512-150">En cas de problème avec le jumelage de SBC ou les problèmes liés à un rejet de «invitation» SIP (par exemple, le nom du nom de domaine complet du Trunk est mal configuré), l’analyse des appels ne vous aide pas.</span><span class="sxs-lookup"><span data-stu-id="7e512-150">In case of issues with SBC pairing or issues where SIP “Invite” was rejected (for example, the name of the trunk FQDN is misconfigured), Call Analytics will not help.</span></span> <span data-ttu-id="7e512-151">Dans le cas présent, veuillez vous référer aux journaux de SBC.</span><span class="sxs-lookup"><span data-stu-id="7e512-151">In this case, please refer to the SBC logs.</span></span> <span data-ttu-id="7e512-152">Le routage direct envoie une description détaillée des problèmes à l’SBCs; ces problèmes peuvent être lus dans les journaux de SBC.</span><span class="sxs-lookup"><span data-stu-id="7e512-152">Direct Routing sends a detailed description of issues to the SBCs; these issues can be read from the SBC logs.</span></span> 
