---
title: 'Lync Server 2013 : vue d’ensemble de l’application Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3bb7b9260e85326718bf388da977833c6e87ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="00e35-102">Vue d’ensemble de l’application Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00e35-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00e35-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="00e35-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="00e35-104">Lorsqu’un appelant appelle un groupe de réponses, l’appel est acheminé vers un agent basé sur un groupement de postes ou vers les réponses vocales interactives (IVR) aux questions de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="00e35-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="00e35-105">L’application Response Group utilise des méthodes de routage Response Group standard pour acheminer l’appel vers le prochain agent disponible.</span><span class="sxs-lookup"><span data-stu-id="00e35-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="00e35-106">Parmi les méthodes de routage d’appel figurent notamment le routage de série, parallèle, le plus longuement inactif, tourniquet (round robin) et le nouveau routage Attendant dans lequel tous les agents sont appelés en même temps pour tous les appels entrants, quelle que soit leur présence actuelle.</span><span class="sxs-lookup"><span data-stu-id="00e35-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="00e35-107">Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère.</span><span class="sxs-lookup"><span data-stu-id="00e35-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="00e35-108">Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel.</span><span class="sxs-lookup"><span data-stu-id="00e35-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="00e35-109">Si la file d’attente est pleine, ou si l’appel arrive à expiration dans la file d’attente, l’appelant entendra probablement un message, puis sera déconnecté ou transféré vers une autre destination.</span><span class="sxs-lookup"><span data-stu-id="00e35-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="00e35-110">Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="00e35-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="00e35-111">Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.</span><span class="sxs-lookup"><span data-stu-id="00e35-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="00e35-112">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="00e35-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="00e35-113">Si un agent est déplacé de local vers en ligne, les appels Response Group ne sont pas acheminés vers cet agent.</span><span class="sxs-lookup"><span data-stu-id="00e35-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="00e35-114">L’application Response Group utilise un service interne, appelé faire correspondre les appels, pour mettre en file d’attente des appels et trouver des agents disponibles.</span><span class="sxs-lookup"><span data-stu-id="00e35-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="00e35-115">Chaque ordinateur qui exécute l’application Response Group exécute le service de mise en correspondance, mais un seul service correspondant est actif par pool Lync Server, les autres étant passifs.</span><span class="sxs-lookup"><span data-stu-id="00e35-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="00e35-116">En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif.</span><span class="sxs-lookup"><span data-stu-id="00e35-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="00e35-117">L’application Response Group fait de son mieux pour s’assurer que le routage des appels et la mise en file d’attente se poursuivent sans interruption.</span><span class="sxs-lookup"><span data-stu-id="00e35-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="00e35-118">Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus.</span><span class="sxs-lookup"><span data-stu-id="00e35-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="00e35-119">Par exemple, si la transition est due au fait que le serveur frontal descend, les appels actuellement traités par le service de correspondance active sur ce serveur frontal sont également perdus.</span><span class="sxs-lookup"><span data-stu-id="00e35-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="00e35-120">Dans Lync Server 2013, deux rôles de gestion sont disponibles pour la gestion des groupes Response Group : Response Group Manager et l’administrateur Response Group.</span><span class="sxs-lookup"><span data-stu-id="00e35-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="00e35-121">Les administrateurs de Response Group peuvent gérer tous les aspects de n’importe quel groupe Response Group.</span><span class="sxs-lookup"><span data-stu-id="00e35-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="00e35-122">Les gestionnaires Response Group ne peuvent gérer que certains aspects, et uniquement pour les groupes Response Group qu’ils possèdent.</span><span class="sxs-lookup"><span data-stu-id="00e35-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="00e35-123">Le nouveau rôle de gestionnaire peut aider à réduire les coûts d’administration, car vous pouvez déléguer des responsabilités limitées pour des groupes Response Group spécifiques à tout utilisateur activé pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="00e35-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="00e35-124">Pour prendre en charge le nouveau rôle de gestionnaire, l’application Response Group Lync Server 2013 introduit un **type de flux de travail** géré ou non géré.</span><span class="sxs-lookup"><span data-stu-id="00e35-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="00e35-125">Le tableau suivant décrit les groupes Response Group gérés et non gérés.</span><span class="sxs-lookup"><span data-stu-id="00e35-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="00e35-126">Groupes Response Group gérés et non gérés</span><span class="sxs-lookup"><span data-stu-id="00e35-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00e35-127">Type de groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="00e35-127">Response group type</span></span></th>
<th><span data-ttu-id="00e35-128">Description</span><span class="sxs-lookup"><span data-stu-id="00e35-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="00e35-129">Non gérés</span><span class="sxs-lookup"><span data-stu-id="00e35-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="00e35-130">Aucun gestionnaire n’est affecté aux groupes Response Group non gérés.</span><span class="sxs-lookup"><span data-stu-id="00e35-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="00e35-131">Seul l’administrateur de groupe de réponse peut configurer ces groupes Response Group.</span><span class="sxs-lookup"><span data-stu-id="00e35-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="00e35-132">Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="00e35-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="00e35-133">Lorsque vous migrez des groupes Response Group d’une version antérieure vers Lync Server 2013, le type est défini sur non géré.</span><span class="sxs-lookup"><span data-stu-id="00e35-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="00e35-134">Géré</span><span class="sxs-lookup"><span data-stu-id="00e35-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="00e35-135">Les administrateurs de Response Group peuvent configurer tous les aspects des groupes Response Group gérés.</span><span class="sxs-lookup"><span data-stu-id="00e35-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="00e35-136">Les gestionnaires Response Group ne peuvent pas afficher ou modifier les groupes Response Group qui ne leur sont pas explicitement affectés.</span><span class="sxs-lookup"><span data-stu-id="00e35-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="00e35-137">Les responsables de groupes Response Group peuvent configurer uniquement certains paramètres des groupes Response Group qui leur sont explicitement affectés.</span><span class="sxs-lookup"><span data-stu-id="00e35-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="00e35-138">Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés.</span><span class="sxs-lookup"><span data-stu-id="00e35-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00e35-139">Le tableau suivant décrit les actions que les gestionnaires de groupe de réponse peuvent et ne peuvent pas effectuer pour les groupes Response Group qui leur sont attribués.</span><span class="sxs-lookup"><span data-stu-id="00e35-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="00e35-140">Fonctions du gestionnaire Response Group</span><span class="sxs-lookup"><span data-stu-id="00e35-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="00e35-141">Peut configurer :</span><span class="sxs-lookup"><span data-stu-id="00e35-141">Can configure:</span></span></th>
<th><span data-ttu-id="00e35-142">Peut créer, supprimer ou configurer :</span><span class="sxs-lookup"><span data-stu-id="00e35-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="00e35-143">Pouvant</span><span class="sxs-lookup"><span data-stu-id="00e35-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="00e35-144">Représentants</span><span class="sxs-lookup"><span data-stu-id="00e35-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="00e35-145">Message d’accueil</span><span class="sxs-lookup"><span data-stu-id="00e35-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="00e35-146">Nom du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="00e35-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="00e35-147">Description</span><span class="sxs-lookup"><span data-stu-id="00e35-147">Description</span></span></p></li>
<li><p><span data-ttu-id="00e35-148">Numéro affiché</span><span class="sxs-lookup"><span data-stu-id="00e35-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="00e35-149">Heures d’ouverture</span><span class="sxs-lookup"><span data-stu-id="00e35-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="00e35-150">Attente musicale</span><span class="sxs-lookup"><span data-stu-id="00e35-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="00e35-151">Statut (actif/inactif)</span><span class="sxs-lookup"><span data-stu-id="00e35-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="00e35-152">Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR)</span><span class="sxs-lookup"><span data-stu-id="00e35-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="00e35-153">Groupes d’agents</span><span class="sxs-lookup"><span data-stu-id="00e35-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="00e35-154">Files d’attente</span><span class="sxs-lookup"><span data-stu-id="00e35-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="00e35-155">Périodes de congé</span><span class="sxs-lookup"><span data-stu-id="00e35-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="00e35-156">Créer ou supprimer un type de flux de travail</span><span class="sxs-lookup"><span data-stu-id="00e35-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="00e35-157">Modifier les paramètres principaux des groupes Response Group, tels que : <strong>URI SIP</strong>, <strong>Numéro de téléphone</strong> ou <strong>Type de flux de travail</strong></span><span class="sxs-lookup"><span data-stu-id="00e35-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="00e35-158">Les responsables des groupes Response Group peuvent utiliser les outils suivants pour gérer leurs groupes Response Group désignés.</span><span class="sxs-lookup"><span data-stu-id="00e35-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="00e35-159">Panneau de commande Lync Server</span><span class="sxs-lookup"><span data-stu-id="00e35-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="00e35-160">Les gestionnaires Response Group peuvent gérer uniquement les paramètres Response Group à l’aide de cet outil.</span><span class="sxs-lookup"><span data-stu-id="00e35-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="00e35-161">Les autres paramètres de Lync Server ne sont pas disponibles pour les responsables.</span><span class="sxs-lookup"><span data-stu-id="00e35-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="00e35-162">outil de configuration Response Group</span><span class="sxs-lookup"><span data-stu-id="00e35-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="00e35-163">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="00e35-163">Lync Server Management Shell</span></span>

<span data-ttu-id="00e35-164">Response Group est adapté aux environnements de service ou de groupe de travail (pour plus d’informations, consultez la rubrique [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) et peut être déployé dans des installations de téléphonie entièrement nouvelles.</span><span class="sxs-lookup"><span data-stu-id="00e35-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="00e35-165">Il prend en charge les appels entrants du déploiement voix entreprise et du réseau de l’opérateur local.</span><span class="sxs-lookup"><span data-stu-id="00e35-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="00e35-166">Les agents peuvent utiliser Lync 2013, Lync 2010, Lync 2010 attendant ou Lync Phone Edition pour prendre les appels qui leur sont routés.</span><span class="sxs-lookup"><span data-stu-id="00e35-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="00e35-167">L’application Response Group est un composant de voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="00e35-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="00e35-168">Lorsque vous déployez voix entreprise, l’application Response Group est installée et activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="00e35-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

