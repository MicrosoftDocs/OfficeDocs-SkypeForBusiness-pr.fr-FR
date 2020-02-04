---
title: 'Lync Server 2013 : Création d’une topologie de serveurs Edge et directeurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Building an edge and Director topology
ms:assetid: 11e5759e-d69f-4c39-8994-f467c279c558
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398202(v=OCS.15)
ms:contentKeyID: 48183451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f8a86d4f80b7fb4fc9990911908ef0c8a317c98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741784"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="building-an-edge-and-director-topology-in-lync-server-2013"></a><span data-ttu-id="c95c5-102">Création d’une topologie de serveurs Edge et directeurs dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c95c5-102">Building an edge and Director topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c95c5-103">_**Dernière modification de la rubrique :** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c95c5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c95c5-104">La création de la topologie implique les tâches de planification et de déploiement suivantes :</span><span class="sxs-lookup"><span data-stu-id="c95c5-104">Building the topology involves the following planning and deployment tasks:</span></span>

  - <span data-ttu-id="c95c5-105">**Planification**   vous devez définir une topologie appropriée pour votre organisation et identifier les composants requis pour la déployer.</span><span class="sxs-lookup"><span data-stu-id="c95c5-105">**Planning**   You need to define an appropriate topology for your organization and identify the components required to deploy it.</span></span> <span data-ttu-id="c95c5-106">Voici les étapes standard du processus de planification.</span><span class="sxs-lookup"><span data-stu-id="c95c5-106">These are standard steps in the planning process.</span></span> <span data-ttu-id="c95c5-107">L’outil de planification de Microsoft Lync Server 2013, fourni avec Lync Server 2013, simplifie le démarrage du processus de planification, ainsi que la possibilité d’apporter facilement des modifications à la fin de vos exigences et plans.</span><span class="sxs-lookup"><span data-stu-id="c95c5-107">The Microsoft Lync Server 2013, Planning Tool provided with Lync Server 2013 makes it easy to start the planning process, as well as including the ability to easily make changes as your requirements and plans are finalized.</span></span>

  - <span data-ttu-id="c95c5-108">**Le déploiement**   de la topologie définie à l’aide du générateur de topologie est essentiel pour le déploiement de n’importe quel serveur Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c95c5-108">**Deployment**   The topology that you define using Topology Builder is essential to the deployment of any Lync Server 2013 server.</span></span> <span data-ttu-id="c95c5-109">Si vous n’avez pas fini de définir et de publier votre topologie à l’aide du générateur de topologie dans le cadre de vos efforts de planification, vous devez la terminer et publier la topologie avant de déployer vos serveurs Edge.</span><span class="sxs-lookup"><span data-stu-id="c95c5-109">If you do not finish defining and publishing your topology by using Topology Builder as part of your planning efforts, you must complete it and publish the topology before you deploy your Edge Servers.</span></span>

<span data-ttu-id="c95c5-110">Vous ne pouvez pas déployer les composants du serveur Edge tant que vous n’avez pas déployé au moins un pool interne et vous devez installer le générateur de topologie pour déployer un pool interne.</span><span class="sxs-lookup"><span data-stu-id="c95c5-110">You cannot deploy Edge Server components until you have deployed at least one internal pool, and you must install Topology Builder to deploy an internal pool.</span></span> <span data-ttu-id="c95c5-111">Cette section ne couvre pas l’installation du générateur de topologie, car elle fait partie du processus d’installation du pool interne.</span><span class="sxs-lookup"><span data-stu-id="c95c5-111">This section does not cover installation of Topology Builder because that is part of the installation process for the internal pool.</span></span>

<span data-ttu-id="c95c5-112">Pour plus d’informations sur ces outils, voir [liste de vérification de déploiement pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="c95c5-112">For details about these tools, see [Deployment checklist for external user access in Lync Server 2013](lync-server-2013-deployment-checklist-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c95c5-113">Si vous avez déjà utilisé le générateur de topologie pour définir une topologie complète, y compris la topologie de bord, vous pouvez ignorer la <A href="lync-server-2013-define-your-edge-topology.md">topologie de définition de votre topologie Edge dans Lync server 2013</A> et <A href="lync-server-2013-publish-your-topology.md">publier votre topologie dans les tâches 2013 serveur Lync</A> de cette section, mais vous devez effectuer l' <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportation de votre topologie Lync Server 2013 et la copier vers le média externe pour la tâche d’installation Edge</A> .</span><span class="sxs-lookup"><span data-stu-id="c95c5-113">If you previously used Topology Builder to define a complete topology, including the edge topology, you do can skip the <A href="lync-server-2013-define-your-edge-topology.md">Define your edge topology in Lync Server 2013</A> and <A href="lync-server-2013-publish-your-topology.md">Publish your topology in Lync Server 2013</A> tasks in this section, but you do need to complete the <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A> task.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c95c5-114">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c95c5-114">In This Section</span></span>

  - [<span data-ttu-id="c95c5-115">Définition de la topologie Edge dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c95c5-115">Define your edge topology in Lync Server 2013</span></span>](lync-server-2013-define-your-edge-topology.md)

  - [<span data-ttu-id="c95c5-116">Définition des topologies facultatives de directeur dans votre topologie pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c95c5-116">Define optional Director topologies in your topology for Lync Server 2013</span></span>](lync-server-2013-define-optional-director-topologies-in-your-topology.md)

  - [<span data-ttu-id="c95c5-117">Publication de la topologie dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c95c5-117">Publish your topology in Lync Server 2013</span></span>](lync-server-2013-publish-your-topology.md)

  - [<span data-ttu-id="c95c5-118">Exportation de la topologie Lync Server 2013 et copie vers le support externe de l’installation Edge</span><span class="sxs-lookup"><span data-stu-id="c95c5-118">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

