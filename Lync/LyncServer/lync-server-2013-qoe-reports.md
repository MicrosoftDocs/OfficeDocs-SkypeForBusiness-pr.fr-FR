---
title: 'Lync Server 2013 : rapports QoE'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoE reports
ms:assetid: 49c827af-b8dd-4c6e-b0dc-b4bc6d60e9a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720913(v=OCS.15)
ms:contentKeyID: 63969601
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69caa96c6f0e49d472f13da11b34f7d199322184
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512181"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="668e3-102">Rapports QoE dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="668e3-102">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="668e3-103">_**Dernière modification de la rubrique :** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="668e3-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="668e3-104">Rapports de tendance/Résumé QoE</span><span class="sxs-lookup"><span data-stu-id="668e3-104">QoE summary/trend reports</span></span>

<span data-ttu-id="668e3-105">Les rapports de résumé/tendances QoE sont utiles pour trouver les heures d’utilisation maximale du jour et examiner la qualité des médias pendant ces périodes afin de s’assurer que les ressources réseau de votre organisation sont suffisantes.</span><span class="sxs-lookup"><span data-stu-id="668e3-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="668e3-106">Votre organisation peut également utiliser les nombreux filtres disponibles dans le rapport pour isoler les numéros de performances de certains emplacements, clients et types d’appareils et de serveurs.</span><span class="sxs-lookup"><span data-stu-id="668e3-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="668e3-107">Le résumé des données QoE/rapports de tendance se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="668e3-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="668e3-108">Rapport de tendance/synthèse UC/Cu</span><span class="sxs-lookup"><span data-stu-id="668e3-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="668e3-109">Résumé PSTN/rapport de tendance</span><span class="sxs-lookup"><span data-stu-id="668e3-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="668e3-110">Rapport de tendance/Résumé de conférence</span><span class="sxs-lookup"><span data-stu-id="668e3-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="668e3-111">Rapports de performances QoE</span><span class="sxs-lookup"><span data-stu-id="668e3-111">QoE performance reports</span></span>

<span data-ttu-id="668e3-112">Les rapports sur les performances QoE fournissent des détails sur les trois rapports qui se concentrent sur les performances QoE des serveurs de médiation, des serveurs de conférence A/V et des emplacements de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="668e3-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="668e3-113">Rapport de performances du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="668e3-113">Mediation server performance report</span></span>

