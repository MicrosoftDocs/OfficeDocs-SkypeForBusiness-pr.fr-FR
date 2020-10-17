---
title: Expérience de groupe de réponse Lync Server 2013 en cas de défaillance du pool
description: Expérience de groupe de réponse Lync Server 2013 en cas de défaillance du pool.
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
ms.openlocfilehash: 7d8d5904bc6934d4c330202bafa66d6dd8a16ff5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564570"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="dbfca-103">Expérience Response Group dans Lync Server 2013 en cas de défaillance d’un pool</span><span class="sxs-lookup"><span data-stu-id="dbfca-103">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbfca-104">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="dbfca-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="dbfca-105">Cette section décrit en détail la façon dont l’activité des groupes Response Group est affectée au cours des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="dbfca-105">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="dbfca-106">Une panne se produit dans le pool principal, mais le basculement n’est pas encore démarré.</span><span class="sxs-lookup"><span data-stu-id="dbfca-106">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="dbfca-107">Un basculement du service est effectué vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dbfca-107">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="dbfca-108">Une restauration automatique du service est effectuée vers le pool principal.</span><span class="sxs-lookup"><span data-stu-id="dbfca-108">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="dbfca-109">Expérience utilisateur en cas de panne</span><span class="sxs-lookup"><span data-stu-id="dbfca-109">User Experience When Outage Occurs</span></span>

<span data-ttu-id="dbfca-110">Quand une panne se produit au niveau d’un pool ou d’un site mais que l’administrateur n’a pas encore effectué de basculement, l’activité des groupes Response Group est gérée comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="dbfca-110">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dbfca-p101">Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="dbfca-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="dbfca-113">Situation de panne</span><span class="sxs-lookup"><span data-stu-id="dbfca-113">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbfca-114">Type d’appel ou action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="dbfca-114">Type of call or user action</span></span></th>
<th><span data-ttu-id="dbfca-115">Pendant une panne</span><span class="sxs-lookup"><span data-stu-id="dbfca-115">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-116">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-116">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-117">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-117">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-118">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-118">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-119">Appels en cours pas encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-119">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="dbfca-120">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-120">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-121">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="dbfca-121">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-122">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-122">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-123">Si des groupes Response Group sont importés, les appels se connectent au pool de sauvegarde mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-123">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-124">L’agent appelle pour le compte du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="dbfca-124">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="dbfca-125">La fonctionnalité est désactivée au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="dbfca-125">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-126">Connexion et informations de l’agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-126">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-127">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-127">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-128">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-128">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-129">Les groupes d’agents importés ne sont pas affichés dans la console des agents.</span><span class="sxs-lookup"><span data-stu-id="dbfca-129">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-130">Configuration des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="dbfca-130">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-131">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-131">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-132">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-132">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-133">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dbfca-133">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="dbfca-134">Expérience utilisateur durant le basculement</span><span class="sxs-lookup"><span data-stu-id="dbfca-134">User Experience During Failover</span></span>

