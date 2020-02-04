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
ms.openlocfilehash: 9eead17e9cd08267f941d80cb25460f4d456d896
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="qoe-reports-in-lync-server-2013"></a><span data-ttu-id="07d2b-102">Rapports QoE dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07d2b-102">QoE reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07d2b-103">_**Dernière modification de la rubrique :** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="07d2b-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<div>

## <a name="qoe-summarytrend-reports"></a><span data-ttu-id="07d2b-104">Rapport de synthèse</span><span class="sxs-lookup"><span data-stu-id="07d2b-104">QoE summary/trend reports</span></span>

<span data-ttu-id="07d2b-105">Les rapports de synthèse/tendances QoE permettent de rechercher les heures d’utilisation du PIC et d’examiner la qualité du média pendant ces périodes pour vous assurer que les ressources réseau de votre organisation sont suffisantes.</span><span class="sxs-lookup"><span data-stu-id="07d2b-105">The QoE summary/trends reports are useful for finding the peak usage times of day and examining the media quality during those times to help assure that your organization's network resources are sufficient.</span></span> <span data-ttu-id="07d2b-106">Votre organisation peut également utiliser les nombreux filtres disponibles dans le rapport pour isoler les numéros de performance de certains emplacements, types de clients et de périphériques, et de serveurs.</span><span class="sxs-lookup"><span data-stu-id="07d2b-106">Your organization can also use the many filters available in the report to isolate performance numbers for certain locations, client and device types, and servers.</span></span>

<span data-ttu-id="07d2b-107">Les rapports de synthèse/tendance sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="07d2b-107">QoE summary/trend reports consist of:</span></span>

  - <span data-ttu-id="07d2b-108">Rapport synthèse sur les communications UNIFIÉes/rapport de tendance</span><span class="sxs-lookup"><span data-stu-id="07d2b-108">UC-to-UC Summary/Trend Report</span></span>

  - <span data-ttu-id="07d2b-109">Rapport de synthèse PSTN/tendance</span><span class="sxs-lookup"><span data-stu-id="07d2b-109">PSTN Summary/Trend Report</span></span>

  - <span data-ttu-id="07d2b-110">Rapport de synthèse de conférence/tendance</span><span class="sxs-lookup"><span data-stu-id="07d2b-110">Conference Summary/Trend Report</span></span>

</div>

<div>

## <a name="qoe-performance-reports"></a><span data-ttu-id="07d2b-111">Rapports sur les performances QoE</span><span class="sxs-lookup"><span data-stu-id="07d2b-111">QoE performance reports</span></span>

<span data-ttu-id="07d2b-112">Rapports sur les performances de QoE fournissent des détails sur les trois rapports qui se concentrent sur les performances QoE des serveurs de médiation, des serveurs de conférence A/V et des emplacements de point de terminaison.</span><span class="sxs-lookup"><span data-stu-id="07d2b-112">QoE performance reports provide details about the three reports that concentrate on the QoE performance of Mediation Servers, A/V Conferencing Servers, and endpoint locations.</span></span>

</div>

<div>

## <a name="mediation-server-performance-report"></a><span data-ttu-id="07d2b-113">Rapport de performances du serveur de médiation</span><span class="sxs-lookup"><span data-stu-id="07d2b-113">Mediation server performance report</span></span>

<span data-ttu-id="07d2b-114">Le rapport sur les performances du serveur de médiation recense les métriques accomplies par une ou plusieurs médiation pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="07d2b-114">The Mediation Server Performance report lists the metrics achieved by one or more Mediation during the specified time period.</span></span> <span data-ttu-id="07d2b-115">Les métriques pour la jambe Unified Communications (UC) à médiation Server leg et la direction serveur à passerelle de médiation de chaque appel sont communiquées séparément.</span><span class="sxs-lookup"><span data-stu-id="07d2b-115">The metrics for the unified communications (UC)-to-Mediation Server leg and the Mediation Server-to-Gateway leg of each call are reported separately.</span></span> <span data-ttu-id="07d2b-116">Utilisez ce rapport pour comparer le volume et les performances des divers serveurs de médiation de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="07d2b-116">Use this report to compare the volume and performance of your organization's various Mediation Servers.</span></span>

