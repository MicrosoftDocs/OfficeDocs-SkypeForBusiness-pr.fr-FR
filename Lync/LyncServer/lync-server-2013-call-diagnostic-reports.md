---
title: 'Lync Server 2013 : rapports de diagnostic d’appel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Reports
ms:assetid: 8d362dd9-a119-4601-a3b4-3e7ed0aaa92e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615013(v=OCS.15)
ms:contentKeyID: 48184794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41100a6cc41c38b3d32870d530f99d8c919a2e83
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="fbf72-102">Rapports de diagnostic des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbf72-102">Call Diagnostic Reports in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbf72-103">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="fbf72-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="fbf72-104">Les rapports de diagnostic des appels fournissent des informations récapitulatives et des données de diagnostic relatives aux sessions P2P et de conférence ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="fbf72-104">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbf72-105">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="fbf72-105">In This Section</span></span>

  - <span data-ttu-id="fbf72-106">[Rapport de synthèse des diagnostics dans Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   fournit un récapitulatif global des sessions d’égal à égal et des sessions de conférence.</span><span class="sxs-lookup"><span data-stu-id="fbf72-106">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="fbf72-107">Les sessions P2P sont des sessions impliquant seulement deux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fbf72-107">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="fbf72-108">Les sessions de conférence impliquent trois participants ou plus.</span><span class="sxs-lookup"><span data-stu-id="fbf72-108">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="fbf72-109">[Rapport de diagnostic d’activité d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   fournit une vue de tendance globale des sessions d’égal à égal ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="fbf72-109">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="fbf72-110">Une session P2P implique uniquement deux participants.</span><span class="sxs-lookup"><span data-stu-id="fbf72-110">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="fbf72-111">[Rapport de diagnostic de conférence dans Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   offre une vue d’ensemble des tendances globales des sessions de conférence et des vues de tendance en échec pour chaque modalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="fbf72-111">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="fbf72-112">Les sessions de conférence impliquent au moins trois participants.</span><span class="sxs-lookup"><span data-stu-id="fbf72-112">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="fbf72-113">[Rapport sur les principaux échecs dans Lync Server 2013](lync-server-2013-top-failures-report.md)   fournit une liste des erreurs les plus fréquentes et leurs tendances dans le temps.</span><span class="sxs-lookup"><span data-stu-id="fbf72-113">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="fbf72-114">[Rapport de distribution des échecs dans Lync Server 2013](lync-server-2013-failure-distribution-report.md)   fournit une analyse des sessions ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="fbf72-114">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="fbf72-115">[Rapport de liste d’échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md)   fournit des informations détaillées sur les participants individuels impliqués dans une conférence en échec.</span><span class="sxs-lookup"><span data-stu-id="fbf72-115">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="fbf72-116">[Rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md)   fournit des informations de diagnostic et de dépannage (y compris les codes de réponse SIP et les en-têtes et ID de diagnostic) pour les échecs de session.</span><span class="sxs-lookup"><span data-stu-id="fbf72-116">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

