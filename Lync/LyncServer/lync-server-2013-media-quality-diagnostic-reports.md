---
title: 'Lync Server 2013 : rapports de diagnostic de la qualité des médias'
description: 'Lync Server 2013 : rapports de diagnostic de la qualité des médias.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Diagnostic Reports
ms:assetid: ea61428e-a1d5-4189-aae6-3db19ddc5cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615044(v=OCS.15)
ms:contentKeyID: 48185935
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e346d0f9b8997158cb926ad830d5477950e846d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548210"
---
# <a name="media-quality-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="c2b4a-103">Rapports de diagnostic de la qualité des médias dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2b4a-103">Media Quality Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2b4a-104">_**Dernière modification de la rubrique :** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="c2b4a-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="c2b4a-105">Les rapports de diagnostic de la qualité des médias fournissent des informations sur la qualité des appels, ainsi que des informations de diagnostic et de dépannage pour les appels ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-105">The Media Quality Diagnostic Reports provide information about call quality, and diagnostic and troubleshooting information for failed calls.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c2b4a-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c2b4a-106">In This Section</span></span>

  - <span data-ttu-id="c2b4a-107">[Rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md)     Fournit des données de qualité globale pour différents types de points de terminaison, notamment les appels P2P voix entreprise, les appels de téléconférence voix entreprise et les appels qui reposent sur le réseau téléphonique commuté (PSTN, au moins en partie).</span><span class="sxs-lookup"><span data-stu-id="c2b4a-107">[Media Quality Summary Report in Lync Server 2013](lync-server-2013-media-quality-summary-report.md)   Provides overall quality data for different endpoint types, including Enterprise Voice peer-to-peer calls, Enterprise Voice conference calls, and calls that rely, at least in part, on the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="c2b4a-108">[Rapport de comparaison de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)     Fournit une comparaison des valeurs de qualité des appels pour différents types d’appels audio (par exemple, les appels effectués sur un réseau sans fil ou les appels effectués via une connexion câblée).</span><span class="sxs-lookup"><span data-stu-id="c2b4a-108">[Media Quality Comparison Report in Lync Server 2013](lync-server-2013-media-quality-comparison-report.md)   Provides a comparison of call quality values for different types of audio calls (for example, calls made over a wireless network vs. calls made across a wired connection).</span></span>

  - <span data-ttu-id="c2b4a-109">[Rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md)     Répertorie les serveurs qui ont rencontré le plus de problèmes, en se basant sur les mesures des mesures de qualité clés telles que la dégradation, la perte de paquets et la gigue.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-109">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md)   Lists the servers that have experienced the most problems, based on measurements of such key quality metrics as degradation, packet loss, and jitter.</span></span>

  - <span data-ttu-id="c2b4a-110">[Rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md)     Fournit une liste des emplacements réseau et un résumé de la qualité des médias des appels qui se produisent à chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-110">[Location Report in Lync Server 2013](lync-server-2013-location-report.md)   Provides a list of network locations and a summary of the media quality of the calls that occur at each location.</span></span> <span data-ttu-id="c2b4a-111">Pour les besoins de ce rapport, les emplacements sont basés sur des sous-réseaux IP.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-111">For purposes of this report, locations are based on IP subnets.</span></span>

  - <span data-ttu-id="c2b4a-112">[Rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md)     Fournit un résumé des appareils utilisés pour les appels vocaux d’entreprise et inclut la qualité moyenne des médias des appels par périphérique.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-112">[Device Report in Lync Server 2013](lync-server-2013-device-report.md)   Provides a summary of devices that are used for Enterprise Voice calls and it includes the average media quality of the calls by device.</span></span>

  - <span data-ttu-id="c2b4a-113">[Rapport de liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md)     Fournit des informations détaillées sur les appels téléphoniques émis ou reçus au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-113">[Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md)   Provides detailed information about phone calls made or received within your organization.</span></span>

  - <span data-ttu-id="c2b4a-114">[Rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md)     Fournit des informations détaillées sur les appels téléphoniques émis ou reçus au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-114">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md)   Provides detailed information about phone calls made from or received within your organization.</span></span>

  - <span data-ttu-id="c2b4a-115">[Rapport de tendance de la qualité des médias serveur dans Lync server 2013](lync-server-2013-server-media-quality-trend-report.md)     Vous permet de comparer graphiquement jusqu’à 5 serveurs sur les mesures de qualité de l’expérience, telles que le volume d’appels, le pourcentage d’appels médiocres, la perte de paquets et la gigue.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-115">[Server Media Quality Trend Report in Lync Server 2013](lync-server-2013-server-media-quality-trend-report.md)   Provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span>

  - <span data-ttu-id="c2b4a-116">[Le rapport de distribution des mesures de qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)     Fournit un graphique qui affiche les valeurs de distribution pour une mesure de qualité de l’expérience, comme la gigue ou la perte de paquets.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-116">[The Media Quality Metrics Distribution Report in Lync Server 2013](lync-server-2013-media-quality-metrics-distribution-report.md)   Provides a graph that shows the distribution values for a Quality of Experience metric such as jitter or packet loss.</span></span>

  - <span data-ttu-id="c2b4a-117">[Rapport de tendance des emplacements dans Lync Server 2013](lync-server-2013-location-trend-report.md)     Fournit des informations de tendance sur la qualité des appels pour les emplacements réseau.</span><span class="sxs-lookup"><span data-stu-id="c2b4a-117">[Location Trend Report in Lync Server 2013](lync-server-2013-location-trend-report.md)   Provides call quality trend information for network locations.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

