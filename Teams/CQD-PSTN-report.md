---
title: Utilisation du rapport de routage direct RTC bord
ms.author: lolaj
author: LolaJacobsen
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
description: Utilisez le rapport de routage téléphonique RTC de Microsoft Teams (bord) pour surveiller et résoudre les problèmes de la fonction d’appel RTC de Microsoft Teams.
ms.openlocfilehash: 0987ae30c9bb0b428a4d46bf036c2de938c555f0
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085340"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="fae0a-103">Utilisation du rapport de routage direct RTC bord</span><span class="sxs-lookup"><span data-stu-id="fae0a-103">Using the CQD PSTN Direct Routing report</span></span>

<span data-ttu-id="fae0a-104">Nouveauté du 2020 mars, nous avons ajouté un rapport de routage direct de tableau de bord de qualité des appels de Microsoft Teams (bord) vers nos [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="fae0a-104">New in March 2020, we've added a Microsoft Teams Call Quality Dashboard (CQD) PSTN Direct Routing report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="fae0a-105">Le rapport de routage direct RTC de bord (bord RTC direct Routing. PBiT) vous aide à comprendre les modèles d’utilisation et la qualité de vos services RTC.</span><span class="sxs-lookup"><span data-stu-id="fae0a-105">The CQD PSTN Direct Routing report (CQD PSTN Direct Routing Report.pbit) helps you understand the usage patterns and quality of your PSTN services.</span></span> <span data-ttu-id="fae0a-106">Utilisez ce rapport pour contrôler l’utilisation du service, les informations relatives à votre contrôleur de bordure de session (SBC), au service de téléphonie, aux paramètres réseau et aux détails du rapport d’efficacité réseau.</span><span class="sxs-lookup"><span data-stu-id="fae0a-106">Use this report to monitor service usage, information about your Session Border Controller (SBC), the telephony service, network parameters, and Network Effectiveness Ratio details.</span></span> <span data-ttu-id="fae0a-107">Ces informations peuvent vous aider à identifier les problèmes, notamment le motif des appels interrompus.</span><span class="sxs-lookup"><span data-stu-id="fae0a-107">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="fae0a-108">Par exemple, vous pouvez voir le nombre de chutes de volume ou le nombre d’appels qui sont affectés et la raison pour laquelle vous vous trouvez.</span><span class="sxs-lookup"><span data-stu-id="fae0a-108">For example, you'll be able to see when volume drops, or how many calls get affected and for what reason.</span></span>


<span data-ttu-id="fae0a-109">Le rapport de routage direct RTC de bord comporte quatre sections :</span><span class="sxs-lookup"><span data-stu-id="fae0a-109">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="fae0a-110">Présentation RTC</span><span class="sxs-lookup"><span data-stu-id="fae0a-110">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="fae0a-111">Détails du service</span><span class="sxs-lookup"><span data-stu-id="fae0a-111">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="fae0a-112">Taux d’efficacité du réseau</span><span class="sxs-lookup"><span data-stu-id="fae0a-112">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="fae0a-113">Paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="fae0a-113">Network Parameters</span></span>](#network-parameters)

## <a name="highlights"></a><span data-ttu-id="fae0a-114">Annonces</span><span class="sxs-lookup"><span data-stu-id="fae0a-114">Highlights</span></span>

1. <span data-ttu-id="fae0a-115">Analyser par type d’appel, SBC, appelant et pays de l’appelé</span><span class="sxs-lookup"><span data-stu-id="fae0a-115">Analyze by call type, SBC, caller and callee country</span></span>

   <span data-ttu-id="fae0a-116">Le rapport de routage direct RTC de bord agrège les métriques de fiabilité et d’utilisation de tous les éléments SBCs de votre client pour les derniers 7, 30 ou 180 (6 mois).</span><span class="sxs-lookup"><span data-stu-id="fae0a-116">The CQD PSTN Direct Routing report aggregates reliability and usage metrics for all SBCs on your tenant for the last 7, 30, or 180 days (6 months).</span></span> <span data-ttu-id="fae0a-117">Vous pouvez analyser les données par type d’appel, SBC, appelant et pays de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="fae0a-117">You can analyze data by call type, SBC, caller and callee country.</span></span> <span data-ttu-id="fae0a-118">Si vous êtes intéressé par un SBC ou un pays particulier, vous serez en mesure d’identifier les changements dans les tendances au cours de la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fae0a-118">If you're interested in a particular SBC or country, you'll be able to identify changes in trends over the selected time range.</span></span>
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Capture d’écran de filtres disponibles dans le rapport de routage direct RTC bord":::
   
2. <span data-ttu-id="fae0a-120">Suivi des tendances</span><span class="sxs-lookup"><span data-stu-id="fae0a-120">Track trends</span></span>

    <span data-ttu-id="fae0a-121">L’analyse des tendances est essentielle lorsque l’on tente de comprendre l’utilisation et la fiabilité des services.</span><span class="sxs-lookup"><span data-stu-id="fae0a-121">Trends analysis is essential when trying to understand service usage and reliability.</span></span> <span data-ttu-id="fae0a-122">Les tendances horaires permettent de mieux cerner les performances journalières, ce qui permet d’identifier les incidents en temps réel.</span><span class="sxs-lookup"><span data-stu-id="fae0a-122">Hourly trends provide a close look at daily performance, which helps identify real-time incidents.</span></span> <span data-ttu-id="fae0a-123">Les tendances journalières vous permettent d’afficher l’état de votre service sur une perspective à long terme.</span><span class="sxs-lookup"><span data-stu-id="fae0a-123">Daily trends let you see your service health from a long-term perspective.</span></span> <span data-ttu-id="fae0a-124">Il est important de pouvoir passer d’un mode à l’autre en bénéficiant d’une granularité appropriée aux données.</span><span class="sxs-lookup"><span data-stu-id="fae0a-124">It's important to be able to shift between those two modes with appropriate data granularity.</span></span> <span data-ttu-id="fae0a-125">Le rapport de routage direct RTC bord fournit une vue d’ensemble des tendances de 6 mois, des tendances journalières de 7 et 30 jours et des tendances horaires pour vous permettre d’analyser les performances à chaque niveau.</span><span class="sxs-lookup"><span data-stu-id="fae0a-125">The CQD PSTN Direct Routing report provides 6-month trends overview, 7- and 30-day daily trends, and hourly trends so you can analyze performance at each level.</span></span>
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Capture d’écran de graphes de tendances dans bord rapport de routage direct RTC":::

3. <span data-ttu-id="fae0a-127">Extraire vers le niveau de SBC ou d’utilisateur</span><span class="sxs-lookup"><span data-stu-id="fae0a-127">Drill through to SBC or user level</span></span>

   <span data-ttu-id="fae0a-128">Nous avons créé dans le cadre de la fonctionnalité d’exploration sur de nombreuses catégories de données dans bord, qui vous permettent de mieux comprendre la distribution de l’utilisation et de la fiabilité au niveau du SBC ou de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fae0a-128">We've been building in drill-through capability on many data categories in CQD, which lets you quickly understand usage or reliability distribution at the SBC or user level.</span></span> <span data-ttu-id="fae0a-129">Grâce à l’extraction, vous pouvez rapidement poinpoint des problèmes et comprendre un impact réel sur l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fae0a-129">By using drill through, you can quickly poinpoint issues and understand real user impact.</span></span> <span data-ttu-id="fae0a-130">Les fonctionnalités du rapport de routage direct RTC de bord analysent les détails relatifs au service et aux métriques du rapport d’efficacité réseau.</span><span class="sxs-lookup"><span data-stu-id="fae0a-130">The CQD PSTN Direct Routing report features drill through on the Service Detail and Network Effectiveness Ratio metrics.</span></span> <span data-ttu-id="fae0a-131">Cliquez sur le point de données qui vous intéresse pour extraire des détails au niveau utilisateur ou SBC.</span><span class="sxs-lookup"><span data-stu-id="fae0a-131">Click the data point you're interested in to drill through to SBC- or user-level details.</span></span>
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Capture d’écran illustrant la fonctionnalité d’exploration sur un point de données":::


## <a name="pstn-overview"></a><span data-ttu-id="fae0a-133">Présentation RTC</span><span class="sxs-lookup"><span data-stu-id="fae0a-133">PSTN Overview</span></span>

<span data-ttu-id="fae0a-134">Le rapport de routage direct RTC bord fournit les informations suivantes relatives à l’intégrité globale du service au cours des derniers jours 180.</span><span class="sxs-lookup"><span data-stu-id="fae0a-134">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="fae0a-135">![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="fae0a-135">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="fae0a-136">Par exemple, si vous êtes intéressé par l’utilisation globale et l’intégrité de tous les appels entrants à l’aide de SBC abc.bca.adatum.biz en tant que pays interne :</span><span class="sxs-lookup"><span data-stu-id="fae0a-136">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="fae0a-137">**Appel hors**</span><span class="sxs-lookup"><span data-stu-id="fae0a-137">**Call Out**</span></span> | <span data-ttu-id="fae0a-138">**Description**</span><span class="sxs-lookup"><span data-stu-id="fae0a-138">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fae0a-139">1</span><span class="sxs-lookup"><span data-stu-id="fae0a-139">1</span></span>            | <span data-ttu-id="fae0a-140">Vous pouvez utiliser les filtres en haut pour descendre dans la direction et sélectionner ByotIn en tant que type d’appel, abc.bca.contoso.com en tant que contrôleur de tableau de bord, et vers les États-Unis comme pays interne.</span><span class="sxs-lookup"><span data-stu-id="fae0a-140">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="fae0a-141">2</span><span class="sxs-lookup"><span data-stu-id="fae0a-141">2</span></span>            | <span data-ttu-id="fae0a-142">Tendance d’utilisation pour les 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="fae0a-142">Usage trend for the past 180 days.</span></span> <span data-ttu-id="fae0a-143">Le rapport sur les détails d’utilisation est sur la page des détails du service.</span><span class="sxs-lookup"><span data-stu-id="fae0a-143">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="fae0a-144">3</span><span class="sxs-lookup"><span data-stu-id="fae0a-144">3</span></span>            | <span data-ttu-id="fae0a-145">Envoyez un message de délai de numérotation, de latence, de gigue et de tendance de perte de paquets pour les 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="fae0a-145">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="fae0a-146">Vous trouverez le rapport détaillé sur la page Paramètres du réseau.</span><span class="sxs-lookup"><span data-stu-id="fae0a-146">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="fae0a-147">4</span><span class="sxs-lookup"><span data-stu-id="fae0a-147">4</span></span>            | <span data-ttu-id="fae0a-148">Tendance pour les appels simultanés et les utilisateurs actifs du jour au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="fae0a-148">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="fae0a-149">Ce graphique peut vous aider à comprendre le volume maximal du service.</span><span class="sxs-lookup"><span data-stu-id="fae0a-149">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="fae0a-150">5</span><span class="sxs-lookup"><span data-stu-id="fae0a-150">5</span></span>            | <span data-ttu-id="fae0a-151">Raison de la qualité de service affectée par le top des appels pour les 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="fae0a-151">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="fae0a-152">Pour plus d’informations sur l’état du service, consultez la page NER (Network effective ratio).</span><span class="sxs-lookup"><span data-stu-id="fae0a-152">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="fae0a-153">Détails du service</span><span class="sxs-lookup"><span data-stu-id="fae0a-153">Service Details</span></span>

<span data-ttu-id="fae0a-154">Cette page vous permet d’obtenir des tendances d’utilisation du service par jour et de décomposition des commentaires des utilisateurs par géographie.</span><span class="sxs-lookup"><span data-stu-id="fae0a-154">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="fae0a-155">**Nombre total de tentatives d’appels –** Nombre total de tentatives d’appels dans cette plage de temps, y compris les appels réussis et failed</span><span class="sxs-lookup"><span data-stu-id="fae0a-155">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="fae0a-156">**Nombre total d’appels connectés** Nombre total d’appels connectés dans cet intervalle de temps</span><span class="sxs-lookup"><span data-stu-id="fae0a-156">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="fae0a-157">**Nombre total de minutes –** Utilisation du total des minutes dans cet intervalle de temps</span><span class="sxs-lookup"><span data-stu-id="fae0a-157">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="fae0a-158">**Utilisateurs actifs quotidiens (DAU) :** Nombre d’utilisateurs actifs du jour qui ont effectué au moins un appel connecté à ce jour</span><span class="sxs-lookup"><span data-stu-id="fae0a-158">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="fae0a-159">**Appels simultanés –** Maximum d’appels actifs simultanés en une minute</span><span class="sxs-lookup"><span data-stu-id="fae0a-159">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="fae0a-160">**Commentaires des utilisateurs –** Le score « évaluer mon appel » est fourni par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="fae0a-160">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="fae0a-161">3-5 est considéré comme un bon appel.</span><span class="sxs-lookup"><span data-stu-id="fae0a-161">3-5 is considered as a good call.</span></span> <span data-ttu-id="fae0a-162">1-2 est considéré comme un appel incorrect.</span><span class="sxs-lookup"><span data-stu-id="fae0a-162">1-2 is considered as a bad call.</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report2.png)

<span data-ttu-id="fae0a-164">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fae0a-164">For example:</span></span>

1.  <span data-ttu-id="fae0a-165">Si vous voyez que la durée moyenne des appels tombe à 0 sur 02/14/2020, vous pouvez commencer par vérifier si le volume de l’appel est normal et voir s’il y a une différence importante entre les appels de connexion et les appels de connexion au total.</span><span class="sxs-lookup"><span data-stu-id="fae0a-165">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="fae0a-166">Puis accédez à la page taux d’efficience du réseau pour investir en raison de l’échec de l’appel.</span><span class="sxs-lookup"><span data-stu-id="fae0a-166">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="fae0a-167">Si vous voyez l’augmentation du nombre de points rouges sur la carte de commentaires des utilisateurs, vous pouvez accéder à page du rapport d’efficacité réseau et au paramètre réseau pour voir s’il y a des anomalies et vous pouvez déclencher un ticket avec MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="fae0a-167">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="fae0a-168">Taux d’efficacité du réseau</span><span class="sxs-lookup"><span data-stu-id="fae0a-168">Network Effectiveness Ratio</span></span>

<span data-ttu-id="fae0a-169">Il s’agit de la même métrique qui s’affiche dans le tableau de bord global de l’État.</span><span class="sxs-lookup"><span data-stu-id="fae0a-169">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="fae0a-170">Vous pouvez vérifier le numéro NER en fonction des appels en fonction du nombre d’appels (entrant/sortant) sur le taux d’efficacité du réseau horaire et sur le graphique raison de fin de l’appel ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="fae0a-170">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="fae0a-171">**Ner** -la capacité (%) un réseau pour transmettre les appels en mesurant le nombre d’appels envoyés au destinataire.</span><span class="sxs-lookup"><span data-stu-id="fae0a-171">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="fae0a-172">**Code de réponse SIP**: un code de réponse numérique à trois chiffres affiche l’état de l’appel.</span><span class="sxs-lookup"><span data-stu-id="fae0a-172">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="fae0a-173">**Code de réponse Microsoft**: code de réponse envoyé par le composant Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fae0a-173">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="fae0a-174">**Description** : la phase de raison correspondant au code de réponse SIP et au code de réponse Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fae0a-174">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="fae0a-175">**Nombre d’appels concernés** : le nombre total d’appels a été affecté au cours de la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="fae0a-175">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="fae0a-177">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fae0a-177">For example:</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report4.png)

<span data-ttu-id="fae0a-179">Si la NER quotidienne a une DIP sur 02/05/2020, vous pouvez cliquer sur la date et d’autres graphiques pour effectuer un zoom sur la date spécifique.</span><span class="sxs-lookup"><span data-stu-id="fae0a-179">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report5.png)

