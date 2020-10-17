---
title: Expérience de groupe de réponse Lync Server 2013 en cas de défaillance du pool
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
ms.openlocfilehash: 684d33219bb6146a0c5dc85894c060affd6745a2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511641"
---
# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a><span data-ttu-id="299ff-102">Expérience Response Group dans Lync Server 2013 en cas de défaillance d’un pool</span><span class="sxs-lookup"><span data-stu-id="299ff-102">Response group experience in Lync Server 2013 during pool failure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="299ff-103">_**Dernière modification de la rubrique :** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="299ff-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="299ff-104">Cette section décrit en détail la façon dont l’activité des groupes Response Group est affectée au cours des étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="299ff-104">This section describes in detail how response group activity is affected in the following stages:</span></span>

  - <span data-ttu-id="299ff-105">Une panne se produit dans le pool principal, mais le basculement n’est pas encore démarré.</span><span class="sxs-lookup"><span data-stu-id="299ff-105">An outage occurs in the primary pool, but failover is not yet initiated.</span></span>

  - <span data-ttu-id="299ff-106">Un basculement du service est effectué vers le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="299ff-106">Service is failed over to the backup pool.</span></span>

  - <span data-ttu-id="299ff-107">Une restauration automatique du service est effectuée vers le pool principal.</span><span class="sxs-lookup"><span data-stu-id="299ff-107">Service is failed back to the primary pool.</span></span>

<div>

## <a name="user-experience-when-outage-occurs"></a><span data-ttu-id="299ff-108">Expérience utilisateur en cas de panne</span><span class="sxs-lookup"><span data-stu-id="299ff-108">User Experience When Outage Occurs</span></span>

<span data-ttu-id="299ff-109">Quand une panne se produit au niveau d’un pool ou d’un site mais que l’administrateur n’a pas encore effectué de basculement, l’activité des groupes Response Group est gérée comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="299ff-109">When a pool or site outage occurs, but the administrator has not yet initiated failover, response group activity is handled as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="299ff-p101">Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="299ff-p101">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="outage-occurs"></a><span data-ttu-id="299ff-112">Situation de panne</span><span class="sxs-lookup"><span data-stu-id="299ff-112">Outage Occurs</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="299ff-113">Type d’appel ou action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="299ff-113">Type of call or user action</span></span></th>
<th><span data-ttu-id="299ff-114">Pendant une panne</span><span class="sxs-lookup"><span data-stu-id="299ff-114">During outage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="299ff-115">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="299ff-115">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-116">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-116">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-117">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-117">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-118">Appels en cours pas encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="299ff-118">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="299ff-119">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-119">Calls are disconnected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299ff-120">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="299ff-120">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-121">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-121">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-122">Si des groupes Response Group sont importés, les appels se connectent au pool de sauvegarde mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="299ff-122">If response groups were imported, calls connect to backup pool, but agents homed in primary pool are unreachable.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-123">L’agent appelle pour le compte du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="299ff-123">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="299ff-124">La fonctionnalité est désactivée au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="299ff-124">Feature is disabled during this stage.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299ff-125">Connexion et informations de l’agent</span><span class="sxs-lookup"><span data-stu-id="299ff-125">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-126">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-126">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-127">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-127">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-128">Les groupes d’agents importés ne sont pas affichés dans la console des agents.</span><span class="sxs-lookup"><span data-stu-id="299ff-128">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-129">Configuration des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="299ff-129">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-130">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-130">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-131">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-131">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-132">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="299ff-132">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="299ff-133">Expérience utilisateur durant le basculement</span><span class="sxs-lookup"><span data-stu-id="299ff-133">User Experience During Failover</span></span>

