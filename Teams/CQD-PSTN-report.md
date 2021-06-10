---
title: Utilisation du rapport de routage direct PSTN du CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Utilisez le rapport de routage direct du Microsoft Teams de qualité des appels (CQD) pour surveiller et résoudre les problèmes d’appel RST dans Microsoft Teams.
ms.openlocfilehash: f2b63f991f42aa4de9e0e4474137f7f992f95c53
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094978"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="d718d-103">Utilisation du rapport de routage direct PSTN du CQD</span><span class="sxs-lookup"><span data-stu-id="d718d-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="d718d-104">À partir de mars 2020, nous avons ajouté un rapport de routage direct du tableau de bord de qualité des appels Microsoft Teams (CQD) à nos [modèles](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)de requêtes Power BI téléchargeables pour le tableau de bord de qualité des appels.</span><span class="sxs-lookup"><span data-stu-id="d718d-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="d718d-105">Le rapport de routage direct RQD (CQD PSTN Direct Routing Report.pbit) vous aide à comprendre les modèles d’utilisation et la qualité de vos services RQN.</span><span class="sxs-lookup"><span data-stu-id="d718d-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="d718d-106">Utilisez ce rapport pour surveiller l’utilisation du service, des informations sur votre contrôleur de session border controller (SBC), le service téléphonique, les paramètres réseau et les détails du rapport d’efficacité du réseau.</span><span class="sxs-lookup"><span data-stu-id="d718d-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="d718d-107">Ces informations peuvent vous aider à identifier les problèmes, y compris la raison de l’abandon d’appels.</span><span class="sxs-lookup"><span data-stu-id="d718d-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="d718d-108">Par exemple, vous pouvez voir quand le volume diminue ou combien d’appels sont affectés et pour quelle raison.</span><span class="sxs-lookup"><span data-stu-id="d718d-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="d718d-109">Le rapport de routage direct PSTN du CQD se présente sous quatre sections :</span><span class="sxs-lookup"><span data-stu-id="d718d-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="d718d-110">Vue d’ensemble PSTN</span><span class="sxs-lookup"><span data-stu-id="d718d-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="d718d-111">Détails du service</span><span class="sxs-lookup"><span data-stu-id="d718d-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="d718d-112">Taux d’efficacité du réseau</span><span class="sxs-lookup"><span data-stu-id="d718d-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="d718d-113">Paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="d718d-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="d718d-114">Temps forts</span><span class="sxs-lookup"><span data-stu-id="d718d-114">Highlights</span></span>

1. <span data-ttu-id="d718d-115">Analyser par type d’appel, SBC, appelant et pays de l’appelant</span><span class="sxs-lookup"><span data-stu-id="d718d-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="d718d-116">Le rapport de routage RTC RTC agrège les mesures de fiabilité et d’utilisation de tous les PC de votre client au cours des 7, 30 ou 180 derniers jours (6 mois).</span><span class="sxs-lookup"><span data-stu-id="d718d-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="d718d-117">Vous pouvez analyser les données par type d’appel, SBC, appelant et pays de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="d718d-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="d718d-118">Si vous êtes intéressé par un SBC ou un pays particulier, vous pourrez identifier les changements de tendances sur l’plage de temps sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d718d-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Capture d’écran des filtres disponibles dans le rapport de routage direct PSTN du CQD":::
   
2. <span data-ttu-id="d718d-120">Suivre les tendances</span><span class="sxs-lookup"><span data-stu-id="d718d-120">Track trends</span></span>

    <span data-ttu-id="d718d-121">L’analyse des tendances est essentielle pour tenter de comprendre l’utilisation et la fiabilité des services.</span><span class="sxs-lookup"><span data-stu-id="d718d-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="d718d-122">Les tendances horaires donnent un œil sur les performances quotidiennes, ce qui permet d’identifier les incidents en temps réel.</span><span class="sxs-lookup"><span data-stu-id="d718d-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="d718d-123">Les tendances quotidiennes vous viennent à l’état de votre service dans une perspective à long terme.</span><span class="sxs-lookup"><span data-stu-id="d718d-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="d718d-124">Il est important de pouvoir passer d’un mode à l’autre avec la granularité des données appropriée.</span><span class="sxs-lookup"><span data-stu-id="d718d-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="d718d-125">Le rapport de routage direct RQD fournit une vue d’ensemble des tendances sur 6 mois, des tendances quotidiennes sur 7 et 30 jours, et des tendances toutes les heures afin que vous pouvez analyser les performances à chaque niveau.</span><span class="sxs-lookup"><span data-stu-id="d718d-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Capture d’écran des graphiques de tendances dans le rapport de routage PSTN RQ":::

