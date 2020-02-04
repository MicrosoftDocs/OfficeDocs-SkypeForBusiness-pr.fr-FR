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
ms.openlocfilehash: 2b01181296a42f786a4739b5ec59d775212baaf5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a><span data-ttu-id="d7f6f-102">Vue d’ensemble de l’application Response Group dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d7f6f-102">Overview of the Response Group application in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7f6f-103">_**Dernière modification de la rubrique :** 2012-09-11_</span><span class="sxs-lookup"><span data-stu-id="d7f6f-103">_**Topic Last Modified:** 2012-09-11_</span></span>

<span data-ttu-id="d7f6f-104">Quand un appelant appelle un Response Group, l’appel est acheminé vers un agent en fonction du groupe de recherche ou des réponses de l’appelant aux questions du système de réponse vocale interactive.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-104">When a caller calls a response group, the call is routed to an agent based on a hunt group or the caller's answers to interactive voice response (IVR) questions.</span></span> <span data-ttu-id="d7f6f-105">L’application Response Group utilise des méthodes de routage de groupe de réponse standard pour acheminer l’appel vers le prochain agent disponible.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-105">The Response Group application uses standard response group routing methods to route the call to the next available agent.</span></span> <span data-ttu-id="d7f6f-106">Les méthodes de routage des appels incluent le routage de série, de longue durée, parallèle, de tourniquet cyclique et le routage de l’attendant (c’est-à-dire que tous les agents sont appelés en même temps pour chaque appel entrant, quelle que soit leur présence actuelle).</span><span class="sxs-lookup"><span data-stu-id="d7f6f-106">Call routing methods include serial, longest-idle, parallel, round robin, and Attendant routing (that is, all agents are called at the same time for every incoming call, regardless of their current presence).</span></span> <span data-ttu-id="d7f6f-107">Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-107">If no agents are available, the call is held in a queue until an agent is available.</span></span> <span data-ttu-id="d7f6f-108">Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-108">While in the queue, the caller hears music until an available agent accepts the call.</span></span> <span data-ttu-id="d7f6f-109">S’il s’agit d’une file d’attente complète ou si l’appel est interrompu dans la file d’attente, l’appelant peut entendre un message, puis être déconnecté ou transféré vers une autre destination.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-109">If the queue is full, or if the call times out while in the queue, the caller might hear a message and then is either disconnected or transferred to a different destination.</span></span> <span data-ttu-id="d7f6f-110">Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-110">When an agent accepts the call, the caller might or might not be able to see the agent's identity, depending on how the administrator configures the response group.</span></span> <span data-ttu-id="d7f6f-111">Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-111">Agents can either be formal, which means that they must sign in to the group before they can accept calls routed to the group, or informal, which means that they do not sign into and out of the group to accept calls.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d7f6f-112">Seuls les utilisateurs locaux peuvent être des agents.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-112">Only on-premises users can be agents.</span></span> <span data-ttu-id="d7f6f-113">Si un agent est déplacé de local vers en ligne, les appels de groupe de réponse ne seront pas routés vers cet agent.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-113">If an agent is moved from on-premises to online, Response Group calls will not be routed to that agent.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d7f6f-114">L’application Response Group utilise un service interne appelé faire correspondre pour mettre en file d’attente les appels et rechercher les agents disponibles.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-114">The Response Group application uses an internal service, called Match Making, to queue calls and find available agents.</span></span> <span data-ttu-id="d7f6f-115">Chaque ordinateur exécutant l’application Response Group exécute le service Matching, mais une seule correspondance avec le service par le pool Lync Server est active à la fois, les autres sont passives.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-115">Each computer that runs the Response Group application runs the Match Making service, but only one Match Making service per Lync Server pool is active at a time--the others are passive.</span></span> <span data-ttu-id="d7f6f-116">En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-116">If the active Match Making service becomes unavailable during an unplanned outage, one of the passive Match Making services becomes active.</span></span> <span data-ttu-id="d7f6f-117">L’application de groupe de réponse utilise le mieux pour s’assurer que le routage d’appel et la mise en file d’attente continuent de fonctionner sans interruption.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-117">The Response Group application does its best to make sure that call routing and queuing continues uninterrupted.</span></span> <span data-ttu-id="d7f6f-118">Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-118">However, when a Match Making service transition occurs, any calls that are in transfer at the time are lost.</span></span> <span data-ttu-id="d7f6f-119">Par exemple, si la transition est en raison du fait que le serveur frontal s’arrête, tout appel actuellement géré par le service de correspondance active sur le serveur principal est également perdu.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-119">For example, if the transition is due to the Front End Server going down, any calls currently being handled by the active Match Making service on that Front End Server are also lost.</span></span>



</div>

