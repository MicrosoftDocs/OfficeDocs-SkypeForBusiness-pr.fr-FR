---
title: 'Lync Server 2013 : administration du système'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="8cda0-102">Administration du système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8cda0-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8cda0-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8cda0-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8cda0-104">L’administration du système inclut les tâches d’administration quotidiennes, planifiées et à la demande, qui sont nécessaires pour maintenir le fonctionnement du système informatique en toute transparence.</span><span class="sxs-lookup"><span data-stu-id="8cda0-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="8cda0-105">En règle générale, les tâches d’administration système sont couvertes par des procédures écrites.</span><span class="sxs-lookup"><span data-stu-id="8cda0-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="8cda0-106">Ces procédures permettent de vérifier que les mêmes outils et méthodes standard sont utilisés par tous les membres du personnel de support technique.</span><span class="sxs-lookup"><span data-stu-id="8cda0-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="8cda0-107">Dans un environnement Lync, les tâches d’administration système typiques incluent la sauvegarde et l’archivage des pools, le suivi des journaux, la création et la gestion des utilisateurs, et la mise à jour d’un logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="8cda0-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="8cda0-108">Résolution des problèmes système</span><span class="sxs-lookup"><span data-stu-id="8cda0-108">System troubleshooting</span></span>

<span data-ttu-id="8cda0-109">Une organisation doit se préparer à traiter les problèmes inattendus et doit avoir une procédure pour gérer les problèmes à partir du moment où elles sont communiquées jusqu’à leur résolution.</span><span class="sxs-lookup"><span data-stu-id="8cda0-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="8cda0-110">Des informations sur la manière dont le personnel du support a diagnostiqué un problème doivent être enregistrés et utilisés à l’avenir pour éviter la répétition inutile du fonctionnement.</span><span class="sxs-lookup"><span data-stu-id="8cda0-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="8cda0-111">Processus de résolution des problèmes système</span><span class="sxs-lookup"><span data-stu-id="8cda0-111">System troubleshooting process</span></span>

