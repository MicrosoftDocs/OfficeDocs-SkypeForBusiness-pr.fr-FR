---
title: 'Lync Server 2013 : début du processus de planification'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04bc27b965da5d4761e3283ea3106a8a3b90ebf8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a><span data-ttu-id="eaeec-102">Début du processus de planification pour Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="eaeec-102">Beginning the planning process for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eaeec-103">_**Dernière modification de la rubrique :** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="eaeec-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="eaeec-104">Bien que la planification d’un déploiement de communications unifiées sur site puisse paraître intimidante, Lync Server fournit deux outils utiles pour vous aider à :</span><span class="sxs-lookup"><span data-stu-id="eaeec-104">While planning an on-premises unified communications deployment may seem intimidating, Lync Server provides two valuable tools to help you:</span></span>

  - <span data-ttu-id="eaeec-105">**L’outil de planification** est un assistant qui présente une série de questions sur votre organisation, les fonctionnalités Lync Server que vous souhaitez activer et vos besoins en matière de planification de la capacité.</span><span class="sxs-lookup"><span data-stu-id="eaeec-105">**The Planning Tool** is a wizard that presents a series of questions about your organization, the Lync Server features that you want to enable, and your capacity planning needs.</span></span> <span data-ttu-id="eaeec-106">Il crée ensuite une topologie de déploiement recommandée en fonction de vos réponses et génère un diagramme Microsoft Visio de ce déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaeec-106">It then creates a recommended deployment topology based on your answers, and produces a Microsoft Visio diagram of this deployment.</span></span>

  - <span data-ttu-id="eaeec-107">Le **Générateur de topologies** est un composant d’installation de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaeec-107">**Topology Builder** is an installation component of Lync Server.</span></span> <span data-ttu-id="eaeec-108">Le générateur de topologies vous permet de créer, d’ajuster et de publier votre topologie planifiée.</span><span class="sxs-lookup"><span data-stu-id="eaeec-108">You use Topology Builder to create, adjust, and publish your planned topology.</span></span> <span data-ttu-id="eaeec-109">Il valide également votre topologie avant que vous ne commenciez à installer les serveurs.</span><span class="sxs-lookup"><span data-stu-id="eaeec-109">It also validates your topology before you begin server installations.</span></span> <span data-ttu-id="eaeec-110">Lorsque vous installez Lync Server sur des serveurs individuels, les serveurs lisent la topologie publiée dans le cadre du processus d’installation, et le programme d’installation déploie le serveur comme indiqué dans la topologie.</span><span class="sxs-lookup"><span data-stu-id="eaeec-110">When you install Lync Server on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span>

<div>

## <a name="lync-server-planning-tool"></a><span data-ttu-id="eaeec-111">Outil de planification Lync Server</span><span class="sxs-lookup"><span data-stu-id="eaeec-111">Lync Server Planning Tool</span></span>

<span data-ttu-id="eaeec-112">L’outil de planification répond aux questions posées dans l’outil et génère une topologie basée sur les recommandations et les meilleures pratiques de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaeec-112">The Planning Tool takes your answers to the questions in the tool and generates a topology based on Lync Server guidelines and best practices.</span></span> <span data-ttu-id="eaeec-113">Il propose également plusieurs vues de déploiement en fonction de vos réponses.</span><span class="sxs-lookup"><span data-stu-id="eaeec-113">It also provides several views of a deployment based on your answers.</span></span> <span data-ttu-id="eaeec-114">Il offre à la fois une vue globale de tous vos sites (y compris les sites centraux et les sites de succursale) ainsi que des vues détaillées montrant les serveurs et autres composants de chaque site.</span><span class="sxs-lookup"><span data-stu-id="eaeec-114">It shows both a global view of all your sites (that is, including both central sites and branch sites), and detailed views showing the servers and other components at each site.</span></span>