3. <span data-ttu-id="d718d-127">Drill through to SBC or user level</span><span class="sxs-lookup"><span data-stu-id="d718d-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="d718d-128">Nous avons mis en place une fonctionnalité d’analyse par le détail sur de nombreuses catégories de données du CQD, ce qui vous permet de comprendre rapidement la distribution de l’utilisation ou de la fiabilité au niveau du jeu de données (SBC) ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d718d-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="d718d-129">L’utilisation de l’outil d’évaluation vous permet de rapidement pointer des problèmes et de comprendre l’impact réel sur les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d718d-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="d718d-130">Les fonctionnalités du rapport de routage direct RQD analysent les mesures De détail du service et du rapport d’efficacité du réseau.</span><span class="sxs-lookup"><span data-stu-id="d718d-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="d718d-131">Cliquez sur le point de données qui vous intéresse pour consulter les détails au niveau utilisateur ou SBC.</span><span class="sxs-lookup"><span data-stu-id="d718d-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Capture d’écran montrant la fonctionnalité d’analyse par analyse d’un point de données":::


## <a name="pstn-overview"></a><span data-ttu-id="d718d-133">Vue d’ensemble PSTN</span><span class="sxs-lookup"><span data-stu-id="d718d-133">PSTN Overview</span></span>

<span data-ttu-id="d718d-134">Le rapport de routage direct RQD fournit les informations suivantes sur l’état global du service au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="d718d-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="d718d-135">![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="d718d-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="d718d-136">Par exemple, si vous êtes intéressé par l’utilisation globale et l’état d’état de tous les appels entrants qui traversent des abc.bca.adatum.biz SBC avec les États-Unis comme pays interne :</span><span class="sxs-lookup"><span data-stu-id="d718d-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="d718d-137">**Appeler**</span><span class="sxs-lookup"><span data-stu-id="d718d-137">**Call Out**</span></span> | <span data-ttu-id="d718d-138">**Description**</span><span class="sxs-lookup"><span data-stu-id="d718d-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="d718d-139">1</span><span class="sxs-lookup"><span data-stu-id="d718d-139">1</span></span>            | <span data-ttu-id="d718d-140">Vous pouvez utiliser les filtres dans la partie supérieure pour descendre dans la liste et sélectionner ByotIn comme type d’appel, abc.bca.contoso.com contrôleur de session et États-Unis comme pays interne.</span><span class="sxs-lookup"><span data-stu-id="d718d-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="d718d-141">2</span><span class="sxs-lookup"><span data-stu-id="d718d-141">2</span></span>            | <span data-ttu-id="d718d-142">Tendance d’utilisation au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="d718d-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="d718d-143">Le rapport des détails de l’utilisation se trouve sur la page Détails du service.</span><span class="sxs-lookup"><span data-stu-id="d718d-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="d718d-144">3</span><span class="sxs-lookup"><span data-stu-id="d718d-144">3</span></span>            | <span data-ttu-id="d718d-145">Tendance de retard après la numérotation, de latence, de gigue et de perte de paquets au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="d718d-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="d718d-146">Vous pouvez trouver un rapport détaillé sur la page Paramètres réseau.</span><span class="sxs-lookup"><span data-stu-id="d718d-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="d718d-147">4</span><span class="sxs-lookup"><span data-stu-id="d718d-147">4</span></span>            | <span data-ttu-id="d718d-148">Tendance des appels simultanés et de l’utilisateur actif quotidien au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="d718d-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="d718d-149">Ce graphique peut vous aider à comprendre le volume maximum du service.</span><span class="sxs-lookup"><span data-stu-id="d718d-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="d718d-150">5</span><span class="sxs-lookup"><span data-stu-id="d718d-150">5</span></span>            | <span data-ttu-id="d718d-151">La principale raison de la fin des appels affecte la qualité du service au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="d718d-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="d718d-152">Vous trouverez des détails sur l’état du service sur la page Network Effective Ratio (NER).</span><span class="sxs-lookup"><span data-stu-id="d718d-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="d718d-153">Détails du service</span><span class="sxs-lookup"><span data-stu-id="d718d-153">Service Details</span></span>

