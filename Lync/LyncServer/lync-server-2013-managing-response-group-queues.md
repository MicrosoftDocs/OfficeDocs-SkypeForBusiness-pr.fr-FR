---
title: 'Lync Server 2013 : gestion des files d’attente Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group queues
ms:assetid: 1e91720c-ab67-4dfb-b30c-0ef2a8012310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520960(v=OCS.15)
ms:contentKeyID: 48183576
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7982833a6f2bf07886da0aa0b214926efdc63f4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-response-group-queues-in-lync-server-2013"></a><span data-ttu-id="e93d9-102">Gestion des files d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e93d9-102">Managing Response Group queues in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e93d9-103">_**Dernière modification de la rubrique :** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="e93d9-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="e93d9-104">Les files d’attente mettent en attente les appels vers un groupe de réponse jusqu’à ce qu’un agent y réponde.</span><span class="sxs-lookup"><span data-stu-id="e93d9-104">Queues hold calls to a response group until an agent answers the call.</span></span> <span data-ttu-id="e93d9-105">Lorsque vous gérez une file d’attente, vous devez affecter des groupes d’agents à celle-ci et définir ses paramètres, notamment le nombre d’appels qu’elle peut contenir avant qu’une action de saturation ne soit déclenchée et la durée que doit attendre un appel pour qu’un agent y réponde avant qu’une action d’expiration ne soit déclenchée.</span><span class="sxs-lookup"><span data-stu-id="e93d9-105">When you manage a queue, you assign one or more agent groups to the queue and specify queue settings, such as the number of calls that the queue can hold before performing an overflow action and the length of time that a call waits for an agent before performing a time-out action.</span></span> <span data-ttu-id="e93d9-106">Lorsque l’application Response Group recherche un agent disponible, elle recherche les groupes d’agents dans l’ordre dans lequel vous les répertoriez.</span><span class="sxs-lookup"><span data-stu-id="e93d9-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e93d9-107">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="e93d9-107">In This Section</span></span>

  - [<span data-ttu-id="e93d9-108">Création ou modification d’une file d’attente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e93d9-108">Create or modify a queue in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-queue.md)

  - [<span data-ttu-id="e93d9-109">Supprimer une file d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e93d9-109">Delete a Response Group queue in Lync Server 2013</span></span>](lync-server-2013-delete-a-response-group-queue.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