<span data-ttu-id="dbfca-p102">Quand un administrateur a recours au basculement vers un pool de sauvegarde, l’activité des groupes Response Group est gérée pendant et après le basculement comme indiqué dans le tableau suivant. La première colonne décrit le type d’activité qui peut avoir lieu. La colonne du milieu décrit la façon dont chaque activité est gérée durant le bref laps de temps nécessaire au basculement vers le pool de sauvegarde. La dernière colonne décrit la façon dont l’activité est gérée pendant toute la durée de l’opération, une fois que le processus de basculement est terminé et que le pool de sauvegarde a remplacé le pool principal.</span><span class="sxs-lookup"><span data-stu-id="dbfca-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dbfca-p103">Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="dbfca-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="dbfca-141">Basculement démarré</span><span class="sxs-lookup"><span data-stu-id="dbfca-141">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbfca-142">Type d’appel ou action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="dbfca-142">Type of call or user action</span></span></th>
<th><span data-ttu-id="dbfca-143">Durant le basculement</span><span class="sxs-lookup"><span data-stu-id="dbfca-143">During Failover</span></span></th>
<th><span data-ttu-id="dbfca-144">Une fois le basculement terminé</span><span class="sxs-lookup"><span data-stu-id="dbfca-144">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-145">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-145">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-146">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-146">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-147">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-147">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-148">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-148">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-149">Pour les groupes Response Group importés, les appels anonymes qui ont joint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-149">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-150">Appels en cours pas encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-150">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="dbfca-151">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-151">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-152">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</span><span class="sxs-lookup"><span data-stu-id="dbfca-152">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-153">Pour les groupes Response Group importés, les appels qui ont joint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-153">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-154">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="dbfca-154">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-155">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-155">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-156">Pour les groupes Response Group importés, les appels se connectent au pool de sauvegarde mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-156">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-157">Si les groupes Response Group n’ont pas été importés, les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-157">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-158">Pour les groupes Response Group importés, les appels se connectent au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="dbfca-158">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-159">L’agent appelle pour le compte du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="dbfca-159">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="dbfca-160">La fonctionnalité est désactivée au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="dbfca-160">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-161">Si les groupes Response Group n’ont pas été importés, les appels n’aboutissent pas.</span><span class="sxs-lookup"><span data-stu-id="dbfca-161">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-162">Pour les groupes Response Group importés, les appels aboutissent.</span><span class="sxs-lookup"><span data-stu-id="dbfca-162">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-163">Connexion et informations de l’agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-163">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-164">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-164">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-165">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-165">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-166">Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-166">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-167">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-167">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-168">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-168">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-169">Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-169">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-170">Configuration des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="dbfca-170">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-171">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-171">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-172">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-172">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-173">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dbfca-173">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-174">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-174">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-175">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-175">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-176">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dbfca-176">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="dbfca-177">Expérience utilisateur durant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="dbfca-177">User Experience During Failback</span></span>

<span data-ttu-id="dbfca-178">Quand un administrateur a recours à la restauration automatique vers le pool principal, l’activité des groupes Response Group est gérée pendant et après la restauration automatique comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="dbfca-178">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dbfca-p104">Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="dbfca-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="dbfca-181">Gestion des appels pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="dbfca-181">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbfca-182">Type d’appel ou action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="dbfca-182">Type of call or user action</span></span></th>
<th><span data-ttu-id="dbfca-183">Pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="dbfca-183">During Failback</span></span></th>
<th><span data-ttu-id="dbfca-184">Une fois la restauration automatique terminée</span><span class="sxs-lookup"><span data-stu-id="dbfca-184">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-185">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-185">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-186">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-186">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-187">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel anonyme avec cet état.</span><span class="sxs-lookup"><span data-stu-id="dbfca-187">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-188">Pour les groupes Response Group importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-188">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-189">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-189">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-190">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel anonyme avec cet état.</span><span class="sxs-lookup"><span data-stu-id="dbfca-190">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-191">Pour les groupes Response Group importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-191">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-192">Appels en cours pas encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-192">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-193">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</span><span class="sxs-lookup"><span data-stu-id="dbfca-193">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-194">Pour les groupes Response Group importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-194">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-195">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</span><span class="sxs-lookup"><span data-stu-id="dbfca-195">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-196">Pour les groupes Response Group importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="dbfca-196">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-197">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="dbfca-197">New calls</span></span></p></td>
<td><p><span data-ttu-id="dbfca-198">Les appels se connectent au pool principal mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-198">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="dbfca-199">Les appels se connectent au pool principal.</span><span class="sxs-lookup"><span data-stu-id="dbfca-199">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-200">L’agent appelle pour le compte du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="dbfca-200">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="dbfca-201">La fonctionnalité est désactivée au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="dbfca-201">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="dbfca-202">Les appels aboutissent.</span><span class="sxs-lookup"><span data-stu-id="dbfca-202">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbfca-203">Connexion et informations de l’agent</span><span class="sxs-lookup"><span data-stu-id="dbfca-203">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-204">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-204">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-205">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-205">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-206">Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-206">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-207">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-207">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-208">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="dbfca-208">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-209">Les groupes d’agents importés ne sont pas affichés dans la console des agents.</span><span class="sxs-lookup"><span data-stu-id="dbfca-209">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbfca-210">Configuration des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="dbfca-210">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-211">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-211">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-212">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-212">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-213">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dbfca-213">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="dbfca-214">Les groupes Response Group que possède le pool principal sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-214">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-215">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="dbfca-215">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="dbfca-216">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="dbfca-216">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

