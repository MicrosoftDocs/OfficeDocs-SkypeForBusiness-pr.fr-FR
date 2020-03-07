---
title: Utilisation du rapport de routage direct RTC bord
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: siunies
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
description: Utilisez le rapport de routage direct RTC bord pour surveiller et résoudre les problèmes de la fonction d’appel RTC dans Microsoft Teams.
ms.openlocfilehash: 32d91d56e51c5706c3e460029312f3b6bb6948c3
ms.sourcegitcommit: 98fcfc03c55917d0aca48b7bd97988f81e8930c1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2020
ms.locfileid: "42559421"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a><span data-ttu-id="a692e-103">Utilisation du rapport de routage direct RTC bord</span><span class="sxs-lookup"><span data-stu-id="a692e-103">Using the CQD PSTN Direct Routing Report</span></span>

<span data-ttu-id="a692e-104">Nouveauté du 2020 mars, nous avons ajouté un rapport de routage direct RTC bord aux [modèles de requête Power bi pour bord](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span><span class="sxs-lookup"><span data-stu-id="a692e-104">New in March 2020, we've added a CQD PSTN Direct Routing Report to our downloadable [Power BI query templates for CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true).</span></span> 


<span data-ttu-id="a692e-105">Le rapport de routage direct RTC de bord aide les clients à comprendre les modèles d’utilisation et la qualité de leurs services RTC surveiller les informations relatives à votre SBC, au service de téléphonie, aux paramètres réseau et aux détails sur le taux d’efficacité du réseau et à l’utilisation de la fonction service.</span><span class="sxs-lookup"><span data-stu-id="a692e-105">The CQD PSTN Direct Routing Report helps customers to understand the usage patterns and quality of their PSTN services monitor information about your SBC, the telephony service, the network parameters, and Network Effectiveness Ratio details and usage of the service.</span></span> <span data-ttu-id="a692e-106">Ces informations peuvent vous aider à identifier les problèmes, notamment le motif des appels interrompus.</span><span class="sxs-lookup"><span data-stu-id="a692e-106">This information can help you identify issues, including the reason for dropped calls.</span></span> <span data-ttu-id="a692e-107">Par exemple, vous serez en mesure de déterminer le nombre de chutes d’appels en fonction de la raison pour laquelle vous en avez le volume.</span><span class="sxs-lookup"><span data-stu-id="a692e-107">For example, you will be able to know when volume drops, how many calls get affected by what reason.</span></span>

<span data-ttu-id="a692e-108">Le rapport de routage direct RTC de bord comporte quatre sections :</span><span class="sxs-lookup"><span data-stu-id="a692e-108">The CQD PSTN Direct Routing Report has four sections:</span></span>

  - [<span data-ttu-id="a692e-109">Présentation RTC</span><span class="sxs-lookup"><span data-stu-id="a692e-109">PSTN Overview</span></span>](#pstn-overview)

  - [<span data-ttu-id="a692e-110">Détails du service</span><span class="sxs-lookup"><span data-stu-id="a692e-110">Service Details</span></span>](#service-details)

  - [<span data-ttu-id="a692e-111">Taux d’efficacité du réseau</span><span class="sxs-lookup"><span data-stu-id="a692e-111">Network Effectiveness Ratio</span></span>](#network-effectiveness-ratio)

  - [<span data-ttu-id="a692e-112">Paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="a692e-112">Network Parameters</span></span>](#network-parameters)

## <a name="pstn-overview"></a><span data-ttu-id="a692e-113">Présentation RTC</span><span class="sxs-lookup"><span data-stu-id="a692e-113">PSTN Overview</span></span>

<span data-ttu-id="a692e-114">Le rapport de routage direct RTC bord fournit les informations suivantes relatives à l’intégrité globale du service au cours des derniers jours 180.</span><span class="sxs-lookup"><span data-stu-id="a692e-114">The CQD PSTN Direct Routing Report provides the following information related to overall health of the service for the past 180 days.</span></span>
<span data-ttu-id="a692e-115">![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report1.png)</span><span class="sxs-lookup"><span data-stu-id="a692e-115">![Screenshot: PSTN CQD report](media/CQD-PSTN-report1.png)</span></span>

<span data-ttu-id="a692e-116">Par exemple, si vous êtes intéressé par l’utilisation globale et l’intégrité de tous les appels entrants à l’aide de SBC abc.bca.adatum.biz en tant que pays interne :</span><span class="sxs-lookup"><span data-stu-id="a692e-116">For example, if you are interested in the overall usage and health about all inbound calls going through SBC abc.bca.adatum.biz with US as the internal country:</span></span>

| <span data-ttu-id="a692e-117">**Appel hors**</span><span class="sxs-lookup"><span data-stu-id="a692e-117">**Call Out**</span></span> | <span data-ttu-id="a692e-118">**Description**</span><span class="sxs-lookup"><span data-stu-id="a692e-118">**Description**</span></span>                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="a692e-119">1</span><span class="sxs-lookup"><span data-stu-id="a692e-119">1</span></span>            | <span data-ttu-id="a692e-120">Vous pouvez utiliser les filtres en haut pour descendre dans la direction et sélectionner ByotIn en tant que type d’appel, abc.bca.contoso.com en tant que contrôleur de tableau de bord, et vers les États-Unis comme pays interne.</span><span class="sxs-lookup"><span data-stu-id="a692e-120">You can use the filters at the top to drill down and select ByotIn as call type, abc.bca.contoso.com as Session Boarder Controller, and US as internal country.</span></span> |
| <span data-ttu-id="a692e-121">deuxième</span><span class="sxs-lookup"><span data-stu-id="a692e-121">2</span></span>            | <span data-ttu-id="a692e-122">Tendance d’utilisation pour les 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="a692e-122">Usage trend for the past 180 days.</span></span> <span data-ttu-id="a692e-123">Le rapport sur les détails d’utilisation est sur la page des détails du service.</span><span class="sxs-lookup"><span data-stu-id="a692e-123">You can find usage detail report on Service Detail page.</span></span>                                                                     |
| <span data-ttu-id="a692e-124">3</span><span class="sxs-lookup"><span data-stu-id="a692e-124">3</span></span>            | <span data-ttu-id="a692e-125">Envoyez un message de délai de numérotation, de latence, de gigue et de tendance de perte de paquets pour les 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="a692e-125">Post Dial Delay, Latency, Jitter, and Packet Loss trend for the past 180 days.</span></span> <span data-ttu-id="a692e-126">Vous trouverez le rapport détaillé sur la page Paramètres du réseau.</span><span class="sxs-lookup"><span data-stu-id="a692e-126">You can find detail report on Network Parameters page.</span></span>                           |
| <span data-ttu-id="a692e-127">4</span><span class="sxs-lookup"><span data-stu-id="a692e-127">4</span></span>            | <span data-ttu-id="a692e-128">Tendance pour les appels simultanés et les utilisateurs actifs du jour au cours des 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="a692e-128">Concurrent Call and Daily Active User trend for the past 180 days.</span></span> <span data-ttu-id="a692e-129">Ce graphique peut vous aider à comprendre le volume maximal du service.</span><span class="sxs-lookup"><span data-stu-id="a692e-129">This chart can help you understand the max volume of the service.</span></span>                            |
| <span data-ttu-id="a692e-130">5</span><span class="sxs-lookup"><span data-stu-id="a692e-130">5</span></span>            | <span data-ttu-id="a692e-131">Raison de la qualité de service affectée par le top des appels pour les 180 derniers jours.</span><span class="sxs-lookup"><span data-stu-id="a692e-131">Top Call End Reason affected service quality for the past 180 days.</span></span> <span data-ttu-id="a692e-132">Pour plus d’informations sur l’état du service, consultez la page NER (Network effective ratio).</span><span class="sxs-lookup"><span data-stu-id="a692e-132">You can find service health detail on Network Effective Ratio(NER) page.</span></span>                    |

## <a name="service-details"></a><span data-ttu-id="a692e-133">Détails du service</span><span class="sxs-lookup"><span data-stu-id="a692e-133">Service Details</span></span>

<span data-ttu-id="a692e-134">Cette page vous permet d’obtenir des tendances d’utilisation du service par jour et de décomposition des commentaires des utilisateurs par géographie.</span><span class="sxs-lookup"><span data-stu-id="a692e-134">This page provides service usage trends per day and user feedback breakdown by geographic.</span></span>

  - <span data-ttu-id="a692e-135">**Nombre total de tentatives d’appels –** Nombre total de tentatives d’appels dans cette plage de temps, y compris les appels réussis et failed</span><span class="sxs-lookup"><span data-stu-id="a692e-135">**Total Attempt Calls –** Total attempt calls in that time range, including both success and failed calls</span></span>

  - <span data-ttu-id="a692e-136">**Nombre total d’appels connectés** Nombre total d’appels connectés dans cet intervalle de temps</span><span class="sxs-lookup"><span data-stu-id="a692e-136">**Total Connected Calls -** Total connected calls in that time range</span></span>

  - <span data-ttu-id="a692e-137">**Nombre total de minutes –** Utilisation du total des minutes dans cet intervalle de temps</span><span class="sxs-lookup"><span data-stu-id="a692e-137">**Total Minutes –** Total minute usage in that time range</span></span>

  - <span data-ttu-id="a692e-138">**Utilisateurs actifs quotidiens (DAU) :** Nombre d’utilisateurs actifs du jour qui ont effectué au moins un appel connecté à ce jour</span><span class="sxs-lookup"><span data-stu-id="a692e-138">**Daily Active Users(DAU) –** Count of daily active user who made at least one connected call in that day</span></span>

  - <span data-ttu-id="a692e-139">**Appels simultanés –** Maximum d’appels actifs simultanés en une minute</span><span class="sxs-lookup"><span data-stu-id="a692e-139">**Concurrent Calls –** Max of simultaneous active calls in a minute</span></span>

  - <span data-ttu-id="a692e-140">**Commentaires des utilisateurs –** Le score « évaluer mon appel » est fourni par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="a692e-140">**User Feedback –** "Rate My Call" score comes from the user.</span></span> <span data-ttu-id="a692e-141">3-5 est considéré comme un bon appel.</span><span class="sxs-lookup"><span data-stu-id="a692e-141">3-5 is considered as a good call.</span></span> <span data-ttu-id="a692e-142">1-2 est considéré comme un appel incorrect.</span><span class="sxs-lookup"><span data-stu-id="a692e-142">1-2 is considered as a bad call.</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report2.png)

<span data-ttu-id="a692e-144">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a692e-144">For example:</span></span>

1.  <span data-ttu-id="a692e-145">Si vous voyez que la durée moyenne des appels tombe à 0 sur 02/14/2020, vous pouvez commencer par vérifier si le volume de l’appel est normal et voir s’il y a une différence importante entre les appels de connexion et les appels de connexion au total.</span><span class="sxs-lookup"><span data-stu-id="a692e-145">If you see average call duration drops to 0 at 02/14/2020, you can first check if the call volume looks normal and see if there is a big discrepancy between total connect calls and total attempt calls.</span></span> <span data-ttu-id="a692e-146">Puis accédez à la page taux d’efficience du réseau pour investir en raison de l’échec de l’appel.</span><span class="sxs-lookup"><span data-stu-id="a692e-146">Then go to Network Effectiveness Ratio page to invest on call failure reasons.</span></span>

2.  <span data-ttu-id="a692e-147">Si vous voyez l’augmentation du nombre de points rouges sur la carte de commentaires des utilisateurs, vous pouvez accéder à page du rapport d’efficacité réseau et au paramètre réseau pour voir s’il y a des anomalies et vous pouvez déclencher un ticket avec MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="a692e-147">If you see increasing red spots on the user feedback map, you could go to Network Effectiveness Ratio page and Network Parameter to see if there are any anomalies and you could raise a ticket using MS Service Desk.</span></span>

## <a name="network-effectiveness-ratio"></a><span data-ttu-id="a692e-148">Taux d’efficacité du réseau</span><span class="sxs-lookup"><span data-stu-id="a692e-148">Network Effectiveness Ratio</span></span>

<span data-ttu-id="a692e-149">Il s’agit de la même métrique qui s’affiche dans le tableau de bord global de l’État.</span><span class="sxs-lookup"><span data-stu-id="a692e-149">This is the same metric that appears on the Overall Health dashboard.</span></span> <span data-ttu-id="a692e-150">Vous pouvez vérifier le numéro NER en fonction des appels en fonction du nombre d’appels (entrant/sortant) sur le taux d’efficacité du réseau horaire et sur le graphique raison de fin de l’appel ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="a692e-150">You can check hourly NER number with affected calls detail for both call directions (inbound/outbound) on the Hourly network effectiveness ratio and call ending reason chart below.</span></span>

  - <span data-ttu-id="a692e-151">**Ner** -la capacité (%) un réseau pour transmettre les appels en mesurant le nombre d’appels envoyés au destinataire.</span><span class="sxs-lookup"><span data-stu-id="a692e-151">**NER** - The ability (%) of a network to deliver calls by measuring the number of calls sent versus the number of calls delivered to a recipient.</span></span>

  - <span data-ttu-id="a692e-152">**Code de réponse SIP**: un code de réponse numérique à trois chiffres affiche l’état de l’appel.</span><span class="sxs-lookup"><span data-stu-id="a692e-152">**SIP response code**- A three-digit integer response code shows the call status.</span></span>

  - <span data-ttu-id="a692e-153">**Code de réponse Microsoft**: code de réponse envoyé par le composant Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a692e-153">**Microsoft response code**-A response code sent out from Microsoft component.</span></span>

  - <span data-ttu-id="a692e-154">**Description** : la phase de raison correspondant au code de réponse SIP et au code de réponse Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a692e-154">**Description** – The reason phase that corresponding to the SIP response code and Microsoft response code.</span></span>

  - <span data-ttu-id="a692e-155">**Nombre d’appels concernés** : le nombre total d’appels a été affecté au cours de la période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a692e-155">**Number of calls affected** – The total number of calls got affected during the selected time range.</span></span>

> ![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report3.png)
> 
<span data-ttu-id="a692e-157">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a692e-157">For example:</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report4.png)

<span data-ttu-id="a692e-159">Si la NER quotidienne a une DIP sur 02/05/2020, vous pouvez cliquer sur la date et d’autres graphiques pour effectuer un zoom sur la date spécifique.</span><span class="sxs-lookup"><span data-stu-id="a692e-159">If Daily NER has a dip on 02/05/2020, you can click on the date and other charts will zoom to that specific date.</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report5.png)

<span data-ttu-id="a692e-161">À partir du NER, vous pouvez trouver le DIP qui intervient dans 21:00.</span><span class="sxs-lookup"><span data-stu-id="a692e-161">From the NER Good Percentage Hourly Trend, you can find the dip happens around 21:00.</span></span> <span data-ttu-id="a692e-162">Cliquez de nouveau sur pour effectuer un zoom à l’heure 21, puis cochez la case Afficher les détails de l’appel pour voir le nombre d’appels ayant échoué pendant cette heure et les raisons de fin de l’appel.</span><span class="sxs-lookup"><span data-stu-id="a692e-162">Then click again to zoom to hour 21 and check Effected Call Details to see how many calls failed in that hour and what are the call end reasons.</span></span> <span data-ttu-id="a692e-163">Si le problème n’est pas lié à SBC, vous pouvez démarrer avec l’auto-dépannage des problèmes de SBC ou d’État du service d’assistance technique.</span><span class="sxs-lookup"><span data-stu-id="a692e-163">You can start with self-trouble shooting on any SBC problems or report to Service Desk if the problem is not related to SBC.</span></span>

## <a name="network-parameters"></a><span data-ttu-id="a692e-164">Paramètres réseau</span><span class="sxs-lookup"><span data-stu-id="a692e-164">Network Parameters</span></span>

<span data-ttu-id="a692e-165">Tous les paramètres réseau sont mesurés à partir de l’interface de routage directe vers le contrôleur de bordure de session.</span><span class="sxs-lookup"><span data-stu-id="a692e-165">All network parameters are measured from the Direct Routing interface to the Session Border Controller.</span></span> <span data-ttu-id="a692e-166">Pour plus d’informations sur les valeurs recommandées, voir [préparer le réseau de votre organisation à Microsoft teams](prepare-network.md), et observez les valeurs recommandées par Microsoft Edge pour le client.</span><span class="sxs-lookup"><span data-stu-id="a692e-166">For information about the recommended values, see [Prepare your organization's network for Microsoft Teams](prepare-network.md), and look at the Customer Edge to Microsoft Edge recommended values.</span></span>

  - <span data-ttu-id="a692e-167">**Gigue** : il s’agit de la mesure de milliseconde de la variation du délai de propagation du réseau, calculée entre deux points de terminaison utilisant le protocole RTCP (protocole de contrôle RTP).</span><span class="sxs-lookup"><span data-stu-id="a692e-167">**Jitter** – Is the millisecond measure of variation in network propagation delay time computed between two endpoints using RTCP (The RTP Control Protocol).</span></span>

  - <span data-ttu-id="a692e-168">**Perte de paquets** – est une mesure de paquets qui n’ont pas pu arriver ; Il est calculé entre deux points de terminaison.</span><span class="sxs-lookup"><span data-stu-id="a692e-168">**Packet Loss** – Is a measure of packet that failed to arrive; it is computed between two endpoints.</span></span>

  - <span data-ttu-id="a692e-169">**Latence** -(également connue sous le nom de « durée de l’aller-retour) » est la durée de réception d’un signal et la durée de réception de ce signal.</span><span class="sxs-lookup"><span data-stu-id="a692e-169">**Latency** - (Also known as round trip time) is the length of time it takes for a signal to be sent plus the length of time it takes for the acknowledgment of that signal to be received.</span></span> <span data-ttu-id="a692e-170">Ce délai se compose des temps de propagation entre les deux points d’un signal.</span><span class="sxs-lookup"><span data-stu-id="a692e-170">This time delay consists of the propagation times between the two points of a signal.</span></span>

> ![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report6.png)

<span data-ttu-id="a692e-172">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="a692e-172">For example:</span></span>

<span data-ttu-id="a692e-173">Si vous voyez un pique-notes sur l’un des quatre graphiques (latence, instabilité, taux de perte de package, délai de numérotation après appel) pour une date spécifique (par exemple, latence sur 02/14/2020, cliquez sur le point de la date).</span><span class="sxs-lookup"><span data-stu-id="a692e-173">If you see a spike on any of the four charts (Latency, Jitter, Package Loss Rate, Post Dial Delay) for a specific date, for example, Latency on 02/14/2020, click on the date point.</span></span> <span data-ttu-id="a692e-174">Le graphique tendance en bas de la série est actualisé pour afficher le numéro horaire.</span><span class="sxs-lookup"><span data-stu-id="a692e-174">And the hourly trend chart at the bottom will refresh to show the hourly number.</span></span> <span data-ttu-id="a692e-175">Vous pouvez vérifier l’SBCs ou élever un ticket avec MS Service Desk.</span><span class="sxs-lookup"><span data-stu-id="a692e-175">You can check the SBCs or raise a ticket with MS Service Desk.</span></span>

![Capture d’écran : rapport PSTN bord](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a><span data-ttu-id="a692e-177">Sujets associés</span><span class="sxs-lookup"><span data-stu-id="a692e-177">Related topics</span></span>

[<span data-ttu-id="a692e-178">Utiliser Power BI pour analyser des données bord pour Microsoft teams</span><span class="sxs-lookup"><span data-stu-id="a692e-178">Use Power BI to analyze CQD data for Microsoft Teams</span></span>](CQD-PSTN-report.md)