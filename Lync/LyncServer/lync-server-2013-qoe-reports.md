---
title: 'Lync Server 2013 : rapports QoE'
description: 'Lync Server 2013 : rapports QoE.'
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
ms.openlocfilehash: 55965d246b7f0ddd71eaeeec99d218eaf8819c2e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571400"
---
# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="eb8e7-103">Rapports QoE dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eb8e7-103">QoE reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eb8e7-104">_**Dernière modification de la rubrique :** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="eb8e7-104">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="eb8e7-105">Rapports de tendance/Résumé QoE</span><span class="sxs-lookup"><span data-stu-id="eb8e7-105">QoE summary/trend reports</span></span>

<span data-ttu-id="eb8e7-106">Les rapports de résumé/tendances QoE sont utiles pour trouver les heures d’utilisation maximale du jour et examiner la qualité des médias pendant ces périodes afin de s’assurer que les ressources réseau de votre organisation sont suffisantes.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-106">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="eb8e7-107">Votre organisation peut également utiliser les nombreux filtres disponibles dans le rapport pour isoler les numéros de performances de certains emplacements, clients et types d’appareils et de serveurs.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-107">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="eb8e7-108">Le résumé des données QoE/rapports de tendance se compose des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="eb8e7-108">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="eb8e7-109">Rapport de tendance/synthèse UC/Cu</span><span class="sxs-lookup"><span data-stu-id="eb8e7-109">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="eb8e7-110">Résumé PSTN/rapport de tendance</span><span class="sxs-lookup"><span data-stu-id="eb8e7-110">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="eb8e7-111">Rapport de tendance/Résumé de conférence</span><span class="sxs-lookup"><span data-stu-id="eb8e7-111">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="eb8e7-112">Rapports de performances QoE</span><span class="sxs-lookup"><span data-stu-id="eb8e7-112">QoE performance reports</span></span>

<span data-ttu-id="eb8e7-113">Les rapports sur les performances QoE fournissent des détails sur les trois rapports qui se concentrent sur les performances QoE des serveurs de médiation, des serveurs de conférence A/V et des emplacements de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-113">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="eb8e7-114">Rapport de performances du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="eb8e7-114">Mediation server performance report</span></span>

<span data-ttu-id="eb8e7-115">Le rapport de performances du serveur de médiation répertorie les mesures réalisées par une ou plusieurs médiations pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-115">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="eb8e7-116">Les mesures de la jambe de serveur communications unifiées (UC) à médiation et la partie serveur à passerelle de médiation de chaque appel sont signalées séparément.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-116">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="eb8e7-117">Utilisez ce rapport pour comparer le volume et les performances des différents serveurs de médiation de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-117">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="eb8e7-118">Pour chaque serveur de médiation (et pour chaque tronçon d’appel), le rapport affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="eb8e7-118">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="eb8e7-119">Nombre d’appels</span><span class="sxs-lookup"><span data-stu-id="eb8e7-119">Number of calls</span></span>

  - <span data-ttu-id="eb8e7-120">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="eb8e7-120">Packet Loss</span></span>

  - <span data-ttu-id="eb8e7-121">Durée de la boucle</span><span class="sxs-lookup"><span data-stu-id="eb8e7-121">Round Trip Time</span></span>

  - <span data-ttu-id="eb8e7-122">Scintill</span><span class="sxs-lookup"><span data-stu-id="eb8e7-122">Jitter</span></span>

  - <span data-ttu-id="eb8e7-123">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="eb8e7-123">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="eb8e7-124">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="eb8e7-124">Sending MOS</span></span>

  - <span data-ttu-id="eb8e7-125">Réception d’un MOS</span><span class="sxs-lookup"><span data-stu-id="eb8e7-125">Listening MOS</span></span>

  - <span data-ttu-id="eb8e7-126">MOS réseau</span><span class="sxs-lookup"><span data-stu-id="eb8e7-126">Network MOS</span></span>

  - <span data-ttu-id="eb8e7-127">Dégradation du MOS réseau</span><span class="sxs-lookup"><span data-stu-id="eb8e7-127">Network MOS Degradation</span></span>

  - <span data-ttu-id="eb8e7-128">Retour d’écho</span><span class="sxs-lookup"><span data-stu-id="eb8e7-128">Echo Return</span></span>

  - <span data-ttu-id="eb8e7-129">Niveau du signal</span><span class="sxs-lookup"><span data-stu-id="eb8e7-129">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="eb8e7-130">Rapport de performances du serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="eb8e7-130">A/V conferencing server performance report</span></span>

