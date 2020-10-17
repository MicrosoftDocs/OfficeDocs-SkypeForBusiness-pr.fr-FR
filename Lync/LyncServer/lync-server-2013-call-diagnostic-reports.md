---
title: 'Lync Server 2013 : rapports de diagnostic des appels'
description: 'Lync Server 2013 : Call diagnostic Reports.'
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
ms.openlocfilehash: 6acc41585414e134eebde1635729b470c7f3472c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561710"
---
# <a name="call-diagnostic-reports-in-lync-server-2013"></a><span data-ttu-id="cfc3b-103">Rapports de diagnostic des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfc3b-103">Call Diagnostic Reports in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfc3b-104">_**Dernière modification de la rubrique :** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="cfc3b-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="cfc3b-105">Les rapports de diagnostic des appels fournissent des informations récapitulatives et des données de diagnostic relatives aux sessions d’égal à égal et de conférence ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-105">The Call Diagnostic Reports provide summary information and diagnostic data for failed peer-to-peer and conferencing sessions.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cfc3b-106">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="cfc3b-106">In This Section</span></span>

  - <span data-ttu-id="cfc3b-107">[Rapport de synthèse de diagnostic des appels dans Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)     Fournit une synthèse générale des sessions d’égal à égal et des sessions de conférence ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-107">[Call Diagnostic Summary Report in Lync Server 2013](lync-server-2013-call-diagnostic-summary-report.md)   Provides an overall summary of failed peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="cfc3b-108">Les sessions d’égal à égal sont des sessions qui n’impliquent que deux participants.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-108">Peer-to-peer sessions are sessions that involve just two participants.</span></span> <span data-ttu-id="cfc3b-109">Les sessions de conférence impliquent trois participants ou plus.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-109">Conferencing sessions involve three or more participants.</span></span>

  - <span data-ttu-id="cfc3b-110">[Rapport de diagnostic des activités d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)     Fournit une vue d’ensemble de la tendance des sessions P2P ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-110">[Peer-to-Peer Activity Diagnostic Report in Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)   Provides an overall trend view of failed peer-to-peer sessions.</span></span> <span data-ttu-id="cfc3b-111">Une session d’égal à égal implique uniquement deux participants.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-111">A peer-to-peer session involves just two participants.</span></span>

  - <span data-ttu-id="cfc3b-112">[Rapport de diagnostic de conférence dans Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)     Fournit une vue d’ensemble de la tendance des sessions de conférence et des vues de tendance ayant échoué pour chaque modalité de conférence.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-112">[Conference Diagnostic Report in Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)   Provides an overall trend view of failed conferencing sessions and trend views for each conference modality.</span></span> <span data-ttu-id="cfc3b-113">Les sessions de conférence impliquent au moins trois participants.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-113">Conferencing sessions involve at least three participants.</span></span>

  - <span data-ttu-id="cfc3b-114">[Rapport des principales défaillances dans Lync Server 2013](lync-server-2013-top-failures-report.md)     Fournit une liste des défaillances les plus fréquentes et des tendances dans le temps.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-114">[Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md)   Provides a list of the most frequent failures and their trends over time.</span></span>

  - <span data-ttu-id="cfc3b-115">[Rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md)     Fournit une analyse des sessions ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-115">[Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md)   Provides an analysis of failed sessions.</span></span>

  - <span data-ttu-id="cfc3b-116">[Rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md)     Fournit des informations détaillées sur les participants individuels impliqués dans une conférence ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-116">[Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md)   Provides detailed information about the individual participants involved in a failed conference.</span></span>

  - <span data-ttu-id="cfc3b-117">[Rapport de diagnostic dans Lync Server 2013](lync-server-2013-diagnostic-report.md)     Fournit des informations de diagnostic et de dépannage (notamment des codes de réponse SIP et des en-têtes et ID de diagnostic) pour les sessions ayant échoué.</span><span class="sxs-lookup"><span data-stu-id="cfc3b-117">[Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md)   Provides diagnostic and troubleshooting information (including SIP response codes and diagnostic headers and IDs) for failed sessions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