<span data-ttu-id="07d2b-117">Pour chaque serveur de médiation (et pour chaque tronçon d’appel), le rapport affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="07d2b-117">For each Mediation Server (and for each call leg), the report displays the following:</span></span>

  - <span data-ttu-id="07d2b-118">Nombre d'appels</span><span class="sxs-lookup"><span data-stu-id="07d2b-118">Number of calls</span></span>

  - <span data-ttu-id="07d2b-119">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="07d2b-119">Packet Loss</span></span>

  - <span data-ttu-id="07d2b-120">Durée de l’aller-retour</span><span class="sxs-lookup"><span data-stu-id="07d2b-120">Round Trip Time</span></span>

  - <span data-ttu-id="07d2b-121">Jitter</span><span class="sxs-lookup"><span data-stu-id="07d2b-121">Jitter</span></span>

  - <span data-ttu-id="07d2b-122">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="07d2b-122">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="07d2b-123">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="07d2b-123">Sending MOS</span></span>

  - <span data-ttu-id="07d2b-124">Ecouter le MOS</span><span class="sxs-lookup"><span data-stu-id="07d2b-124">Listening MOS</span></span>

  - <span data-ttu-id="07d2b-125">MOS du réseau</span><span class="sxs-lookup"><span data-stu-id="07d2b-125">Network MOS</span></span>

  - <span data-ttu-id="07d2b-126">Baisse de la dégradation du réseau</span><span class="sxs-lookup"><span data-stu-id="07d2b-126">Network MOS Degradation</span></span>

  - <span data-ttu-id="07d2b-127">Retour d’écho</span><span class="sxs-lookup"><span data-stu-id="07d2b-127">Echo Return</span></span>

  - <span data-ttu-id="07d2b-128">Niveau du signal</span><span class="sxs-lookup"><span data-stu-id="07d2b-128">Signal Level</span></span>

</div>

<div>

## <a name="av-conferencing-server-performance-report"></a><span data-ttu-id="07d2b-129">Rapport de performances du serveur de conférence A/V</span><span class="sxs-lookup"><span data-stu-id="07d2b-129">A/V conferencing server performance report</span></span>

<span data-ttu-id="07d2b-130">Le rapport sur les performances du serveur de conférence A/V fournit des listes de mesures obtenues par un ou plusieurs serveurs de conférence A/V pendant la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="07d2b-130">The A/V Conferencing Server Performance report provides lists of metrics achieved by one or more A/V Conferencing Servers during the specified time period.</span></span> <span data-ttu-id="07d2b-131">Ce rapport peut être utilisé pour comparer le volume et les performances des différents serveurs de conférence A/V de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="07d2b-131">This report can be used to compare the volume and performance of your organization’s various A/V Conferencing Servers.</span></span> <span data-ttu-id="07d2b-132">Votre organisation peut également isoler le rapport pour afficher uniquement l’interface utilisateur de types de clients spécifiques, tels que les clients Lync ou les clients PSTN.</span><span class="sxs-lookup"><span data-stu-id="07d2b-132">Your organization can also isolate the report to show only the experience for specific client types, such as Lync clients or PSTN clients.</span></span>

<span data-ttu-id="07d2b-133">Pour chaque serveur de conférence A/V, le rapport affiche les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="07d2b-133">For each A/V Conferencing Server, the report displays the following:</span></span>

  - <span data-ttu-id="07d2b-134">Nombre de conférences</span><span class="sxs-lookup"><span data-stu-id="07d2b-134">Number of conferences</span></span>

  - <span data-ttu-id="07d2b-135">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="07d2b-135">Packet Loss</span></span>

  - <span data-ttu-id="07d2b-136">Durée de l’aller-retour</span><span class="sxs-lookup"><span data-stu-id="07d2b-136">Round Trip Time</span></span>

  - <span data-ttu-id="07d2b-137">Jitter</span><span class="sxs-lookup"><span data-stu-id="07d2b-137">Jitter</span></span>

  - <span data-ttu-id="07d2b-138">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="07d2b-138">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="07d2b-139">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="07d2b-139">Sending MOS</span></span>

  - <span data-ttu-id="07d2b-140">Ecouter le MOS</span><span class="sxs-lookup"><span data-stu-id="07d2b-140">Listening MOS</span></span>

  - <span data-ttu-id="07d2b-141">MOS du réseau</span><span class="sxs-lookup"><span data-stu-id="07d2b-141">Network MOS</span></span>

  - <span data-ttu-id="07d2b-142">Baisse de la dégradation du réseau</span><span class="sxs-lookup"><span data-stu-id="07d2b-142">Network MOS Degradation</span></span>

  - <span data-ttu-id="07d2b-143">Retour d’écho</span><span class="sxs-lookup"><span data-stu-id="07d2b-143">Echo Return</span></span>

  - <span data-ttu-id="07d2b-144">Niveau du signal</span><span class="sxs-lookup"><span data-stu-id="07d2b-144">Signal Level</span></span>

