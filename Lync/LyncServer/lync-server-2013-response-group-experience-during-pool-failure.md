---
title: Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad00afac363642106019269e86111f61eaca504e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723604"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="c8fe0-102">Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c8fe0-102">Response group experience in Lync Server 2013 during pool failure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8fe0-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="c8fe0-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="c8fe0-104">Cette section décrit en détail la façon dont l’activité du groupe de réponses est affectée aux étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="c8fe0-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="c8fe0-105">Une panne se produit dans le pool principal, mais le basculement n’est pas encore lancé.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="c8fe0-106">Le service est en échec sur le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="c8fe0-107">Le service n’a pas pu revenir au pool principal.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="c8fe0-108">Utilisation de l’interface utilisateur en cas d’interruption</span><span class="sxs-lookup"><span data-stu-id="c8fe0-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="c8fe0-109">En cas d’interruption d’une réserve ou d’un site, mais que l’administrateur n’a pas encore lancé le basculement, l’activité du groupe de réponses est gérée comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8fe0-110">Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-110">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="c8fe0-111">Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-111">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="c8fe0-112">Une panne survient</span><span class="sxs-lookup"><span data-stu-id="c8fe0-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8fe0-113">Type d’appel ou d’action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c8fe0-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="c8fe0-114">Pendant la période d’interruption</span><span class="sxs-lookup"><span data-stu-id="c8fe0-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-115">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-116">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-117">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-118">Appels en cours non encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-119">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-120">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="c8fe0-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-121">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-122">Si les groupes de réponse étaient importés, les appels se connectent à un pool de sauvegarde, mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-123">Appels d’agent de la part de Response Group</span><span class="sxs-lookup"><span data-stu-id="c8fe0-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-124">Cette fonctionnalité est désactivée pendant cette étape.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-125">Informations de connexion et d’agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-126">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-127">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-128">Les groupes d’agent importés ne sont pas affichés dans la console de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-129">Configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="c8fe0-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-130">Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-131">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-132">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="c8fe0-133">Utilisation de l’interface utilisateur pendant le basculement</span><span class="sxs-lookup"><span data-stu-id="c8fe0-133">User Experience During Failover</span></span>

<span data-ttu-id="c8fe0-134">Lorsqu’un administrateur appelle le basculement vers un pool de sauvegarde, l’activité du groupe de réponses est gérée durant et après le basculement, comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-134">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table.</span></span> <span data-ttu-id="c8fe0-135">La première colonne décrit le type d’activité qui peut avoir lieu.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-135">The first column describes the type of activity that might be taking place.</span></span> <span data-ttu-id="c8fe0-136">La colonne du milieu décrit la façon dont chaque activité est gérée au cours de la période de reprise du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-136">The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool.</span></span> <span data-ttu-id="c8fe0-137">La dernière colonne décrit le mode de gestion de l’activité pour la durée, une fois le processus de basculement terminé et le pool de sauvegarde en cours pour le pool principal.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-137">The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8fe0-138">Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-138">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="c8fe0-139">Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-139">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="c8fe0-140">Le basculement est lancé</span><span class="sxs-lookup"><span data-stu-id="c8fe0-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8fe0-141">Type d’appel ou d’action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c8fe0-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="c8fe0-142">Lors du basculement</span><span class="sxs-lookup"><span data-stu-id="c8fe0-142">During Failover</span></span></th>
<th><span data-ttu-id="c8fe0-143">Après le basculement</span><span class="sxs-lookup"><span data-stu-id="c8fe0-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-144">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-145">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-146">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-147">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-148">Pour les groupes de réponse importés, les appels anonymes ayant atteint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-149">Appels en cours non encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-150">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-151">Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-152">Pour les groupes de réponse importés, les appels ayant atteint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-153">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="c8fe0-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-154">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-155">S’il s’agit de groupes de réponse importés, les appels se connectent au pool de sauvegarde, mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-156">Si les Response Groups n’ont pas été importés, les appels sont interrompus.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-157">Pour les groupes de réponse importés, les appels se connectent au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-158">Appels d’agent de la part de Response Group</span><span class="sxs-lookup"><span data-stu-id="c8fe0-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-159">Cette fonctionnalité est désactivée pendant cette étape</span><span class="sxs-lookup"><span data-stu-id="c8fe0-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-160">Si les Response Groups n’ont pas été importés, les appels échouent.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-161">Pour les groupes de réponse importés, les appels aboutissent.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-162">Informations de connexion et d’agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-163">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-164">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-165">Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-166">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-167">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-168">Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-169">Configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="c8fe0-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-170">Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-171">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-172">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-173">En fonction de la disponibilité de la base de données principale, vous pouvez afficher les groupes de réponses détenus par le pool principal, mais ils ne peuvent pas être modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-174">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-175">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="c8fe0-176">Utilisation des utilisateurs lors du retour arrière</span><span class="sxs-lookup"><span data-stu-id="c8fe0-176">User Experience During Failback</span></span>

<span data-ttu-id="c8fe0-177">Lorsqu’un administrateur appelle la restauration automatique vers le pool principal, l’activité de groupe de réponses est gérée pendant et après le retour automatique comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c8fe0-178">Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-178">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery.</span></span> <span data-ttu-id="c8fe0-179">Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-179">In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="c8fe0-180">Gestion des appels en retour automatique</span><span class="sxs-lookup"><span data-stu-id="c8fe0-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c8fe0-181">Type d’appel ou d’action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="c8fe0-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="c8fe0-182">Pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="c8fe0-182">During Failback</span></span></th>
<th><span data-ttu-id="c8fe0-183">Après la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="c8fe0-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-184">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-185">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-186">Si les Response Groups n’ont pas été importés, il n’y a pas de statut anonyme.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-187">Pour les groupes de réponse importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-188">Les appels ordinaires restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-189">Si les Response Groups n’ont pas été importés, il n’y a pas de statut anonyme.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-190">Pour les groupes de réponse importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-191">Appels en cours non encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-192">Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-193">Pour les groupes de réponse importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-194">Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-195">Pour les groupes de réponse importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-196">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="c8fe0-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-197">Les appels se connectent au pool principal, mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-198">Les appels se connectent à la liste principale.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-199">Appels d’agent de la part de Response Group</span><span class="sxs-lookup"><span data-stu-id="c8fe0-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-200">Cette fonctionnalité est désactivée pendant cette étape.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="c8fe0-201">Appels réussis.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c8fe0-202">Informations de connexion et d’agent</span><span class="sxs-lookup"><span data-stu-id="c8fe0-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-203">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-204">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-205">Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-206">Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-207">Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-208">Les groupes d’agent importés ne sont pas affichés dans la console de l’agent.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c8fe0-209">Configuration de Response Group</span><span class="sxs-lookup"><span data-stu-id="c8fe0-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-210">Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-211">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-212">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="c8fe0-213">Les groupes de réponse appartenant au pool principal peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-214">Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="c8fe0-215">Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="c8fe0-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

