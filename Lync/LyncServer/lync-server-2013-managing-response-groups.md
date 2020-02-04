---
title: 'Lync Server 2013 : gestion des groupes de réponse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing response groups
ms:assetid: 5a804d7d-3c1a-4647-a0e0-d5c4c8c23b73
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520996(v=OCS.15)
ms:contentKeyID: 48184222
ms.date: 02/01/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 210debb3c3879d6895b127b960139970bf73d020
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756068"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="36281-102">Gestion des groupes de réponses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36281-102">Managing response groups in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36281-103">_**Dernière modification de la rubrique :** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="36281-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="36281-104">Les Response Groups sont une fonctionnalité de gestion des appels qui vous permet d’effectuer la mise en file d’attente d’appels passés vers une zone spécifique, par exemple un support technique, puis diriger les appels vers un groupe de personnes désignés, appelé *agents*.</span><span class="sxs-lookup"><span data-stu-id="36281-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="36281-105">Pour gérer les groupes de réponse, vous configurez des groupes d’agents, des files d’attente et des flux de travail, qui définissent ce qu’il advient de l’appel jusqu’à ce qu’un agent réponde.</span><span class="sxs-lookup"><span data-stu-id="36281-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="36281-106">Si vous avez plus de flux de travail 300 dans un seul pool dans le déploiement de votre groupe de réponse, il est préférable d’utiliser les applets de cmdlet Lync Server Management Shell pour créer les flux de travail.</span><span class="sxs-lookup"><span data-stu-id="36281-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="36281-107">Si vous utilisez l’outil de configuration de Response Group pour créer des flux de travail pour un pool qui comporte plus de flux de travail 300, le chargement de la page Web prend du temps.</span><span class="sxs-lookup"><span data-stu-id="36281-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="36281-108">Le nombre d’agents indirectement associés à des flux de travail par le biais des files d’attente a également un effet proportionnel sur le chargement de la page.</span><span class="sxs-lookup"><span data-stu-id="36281-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="36281-109">Les rubriques de cette section fournissent des procédures pas à pas pour les tâches que vous pouvez effectuer pour personnaliser et mettre à jour l’application Response Group dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="36281-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="36281-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="36281-110">In This Section</span></span>

  - [<span data-ttu-id="36281-111">Gestion des groupes d’agents de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36281-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="36281-112">Gestion des files d’attente de groupe de réponses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36281-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="36281-113">Gestion des flux de travail de groupe de réponses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36281-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="36281-114">Gestion des paramètres du groupe de réponses au niveau de l’application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36281-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="36281-115">Déplacer des groupes de réponse vers un nouveau pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36281-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="36281-116">Gestion des groupes Response Group dans Lync Server 2013 lors d’un sinistre</span><span class="sxs-lookup"><span data-stu-id="36281-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

