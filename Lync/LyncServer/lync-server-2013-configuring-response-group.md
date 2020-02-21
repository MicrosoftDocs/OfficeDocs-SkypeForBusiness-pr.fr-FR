---
title: 'Lync Server 2013 : configuration du groupe Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c40f48b52759bfc12441a558b85de89d149f4bf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196487"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="0ba78-102">Configuration du groupe Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ba78-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="0ba78-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="0ba78-104">Response Group est une fonctionnalité voix entreprise qui achemine et met en file d’attente les appels entrants vers des groupes de personnes, appelés *agents*, comme un support technique ou un service clientèle.</span><span class="sxs-lookup"><span data-stu-id="0ba78-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="0ba78-105">Les composants nécessaires à Response Group sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ba78-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0ba78-106">Pour rendre Response Group accessible aux utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des workflows.</span><span class="sxs-lookup"><span data-stu-id="0ba78-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="0ba78-107">En outre, un administrateur Response Group peut déléguer la configuration d’un flux de travail existant à un responsable de groupe Response Group, qui peut ensuite modifier et reconfigurer le flux de travail, ainsi que les groupes d’agents et les files d’attente associés.</span><span class="sxs-lookup"><span data-stu-id="0ba78-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="0ba78-108">Cette section vous guide tout au long de la configuration du groupe Response Group Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0ba78-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="0ba78-109">Il part du principe que vous avez déjà lu les sections de planification relatives au Response Group et que vous avez déployé un serveur Enterprise Edition ou un serveur Standard Edition avec voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="0ba78-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="0ba78-110">Pour plus d’informations sur la création d’un groupe Response Group à l’aide de Lync Server Management Shell, notamment un exemple de script, reportez-vous à <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>la rubrique « Creating Your First Response Group using Lync Server Management Shell » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0ba78-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0ba78-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0ba78-111">In This Section</span></span>

  - [<span data-ttu-id="0ba78-112">Autorisations et conditions préalables à la configuration du groupe Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="0ba78-113">Processus de déploiement du groupe Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="0ba78-114">Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="0ba78-115">Créer des groupes d’agents Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="0ba78-116">Créer des files d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="0ba78-117">Module Définition des heures d’ouverture d’un groupe Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="0ba78-118">Module Définir les groupes de congés Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="0ba78-119">Créer des flux de travail Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="0ba78-120">Module Vérifier le déploiement de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0ba78-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0ba78-121">See Also</span></span>


[<span data-ttu-id="0ba78-122">Planification des fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0ba78-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