<span data-ttu-id="d718d-154">Cette page présente les tendances d’utilisation des services par jour et le détail des commentaires des utilisateurs par géographie.</span><span class="sxs-lookup"><span data-stu-id="d718d-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="d718d-155">**Nombre total de tentatives d’appels –** Nombre total de tentatives d’appels dans ce plage de temps, y compris les appels réussis et les appels en échec</span><span class="sxs-lookup"><span data-stu-id="d718d-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="d718d-156">**Nombre total d’appels connectés -** Nombre total d’appels connectés dans ce délai</span><span class="sxs-lookup"><span data-stu-id="d718d-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="d718d-157">**Nombre total de minutes –** Utilisation totale des minutes dans cet plage</span><span class="sxs-lookup"><span data-stu-id="d718d-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="d718d-158">**Utilisateurs actifs quotidiens (DAU) –** Nombre d’utilisateurs actifs par jour ayant effectué au moins un appel connecté ce jour-là</span><span class="sxs-lookup"><span data-stu-id="d718d-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="d718d-159">**Appels simultanés –** Nombre maximum d’appels actifs simultanés en une minute</span><span class="sxs-lookup"><span data-stu-id="d718d-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="d718d-160">**Commentaires des utilisateurs –** La note « Évaluer mon appel » provient de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="d718d-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="d718d-161">3-5 est considéré comme un appel bon.</span><span class="sxs-lookup"><span data-stu-id="d718d-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="d718d-162">Le 1-2 est considéré comme un appel mauvais.</span><span class="sxs-lookup"><span data-stu-id="d718d-162">1-2 is considered as a bad call.</span></span>

![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report2.png)

<span data-ttu-id="d718d-164">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d718d-164">For example:</span></span>

1.  <span data-ttu-id="d718d-165">Si vous constatez que la durée moyenne de l’appel passe à 0 au 14/02/2020, vous pouvez tout d’abord vérifier si le volume d’appel semble normal et vérifier s’il existe une différence importante entre le nombre total d’appels de connexion et le nombre total d’appels tentés.</span><span class="sxs-lookup"><span data-stu-id="d718d-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="d718d-166">Ensuite, sur la page Rapport d’efficacité du réseau, vous allez investir sur les raisons d’échec d’appel.</span><span class="sxs-lookup"><span data-stu-id="d718d-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="d718d-167">Si vous remarquez des spots rouges croissants sur la carte de commentaires des utilisateurs, vous pouvez passer à la page Rapport d’efficacité du réseau et au paramètre réseau pour voir s’il existe des points de suite, et élever un ticket à l’aide de MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="d718d-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="d718d-168">Taux d’efficacité du réseau</span><span class="sxs-lookup"><span data-stu-id="d718d-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="d718d-169">Il s’agit de la même valeur qui apparaît dans le tableau de bord État global.</span><span class="sxs-lookup"><span data-stu-id="d718d-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="d718d-170">Vous pouvez vérifier toutes les heures le numéro de neR avec les détails des appels affectés pour les deux itinéraires d’appel (entrant/sortant) sur le rapport d’efficacité du réseau toutes les heures et le graphique de raison de fin d’appel ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="d718d-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="d718d-171">**NER** - Possibilité (%) d’un réseau pour envoyer des appels en mesurant le nombre d’appels envoyés et le nombre d’appels remis à un destinataire.</span><span class="sxs-lookup"><span data-stu-id="d718d-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="d718d-172">**Code de réponse SIP**: code de réponse d’un nombre de trois chiffres indique le statut de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d718d-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="d718d-173">**Code de réponse De Microsoft**- Code de réponse envoyé à partir du composant Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d718d-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="d718d-174">**Description** – Phase de raison correspondant au code de réponse SIP et au code de réponse de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d718d-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="d718d-175">**Nombre d’appels affectés** – Nombre total d’appels affectés pendant l’plage de temps sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="d718d-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="d718d-177">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d718d-177">For example:</span></span>

