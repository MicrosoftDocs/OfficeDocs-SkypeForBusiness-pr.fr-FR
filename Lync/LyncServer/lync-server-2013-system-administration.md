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
ms.openlocfilehash: 5e910da744bf88b485fc693c02544ad8a7093ead
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a><span data-ttu-id="457bc-102">Administration système dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="457bc-102">System administration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="457bc-103">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="457bc-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="457bc-104">L’administration du système comprend les tâches d’administration quotidiennes, planifiées et à la demande, qui sont requises pour maintenir un système informatique sans problème.</span><span class="sxs-lookup"><span data-stu-id="457bc-104">System administration includes the day-to-day administrative tasks, both planned and on-demand, that are required to keep an IT system operating smoothly.</span></span> <span data-ttu-id="457bc-105">En règle générale, les tâches d’administration du système sont traitées par des procédures écrites.</span><span class="sxs-lookup"><span data-stu-id="457bc-105">Typically, system administration tasks are covered by written procedures.</span></span> <span data-ttu-id="457bc-106">Ces procédures permettent de s’assurer que les mêmes outils et méthodes standard sont utilisés par tous les employés du support technique.</span><span class="sxs-lookup"><span data-stu-id="457bc-106">These procedures help ensure that the same standard tools and methods are used by all support staff.</span></span>

<span data-ttu-id="457bc-107">Dans un environnement Lync, les tâches d’administration système classiques incluent la sauvegarde et l’archivage des pools, la surveillance des journaux, la création et la gestion des utilisateurs, ainsi que la mise à jour d’un logiciel antivirus.</span><span class="sxs-lookup"><span data-stu-id="457bc-107">In a Lync environment, typical system administration tasks include backing up and archiving pools, monitoring logs, creating and managing users, and updating antivirus software.</span></span>

<div>

## <a name="system-troubleshooting"></a><span data-ttu-id="457bc-108">Dépannage du système</span><span class="sxs-lookup"><span data-stu-id="457bc-108">System troubleshooting</span></span>

<span data-ttu-id="457bc-109">Une organisation doit être prête à traiter des problèmes inattendus et doit disposer d’une procédure pour gérer les problèmes à partir du point auquel ils sont signalés jusqu’à leur résolution.</span><span class="sxs-lookup"><span data-stu-id="457bc-109">An organization must be prepared to deal with unexpected issues and should have a procedure to manage issues from the point at which they are reported until their resolution.</span></span> <span data-ttu-id="457bc-110">Informations sur la façon dont le personnel de support a diagnostiqué un problème doit être enregistré et utilisé à l’avenir pour éviter un travail terminé inutilement répétitif.</span><span class="sxs-lookup"><span data-stu-id="457bc-110">Information about how support staff diagnosed an issue should be recorded and used in the future to avoid unnecessarily repeating completed work.</span></span>

</div>

<div>

## <a name="system-troubleshooting-process"></a><span data-ttu-id="457bc-111">Processus de résolution des problèmes système</span><span class="sxs-lookup"><span data-stu-id="457bc-111">System troubleshooting process</span></span>

<span data-ttu-id="457bc-112">Le diagramme suivant illustre le processus de résolution des problèmes et les interactions avec les autres rôles d’opération.</span><span class="sxs-lookup"><span data-stu-id="457bc-112">The following diagram shows the system troubleshooting process and the interactions with other operations roles.</span></span>

<span data-ttu-id="457bc-113">**Organigramme de résolution des problèmes système**</span><span class="sxs-lookup"><span data-stu-id="457bc-113">**System troubleshooting flowchart**</span></span>

