---
title: 'Lync Server 2013 : création de flux de travail Response Group'
description: 'Lync Server 2013 : créer des flux de travail Response Group.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Response Group workflows
ms:assetid: 41272258-728d-42bd-b4d4-2a499734c720
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425918(v=OCS.15)
ms:contentKeyID: 48183954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7082295eeca45c4dac76d68ef54b5c32fafb25d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548650"
---
# <a name="create-response-group-workflows-in-lync-server-2013"></a><span data-ttu-id="6dff3-103">Créer des flux de travail Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dff3-103">Create Response Group workflows in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6dff3-104">_**Dernière modification de la rubrique :** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6dff3-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6dff3-p101">Un flux de travail définit le comportement d’un appel, depuis le déclenchement de la sonnerie du téléphone jusqu’au moment où une personne répond à l’appel. Le flux de travail spécifie la file d’attente à utiliser pour la mise en attente de l’appel et indique la méthode de routage à appliquer aux groupes de recherche, ou les questions et les réponses à utiliser pour les groupes Response Group interactifs. Un flux de travail définit également des paramètres comme un message de bienvenue, l’attente musicale, les heures de bureau et les vacances.</span><span class="sxs-lookup"><span data-stu-id="6dff3-p101">A workflow defines the behavior of a call from the time that the phone rings to the time that someone answers the call. The workflow specifies the queue to use for holding the call, and specifies the routing method to use for hunt groups or the questions and answers to use for interactive response groups. A workflow also defines settings such as a welcome message, music on hold, business hours, and holidays.</span></span>

<span data-ttu-id="6dff3-108">Vous utilisez l’outil de configuration Response Group pour créer des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="6dff3-108">You use the Response Group Configuration Tool to create workflows.</span></span> <span data-ttu-id="6dff3-109">Vous pouvez accéder à l’outil de configuration Response Group à partir de la page Response Group du panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6dff3-109">You can access the Response Group Configuration Tool from the Response Group page of Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6dff3-110">Vous devez créer des groupes d’agents et des files d’attente avant de créer un flux de travail qui les utilise.</span><span class="sxs-lookup"><span data-stu-id="6dff3-110">You must create agent groups and queues before you create a workflow that uses them.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6dff3-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="6dff3-111">In This Section</span></span>

  - [<span data-ttu-id="6dff3-112">Création ou modification d’un flux de travail de groupe de recherche dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dff3-112">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)

  - [<span data-ttu-id="6dff3-113">Concevoir des flux d’appels de réponse vocale interactive dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dff3-113">Design interactive voice response call flows in Lync Server 2013</span></span>](lync-server-2013-design-interactive-voice-response-call-flows.md)

  - [<span data-ttu-id="6dff3-114">Création ou modification d’un flux de travail interactif dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dff3-114">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="6dff3-115">Sections connexes</span><span class="sxs-lookup"><span data-stu-id="6dff3-115">Related Sections</span></span>

  - [<span data-ttu-id="6dff3-116">Créer des groupes d’agents Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dff3-116">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="6dff3-117">Créer des files d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6dff3-117">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

