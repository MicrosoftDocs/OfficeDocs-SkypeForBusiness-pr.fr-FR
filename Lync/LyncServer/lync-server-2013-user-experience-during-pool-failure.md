---
title: Expérience utilisateur Lync Server 2013 en cas de défaillance du pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63bef718af5664c18ccedca7482e4ca0a0a7f95e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42192957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="43d80-102">Expérience utilisateur en cas de défaillance du pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43d80-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43d80-103">_**Dernière modification de la rubrique :** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="43d80-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="43d80-104">Si un pool est basculé, tous les utilisateurs du pool affecté sont obligés de se déconnecter, puis de se reconnecter au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43d80-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="43d80-105">Pendant quelques instants, les utilisateurs qui se connectent au pool de sauvegarde peuvent être en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="43d80-106">En mode résistance, les utilisateurs ne peuvent pas effectuer des tâches qui provoqueraient une modification permanente sur Lync Server, comme l’ajout d’un contact.</span><span class="sxs-lookup"><span data-stu-id="43d80-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="43d80-107">Une fois le basculement terminé, tous les utilisateurs peuvent obtenir tous les services du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43d80-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="43d80-108">Toutes les sessions en cours d’un utilisateur au moment de la défaillance du pool sont interrompues, et l’utilisateur doit rétablir ces sessions après le basculement pour continuer.</span><span class="sxs-lookup"><span data-stu-id="43d80-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="43d80-p102">Les utilisateurs ne sont pas rapatriés pendant le basculement ou la restauration automatique. Les utilisateurs hébergés sur un pool qui subit une défaillance sont temporairement pris en charge par le pool de sauvegarde. Lorsque le pool d’accueil est restauré, l’administrateur peut restaurer ces utilisateurs afin qu’ils soient pris en charge par leur pool d’accueil d’origine.</span><span class="sxs-lookup"><span data-stu-id="43d80-p102">Users are not rehomed during failover or failback. Users who are homed on a pool that fails will be temporarily serviced by the backup pool. When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="43d80-112">Remarque dans Lync 2013, la base de données du serveur d’informations d’emplacement n’est pas répliquée dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="43d80-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="43d80-113">Il est recommandé que l’administrateur sauvegarde régulièrement la base de données LIS et utilise la dernière copie de sauvegarde pour la restaurer dans le pool de sauvegarde après le basculement.</span><span class="sxs-lookup"><span data-stu-id="43d80-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="43d80-114">Expérience utilisateur durant le basculement</span><span class="sxs-lookup"><span data-stu-id="43d80-114">User Experience During Failover</span></span>

<span data-ttu-id="43d80-p104">Lorsqu’un utilisateur se trouve dans un pool subissant une défaillance, il est déconnecté. Toute session d’égal à égal à laquelle l’utilisateur participait est terminée, de même que les conférences organisées par cet utilisateur. L’utilisateur ne peut se reconnecter qu’après l’expiration du minuteur de résistance du serveur d’inscriptions avancé ou lorsque l’administrateur initie des procédures de basculement. Lorsque l’utilisateur se reconnecte, il se connecte au pool de sauvegarde. S’il se connecte avant que le basculement soit terminé, il sera en mode Résistance jusqu’à la fin du basculement. C’est seulement alors que l’utilisateur peut établir de nouvelles sessions pour rétablir des sessions précédentes.</span><span class="sxs-lookup"><span data-stu-id="43d80-p104">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user. The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first. When the user logs back in, they will log in to the backup pool. If they log in before the failover has completed, they will be in Resiliency mode until failover is complete. Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="43d80-120">Expérience utilisateur durant la restauration</span><span class="sxs-lookup"><span data-stu-id="43d80-120">User Experience During Failback</span></span>