<span data-ttu-id="eb8e7-131">Le rapport de performances du serveur de conférence A/V fournit des listes de mesures réalisées par un ou plusieurs serveurs de conférence A/V pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-131">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="eb8e7-132">Ce rapport peut être utilisé pour comparer le volume et les performances des différents serveurs de conférence A/V de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-132">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="eb8e7-133">Votre organisation peut également isoler le rapport pour afficher uniquement l’expérience de types de clients spécifiques, tels que les clients Lync ou les clients RTC.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-133">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="eb8e7-134">Pour chaque serveur de conférence A/V, le rapport affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="eb8e7-134">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="eb8e7-135">Nombre de conférences</span><span class="sxs-lookup"><span data-stu-id="eb8e7-135">Number of conferences</span></span>

  - <span data-ttu-id="eb8e7-136">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="eb8e7-136">Packet Loss</span></span>

  - <span data-ttu-id="eb8e7-137">Durée de la boucle</span><span class="sxs-lookup"><span data-stu-id="eb8e7-137">Round Trip Time</span></span>

  - <span data-ttu-id="eb8e7-138">Scintill</span><span class="sxs-lookup"><span data-stu-id="eb8e7-138">Jitter</span></span>

  - <span data-ttu-id="eb8e7-139">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="eb8e7-139">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="eb8e7-140">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="eb8e7-140">Sending MOS</span></span>

  - <span data-ttu-id="eb8e7-141">Réception d’un MOS</span><span class="sxs-lookup"><span data-stu-id="eb8e7-141">Listening MOS</span></span>

  - <span data-ttu-id="eb8e7-142">MOS réseau</span><span class="sxs-lookup"><span data-stu-id="eb8e7-142">Network MOS</span></span>

  - <span data-ttu-id="eb8e7-143">Dégradation du MOS réseau</span><span class="sxs-lookup"><span data-stu-id="eb8e7-143">Network MOS Degradation</span></span>

  - <span data-ttu-id="eb8e7-144">Retour d’écho</span><span class="sxs-lookup"><span data-stu-id="eb8e7-144">Echo Return</span></span>

  - <span data-ttu-id="eb8e7-145">Niveau du signal</span><span class="sxs-lookup"><span data-stu-id="eb8e7-145">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="eb8e7-146">Rapport de performances basé sur l’emplacement</span><span class="sxs-lookup"><span data-stu-id="eb8e7-146">Location-based performance report</span></span>

<span data-ttu-id="eb8e7-147">Le rapport de performances de Location-Based fournit une liste des emplacements réseau et indique le nombre d’appels dans chaque plage de qualité prédéterminée.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-147">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="eb8e7-148">L’objectif de ce rapport est de fournir une vue d’ensemble de la qualité des médias de l’ensemble des appels téléphoniques de votre organisation pour les différents emplacements, afin que vous puissiez identifier les emplacements les plus performants et voir les différentes qualités de médias dans les différents emplacements de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-148">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="eb8e7-149">Lors de l’affichage du rapport, différentes tables de mesures apparaissent : une table pour chaque mesure que votre organisation décide d’effectuer des rapports.</span><span class="sxs-lookup"><span data-stu-id="eb8e7-149">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="eb8e7-150">Vous pouvez choisir l’une des mesures suivantes pour ce rapport :</span><span class="sxs-lookup"><span data-stu-id="eb8e7-150">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="eb8e7-151">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="eb8e7-151">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="eb8e7-152">MOS réseau</span><span class="sxs-lookup"><span data-stu-id="eb8e7-152">Network MOS</span></span>

  - <span data-ttu-id="eb8e7-153">Dégradation du MOS réseau</span><span class="sxs-lookup"><span data-stu-id="eb8e7-153">Network MOS Degradation</span></span>

  - <span data-ttu-id="eb8e7-154">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="eb8e7-154">Sending MOS</span></span>

  - <span data-ttu-id="eb8e7-155">Réception d’un MOS</span><span class="sxs-lookup"><span data-stu-id="eb8e7-155">Listening MOS</span></span>

  - <span data-ttu-id="eb8e7-156">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="eb8e7-156">Packet Loss</span></span>

  - <span data-ttu-id="eb8e7-157">Scintill</span><span class="sxs-lookup"><span data-stu-id="eb8e7-157">Jitter</span></span>

  - <span data-ttu-id="eb8e7-158">Latence</span><span class="sxs-lookup"><span data-stu-id="eb8e7-158">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

