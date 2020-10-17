---
title: Prise en charge de Lync Server 2013 pour les grandes réunions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for large meetings
ms:assetid: 8f0446d5-1ed9-4ea0-bb97-6c062a98a1eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205090(v=OCS.15)
ms:contentKeyID: 48184820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f177c7555a945be4e871c53e0e49a57c1a304a7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519411"
---
# <a name="support-for-large-meetings-in-lync-server-2013"></a><span data-ttu-id="0d642-102">Prise en charge des grandes réunions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d642-102">Support for large meetings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d642-103">_**Dernière modification de la rubrique :** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0d642-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0d642-104">Lync Server 2013 peut prendre en charge des réunions avec un maximum de 1000 participants à l’aide de la conférence audio/vidéo (A/V), y compris le partage de présentations PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="0d642-104">Lync Server 2013 can support meetings with up to 1000 participants using audio/video (A/V) conferencing, including sharing PowerPoint presentations.</span></span> <span data-ttu-id="0d642-105">Cette prise en charge requiert un pool dédié configuré pour prendre en charge de grandes réunions et géré pour n’héberger qu’une seule grande réunion à la fois.</span><span class="sxs-lookup"><span data-stu-id="0d642-105">This support requires a dedicated pool configured to support large meetings and managed in a way that ensures hosting of only a single large meeting at a time.</span></span>

<span data-ttu-id="0d642-106">Cette section décrit comment prendre en charge les grandes réunions à l’aide d’un pool Lync Server 2013 dédié.</span><span class="sxs-lookup"><span data-stu-id="0d642-106">This section describes how to support large meetings using a dedicated Lync Server 2013 pool.</span></span> <span data-ttu-id="0d642-107">Elle décrit les exigences d’extensibilité et d’implémentation requises pour un pool dédié, y compris la topologie, le matériel, les logiciels et la configuration requise.</span><span class="sxs-lookup"><span data-stu-id="0d642-107">It describes scalability considerations and the implementation requirements for a dedicated pool, including topology, hardware, software, and configuration requirements.</span></span> <span data-ttu-id="0d642-108">Elle fournit également une série de recommandations pour la prise en charge de grandes réunions, un résumé des méthodes de test et des résultats des tests d’évolutivité de serveur menés par l’équipe d’ingénierie Lync Server, ainsi que les réponses aux questions fréquemment posées sur la prise en charge des grandes réunions.</span><span class="sxs-lookup"><span data-stu-id="0d642-108">It also provides a set of best practice recommendations for supporting large meetings, a summary of the test methods and results of server scalability testing conducted by the Lync Server engineering team, and the answers to frequently asked questions about support for large meetings.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0d642-109">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0d642-109">In This Section</span></span>

  - [<span data-ttu-id="0d642-110">Vue d’ensemble de l’évolutivité des conférences dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d642-110">Overview of conferencing scalability in Lync Server 2013</span></span>](lync-server-2013-conferencing-scalability-overview.md)

  - [<span data-ttu-id="0d642-111">Prise en charge des grandes réunions à l’aide de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d642-111">Supporting large meetings using Lync Server 2013</span></span>](lync-server-2013-supporting-large-meetings.md)

  - [<span data-ttu-id="0d642-112">Forum aux questions sur la prise en charge des grandes réunions pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d642-112">Large meeting support FAQ for Lync Server 2013</span></span>](lync-server-2013-large-meeting-support-faq.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