<span data-ttu-id="d7f6f-120">Dans Lync Server 2013, deux rôles de gestion sont disponibles pour gérer les groupes de réponse : responsable du groupe de réponse et administrateur du groupe de réponse.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-120">In Lync Server 2013, two management roles are available for managing response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="d7f6f-121">Les administrateurs de groupe de réponse peuvent gérer tout aspect de n’importe quel Response Group.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-121">Response Group Administrators can manage any aspect of any response group.</span></span> <span data-ttu-id="d7f6f-122">Les responsables de groupe de réponse peuvent uniquement gérer certains aspects, et uniquement pour les groupes de réponse qu’ils possèdent.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-122">Response Group Managers can manage only certain aspects, and only for the response groups that they own.</span></span> <span data-ttu-id="d7f6f-123">Le nouveau rôle de responsable peut vous aider à réduire les coûts d’administration, car vous pouvez déléguer des responsabilités limitées pour des groupes de réponse spécifiques à n’importe quel utilisateur qui est activé pour voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-123">The new Manager role can help reduce administration costs, because you can delegate limited responsibilities for specific response groups to any user who is enabled for Enterprise Voice.</span></span>

<span data-ttu-id="d7f6f-124">Pour prendre en charge le rôle de nouveau directeur, l’application Response Group de Lync Server 2013 introduit un **type de flux de travail de type** géré ou non géré.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-124">To accommodate the new Manager role, Lync Server 2013 Response Group application introduces a **Workflow Type** of Managed or Unmanaged.</span></span> <span data-ttu-id="d7f6f-125">Le tableau ci-dessous décrit les groupes Response Group gérés et non gérés.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-125">The following table describes Managed and Unmanaged response groups.</span></span>

### <a name="managed-and-unmanaged-response-groups"></a><span data-ttu-id="d7f6f-126">Groupes Response Group gérés et non gérés</span><span class="sxs-lookup"><span data-stu-id="d7f6f-126">Managed and Unmanaged Response Groups</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7f6f-127">Type de groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="d7f6f-127">Response group type</span></span></th>
<th><span data-ttu-id="d7f6f-128">Description</span><span class="sxs-lookup"><span data-stu-id="d7f6f-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7f6f-129">Non géré</span><span class="sxs-lookup"><span data-stu-id="d7f6f-129">Unmanaged</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d7f6f-130">Aucun gestionnaire n’est affecté aux groupes Response Group non gérés.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-130">Unmanaged response groups have no assigned Managers.</span></span> <span data-ttu-id="d7f6f-131">Seul l’administrateur du groupe de réponse peut configurer ces groupes de réponse.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-131">Only the Response Group Administrator can configure these response groups.</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-132">Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-132">Multiple unmanaged response groups can share a queue or agent group.</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-133">Lorsque vous migrez des groupes de réponses d’une version antérieure vers Lync Server 2013, le type est défini sur non géré.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-133">When you migrate response groups from a prior version to Lync Server 2013, the type is set to Unmanaged.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7f6f-134">Géré</span><span class="sxs-lookup"><span data-stu-id="d7f6f-134">Managed</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="d7f6f-135">Les administrateurs de groupe de réponse peuvent configurer n’importe quel aspect de groupes de réponse gérés.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-135">Response Group Administrators can configure any aspect of managed response groups.</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-136">Les responsables de groupe de réponse ne peuvent pas afficher ou modifier des groupes de réponse qui ne sont pas explicitement attribués.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-136">Response Group Managers cannot view or modify response groups that are not explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-137">Les responsables de groupe de réponse peuvent configurer uniquement certains paramètres des groupes de réponse qui leur sont explicitement affectés.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-137">Response Group Managers can configure only some settings for the response groups that are explicitly assigned to them.</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-138">Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-138">Managed response groups can't share any queues or agent groups with any other response group, managed or unmanaged.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7f6f-139">Le tableau suivant décrit les actions que les responsables de groupe de réponse peuvent exécuter et ne peuvent pas effectuer pour les groupes de réponse qui leur sont attribués.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-139">The following table describes the actions that Response Group Managers can and cannot perform for the response groups assigned to them.</span></span>