<span data-ttu-id="457bc-114">![Organigramme de résolution des problèmes système](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Organigramme de résolution des problèmes système")</span><span class="sxs-lookup"><span data-stu-id="457bc-114">![System Troubleshooting Flowchart](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "System Troubleshooting Flowchart")</span></span>

  - <span data-ttu-id="457bc-115">**Classer et**   classer par ordre de priorité cette tâche est généralement effectuée par le service d’assistance.</span><span class="sxs-lookup"><span data-stu-id="457bc-115">**Classify and Prioritize**   This task is typically performed by the service desk.</span></span> <span data-ttu-id="457bc-116">Par exemple, un problème peut être regroupé sous la forme d’un problème logiciel ou d’un problème matériel.</span><span class="sxs-lookup"><span data-stu-id="457bc-116">For example, an issue may be grouped as a software issue or a hardware issue.</span></span> <span data-ttu-id="457bc-117">Le problème est ensuite acheminé vers l’équipe de support appropriée pour l’enquête.</span><span class="sxs-lookup"><span data-stu-id="457bc-117">The issue is then routed to the appropriate support team for investigation.</span></span> <span data-ttu-id="457bc-118">Les règles permettant de déterminer la priorité d’un problème, ainsi que le temps de réponse et le temps à résoudre, sont généralement définies dans le contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="457bc-118">The rules for determining the priority of an issue, together with the time to respond and time to resolve, are typically defined in the SLA.</span></span>

  - <span data-ttu-id="457bc-119">**Examinez et diagnostiquez**   l’équipe de support technique appropriée pour diagnostiquer le problème et propose des modifications pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="457bc-119">**Investigate and Diagnose**   The appropriate support team diagnoses the issue and proposes changes to resolve the issue.</span></span> <span data-ttu-id="457bc-120">Si la solution est simple et ne nécessite pas de contrôle des modifications, la solution peut être appliquée immédiatement.</span><span class="sxs-lookup"><span data-stu-id="457bc-120">If the solution is simple and does not require change control, the solution can be applied immediately.</span></span> <span data-ttu-id="457bc-121">Si la solution n’est pas facile, une demande de modification doit être générée et le travail proposé doit être géré par le processus de gestion des modifications, souvent sous la forme d’une procédure « Fast-Track ».</span><span class="sxs-lookup"><span data-stu-id="457bc-121">If the solution is not easy, a request for change should be raised and the proposed work should be managed by the change management process, frequently under a “fast-track” procedure.</span></span> <span data-ttu-id="457bc-122">Les modifications apportées doivent être enregistrées à l’aide du processus de gestion de la configuration.</span><span class="sxs-lookup"><span data-stu-id="457bc-122">Any changes that are made should be recorded using the configuration management process.</span></span>

  - <span data-ttu-id="457bc-123">**Fermer et enregistrer**   après avoir testé la résolution, le problème doit être fermé.</span><span class="sxs-lookup"><span data-stu-id="457bc-123">**Close and Record**   After testing the resolution, the issue should be closed.</span></span> <span data-ttu-id="457bc-124">S’il existe des leçons à apprendre à partir du problème, une entrée doit être créée dans la base de connaissances.</span><span class="sxs-lookup"><span data-stu-id="457bc-124">If there are lessons to be learned from the issue, an entry should be created in the knowledge base.</span></span>

  - <span data-ttu-id="457bc-125">**Examen et analyse**   des tendances les révisions périodiques des problèmes récents doivent être effectuées pour identifier les tendances des problèmes.</span><span class="sxs-lookup"><span data-stu-id="457bc-125">**Review and Trend Analysis**   Periodic reviews of recent issues should be performed to identify issue trends.</span></span> <span data-ttu-id="457bc-126">Par exemple, si les utilisateurs rencontrent des problèmes fréquents avec des connexions lentes sur leurs sites Lync, les problèmes de bande passante réseau peuvent être à l’origine du problème.</span><span class="sxs-lookup"><span data-stu-id="457bc-126">For example, if the users are experiencing frequent issues with slow logons to their Lync sites, network bandwidth issues may be the cause.</span></span> <span data-ttu-id="457bc-127">Les temps de résolution des problèmes et l’effet de toutes les pannes de disponibilité du système doivent être examinés et comparés avec le contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="457bc-127">Issue resolution times and the effect of any outages on system availability should be reviewed and compared with the SLA.</span></span> <span data-ttu-id="457bc-128">La personne qui assure la communication avec le client sur les problèmes de service, comme un responsable de compte, doit être informée des problèmes importants.</span><span class="sxs-lookup"><span data-stu-id="457bc-128">The person who liaises with the customer on service issues, such as an account manager, should be informed of any significant issues.</span></span>

</div>

<div>

## <a name="issue-management-tools"></a><span data-ttu-id="457bc-129">Outils de gestion des problèmes</span><span class="sxs-lookup"><span data-stu-id="457bc-129">Issue management tools</span></span>

<span data-ttu-id="457bc-130">Les outils du service d’assistance permettent aux employés d’enregistrer, de classer et de classer par priorité les nouveaux problèmes.</span><span class="sxs-lookup"><span data-stu-id="457bc-130">Service desk tools enable staff to record, classify, and prioritize new issues.</span></span> <span data-ttu-id="457bc-131">Les outils fournissent ensuite les processus de flux de travail pour gérer la demande de service de problème par le biais d’une enquête et d’un diagnostic, souvent par plusieurs équipes de support technique.</span><span class="sxs-lookup"><span data-stu-id="457bc-131">Tools will then provide the workflow processes to manage the issue service request through investigation and diagnosis, often by more than one support team.</span></span> <span data-ttu-id="457bc-132">Les outils, qui fournissent fréquemment des rapports sur les temps de résolution et les tendances historiques, peuvent également inclure une base de données de la base de connaissances, qui peut être utilisée pour effectuer des recherches dans les problèmes précédents.</span><span class="sxs-lookup"><span data-stu-id="457bc-132">Tools, which will frequently provide reports about resolution times and historical trends, may also include a knowledge base database, which can be used to search through past issues.</span></span>

<span data-ttu-id="457bc-133">La base de connaissances Microsoft est un enregistrement utile des problèmes de support rencontrés par Microsoft.</span><span class="sxs-lookup"><span data-stu-id="457bc-133">The Microsoft Knowledge Base is a useful record of support issues that were encountered by Microsoft.</span></span> <span data-ttu-id="457bc-134">Pour plus d’informations, consultez le site Web du<https://go.microsoft.com/fwlink/?linkid=14898>support Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="457bc-134">For more information, see the Microsoft Support website (<https://go.microsoft.com/fwlink/?linkid=14898>).</span></span>

<span data-ttu-id="457bc-135">Les logiciels tiers nécessitent généralement une personnalisation pour répondre aux besoins de l’organisation, tels que l’Organisation des équipes, les exigences en matière de création de rapports et les mesures requises par le contrat SLA.</span><span class="sxs-lookup"><span data-stu-id="457bc-135">Third-party software typically requires customization to suit the organization’s needs, such as the organization of teams, reporting requirements, and measures required by the SLA.</span></span>

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a><span data-ttu-id="457bc-136">Administration centralisée et administration décentralisée</span><span class="sxs-lookup"><span data-stu-id="457bc-136">Centralized vs. decentralized administration</span></span>

<span data-ttu-id="457bc-137">Les rôles et les responsabilités liés à l’exécution de tâches d’administration système varient selon que l’organisation suit ou non un modèle centralisé, un modèle décentralisé ou une combinaison des deux.</span><span class="sxs-lookup"><span data-stu-id="457bc-137">Roles and responsibilities for performing system administration tasks depend on whether the organization follows a centralized model, a decentralized model, or a combination of both.</span></span>

  - <span data-ttu-id="457bc-138">**Modèle centralisé dans**   un modèle centralisé, un ou plusieurs groupes d’administration conservent un contrôle total de l’ensemble de l’environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="457bc-138">**Centralized Model**   In a centralized model, one or several administrative groups maintain complete control of the whole Lync Server environment.</span></span> <span data-ttu-id="457bc-139">Ce modèle d’administration ressemble à un centre de données où toutes les tâches d’administration sont réalisées par un groupe informatique unique.</span><span class="sxs-lookup"><span data-stu-id="457bc-139">This administrative model resembles a data center where all administration tasks are performed by a single information technology group.</span></span> <span data-ttu-id="457bc-140">Les rôles et les responsabilités au sein de l’équipe doivent être définis en fonction de l’expérience et de l’expertise.</span><span class="sxs-lookup"><span data-stu-id="457bc-140">Roles and responsibilities within the team should be defined according to experience and expertise.</span></span>

  - <span data-ttu-id="457bc-141">**Modèle**   décentralisé les organisations décentralisées se trouvent dans plusieurs emplacements géographiques et ont des serveurs Lync Server et des équipes d’administrateurs à des emplacements différents.</span><span class="sxs-lookup"><span data-stu-id="457bc-141">**Decentralized Model**   Decentralized organizations are located in several geographic locations and have functioning Lync Server servers and teams of administrators in different locations.</span></span> <span data-ttu-id="457bc-142">Par exemple, il peut y avoir un personnel d’administration local et un ou plusieurs serveurs exécutant Lync Server 2013 pour chaque pays/région.</span><span class="sxs-lookup"><span data-stu-id="457bc-142">For example, there may be local administration staff and one or more servers that are running Lync Server 2013 for each country/region.</span></span> <span data-ttu-id="457bc-143">Ou, il peut y avoir un pool de serveurs qui exécutent Lync Server 2013 et une équipe administrative pour l’Amérique du Nord et une autre pour l’Europe.</span><span class="sxs-lookup"><span data-stu-id="457bc-143">Or, there may be a pool of servers that are running Lync Server 2013 and an administrative team for North America and one for Europe.</span></span> <span data-ttu-id="457bc-144">Parfois, vous pouvez souhaiter que les administrateurs soient uniquement responsables de leur propre zone géographique et restreignent les autorisations pour administrer les ressources dans d’autres domaines.</span><span class="sxs-lookup"><span data-stu-id="457bc-144">Sometimes, you may want administrators to be responsible only for their own geographical area and restrict permissions to administer resources in other areas.</span></span>

<span data-ttu-id="457bc-145">Lync Server vous permet également de déléguer des tâches d’administration spécifiques à des personnes ou des groupes spécifiques à l’aide du contrôle d’accès basé sur un rôle (RBAC).</span><span class="sxs-lookup"><span data-stu-id="457bc-145">Lync Server also allows you to delegate specific administrative tasks to specific people or groups by using role-based access control (RBAC).</span></span> <span data-ttu-id="457bc-146">RBAC permet aux administrateurs de déléguer des droits et des autorisations d’utilisateur spécifiques à d’autres administrateurs afin d’effectuer un sous-ensemble des tâches administratives possibles.</span><span class="sxs-lookup"><span data-stu-id="457bc-146">RBAC allows administrators to delegate specific user rights and permissions to other administrators to perform a subset of the administrative tasks possible.</span></span> <span data-ttu-id="457bc-147">À l’aide de RBAC, la capacité de l’utilisateur à effectuer des tâches d’administration spécifiques dépend des rôles RBAC attribués à l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="457bc-147">By using RBAC, the user’s ability to perform specific administrative tasks depends on the RBAC roles that are assigned to the user.</span></span> <span data-ttu-id="457bc-148">RBAC fournit une liste des cmdlets que l’utilisateur peut exécuter en fonction des rôles RBAC dont l’utilisateur est membre.</span><span class="sxs-lookup"><span data-stu-id="457bc-148">RBAC provides a list of cmdlets that the user can run based on the RBAC roles that the user is a member of.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