<span data-ttu-id="299ff-p102">Quand un administrateur a recours au basculement vers un pool de sauvegarde, l’activité des groupes Response Group est gérée pendant et après le basculement comme indiqué dans le tableau suivant. La première colonne décrit le type d’activité qui peut avoir lieu. La colonne du milieu décrit la façon dont chaque activité est gérée durant le bref laps de temps nécessaire au basculement vers le pool de sauvegarde. La dernière colonne décrit la façon dont l’activité est gérée pendant toute la durée de l’opération, une fois que le processus de basculement est terminé et que le pool de sauvegarde a remplacé le pool principal.</span><span class="sxs-lookup"><span data-stu-id="299ff-p102">When an administrator invokes failover to a backup pool, response group activity is handled during and after the failover as described in the following table. The first column describes the type of activity that might be taking place. The middle column describes how each activity is handled during the brief time that it takes to fail over to the backup pool. The last column describes how the activity is handled for the duration, after the failover process is complete and the backup pool is standing in for the primary pool.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="299ff-p103">Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="299ff-p103">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="failover-is-initiated"></a><span data-ttu-id="299ff-140">Basculement démarré</span><span class="sxs-lookup"><span data-stu-id="299ff-140">Failover Is Initiated</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="299ff-141">Type d’appel ou action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="299ff-141">Type of call or user action</span></span></th>
<th><span data-ttu-id="299ff-142">Durant le basculement</span><span class="sxs-lookup"><span data-stu-id="299ff-142">During Failover</span></span></th>
<th><span data-ttu-id="299ff-143">Une fois le basculement terminé</span><span class="sxs-lookup"><span data-stu-id="299ff-143">After Failover Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="299ff-144">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="299ff-144">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-145">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-145">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-146">Les appels anonymes sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-146">Anonymous calls are disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-147">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-147">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-148">Pour les groupes Response Group importés, les appels anonymes qui ont joint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-148">For imported response groups, anonymous calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-149">Appels en cours pas encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="299ff-149">In progress calls not yet connected to an agent</span></span></p></td>
<td><p><span data-ttu-id="299ff-150">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-150">Calls are disconnected.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-151">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</span><span class="sxs-lookup"><span data-stu-id="299ff-151">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="299ff-152">Pour les groupes Response Group importés, les appels qui ont joint le pool de sauvegarde restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-152">For imported response groups, calls that have reached the backup pool remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299ff-153">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="299ff-153">New calls</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-154">Les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-154">Calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-155">Pour les groupes Response Group importés, les appels se connectent au pool de sauvegarde mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="299ff-155">For imported response groups, calls connect to the backup pool, but agents homed in the primary pool are unreachable.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-156">Si les groupes Response Group n’ont pas été importés, les appels sont déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-156">If response groups were not imported, calls are disconnected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-157">Pour les groupes Response Group importés, les appels se connectent au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="299ff-157">For imported response groups, calls connect to the backup pool.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-158">L’agent appelle pour le compte du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="299ff-158">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="299ff-159">La fonctionnalité est désactivée au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="299ff-159">Feature is disabled during this stage</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-160">Si les groupes Response Group n’ont pas été importés, les appels n’aboutissent pas.</span><span class="sxs-lookup"><span data-stu-id="299ff-160">If response groups were not imported, calls fail.</span></span></p></li>
<li><p><span data-ttu-id="299ff-161">Pour les groupes Response Group importés, les appels aboutissent.</span><span class="sxs-lookup"><span data-stu-id="299ff-161">For imported response groups, calls succeed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299ff-162">Connexion et informations de l’agent</span><span class="sxs-lookup"><span data-stu-id="299ff-162">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-163">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-163">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-164">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-164">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-165">Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-165">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-166">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-166">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-167">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-167">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-168">Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-168">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-169">Configuration des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="299ff-169">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-170">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-170">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-171">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-171">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-172">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="299ff-172">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-173">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-173">Response groups owned by the primary pool can be viewed, depending on the availability of the back end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-174">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-174">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-175">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="299ff-175">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="299ff-176">Expérience utilisateur durant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="299ff-176">User Experience During Failback</span></span>

<span data-ttu-id="299ff-177">Quand un administrateur a recours à la restauration automatique vers le pool principal, l’activité des groupes Response Group est gérée pendant et après la restauration automatique comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="299ff-177">When an administrator invokes failback to the primary pool, response group activity is handled during and after the failback as described in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="299ff-p104">Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="299ff-p104">During disaster recovery, calls behave differently depending on whether the primary pool response groups were imported to the backup pool during recovery. In the following table, references to imported response groups mean that primary pool response groups were imported to the backup pool during disaster recovery mode.</span></span>



</div>