![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report4.png)

<span data-ttu-id="d718d-179">Si la fonction NER quotidienne présente une baisse le 05/02/2020, vous pouvez cliquer sur la date pour que les autres graphiques effectuent un zoom sur cette date spécifique.</span><span class="sxs-lookup"><span data-stu-id="d718d-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report5.png)

<span data-ttu-id="d718d-181">À partir de la tendance du pourcentage d’heures faible, la baisse se produit aux environs de 21:00.</span><span class="sxs-lookup"><span data-stu-id="d718d-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="d718d-182">Cliquez à nouveau pour effectuer un zoom avant sur l’heure 21 et consultez les détails de l’appel pour voir le nombre d’appels qui ont échoué au cours de cette heure et quelles sont les raisons de la fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="d718d-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="d718d-183">Vous pouvez commencer par vous-même résoudre les problèmes SBC ou signaler à Service Desk si le problème n’est pas lié à SBC.</span><span class="sxs-lookup"><span data-stu-id="d718d-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="d718d-184">Paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="d718d-184">Network Parameters</span></span>

<span data-ttu-id="d718d-185">Tous les paramètres réseau sont mesurés à partir de l’interface de routage direct vers le contrôleur de bordure de session.</span><span class="sxs-lookup"><span data-stu-id="d718d-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="d718d-186">Pour plus [d’informations](prepare-network.md)sur les valeurs recommandées, voir Préparer le réseau de votre organisation pour Microsoft Teams et examiner le bord du client pour Microsoft Edge valeurs recommandées.</span><span class="sxs-lookup"><span data-stu-id="d718d-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="d718d-187">**Gigue –** Mesure en millisecondes du retard de propagation réseau calculée entre deux points de terminaison à l’aide du protocole RTCP (protocole de contrôle RTP).</span><span class="sxs-lookup"><span data-stu-id="d718d-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="d718d-188">**Perte de paquets** – mesure du nombre de paquets qui n’ont pas réussi à arriver ; elle est calculée entre deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="d718d-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="d718d-189">**Latence** - (également appelée durée des allers-retours) est la durée de l’envoi d’un signal, plus la durée de réception de l’accusé de réception de ce signal.</span><span class="sxs-lookup"><span data-stu-id="d718d-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="d718d-190">Ce délai est constitué des heures de propagation entre les deux points d’un signal.</span><span class="sxs-lookup"><span data-stu-id="d718d-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report6.png)

<span data-ttu-id="d718d-192">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="d718d-192">For example:</span></span>

<span data-ttu-id="d718d-193">Si vous voyez un pic sur l’un des quatre graphiques (Latence, Gigue, Taux de perte de package, Retard après la numérotation) pour une date spécifique (par exemple, Latence le 14/02/2020), cliquez sur le point de date.</span><span class="sxs-lookup"><span data-stu-id="d718d-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="d718d-194">Le graphique de tendance horaire au bas de la page sera actualisé pour afficher le nombre toutes les heures.</span><span class="sxs-lookup"><span data-stu-id="d718d-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="d718d-195">Vous pouvez vérifier les SBCs ou lever un ticket auprès de MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="d718d-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Capture d’écran : Rapport du QQD PSTN](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="d718d-197">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="d718d-197">Related topics</span></span>

[<span data-ttu-id="d718d-198">Utiliser Power BI pour analyser les données du sous-Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d718d-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="d718d-199">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="d718d-199">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)