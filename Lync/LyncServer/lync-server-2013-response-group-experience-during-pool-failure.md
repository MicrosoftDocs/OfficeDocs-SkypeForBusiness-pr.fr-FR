---
title: Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="5712d-102">Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5712d-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5712d-103">_**Dernière modification de la rubrique:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="5712d-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="5712d-104">Cette section décrit en détail la façon dont l’activité du groupe de réponses est affectée aux étapes suivantes:</span><span class="sxs-lookup"><span data-stu-id="5712d-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="5712d-105">Une panne se produit dans le pool principal, mais le basculement n’est pas encore lancé.</span><span class="sxs-lookup"><span data-stu-id="5712d-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="5712d-106">Le service est en échec sur le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5712d-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="5712d-107">Le service n’a pas pu revenir au pool principal.</span><span class="sxs-lookup"><span data-stu-id="5712d-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="5712d-108">Utilisation de l’interface utilisateur en cas d’interruption</span><span class="sxs-lookup"><span data-stu-id="5712d-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="5712d-109">En cas d’interruption d’une réserve ou d’un site, mais que l’administrateur n’a pas encore lancé le basculement, l’activité du groupe de réponses est gérée comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5712d-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5712d-110">Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="5712d-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="5712d-111">Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="5712d-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="5712d-112">Une panne survient</span><span class="sxs-lookup"><span data-stu-id="5712d-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5712d-113">Type d’appel ou d’action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5712d-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="5712d-114">Pendant la période d’interruption</span><span class="sxs-lookup"><span data-stu-id="5712d-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5712d-115">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="5712d-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-116">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-117">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-118">Appels en cours non encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="5712d-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="5712d-119">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5712d-120">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="5712d-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-121">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-122">Si les groupes de réponse étaient importés, les appels se connectent à un pool de sauvegarde, mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="5712d-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-123">Appels d’agent de la part de Response Group</span><span class="sxs-lookup"><span data-stu-id="5712d-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="5712d-124">Cette fonctionnalité est désactivée pendant cette étape.</span><span class="sxs-lookup"><span data-stu-id="5712d-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5712d-125">Informations de connexion et d’agent</span><span class="sxs-lookup"><span data-stu-id="5712d-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-126">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-127">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-128">Les groupes d’agent importés ne sont pas affichés dans la console de l’agent.</span><span class="sxs-lookup"><span data-stu-id="5712d-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-129">Configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="5712d-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-130">Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</span><span class="sxs-lookup"><span data-stu-id="5712d-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-131">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-132">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5712d-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="5712d-133">Utilisation de l’interface utilisateur pendant le basculement</span><span class="sxs-lookup"><span data-stu-id="5712d-133">User Experience During Failover</span></span>

