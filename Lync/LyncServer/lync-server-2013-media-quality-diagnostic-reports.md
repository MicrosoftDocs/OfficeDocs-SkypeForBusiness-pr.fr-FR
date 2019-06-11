---
title: 'Lync Server 2013: rapports de diagnostic de qualité multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05836ea853c89b132d39eaaba1b66056fa958072
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="a9ef7-102">Rapports de diagnostic de qualité multimédia dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a9ef7-102">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9ef7-103">_**Dernière modification de la rubrique:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="a9ef7-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="a9ef7-104">Les rapports de diagnostic de la qualité des médias fournissent des informations sur la qualité des appels, ainsi que des informations de diagnostic et de résolution des problèmes pour les appels ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-104">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a9ef7-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="a9ef7-105">In This Section</span></span>

  - <span data-ttu-id="a9ef7-106">[Rapport synthèse sur la qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   fournit des données de qualité globale pour les différents types de points de terminaison, notamment les appels d’égal à égal d’entreprise voix, les appels de conférence vocale d’entreprise et les appels qui s’appuient, au moins en partie, sur le public réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="a9ef7-106">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="a9ef7-107">[Rapport de comparaison de qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   fournit une comparaison des valeurs de qualité d’appel pour les différents types d’appels audio (par exemple, les appels passés via un réseau sans fil et les appels effectués sur une connexion câblée).</span><span class="sxs-lookup"><span data-stu-id="a9ef7-107">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="a9ef7-108">[Le rapport sur les performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md)   répertorie les serveurs ayant rencontré le plus de problèmes, en fonction des mesures de ces mesures de qualité clé en matière de dégradation, de perte de paquets et de gigue.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="a9ef7-109">[Rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md)   fournit une liste d’emplacements réseau et une synthèse de la qualité de média des appels qui se produisent à chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-109">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="a9ef7-110">En raison des objectifs de ce rapport, les emplacements sont basés sur les sous-réseaux IP.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-110">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="a9ef7-111">[Rapport sur les appareils dans Lync Server 2013](lync-server-2013-device-report.md)   fournit un résumé des appareils utilisés pour les appels voix entreprise et inclut la qualité de média moyenne des appels par appareil.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-111">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="a9ef7-112">[Rapport de liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md)   fournit des informations détaillées sur les appels téléphoniques passés ou reçus au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-112">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="a9ef7-113">[Rapport Détails des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md)   fournit des informations détaillées sur les appels téléphoniques passés ou reçus au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-113">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="a9ef7-114">[Rapport sur les tendances de la qualité Media Media dans Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   vous permet de comparer graphiquement les statistiques de qualité d’appel, telles que le volume des appels, le pourcentage d’appels médiocres, la perte de paquets et la gigue.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-114">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="a9ef7-115">[Le rapport de distribution des métriques de qualité multimédia dans Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   fournit un graphique montrant les valeurs de distribution pour une métrique de qualité d’acquisition telle que la gigue ou la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-115">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="a9ef7-116">[Rapport de tendance d’emplacement dans Lync Server 2013](lync-server-2013-location-trend-report.md)   fournit des informations de tendance de qualité d’appel pour les emplacements réseau.</span><span class="sxs-lookup"><span data-stu-id="a9ef7-116">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