<span data-ttu-id="8cda0-112">Le diagramme suivant illustre le processus de résolution des problèmes de système et les interactions avec d’autres rôles d’opérations.</span><span class="sxs-lookup"><span data-stu-id="8cda0-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="8cda0-113">**Organigramme de résolution des problèmes système**</span><span class="sxs-lookup"><span data-stu-id="8cda0-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="8cda0-114">![Organigramme de dépannage du système](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Organigramme de dépannage du système")</span><span class="sxs-lookup"><span data-stu-id="8cda0-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="8cda0-115">**Pour classer et**   définir la priorité de cette tâche, le service d’assistance est généralement exécuté.</span><span class="sxs-lookup"><span data-stu-id="8cda0-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="8cda0-116">Par exemple, un problème est susceptible d’être regroupé en tant que problème logiciel ou en cas de problème de matériel.</span><span class="sxs-lookup"><span data-stu-id="8cda0-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="8cda0-117">Le problème est ensuite acheminé vers l’équipe de support technique appropriée pour examen.</span><span class="sxs-lookup"><span data-stu-id="8cda0-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="8cda0-118">Les règles de détermination de la priorité d’un problème, ainsi que le temps de réponse et le temps de résolution, sont généralement définis dans le contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="8cda0-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="8cda0-119">**Recherchez et diagnostiquez**   l’équipe de support technique appropriée pour diagnostiquer le problème et proposer des modifications pour résoudre ce problème.</span><span class="sxs-lookup"><span data-stu-id="8cda0-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="8cda0-120">S’il s’agit d’une solution simple et qu’elle n’exige aucun contrôle de modification, la solution peut être appliquée immédiatement.</span><span class="sxs-lookup"><span data-stu-id="8cda0-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="8cda0-121">Si la solution n’est pas facile, une demande de modification doit être levée et le processus de gestion des modifications doit être géré par le processus de gestion des modifications, souvent dans le cadre d’une procédure de suivi rapide.</span><span class="sxs-lookup"><span data-stu-id="8cda0-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="8cda0-122">Les modifications apportées doivent être enregistrées à l’aide du processus de gestion de la configuration.</span><span class="sxs-lookup"><span data-stu-id="8cda0-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="8cda0-123">**Fermez et notez**   après avoir testé la résolution, le problème devrait être clos.</span><span class="sxs-lookup"><span data-stu-id="8cda0-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="8cda0-124">S’il existe des leçons à découvrir du problème, une entrée doit être créée dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="8cda0-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="8cda0-125">**Réviser et analyse**   des tendances les avis périodiques des problèmes récents doivent être réalisés pour identifier les tendances des problèmes.</span><span class="sxs-lookup"><span data-stu-id="8cda0-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="8cda0-126">Par exemple, si les utilisateurs rencontrent des problèmes fréquents de connexion lente à leurs sites Lync, des problèmes de bande passante réseau peuvent en être la cause.</span><span class="sxs-lookup"><span data-stu-id="8cda0-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="8cda0-127">Les délais de résolution des problèmes et l’incidence de tout problème de disponibilité du système doivent être examinés et comparés avec le contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="8cda0-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="8cda0-128">La personne qui se connecte au client en cas de problème de service, par exemple, un responsable de compte, doit être informée de problèmes importants.</span><span class="sxs-lookup"><span data-stu-id="8cda0-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="8cda0-129">Outils de gestion des problèmes</span><span class="sxs-lookup"><span data-stu-id="8cda0-129">Issue management tools</span></span>

<span data-ttu-id="8cda0-130">Les outils de support technique permettent aux membres du personnel d’enregistrer, de classifier et de hiérarchiser les nouveaux problèmes.</span><span class="sxs-lookup"><span data-stu-id="8cda0-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="8cda0-131">Les outils fournissent alors les processus de flux de travail de gestion de la demande de service de problème par le biais d’enquêtes et de diagnostics, souvent par plusieurs membres de l’équipe de support technique.</span><span class="sxs-lookup"><span data-stu-id="8cda0-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="8cda0-132">Outils, qui fournissent fréquemment des rapports sur les temps de résolution et les tendances historiques, peuvent également inclure une base de données de la base de connaissances, qui peut être utilisée pour effectuer une recherche dans d’anciens problèmes.</span><span class="sxs-lookup"><span data-stu-id="8cda0-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="8cda0-133">La base de connaissances Microsoft est un enregistrement utile des problèmes de support rencontrés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8cda0-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="8cda0-134">Pour plus d’informations, consultez le site Web du<http://go.microsoft.com/fwlink/?linkid=14898>support Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="8cda0-134">For more information, see the Microsoft Support website (<http://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="8cda0-135">Le logiciel tiers doit généralement être personnalisé pour répondre aux besoins de l’organisation, par exemple, l’Organisation des équipes, les exigences en matière de création de rapports et les mesures requises par le SLA.</span><span class="sxs-lookup"><span data-stu-id="8cda0-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="8cda0-136">Administration centralisée et décentralisée</span><span class="sxs-lookup"><span data-stu-id="8cda0-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="8cda0-137">Les rôles et les responsabilités liés à l’exécution des tâches d’administration du système varient selon que l’organisation suit ou non un modèle centralisé, un modèle décentralisé ou une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="8cda0-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="8cda0-138">**Modèle centralisé dans**   un modèle centralisé, un ou plusieurs groupes d’administration conservent le contrôle total de l’ensemble de l’environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8cda0-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="8cda0-139">Ce modèle d’administration ressemble à un centre de données dans lequel toutes les tâches d’administration sont effectuées par un groupe de technologies d’information unique.</span><span class="sxs-lookup"><span data-stu-id="8cda0-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="8cda0-140">Les rôles et les responsabilités au sein de l’équipe doivent être définis en fonction de l’expérience et de l’expertise.</span><span class="sxs-lookup"><span data-stu-id="8cda0-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="8cda0-141">\*\*\*\*   Les organisations décentralisées du modèle décentralisé sont situées dans plusieurs emplacements géographiques et disposent de serveurs Lync Server et de équipes d’administrateurs situés à des emplacements différents.</span><span class="sxs-lookup"><span data-stu-id="8cda0-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="8cda0-142">Par exemple, il se peut que le personnel d’administration local et un ou plusieurs serveurs exécutant Lync Server 2013 pour chaque pays/région.</span><span class="sxs-lookup"><span data-stu-id="8cda0-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="8cda0-143">Il est possible qu’il y ait un pool de serveurs exécutant Lync Server 2013 et une équipe administrative pour l’Amérique du Nord et une pour l’Europe.</span><span class="sxs-lookup"><span data-stu-id="8cda0-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="8cda0-144">Parfois, vous souhaiterez peut-être que les administrateurs puissent être responsables uniquement de leur propre zone géographique et limiter les autorisations d’administration des ressources dans d’autres zones.</span><span class="sxs-lookup"><span data-stu-id="8cda0-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="8cda0-145">Lync Server vous permet également de déléguer des tâches administratives spécifiques à des personnes ou groupes spécifiques à l’aide d’un contrôle d’accès basé sur les rôles (RBAC).</span><span class="sxs-lookup"><span data-stu-id="8cda0-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="8cda0-146">Le RBAC permet aux administrateurs de déléguer des droits d’utilisateur et des autorisations à d’autres administrateurs pour effectuer un sous-ensemble de tâches administratives possibles.</span><span class="sxs-lookup"><span data-stu-id="8cda0-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="8cda0-147">En utilisant RBAC, la capacité de l’utilisateur à effectuer des tâches d’administration dépend des rôles RBAC attribués à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8cda0-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="8cda0-148">Le RBAC fournit une liste des cmdlets que l’utilisateur peut exécuter en fonction des rôles RBAC dont l’utilisateur est membre.</span><span class="sxs-lookup"><span data-stu-id="8cda0-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