### <a name="response-group-manager-capabilities"></a><span data-ttu-id="d7f6f-140">Fonctions du gestionnaire Response Group</span><span class="sxs-lookup"><span data-stu-id="d7f6f-140">Response Group Manager Capabilities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7f6f-141">Peut configurer :</span><span class="sxs-lookup"><span data-stu-id="d7f6f-141">Can configure:</span></span></th>
<th><span data-ttu-id="d7f6f-142">Peut créer, supprimer ou configurer :</span><span class="sxs-lookup"><span data-stu-id="d7f6f-142">Can create, delete, or configure:</span></span></th>
<th><span data-ttu-id="d7f6f-143">Ne peut pas :</span><span class="sxs-lookup"><span data-stu-id="d7f6f-143">Cannot:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><span data-ttu-id="d7f6f-144">Agents</span><span class="sxs-lookup"><span data-stu-id="d7f6f-144">Agents</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-145">Message d’accueil</span><span class="sxs-lookup"><span data-stu-id="d7f6f-145">Welcome message</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-146">Nom du groupe de réponse</span><span class="sxs-lookup"><span data-stu-id="d7f6f-146">Response Group name</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-147">Description</span><span class="sxs-lookup"><span data-stu-id="d7f6f-147">Description</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-148">Numéro affiché</span><span class="sxs-lookup"><span data-stu-id="d7f6f-148">Display number</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-149">Heures d’ouverture</span><span class="sxs-lookup"><span data-stu-id="d7f6f-149">Business hours</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-150">Attente musicale</span><span class="sxs-lookup"><span data-stu-id="d7f6f-150">Music on hold</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-151">Statut (actif/inactif)</span><span class="sxs-lookup"><span data-stu-id="d7f6f-151">Status (active/inactive)</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-152">Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR)</span><span class="sxs-lookup"><span data-stu-id="d7f6f-152">Hunt group workflows or Interactive voice response (IVR) workflows</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d7f6f-153">Groupes d’agents</span><span class="sxs-lookup"><span data-stu-id="d7f6f-153">Agent Groups</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-154">Files d’attente</span><span class="sxs-lookup"><span data-stu-id="d7f6f-154">Queues</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-155">Périodes de congé</span><span class="sxs-lookup"><span data-stu-id="d7f6f-155">Holiday sets</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="d7f6f-156">Créer ou supprimer un type de flux de travail</span><span class="sxs-lookup"><span data-stu-id="d7f6f-156">Create or delete any type of workflow</span></span></p></li>
<li><p><span data-ttu-id="d7f6f-157">Modifier les paramètres principaux des groupes Response Group, tels que : <strong>URI SIP</strong>, <strong>Numéro de téléphone</strong> ou <strong>Type de flux de travail</strong></span><span class="sxs-lookup"><span data-stu-id="d7f6f-157">Modify core response group settings, such as: <strong>SIP URI</strong>, <strong>Telephone Number</strong>, or <strong>Workflow Type</strong>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d7f6f-158">Les responsables de groupe de réponse peuvent utiliser les outils suivants pour gérer leurs groupes de réponse désignés.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-158">Response Group Managers can use the following tools to manage their designated response groups.</span></span>

  - <span data-ttu-id="d7f6f-159">Panneau de configuration Lync Server</span><span class="sxs-lookup"><span data-stu-id="d7f6f-159">Lync Server Control Panel</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d7f6f-160">Les responsables de groupe de réponse peuvent uniquement gérer les paramètres de groupe de réponse à l’aide de cet outil.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-160">Response Group Managers can only manage Response Group settings with this tool.</span></span> <span data-ttu-id="d7f6f-161">Les autres paramètres du serveur Lync ne sont pas disponibles aux responsables.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-161">Other Lync Server settings are not available to Managers.</span></span>

    
    </div>

  - <span data-ttu-id="d7f6f-162">outil de configuration Response Group</span><span class="sxs-lookup"><span data-stu-id="d7f6f-162">Response Group Configuration Tool</span></span>

  - <span data-ttu-id="d7f6f-163">Lync Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="d7f6f-163">Lync Server Management Shell</span></span>

<span data-ttu-id="d7f6f-164">Response Group s’adapte bien aux environnements de services ou de groupe de travail (pour plus de détails, voir [planification de la capacité pour Response Group dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) et peut être déployé dans les nouvelles installations de téléphonie.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-164">Response Group scales well to departmental or workgroup environments (for details, see [Capacity planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) and can be deployed in entirely new telephony installations.</span></span> <span data-ttu-id="d7f6f-165">Il prend en charge les appels entrants du déploiement voix entreprise et du réseau d’opérateur local.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-165">It supports incoming calls from the Enterprise Voice deployment and from the local carrier network.</span></span> <span data-ttu-id="d7f6f-166">Les agents peuvent utiliser Lync 2013, Lync 2010, Lync 2010 attendant ou Lync Phone Edition pour prendre les appels routés vers eux.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-166">Agents can use Lync 2013, Lync 2010, Lync 2010 Attendant, or Lync Phone Edition to take the calls routed to them.</span></span>

<span data-ttu-id="d7f6f-167">L’application Response Group est un composant d’Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-167">The Response Group application is a component of Enterprise Voice.</span></span> <span data-ttu-id="d7f6f-168">Lorsque vous déployez Enterprise Voice, l’application Response Group est installée et activée automatiquement.</span><span class="sxs-lookup"><span data-stu-id="d7f6f-168">When you deploy Enterprise Voice, the Response Group application is installed and activated automatically.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