### <a name="call-handling-in-failback"></a><span data-ttu-id="299ff-180">Gestion des appels pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="299ff-180">Call Handling in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="299ff-181">Type d’appel ou action de l’utilisateur</span><span class="sxs-lookup"><span data-stu-id="299ff-181">Type of call or user action</span></span></th>
<th><span data-ttu-id="299ff-182">Pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="299ff-182">During Failback</span></span></th>
<th><span data-ttu-id="299ff-183">Une fois la restauration automatique terminée</span><span class="sxs-lookup"><span data-stu-id="299ff-183">After Failback Completes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="299ff-184">Appels connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="299ff-184">Calls connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-185">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-185">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-186">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel anonyme avec cet état.</span><span class="sxs-lookup"><span data-stu-id="299ff-186">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="299ff-187">Pour les groupes Response Group importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-187">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-188">Les appels normaux restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-188">Regular calls remain connected.</span></span></p></li>
<li><p><span data-ttu-id="299ff-189">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel anonyme avec cet état.</span><span class="sxs-lookup"><span data-stu-id="299ff-189">If response groups were not imported, no anonymous calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="299ff-190">Pour les groupes Response Group importés, les appels anonymes restent connectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-190">For imported response groups, anonymous calls remain connected.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-191">Appels en cours pas encore connectés à un agent</span><span class="sxs-lookup"><span data-stu-id="299ff-191">In progress calls not yet connected to an agent</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-192">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</span><span class="sxs-lookup"><span data-stu-id="299ff-192">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="299ff-193">Pour les groupes Response Group importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-193">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-194">Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</span><span class="sxs-lookup"><span data-stu-id="299ff-194">If response groups were not imported, no calls are in this status.</span></span></p></li>
<li><p><span data-ttu-id="299ff-195">Pour les groupes Response Group importés, les appels seront déconnectés.</span><span class="sxs-lookup"><span data-stu-id="299ff-195">For imported response groups, calls will be disconnected.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299ff-196">Nouveaux appels</span><span class="sxs-lookup"><span data-stu-id="299ff-196">New calls</span></span></p></td>
<td><p><span data-ttu-id="299ff-197">Les appels se connectent au pool principal mais les agents hébergés dans le pool principal sont injoignables.</span><span class="sxs-lookup"><span data-stu-id="299ff-197">Calls connect to the primary pool, but agents homed in the primary pool are unreachable.</span></span></p></td>
<td><p><span data-ttu-id="299ff-198">Les appels se connectent au pool principal.</span><span class="sxs-lookup"><span data-stu-id="299ff-198">Calls connect to the primary pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-199">L’agent appelle pour le compte du groupe Response Group</span><span class="sxs-lookup"><span data-stu-id="299ff-199">Agent calls on behalf of response group</span></span></p></td>
<td><p><span data-ttu-id="299ff-200">La fonctionnalité est désactivée au cours de cette étape.</span><span class="sxs-lookup"><span data-stu-id="299ff-200">Feature is disabled during this stage.</span></span></p></td>
<td><p><span data-ttu-id="299ff-201">Les appels aboutissent.</span><span class="sxs-lookup"><span data-stu-id="299ff-201">Calls succeed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="299ff-202">Connexion et informations de l’agent</span><span class="sxs-lookup"><span data-stu-id="299ff-202">Agent sign-in and agent information</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-203">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-203">Agent groups owned by the primary pool can be viewed on agent console but agents cannot sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-204">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-204">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-205">Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-205">Imported agent groups are displayed on agent console and agents can sign in.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-206">Les groupes d’agents que possède le pool principal sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-206">Agent groups owned by the primary pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-207">Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</span><span class="sxs-lookup"><span data-stu-id="299ff-207">Agent groups owned by the backup pool can be viewed on agent console and agents can sign in.</span></span></p></li>
<li><p><span data-ttu-id="299ff-208">Les groupes d’agents importés ne sont pas affichés dans la console des agents.</span><span class="sxs-lookup"><span data-stu-id="299ff-208">Imported agent groups are not displayed on agent console.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="299ff-209">Configuration des groupes Response Group</span><span class="sxs-lookup"><span data-stu-id="299ff-209">Response group configuration</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="299ff-210">Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-210">Response groups owned by the primary pool can be viewed, depending on the availability of the primary pool’s back-end database, but cannot be modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-211">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-211">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-212">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="299ff-212">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
</ul></td>
<td><ul>
<li><p><span data-ttu-id="299ff-213">Les groupes Response Group que possède le pool principal sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-213">Response groups owned by the primary pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-214">Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</span><span class="sxs-lookup"><span data-stu-id="299ff-214">Response groups owned by the backup pool can be viewed and modified.</span></span></p></li>
<li><p><span data-ttu-id="299ff-215">Les groupes Response Group importés ne peuvent pas être affichés à l’aide du panneau de configuration Lync Server ou de l’outil de configuration Response Group, mais ils peuvent être configurés à l’aide des applets de commande Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="299ff-215">Imported response groups cannot be viewed with Lync Server Control Panel or the Response Group Configuration Tool, but can be configured by using Lync Server Management Shell cmdlets.</span></span></p></li>
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