<span data-ttu-id="eaeec-115">L’exécution de l’outil de planification ne vous engage pas sur un déploiement spécifique ou ne lance pas de processus.</span><span class="sxs-lookup"><span data-stu-id="eaeec-115">Running the Planning Tool does not commit you to any specific deployment or initiate any processes.</span></span> <span data-ttu-id="eaeec-116">En fait, l’exécution de l’outil de planification, même avant que vous ne soyez prêt à l’esprit, peut être une façon très instructive de comprendre les types de questions que vous devez prendre en compte dans votre processus de planification.</span><span class="sxs-lookup"><span data-stu-id="eaeec-116">In fact, running the Planning Tool even before you have a firm plan in mind can be a very instructive way to understand the kinds of questions you need to think about in your planning process.</span></span>

<span data-ttu-id="eaeec-117">Vous pouvez exécuter l’outil de planification plusieurs fois, répondre différemment aux questions et comparer les résultats.</span><span class="sxs-lookup"><span data-stu-id="eaeec-117">You can run the Planning Tool multiple times, answering questions differently, and compare the outcomes.</span></span> <span data-ttu-id="eaeec-118">Si vous disposez d’une conception que vous êtes le plus satisfaite, mais que vous devez y effectuer des modifications, vous pouvez revenir à l’outil de planification, charger la conception et effectuer les modifications.</span><span class="sxs-lookup"><span data-stu-id="eaeec-118">If you have a design you are mostly satisfied with but that you need to make changes to, you can return to the Planning Tool, load the design, and make the changes.</span></span> <span data-ttu-id="eaeec-119">Il faut environ 15 minutes pour terminer l’outil de planification une seule fois.</span><span class="sxs-lookup"><span data-stu-id="eaeec-119">It takes about 15 minutes to complete the Planning Tool once.</span></span>

<span data-ttu-id="eaeec-120">Une fois que vous êtes satisfait, vous pouvez utiliser l’outil de planification pour créer un diagramme de votre déploiement planifié.</span><span class="sxs-lookup"><span data-stu-id="eaeec-120">After you are satisfied, you can use the Planning Tool to create a diagram of your planned deployment.</span></span> <span data-ttu-id="eaeec-121">Vous pouvez utiliser ce diagramme lors de la création du déploiement dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="eaeec-121">You can use this diagram while creating the deployment in Topology Builder.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eaeec-122">L’outil de planification inclus dans cette version de Lync Server 2013 est une version préliminaire.</span><span class="sxs-lookup"><span data-stu-id="eaeec-122">The Planning Tool included with this release of Lync Server 2013 is a prerelease version.</span></span> <span data-ttu-id="eaeec-123">Notez que les nombres de planification de la capacité dans l’Outil de planification sont préliminaires et ne sont pas pris en charge pour la version finale.</span><span class="sxs-lookup"><span data-stu-id="eaeec-123">Note that the capacity planning numbers in the Planning Tool are preliminary and are not supported for the final release.</span></span>



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a><span data-ttu-id="eaeec-124">Générateur de topologies Lync Server</span><span class="sxs-lookup"><span data-stu-id="eaeec-124">Lync Server Topology Builder</span></span>

<span data-ttu-id="eaeec-125">Une fois que vous avez choisi votre plan de déploiement, vous utilisez le générateur de topologie pour commencer le déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaeec-125">Once you have decided on your deployment plan, you use Topology Builder to begin deploying.</span></span> <span data-ttu-id="eaeec-126">Lorsque vous avez terminé, vous utilisez le générateur de topologies pour valider la topologie, puis, si elle réussit, vous pouvez publier la topologie.</span><span class="sxs-lookup"><span data-stu-id="eaeec-126">When finished, you use Topology Builder to validate the topology, and then, if it passes, you can publish the topology.</span></span> <span data-ttu-id="eaeec-127">Lorsque vous publiez la topologie, Lync Server place la topologie dans le magasin central de gestion, qui est créé à ce stade s’il n’existe pas déjà.</span><span class="sxs-lookup"><span data-stu-id="eaeec-127">When you publish the topology, Lync Server puts the topology into the Central Management store, which is created at this time if it does not already exist.</span></span> <span data-ttu-id="eaeec-128">Lorsque vous installez Lync Server sur chaque serveur de votre déploiement, le serveur lit la topologie à partir du magasin central de gestion et s’installe en fonction de son rôle dans votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaeec-128">When you install Lync Server on each server in your deployment, the server reads the topology from the Central Management store and installs itself to fit into its role in your deployment.</span></span>