<span data-ttu-id="5712d-134">Lorsqu’un administrateur appelle le basculement vers un pool de sauvegarde, l’activité du groupe de réponses est gérée durant et après le basculement, comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5712d-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="5712d-135">La première colonne décrit le type d’activité qui peut avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="5712d-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="5712d-136">La colonne du milieu décrit la façon dont chaque activité est gérée au cours de la période de reprise du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5712d-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="5712d-137">La dernière colonne décrit le mode de gestion de l’activité pour la durée, une fois le processus de basculement terminé et le pool de sauvegarde en cours pour le pool principal.</span><span class="sxs-lookup"><span data-stu-id="5712d-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5712d-138">Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="5712d-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="5712d-139">Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="5712d-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="5712d-140">Le basculement est lancé</span><span class="sxs-lookup"><span data-stu-id="5712d-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5712d-141">Type d’appel ou d’action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5712d-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="5712d-142">Lors du basculement</span><span class="sxs-lookup"><span data-stu-id="5712d-142">During Failover</span></span></th>
<th><span data-ttu-id="5712d-143">Après le basculement</span><span class="sxs-lookup"><span data-stu-id="5712d-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5712d-144">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="5712d-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-145">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-146">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-147">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-148">Pour les groupes de réponse importés, les appels anonymes ayant atteint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-149">Appels en cours non encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="5712d-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="5712d-150">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-151">Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</span><span class="sxs-lookup"><span data-stu-id="5712d-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="5712d-152">Pour les groupes de réponse importés, les appels ayant atteint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5712d-153">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="5712d-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-154">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-155">S’il s’agit de groupes de réponse importés, les appels se connectent au pool de sauvegarde, mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="5712d-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-156">Si les Response Groups n’ont pas été importés, les appels sont interrompus.</span><span class="sxs-lookup"><span data-stu-id="5712d-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-157">Pour les groupes de réponse importés, les appels se connectent au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="5712d-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-158">Appels d’agent de la part de Response Group</span><span class="sxs-lookup"><span data-stu-id="5712d-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="5712d-159">Cette fonctionnalité est désactivée pendant cette étape</span><span class="sxs-lookup"><span data-stu-id="5712d-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-160">Si les Response Groups n’ont pas été importés, les appels échouent.</span><span class="sxs-lookup"><span data-stu-id="5712d-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="5712d-161">Pour les groupes de réponse importés, les appels aboutissent.</span><span class="sxs-lookup"><span data-stu-id="5712d-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5712d-162">Informations de connexion et d’agent</span><span class="sxs-lookup"><span data-stu-id="5712d-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-163">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-164">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-165">Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-166">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-167">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-168">Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-169">Configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="5712d-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-170">Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</span><span class="sxs-lookup"><span data-stu-id="5712d-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-171">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-172">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5712d-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-173">En fonction de la disponibilité de la base de données principale, vous pouvez afficher les groupes de réponses détenus par le pool principal, mais ils ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-174">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-175">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5712d-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="5712d-176">Utilisation des utilisateurs lors du retour arrière</span><span class="sxs-lookup"><span data-stu-id="5712d-176">User Experience During Failback</span></span>

<span data-ttu-id="5712d-177">Lorsqu’un administrateur appelle la restauration automatique vers le pool principal, l’activité de groupe de réponses est gérée pendant et après le retour automatique comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="5712d-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5712d-178">Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="5712d-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="5712d-179">Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="5712d-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="5712d-180">Gestion des appels en retour automatique</span><span class="sxs-lookup"><span data-stu-id="5712d-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5712d-181">Type d’appel ou d’action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="5712d-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="5712d-182">Pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="5712d-182">During Failback</span></span></th>
<th><span data-ttu-id="5712d-183">Après la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="5712d-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5712d-184">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="5712d-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-185">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-186">Si les Response Groups n’ont pas été importés, il n’y a pas de statut anonyme.</span><span class="sxs-lookup"><span data-stu-id="5712d-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="5712d-187">Pour les groupes de réponse importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-188">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="5712d-189">Si les Response Groups n’ont pas été importés, il n’y a pas de statut anonyme.</span><span class="sxs-lookup"><span data-stu-id="5712d-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="5712d-190">Pour les groupes de réponse importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-191">Appels en cours non encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="5712d-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-192">Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</span><span class="sxs-lookup"><span data-stu-id="5712d-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="5712d-193">Pour les groupes de réponse importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-194">Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</span><span class="sxs-lookup"><span data-stu-id="5712d-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="5712d-195">Pour les groupes de réponse importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="5712d-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5712d-196">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="5712d-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="5712d-197">Les appels se connectent au pool principal, mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="5712d-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="5712d-198">Les appels se connectent à la liste principale.</span><span class="sxs-lookup"><span data-stu-id="5712d-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-199">Appels d’agent de la part de Response Group</span><span class="sxs-lookup"><span data-stu-id="5712d-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="5712d-200">Cette fonctionnalité est désactivée pendant cette étape.</span><span class="sxs-lookup"><span data-stu-id="5712d-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="5712d-201">Appels réussis.</span><span class="sxs-lookup"><span data-stu-id="5712d-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5712d-202">Informations de connexion et d’agent</span><span class="sxs-lookup"><span data-stu-id="5712d-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-203">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-204">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-205">Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-206">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-207">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="5712d-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="5712d-208">Les groupes d’agent importés ne sont pas affichés dans la console de l’agent.</span><span class="sxs-lookup"><span data-stu-id="5712d-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5712d-209">Configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="5712d-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="5712d-210">Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</span><span class="sxs-lookup"><span data-stu-id="5712d-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-211">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-212">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5712d-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="5712d-213">Les groupes de réponse appartenant au pool principal peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-214">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="5712d-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="5712d-215">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5712d-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