</div>

<div>

## <a name="location-based-performance-report"></a><span data-ttu-id="07d2b-145">Rapport sur les performances de l’emplacement</span><span class="sxs-lookup"><span data-stu-id="07d2b-145">Location-based performance report</span></span>

<span data-ttu-id="07d2b-146">Le rapport sur les performances de géolocalisation fournit une liste d’emplacements réseau et chaque emplacement indique le nombre d’appels dans chaque gamme de qualité prédéfinie.</span><span class="sxs-lookup"><span data-stu-id="07d2b-146">The Location-Based Performance report provides a list of network locations and for each location shows the number of calls in each pre-determined range of quality.</span></span> <span data-ttu-id="07d2b-147">L’objectif de ce rapport est d’offrir une vue d’ensemble de la qualité de média des appels téléphoniques de votre organisation pour différents emplacements, afin que vous puissiez identifier les emplacements médiocres et voir les différentes notes de qualité multimédia dans votre organisation. différents emplacements.</span><span class="sxs-lookup"><span data-stu-id="07d2b-147">The goal of this report is to provide insight into the media quality of the bulk of your organization’s telephone calls for various locations so that you can identify poorly performing locations, and see the different grades of media quality in your organization’s different locations.</span></span>

<span data-ttu-id="07d2b-148">Lors de l’affichage du rapport, différentes tables de métriques apparaissent : une table pour chaque métrique que votre organisation décide de signaler.</span><span class="sxs-lookup"><span data-stu-id="07d2b-148">When displaying the report, different tables of metrics appear—one table for each metric your organization decides to report on.</span></span> <span data-ttu-id="07d2b-149">Pour ce rapport, vous pouvez choisir parmi les mesures suivantes :</span><span class="sxs-lookup"><span data-stu-id="07d2b-149">You can choose from the following metrics for this report:</span></span>

  - <span data-ttu-id="07d2b-150">Note moyenne d’opinion de conversation (MOS)</span><span class="sxs-lookup"><span data-stu-id="07d2b-150">Conversational mean opinion score (MOS)</span></span>

  - <span data-ttu-id="07d2b-151">MOS du réseau</span><span class="sxs-lookup"><span data-stu-id="07d2b-151">Network MOS</span></span>

  - <span data-ttu-id="07d2b-152">Baisse de la dégradation du réseau</span><span class="sxs-lookup"><span data-stu-id="07d2b-152">Network MOS Degradation</span></span>

  - <span data-ttu-id="07d2b-153">Envoi d’un MOS</span><span class="sxs-lookup"><span data-stu-id="07d2b-153">Sending MOS</span></span>

  - <span data-ttu-id="07d2b-154">Ecouter le MOS</span><span class="sxs-lookup"><span data-stu-id="07d2b-154">Listening MOS</span></span>

  - <span data-ttu-id="07d2b-155">Perte de paquets</span><span class="sxs-lookup"><span data-stu-id="07d2b-155">Packet Loss</span></span>

  - <span data-ttu-id="07d2b-156">Jitter</span><span class="sxs-lookup"><span data-stu-id="07d2b-156">Jitter</span></span>

  - <span data-ttu-id="07d2b-157">Latence</span><span class="sxs-lookup"><span data-stu-id="07d2b-157">Latency</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