<span data-ttu-id="eaeec-129">Par ailleurs, si vous connaissez Lync Server et que vous avez besoin de conseils moins normatifs, vous pouvez ignorer l’outil de planification et utiliser les assistants du générateur de topologies pour la conception initiale de votre déploiement, ainsi que les étapes de validation et de publication.</span><span class="sxs-lookup"><span data-stu-id="eaeec-129">Alternatively, if you are very familiar with Lync Server and need less prescriptive guidance, you can skip the Planning Tool and use the wizards in Topology Builder for the initial design of your deployment and also for the validation and publishing steps.</span></span>

<span data-ttu-id="eaeec-130">L’utilisation du générateur de topologie pour planifier et publier une topologie est une étape obligatoire.</span><span class="sxs-lookup"><span data-stu-id="eaeec-130">Using Topology Builder to plan and publish a topology is a required step.</span></span> <span data-ttu-id="eaeec-131">Vous ne pouvez pas contourner le générateur de topologie et installer Lync Server individuellement sur les serveurs de votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaeec-131">You cannot bypass Topology Builder and install Lync Server individually on the servers in your deployment.</span></span> <span data-ttu-id="eaeec-132">Chaque serveur doit lire la topologie à partir d’une topologie validée et publiée dans le magasin central de gestion.</span><span class="sxs-lookup"><span data-stu-id="eaeec-132">Each server must read the topology from a validated, published topology in the Central Management store.</span></span>

</div>

<div>

## <a name="high-level-planning-process"></a><span data-ttu-id="eaeec-133">Processus de planification de haut niveau</span><span class="sxs-lookup"><span data-stu-id="eaeec-133">High-Level Planning Process</span></span>

<span data-ttu-id="eaeec-134">Nous vous recommandons d’utiliser la documentation et l’outil de planification pour planifier votre déploiement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaeec-134">We recommend the following general process for using both the documentation and the Planning Tool to plan your Lync Server deployment.</span></span>

1.  <span data-ttu-id="eaeec-135">Si vous êtes familiarisé avec les versions précédentes de Lync Server, lisez les [nouvelles fonctionnalités de Lync server 2013](lync-server-2013-new-features.md) pour vous familiariser avec les nouvelles fonctionnalités et conditions requises dans lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eaeec-135">If you are familiar with previous versions of Lync Server, read [New features in Lync Server 2013](lync-server-2013-new-features.md) to familiarize yourself with the new features and requirements in Lync Server 2013.</span></span>

2.  <span data-ttu-id="eaeec-136">Lisez les autres rubriques de cette section de la documentation : [notions de base sur la topologie que vous devez savoir avant de planifier Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md), [décisions de planification initiale pour Lync Server 2013](lync-server-2013-initial-planning-decisions.md)et [clients pour Lync Server 2013](lync-server-2013-clients.md).</span><span class="sxs-lookup"><span data-stu-id="eaeec-136">Read the other topics in this section of the documentation: [Topology basics you must know before planning for Lync Server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md), [Initial planning decisions for Lync Server 2013](lync-server-2013-initial-planning-decisions.md), and [Clients for Lync Server 2013](lync-server-2013-clients.md).</span></span> <span data-ttu-id="eaeec-137">Notez les décisions de planification représentées dans les [topologies de référence dans Lync Server 2013](lync-server-2013-reference-topologies.md).</span><span class="sxs-lookup"><span data-stu-id="eaeec-137">Note the planning decisions represented in [Reference topologies in Lync Server 2013](lync-server-2013-reference-topologies.md).</span></span>