<span data-ttu-id="43d80-p105">La restauration automatique du pool peut survenir pendant qu’un utilisateur affecté est connecté au pool de sauvegarde ; l’utilisateur reste connecté et opérationnel pendant la restauration. Notez que l’exécution du processus de restauration automatique prend plusieurs minutes. À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="43d80-p105">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback. Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="43d80-124">Les tableaux suivants présentent des détails supplémentaires sur la façon dont un utilisateur avec un client Lync 2013 ou un client Microsoft Lync 2010 est concerné pendant et après la restauration automatique, ainsi que la façon dont les utilisateurs d’autres pools voient et interagissent avec un utilisateur d’un pool qui est en cours d’échec.</span><span class="sxs-lookup"><span data-stu-id="43d80-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="43d80-125">Les utilisateurs disposant de clients Microsoft Office Communicator 2007 R2 ne peuvent pas se connecter tant que le pool frontal n’est pas complètement restauré.)</span><span class="sxs-lookup"><span data-stu-id="43d80-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="43d80-p107">Le terme *utilisateur affecté* fait référence à tous les utilisateurs qui ont été basculés à partir du pool d’accueil et qui sont pris en charge par le pool de sauvegarde. Par définition, tout utilisateur initialement hébergé sur le pool de sauvegarde n’est pas un utilisateur affecté.</span><span class="sxs-lookup"><span data-stu-id="43d80-p107">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool. By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="43d80-128">Expérience utilisateur pour un utilisateur affecté dans un pool en restauration automatique</span><span class="sxs-lookup"><span data-stu-id="43d80-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d80-129">Statut de l’utilisateur ou tâche</span><span class="sxs-lookup"><span data-stu-id="43d80-129">User state or task</span></span></th>
<th><span data-ttu-id="43d80-130">Pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="43d80-130">During failback</span></span></th>
<th><span data-ttu-id="43d80-131">Une fois la restauration automatique terminée</span><span class="sxs-lookup"><span data-stu-id="43d80-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d80-132">Statut d’un utilisateur déjà connecté</span><span class="sxs-lookup"><span data-stu-id="43d80-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="43d80-p108">L’utilisateur reste connecté au pool de sauvegarde. À un certain moment, l’utilisateur sera déconnecté et reconnecté au pool d’accueil d’origine, en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="43d80-135">L’utilisateur reste connecté et passe en mode normal.</span><span class="sxs-lookup"><span data-stu-id="43d80-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d80-136">Connexion d’un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="43d80-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="43d80-137">L’utilisateur peut se connecter au pool d’accueil en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="43d80-138">L’utilisateur peut se connecter au pool d’accueil d’origine en mode normal.</span><span class="sxs-lookup"><span data-stu-id="43d80-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d80-139">Conférences en cours organisées par un utilisateur affecté</span><span class="sxs-lookup"><span data-stu-id="43d80-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="43d80-p109">Toutes les modalités de conférence sont terminées. Le bouton Rejoindre s’affiche, mais aucun utilisateur ne peut rejoindre la conférence tant que l’utilisateur affecté est en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="43d80-p110">Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="43d80-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d80-144">Conférences en cours organisées par un utilisateur non affecté</span><span class="sxs-lookup"><span data-stu-id="43d80-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="43d80-p111">La conférence se poursuit et l’utilisateur affecté peut rester dans la conférence. L’utilisateur affecté est limité à ce qu’il peut faire en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="43d80-147">La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent une fois que l’utilisateur a quitté le mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d80-148">Planification ou modification de réunions planifiées, création de conférences ad hoc</span><span class="sxs-lookup"><span data-stu-id="43d80-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="43d80-149">Impossibles pendant que l’utilisateur est en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="43d80-150">Disponibles pour toutes les modalités.</span><span class="sxs-lookup"><span data-stu-id="43d80-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d80-151">Présence telle qu’elle est vue par les autres utilisateurs du même pool</span><span class="sxs-lookup"><span data-stu-id="43d80-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="43d80-152">Présence inconnue pendant que l’utilisateur est connecté au pool de sauvegarde en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="43d80-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="43d80-153">Affiche le dernier état de présence défini par l’utilisateur, et les changements du statut de présence sont maintenant reflétés.</span><span class="sxs-lookup"><span data-stu-id="43d80-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d80-154">Disponibilité de la liste de contacts et du Service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="43d80-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="43d80-155">Non disponibles</span><span class="sxs-lookup"><span data-stu-id="43d80-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="43d80-156">Available</span><span class="sxs-lookup"><span data-stu-id="43d80-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d80-157">Ensemble des sessions et modalités pair à pair</span><span class="sxs-lookup"><span data-stu-id="43d80-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="43d80-158">Available</span><span class="sxs-lookup"><span data-stu-id="43d80-158">Available</span></span></p></td>
<td><p><span data-ttu-id="43d80-159">Available</span><span class="sxs-lookup"><span data-stu-id="43d80-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="43d80-160">Expérience utilisateur pour un utilisateur hébergé dans un pool non affecté pendant la restauration automatique d’un autre pool</span><span class="sxs-lookup"><span data-stu-id="43d80-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43d80-161">Tâche utilisateur</span><span class="sxs-lookup"><span data-stu-id="43d80-161">User task</span></span></th>
<th><span data-ttu-id="43d80-162">Pendant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="43d80-162">During failback</span></span></th>
<th><span data-ttu-id="43d80-163">Une fois la restauration automatique terminée</span><span class="sxs-lookup"><span data-stu-id="43d80-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43d80-164">Affichage de la présence de l’utilisateur affecté</span><span class="sxs-lookup"><span data-stu-id="43d80-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="43d80-165">Affiche le dernier état de présence défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43d80-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="43d80-p112">Opérationnel. Les utilisateurs non affectés voient les mises à jour effectuées par les utilisateurs affectés.</span><span class="sxs-lookup"><span data-stu-id="43d80-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d80-168">Conférences en cours organisées par un utilisateur affecté</span><span class="sxs-lookup"><span data-stu-id="43d80-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="43d80-169">Toutes les modalités de conférence sont terminées.</span><span class="sxs-lookup"><span data-stu-id="43d80-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="43d80-p113">Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="43d80-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43d80-172">Conférences en cours organisées par un utilisateur non affecté</span><span class="sxs-lookup"><span data-stu-id="43d80-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="43d80-173">La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="43d80-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="43d80-174">La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="43d80-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43d80-175">Ensemble des sessions et modalités pair à pair</span><span class="sxs-lookup"><span data-stu-id="43d80-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="43d80-176">Available</span><span class="sxs-lookup"><span data-stu-id="43d80-176">Available</span></span></p></td>
<td><p><span data-ttu-id="43d80-177">Available</span><span class="sxs-lookup"><span data-stu-id="43d80-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

