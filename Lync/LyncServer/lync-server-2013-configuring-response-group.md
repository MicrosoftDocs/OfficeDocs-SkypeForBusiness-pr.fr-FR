---
title: 'Lync Server 2013 : Configuration du groupe Response Group'
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
ms.openlocfilehash: b94bc731ac00a4ff774930f506282b6aef16cbaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-response-group-in-lync-server-2013"></a><span data-ttu-id="48b7d-102">Configuration du groupe Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-102">Configuring Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b7d-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="48b7d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="48b7d-104">Response Group est une fonctionnalité de voix entreprise qui achemine et met en file d’attente les appels entrants vers des groupes de personnes, appelés *agents*, tels qu’un service d’assistance ou un service clientèle.</span><span class="sxs-lookup"><span data-stu-id="48b7d-104">Response Group is an Enterprise Voice feature that routes and queues incoming calls to groups of people, called *agents*, such as a help desk or a customer service desk.</span></span>

<span data-ttu-id="48b7d-105">Les composants requis par le groupe de réponse sont installés et activés automatiquement sur le serveur frontal ou le serveur Standard Edition lors du déploiement de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="48b7d-105">The components that Response Group requires are installed and enabled automatically on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="48b7d-106">Pour rendre le groupe de réponses disponible pour les utilisateurs, vous devez configurer des groupes d’agents, des files d’attente, puis des flux de travail.</span><span class="sxs-lookup"><span data-stu-id="48b7d-106">To make Response Group available to users, you must configure agent groups, then queues, and then workflows.</span></span> <span data-ttu-id="48b7d-107">Par ailleurs, un administrateur de groupe de réponse peut déléguer la configuration d’un flux de travail existant à un gestionnaire de groupe de réponse, qui peut ensuite modifier et reconfigurer le flux de travail ainsi que ses groupes d’agents et files d’attente associés.</span><span class="sxs-lookup"><span data-stu-id="48b7d-107">Additionally, a Response Group Administrator can delegate configuration of an existing workflow to a Response Group Manager, who can then modify and reconfigure the workflow and its associated agent groups and queues.</span></span>

<span data-ttu-id="48b7d-108">Cette section vous guide dans la configuration du groupe de réponse Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="48b7d-108">This section guides you through the configuration of Lync Server 2013 Response Group.</span></span> <span data-ttu-id="48b7d-109">Il part du principe que vous avez déjà lu les sections de planification associées au Response Group et avez déployé un serveur Enterprise Edition ou un serveur Standard Edition avec Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="48b7d-109">It assumes that you have already read the planning sections related to Response Group and have deployed an Enterprise Edition server or a Standard Edition server with Enterprise Voice.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="48b7d-110">Pour plus d’informations sur la création d’un groupe de réponse à l’aide de Lync Server Management Shell, y compris un exemple de script, reportez-vous <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>à la section « Création de votre premier groupe de réponse avec Lync Server Management Shell ».</span><span class="sxs-lookup"><span data-stu-id="48b7d-110">For details about creating a Response Group by using Lync Server Management Shell, including a sample script, see "Creating Your First Response Group Using Lync Server Management Shell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=204108">http://go.microsoft.com/fwlink/p/?linkId=204108</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="48b7d-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="48b7d-111">In This Section</span></span>

  - [<span data-ttu-id="48b7d-112">Autorisations et conditions prérequises pour la configuration de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-112">Response Group configuration permissions and prerequisites in Lync Server 2013</span></span>](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [<span data-ttu-id="48b7d-113">Processus de déploiement pour Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-113">Deployment process for Response Group in Lync Server 2013</span></span>](lync-server-2013-deployment-process-for-response-group.md)

  - [<span data-ttu-id="48b7d-114">Vue d’ensemble des scénarios de création de flux de travail dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-114">Overview of workflow creation scenarios in Lync Server 2013</span></span>](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [<span data-ttu-id="48b7d-115">Création des groupes d’agents Response Group Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-115">Create Response Group agent groups Lync Server 2013</span></span>](lync-server-2013-create-response-group-agent-groups.md)

  - [<span data-ttu-id="48b7d-116">Création des files d’attente Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-116">Create Response Group queues in Lync Server 2013</span></span>](lync-server-2013-create-response-group-queues.md)

  - [<span data-ttu-id="48b7d-117">Facultatif Définir les heures d’activité du groupe de réponses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-117">(Optional) Define Response Group business hours in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-business-hours.md)

  - [<span data-ttu-id="48b7d-118">Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-118">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [<span data-ttu-id="48b7d-119">Création des flux de travail Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-119">Create Response Group workflows in Lync Server 2013</span></span>](lync-server-2013-create-response-group-workflows.md)

  - [<span data-ttu-id="48b7d-120">Facultatif Vérifier le déploiement de Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-120">(Optional) Verify Response Group deployment in Lync Server 2013</span></span>](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48b7d-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="48b7d-121">See Also</span></span>


[<span data-ttu-id="48b7d-122">Planifier les fonctionnalités de gestion des appels dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b7d-122">Planning for call management features in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