3.  <span data-ttu-id="eaeec-138">Maintenant que vous êtes familiarisé avec les fonctionnalités de Lync Server et les types de questions auxquelles vous devez répondre, exécutez l’outil de planification et affichez la topologie résultante et ses détails.</span><span class="sxs-lookup"><span data-stu-id="eaeec-138">Now that you are more familiar with Lync Server features and the kinds of questions that must be answered, run the Planning Tool and view the resulting topology and its details.</span></span> <span data-ttu-id="eaeec-139">Assurez-vous que la topologie s’adapte aux exigences uniques de votre entreprise.</span><span class="sxs-lookup"><span data-stu-id="eaeec-139">Make sure that the topology fits the unique requirements for your organization.</span></span>

4.  <span data-ttu-id="eaeec-140">S’il existe des charges de travail ou des fonctionnalités particulières qui vous intéressent ou que vous devez en savoir plus, lisez les sections appropriées de la [planification de Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="eaeec-140">If there are particular workloads or features you are interested in or need to learn about, read the appropriate sections of [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

5.  <span data-ttu-id="eaeec-141">Réexécutez l’outil de planification.</span><span class="sxs-lookup"><span data-stu-id="eaeec-141">Run the Planning Tool again.</span></span> <span data-ttu-id="eaeec-142">Vous pouvez commencer par le déploiement que vous avez créé à l’étape 3 puis modifier les résultats, ou reprendre tout à zéro.</span><span class="sxs-lookup"><span data-stu-id="eaeec-142">You can start with the deployment you created in step 3 and modify the results, or start over from the beginning.</span></span>
    
    <span data-ttu-id="eaeec-143">Si nécessaire, exécutez l’outil de planification une troisième fois et répétez l’opération jusqu’à ce que vous soyez satisfait du résultat.</span><span class="sxs-lookup"><span data-stu-id="eaeec-143">If needed, run the Planning Tool a third time and repeat until you are satisfied with the output.</span></span>

6.  <span data-ttu-id="eaeec-144">Une fois que vous avez finalisé le plan de la topologie, utilisez l’outil de planification pour créer et imprimer un diagramme Visio de votre topologie.</span><span class="sxs-lookup"><span data-stu-id="eaeec-144">When you have finalized the topology plan, use Planning Tool to create and print a Visio diagram of your topology.</span></span> <span data-ttu-id="eaeec-145">Vous pouvez utiliser cette impression lorsque vous utilisez le générateur de topologie pour entrer votre topologie.</span><span class="sxs-lookup"><span data-stu-id="eaeec-145">You can use this printout while working with Topology Builder to input your topology.</span></span>

7.  <span data-ttu-id="eaeec-146">Avant de commencer le déploiement, consultez la détermination de la [Configuration système requise pour Lync server 2013](lync-server-2013-determining-your-system-requirements.md) et détermination de la [Configuration requise pour votre infrastructure pour Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) afin de vous familiariser avec les conditions préalables et l’infrastructure nécessaire pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="eaeec-146">Before you begin deployment, read [Determining your system requirements for Lync Server 2013](lync-server-2013-determining-your-system-requirements.md) and [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) to familiarize yourself with the prerequisites and necessary infrastructure for Lync Server.</span></span> <span data-ttu-id="eaeec-147">De plus, vérifiez que vous avez lu toutes les sections de [planification de Lync Server 2013](lync-server-2013-planning.md) qui s’appliquent aux charges de travail et aux fonctionnalités que vous prévoyez de déployer.</span><span class="sxs-lookup"><span data-stu-id="eaeec-147">Additionally, be sure you have read all the sections of [Planning for Lync Server 2013](lync-server-2013-planning.md) that apply to the workloads and features that you plan to deploy.</span></span>

</div>

<div>

## <a name="migrating-from-previous-versions"></a><span data-ttu-id="eaeec-148">Migration à partir de versions précédentes</span><span class="sxs-lookup"><span data-stu-id="eaeec-148">Migrating from Previous Versions</span></span>

<span data-ttu-id="eaeec-149">Si vous effectuez une migration vers Lync Server à partir d’une version antérieure, reportez-vous à la documentation de [migration](migration.md) pour obtenir des instructions spécifiques pour votre migration et votre déploiement.</span><span class="sxs-lookup"><span data-stu-id="eaeec-149">If you are migrating to Lync Server from a previous version, see the [Migration](migration.md) documentation for specific instructions for your migration and deployment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

