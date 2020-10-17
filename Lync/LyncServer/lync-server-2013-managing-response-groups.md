---
title: 'Lync Server 2013 : gestion des groupes Response Group'
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
ms.openlocfilehash: 00736a94cc383a362a3f952519acc603c5beefab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507191"
---
# <a name="managing-response-groups-in-lync-server-2013"></a><span data-ttu-id="7faf8-102">Gestion des groupes Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7faf8-102">Managing response groups in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7faf8-103">_**Dernière modification de la rubrique :** 2018-02-01_</span><span class="sxs-lookup"><span data-stu-id="7faf8-103">_**Topic Last Modified:** 2018-02-01_</span></span>

<span data-ttu-id="7faf8-104">Les groupes Response Group sont une fonctionnalité de gestion des appels qui vous permet de mettre en file d’attente les appels passés vers une zone spécifique, telle qu’un service de support technique, puis de les acheminer vers un groupe de personnes désignées, appelées des *agents*.</span><span class="sxs-lookup"><span data-stu-id="7faf8-104">Response groups are a call management feature that enables you to queue calls that are made to a specific area, such as a Help Desk, and then route the calls to a designated group of people, called *agents*.</span></span>

<span data-ttu-id="7faf8-105">Pour gérer les groupes Response Group, vous devez configurer des groupes d’agents, des files d’attente et des flux de travail, qui définissent ce qui arrive à un appel entre le moment où il est passé et le moment où un agent y répond.</span><span class="sxs-lookup"><span data-stu-id="7faf8-105">To manage response groups, you configure agent groups, queues, and workflows, which define what happens to a call from the time it is placed until an agent answers it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7faf8-106">Si vous avez plus de 300 flux de travail dans un seul pool dans votre déploiement de Response Group, il est préférable d’utiliser des applets de commande Lync Server Management Shell pour créer les flux de travail.</span><span class="sxs-lookup"><span data-stu-id="7faf8-106">If you have more than 300 workflows in a single pool in your Response Group deployment, it is better to use Lync Server Management Shell cmdlets to create the workflows.</span></span> <span data-ttu-id="7faf8-107">Si vous utilisez l’outil de configuration de groupes Response Group en vue de créer des flux de travail pour un pool qui en contient plus de 300, le chargement de la page web sera plus long.</span><span class="sxs-lookup"><span data-stu-id="7faf8-107">If you use the Response Group Configuration Tool to create workflows for a pool that has more than 300 workflows, the webpage takes a long time to load.</span></span> <span data-ttu-id="7faf8-108">Le nombre d’agents indirectement associés aux flux de travail par le biais des files d’attente a également un effet proportionnel au chargement de la page.</span><span class="sxs-lookup"><span data-stu-id="7faf8-108">The number of agents that are indirectly associated with workflows through the queues also has a proportional effect on page loading.</span></span>



</div>

<span data-ttu-id="7faf8-109">Les rubriques de cette section comportent des procédures détaillées pour les tâches que vous pouvez effectuer pour personnaliser et gérer l’application Response Group dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="7faf8-109">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Response Group application in your deployment</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7faf8-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7faf8-110">In This Section</span></span>

  - [<span data-ttu-id="7faf8-111">Gestion des groupes d’agents Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7faf8-111">Managing Response Group agent groups in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-agent-groups.md)

  - [<span data-ttu-id="7faf8-112">Gestion des files d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7faf8-112">Managing Response Group queues in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-queues.md)

  - [<span data-ttu-id="7faf8-113">Gestion des flux de travail Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7faf8-113">Managing Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-managing-response-group-workflows.md)

  - [<span data-ttu-id="7faf8-114">Gestion des paramètres de groupe Response Group au niveau de l’application dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7faf8-114">Managing application-level Response Group settings in Lync Server 2013</span></span>](lync-server-2013-managing-application-level-response-group-settings.md)

  - [<span data-ttu-id="7faf8-115">Transfert de groupes Response Group vers un nouveau pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7faf8-115">Moving response groups to a new pool in Lync Server 2013</span></span>](lync-server-2013-moving-response-groups-to-a-new-pool.md)

  - [<span data-ttu-id="7faf8-116">Gestion des groupes Response Group dans Lync Server 2013 lors d’un sinistre</span><span class="sxs-lookup"><span data-stu-id="7faf8-116">Managing response groups in Lync Server 2013 during a disaster</span></span>](lync-server-2013-managing-response-groups-during-a-disaster.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