<span data-ttu-id="fae0a-181">À partir du NER, vous pouvez trouver le DIP qui intervient dans 21:00.</span><span class="sxs-lookup"><span data-stu-id="fae0a-181">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="fae0a-182">Cliquez de nouveau sur pour effectuer un zoom à l’heure 21, puis cochez la case Afficher les détails de l’appel pour voir le nombre d’appels ayant échoué pendant cette heure et les raisons de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="fae0a-182">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="fae0a-183">Si le problème n’est pas lié à SBC, vous pouvez démarrer avec l’auto-dépannage des problèmes de SBC ou d’État du service d’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="fae0a-183">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="fae0a-184">Paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="fae0a-184">Network Parameters</span></span>

<span data-ttu-id="fae0a-185">Tous les paramètres réseau sont mesurés à partir de l’interface de routage directe vers le contrôleur de bordure de session.</span><span class="sxs-lookup"><span data-stu-id="fae0a-185">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="fae0a-186">Pour plus d’informations sur les valeurs recommandées, voir [préparer le réseau de votre organisation à Microsoft teams](prepare-network.md), et observez les valeurs recommandées par Microsoft Edge pour le client.</span><span class="sxs-lookup"><span data-stu-id="fae0a-186">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="fae0a-187">**Gigue** : il s’agit de la mesure de milliseconde de la variation du délai de propagation du réseau, calculée entre deux points de terminaison utilisant le protocole RTCP (protocole de contrôle RTP).</span><span class="sxs-lookup"><span data-stu-id="fae0a-187">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="fae0a-188">**Perte de paquets** – est une mesure de paquets qui n’ont pas pu arriver ; Il est calculé entre deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="fae0a-188">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="fae0a-189">**Latence** -(également connue sous le nom de « durée de l’aller-retour) » est la durée de réception d’un signal et la durée de réception de ce signal.</span><span class="sxs-lookup"><span data-stu-id="fae0a-189">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="fae0a-190">Ce délai se compose des temps de propagation entre les deux points d’un signal.</span><span class="sxs-lookup"><span data-stu-id="fae0a-190">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report6.png)

<span data-ttu-id="fae0a-192">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="fae0a-192">For example:</span></span>

<span data-ttu-id="fae0a-193">Si vous voyez un pique-notes sur l’un des quatre graphiques (latence, instabilité, taux de perte de package, délai de numérotation après appel) pour une date spécifique (par exemple, latence sur 02/14/2020, cliquez sur le point de la date).</span><span class="sxs-lookup"><span data-stu-id="fae0a-193">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="fae0a-194">Le graphique tendance en bas de la série est actualisé pour afficher le numéro horaire.</span><span class="sxs-lookup"><span data-stu-id="fae0a-194">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="fae0a-195">Vous pouvez vérifier l’SBCs ou élever un ticket avec MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="fae0a-195">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="fae0a-197">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fae0a-197">Related topics</span></span>

[<span data-ttu-id="fae0a-198">Utiliser Power BI pour analyser des données bord pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="fae0a-198">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)

[<span data-ttu-id="fae0a-199">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="fae0a-199">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)