<span data-ttu-id="668e3-114">Le rapport de performances du serveur de médiation répertorie les mesures réalisées par une ou plusieurs médiations pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="668e3-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="668e3-115">Les mesures de la jambe de serveur communications unifiées (UC) à médiation et la partie serveur à passerelle de médiation de chaque appel sont signalées séparément.</span><span class="sxs-lookup"><span data-stu-id="668e3-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="668e3-116">Utilisez ce rapport pour comparer le volume et les performances des différents serveurs de médiation de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="668e3-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="668e3-117">Pour chaque serveur de médiation (et pour chaque tronçon d’appel), le rapport affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="668e3-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="668e3-118">Nombre d’appels</span><span class="sxs-lookup"><span data-stu-id="668e3-118">Number of calls</span></span>

  - <span data-ttu-id="668e3-119">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="668e3-119">Packet Loss</span></span>

  - <span data-ttu-id="668e3-120">Durée de la boucle</span><span class="sxs-lookup"><span data-stu-id="668e3-120">Round Trip Time</span></span>

  - <span data-ttu-id="668e3-121">Scintill</span><span class="sxs-lookup"><span data-stu-id="668e3-121">Jitter</span></span>

  - <span data-ttu-id="668e3-122">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="668e3-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="668e3-123">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="668e3-123">Sending MOS</span></span>

  - <span data-ttu-id="668e3-124">Réception d’un MOS</span><span class="sxs-lookup"><span data-stu-id="668e3-124">Listening MOS</span></span>

  - <span data-ttu-id="668e3-125">MOS réseau</span><span class="sxs-lookup"><span data-stu-id="668e3-125">Network MOS</span></span>

  - <span data-ttu-id="668e3-126">Dégradation du MOS réseau</span><span class="sxs-lookup"><span data-stu-id="668e3-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="668e3-127">Retour d’écho</span><span class="sxs-lookup"><span data-stu-id="668e3-127">Echo Return</span></span>

  - <span data-ttu-id="668e3-128">Niveau du signal</span><span class="sxs-lookup"><span data-stu-id="668e3-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="668e3-129">Rapport de performances du serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="668e3-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="668e3-130">Le rapport de performances du serveur de conférence A/V fournit des listes de mesures réalisées par un ou plusieurs serveurs de conférence A/V pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="668e3-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="668e3-131">Ce rapport peut être utilisé pour comparer le volume et les performances des différents serveurs de conférence A/V de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="668e3-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="668e3-132">Votre organisation peut également isoler le rapport pour afficher uniquement l’expérience de types de clients spécifiques, tels que les clients Lync ou les clients RTC.</span><span class="sxs-lookup"><span data-stu-id="668e3-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="668e3-133">Pour chaque serveur de conférence A/V, le rapport affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="668e3-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="668e3-134">Nombre de conférences</span><span class="sxs-lookup"><span data-stu-id="668e3-134">Number of conferences</span></span>

  - <span data-ttu-id="668e3-135">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="668e3-135">Packet Loss</span></span>

  - <span data-ttu-id="668e3-136">Durée de la boucle</span><span class="sxs-lookup"><span data-stu-id="668e3-136">Round Trip Time</span></span>

  - <span data-ttu-id="668e3-137">Scintill</span><span class="sxs-lookup"><span data-stu-id="668e3-137">Jitter</span></span>

  - <span data-ttu-id="668e3-138">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="668e3-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="668e3-139">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="668e3-139">Sending MOS</span></span>

  - <span data-ttu-id="668e3-140">Réception d’un MOS</span><span class="sxs-lookup"><span data-stu-id="668e3-140">Listening MOS</span></span>

  - <span data-ttu-id="668e3-141">MOS réseau</span><span class="sxs-lookup"><span data-stu-id="668e3-141">Network MOS</span></span>

  - <span data-ttu-id="668e3-142">Dégradation du MOS réseau</span><span class="sxs-lookup"><span data-stu-id="668e3-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="668e3-143">Retour d’écho</span><span class="sxs-lookup"><span data-stu-id="668e3-143">Echo Return</span></span>

  - <span data-ttu-id="668e3-144">Niveau du signal</span><span class="sxs-lookup"><span data-stu-id="668e3-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="668e3-145">Rapport de performances basé sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="668e3-145">Location-based performance report</span></span>

<span data-ttu-id="668e3-146">Le rapport de performances de Location-Based fournit une liste des emplacements réseau et indique le nombre d’appels dans chaque plage de qualité prédéterminée.</span><span class="sxs-lookup"><span data-stu-id="668e3-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="668e3-147">L’objectif de ce rapport est de fournir une vue d’ensemble de la qualité des médias de l’ensemble des appels téléphoniques de votre organisation pour les différents emplacements, afin que vous puissiez identifier les emplacements les plus performants et voir les différentes qualités de médias dans les différents emplacements de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="668e3-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="668e3-148">Lors de l’affichage du rapport, différentes tables de mesures apparaissent : une table pour chaque mesure que votre organisation décide d’effectuer des rapports.</span><span class="sxs-lookup"><span data-stu-id="668e3-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="668e3-149">Vous pouvez choisir l’une des mesures suivantes pour ce rapport :</span><span class="sxs-lookup"><span data-stu-id="668e3-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="668e3-150">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="668e3-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="668e3-151">MOS réseau</span><span class="sxs-lookup"><span data-stu-id="668e3-151">Network MOS</span></span>

  - <span data-ttu-id="668e3-152">Dégradation du MOS réseau</span><span class="sxs-lookup"><span data-stu-id="668e3-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="668e3-153">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="668e3-153">Sending MOS</span></span>

  - <span data-ttu-id="668e3-154">Réception d’un MOS</span><span class="sxs-lookup"><span data-stu-id="668e3-154">Listening MOS</span></span>

  - <span data-ttu-id="668e3-155">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="668e3-155">Packet Loss</span></span>

  - <span data-ttu-id="668e3-156">Scintill</span><span class="sxs-lookup"><span data-stu-id="668e3-156">Jitter</span></span>

  - <span data-ttu-id="668e3-157">Latence</span><span class="sxs-lookup"><span data-stu-id="668e3-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

