---
title: Utilisation de l’interface utilisateur de Lync Server 2013 lors de l’échec du pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ca33dc8f77ac697b7eea9cc89fee9aa401318566
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a><span data-ttu-id="25782-102">Utilisation de l’interface utilisateur en cas d’échec du pool dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25782-102">User experience during pool failure in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25782-103">_**Dernière modification de la rubrique:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="25782-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="25782-104">En cas d’échec de la liste, tous les utilisateurs du pool affecté sont obligés de se déconnecter, puis de se connecter au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25782-104">If a pool is failed over, all users of the affected pool are forced to sign out and then sign into the backup pool.</span></span> <span data-ttu-id="25782-105">Pendant quelques instants, les utilisateurs qui se connectent au pool de sauvegarde peuvent être en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-105">For a brief period users who sign into the backup pool may be in resiliency mode.</span></span> <span data-ttu-id="25782-106">Dans le mode de résilience, les utilisateurs ne peuvent pas effectuer de tâches qui entraîneraient un changement permanent sur Lync Server, comme l’ajout d’un contact.</span><span class="sxs-lookup"><span data-stu-id="25782-106">In Resiliency mode, users are unable to perform tasks that would cause a persistent change on Lync Server, such as adding a contact.</span></span> <span data-ttu-id="25782-107">Une fois le basculement terminé, tous les utilisateurs peuvent obtenir tous les services du pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25782-107">After the failover is complete, all users can get all services from the backup pool.</span></span>

<span data-ttu-id="25782-108">Toutes les sessions d’un utilisateur en cas d’échec de la liste sont perturbées et l’utilisateur doit réorganiser ces sessions après le basculement pour continuer.</span><span class="sxs-lookup"><span data-stu-id="25782-108">Any sessions a user has when the pool fails are disrupted, and the user must re-establish those sessions after failover to continue.</span></span>

<span data-ttu-id="25782-109">Les utilisateurs ne sont pas rapatriés pendant le basculement ou la restauration automatique.</span><span class="sxs-lookup"><span data-stu-id="25782-109">Users are not rehomed during failover or failback.</span></span> <span data-ttu-id="25782-110">Les utilisateurs hébergés sur un pool qui subit une défaillance sont temporairement pris en charge par le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25782-110">Users who are homed on a pool that fails will be temporarily serviced by the backup pool.</span></span> <span data-ttu-id="25782-111">Lorsque le pool de domicile est restauré, l’administrateur peut basculer ces utilisateurs pour qu’ils soient remis en service par leur liste de démarrage d’origine.</span><span class="sxs-lookup"><span data-stu-id="25782-111">When the home pool is restored, the administrator can fail back these users to be serviced by their original home pool.</span></span>

<span data-ttu-id="25782-112">Remarque dans Lync 2013, la base de données du serveur informations d’emplacement n’est pas répliquée dans le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25782-112">Note in Lync 2013, the Location Information Server database is not replicated to the backup pool.</span></span> <span data-ttu-id="25782-113">Il est recommandé que l’administrateur sauvegarde régulièrement la base de données LIS et utilise la dernière copie de sauvegarde pour la restaurer dans le pool de sauvegarde après le basculement.</span><span class="sxs-lookup"><span data-stu-id="25782-113">For best practice, the administrator should regularly back up the LIS database and use the latest backup copy to restore the LIS database in the backup pool after the failover.</span></span>

<div>

## <a name="user-experience-during-failover"></a><span data-ttu-id="25782-114">Utilisation de l’interface utilisateur pendant le basculement</span><span class="sxs-lookup"><span data-stu-id="25782-114">User Experience During Failover</span></span>

<span data-ttu-id="25782-115">Lorsque l’utilisateur se trouve dans un pool qui échoue, il est déconnecté. Toutes les sessions d’égal à égal auxquelles l’utilisateur a participé sont arrêtées, en tant que conférences organisées par cet utilisateur.</span><span class="sxs-lookup"><span data-stu-id="25782-115">When a user is in a pool that fails, the user is logged out. Any peer-to-peer session the user was participating in is terminated, as are conferences organized by that user.</span></span> <span data-ttu-id="25782-116">L’utilisateur ne peut se reconnecter qu’après l’expiration du minuteur de résistance du serveur d’inscriptions avancé ou lorsque l’administrateur lance des procédures de basculement.</span><span class="sxs-lookup"><span data-stu-id="25782-116">The user cannot log back in until either the registrar resiliency timer expires or the administrator initiates failover procedures, whichever comes first.</span></span> <span data-ttu-id="25782-117">Lorsque l’utilisateur se reconnecte, il se connecte au pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25782-117">When the user logs back in, they will log in to the backup pool.</span></span> <span data-ttu-id="25782-118">S’il se connecte avant que le basculement soit terminé, il sera en mode Résistance jusqu’à la fin du basculement.</span><span class="sxs-lookup"><span data-stu-id="25782-118">If they log in before the failover has completed, they will be in Resiliency mode until failover is complete.</span></span> <span data-ttu-id="25782-119">Seul l’utilisateur est en mesure d’établir de nouvelles sessions ou de rétablir une session précédente.</span><span class="sxs-lookup"><span data-stu-id="25782-119">Only then the user is able to establish new sessions or re-establish previous sessions.</span></span>

</div>

<div>

## <a name="user-experience-during-failback"></a><span data-ttu-id="25782-120">Utilisation des utilisateurs lors du retour arrière</span><span class="sxs-lookup"><span data-stu-id="25782-120">User Experience During Failback</span></span>

<span data-ttu-id="25782-121">La restauration automatique du pool peut survenir pendant qu’un utilisateur affecté est connecté au pool de sauvegarde ; l’utilisateur reste connecté et opérationnel pendant la restauration.</span><span class="sxs-lookup"><span data-stu-id="25782-121">Pool failback can happen while an affected user is logged on to the backup pool, and the user remains logged on and working during the failback.</span></span> <span data-ttu-id="25782-122">Notez que le processus de restauration automatique prend quelques minutes.</span><span class="sxs-lookup"><span data-stu-id="25782-122">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="25782-123">À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="25782-123">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

<span data-ttu-id="25782-124">Les tableaux suivants montrent plus d’informations sur la façon dont un utilisateur disposant d’un client 2013 Lync ou d’un client Microsoft Lync 2010 est touché pendant et après un retour arrière, et la façon dont les utilisateurs d’autres pools voient et interagissent avec un utilisateur d’un pool qui est en échec de retour.</span><span class="sxs-lookup"><span data-stu-id="25782-124">The following tables show more details about how a user with a Lync 2013 client or a Microsoft Lync 2010 client is affected during and after failback, and also how users in other pools see and interact with a user in a pool who is being failed back.</span></span> <span data-ttu-id="25782-125">Les utilisateurs dotés de clients Microsoft Office Communicator 2007 R2 ne peuvent pas se connecter tant que le pool frontal n’a pas été complètement restauré.</span><span class="sxs-lookup"><span data-stu-id="25782-125">Users with Microsoft Office Communicator 2007 R2 clients cannot sign in until the Front End pool is completely failed back.)</span></span>

<span data-ttu-id="25782-126">Le terme *utilisateur affecté* fait référence à tous les utilisateurs qui ont été basculés à partir du pool d’accueil et qui sont pris en charge par le pool de sauvegarde.</span><span class="sxs-lookup"><span data-stu-id="25782-126">The term *affected user* refers to any user who was failed over from the home pool and is being serviced by the backup pool.</span></span> <span data-ttu-id="25782-127">Par définition, tous les utilisateurs hébergés sur le pool de sauvegarde ne sont pas des utilisateurs concernés.</span><span class="sxs-lookup"><span data-stu-id="25782-127">By definition, any user originally homed on the backup pool is not an affected user.</span></span>

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a><span data-ttu-id="25782-128">Expérience utilisateur pour un utilisateur affecté dans un pool en restauration automatique</span><span class="sxs-lookup"><span data-stu-id="25782-128">User Experience for an Affected User in a Pool in Failback</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25782-129">Statut de l’utilisateur ou tâche</span><span class="sxs-lookup"><span data-stu-id="25782-129">User state or task</span></span></th>
<th><span data-ttu-id="25782-130">Durant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="25782-130">During failback</span></span></th>
<th><span data-ttu-id="25782-131">Une fois la restauration automatique terminée</span><span class="sxs-lookup"><span data-stu-id="25782-131">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25782-132">Statut d’un utilisateur déjà connecté</span><span class="sxs-lookup"><span data-stu-id="25782-132">User state of user already logged in</span></span></p></td>
<td><p><span data-ttu-id="25782-p108">L’utilisateur reste connecté au pool de sauvegarde. À un certain moment, l’utilisateur sera déconnecté et reconnecté au pool d’accueil d’origine, en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-p108">User stays signed in and connected to backup pool. At some point user will be signed out and sign back in to the original home pool, in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="25782-135">L’utilisateur reste connecté et passe en mode normal.</span><span class="sxs-lookup"><span data-stu-id="25782-135">User remains signed in and goes into regular mode.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25782-136">Connexion d’un nouvel utilisateur</span><span class="sxs-lookup"><span data-stu-id="25782-136">New user logging in</span></span></p></td>
<td><p><span data-ttu-id="25782-137">L’utilisateur peut se connecter au pool d’accueil en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-137">User can sign in to the home pool in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="25782-138">L’utilisateur peut se connecter au pool d’accueil d’origine en mode normal.</span><span class="sxs-lookup"><span data-stu-id="25782-138">User can sign in to the original home pool in regular mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25782-139">Conférences en cours organisées par un utilisateur affecté</span><span class="sxs-lookup"><span data-stu-id="25782-139">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="25782-p109">Toutes les modalités de conférence sont terminées. Le bouton Rejoindre s’affiche, mais aucun utilisateur ne peut rejoindre la conférence tant que l’utilisateur affecté est en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-p109">All modalities of conference are terminated. Rejoin button will appear, but no users can rejoin while the affected user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="25782-p110">Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="25782-p110">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25782-144">Conférences en cours organisées par un utilisateur non affecté</span><span class="sxs-lookup"><span data-stu-id="25782-144">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="25782-p111">La conférence se poursuit et l’utilisateur affecté peut rester dans la conférence. L’utilisateur affecté est limité à ce qu’il peut faire en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-p111">Conference continues and affected user can stay in the conference. Affected user is restricted to what he/she can do in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="25782-147">La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent une fois que l’utilisateur a quitté le mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-147">Conference continues, and affected user can stay in the conference and all modalities work after user exits Resiliency mode.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25782-148">Planification ou modification de réunions planifiées, création de conférences ad hoc</span><span class="sxs-lookup"><span data-stu-id="25782-148">Scheduling or modifying scheduled meetings, creating ad-hoc conferences</span></span></p></td>
<td><p><span data-ttu-id="25782-149">Impossibles pendant que l’utilisateur est en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-149">Not possible while user is in Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="25782-150">Disponibles pour toutes les modalités.</span><span class="sxs-lookup"><span data-stu-id="25782-150">Available for all modalities.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25782-151">Présence telle qu’elle est vue par les autres utilisateurs du même pool</span><span class="sxs-lookup"><span data-stu-id="25782-151">Presence as seen by other users in the same pool</span></span></p></td>
<td><p><span data-ttu-id="25782-152">Présence inconnue pendant que l’utilisateur est connecté au pool de sauvegarde en mode Résistance.</span><span class="sxs-lookup"><span data-stu-id="25782-152">Presence unknown while user is signed into backup pool during Resiliency mode.</span></span></p></td>
<td><p><span data-ttu-id="25782-153">Affiche le dernier état de présence défini par l’utilisateur, et les changements du statut de présence sont maintenant reflétés.</span><span class="sxs-lookup"><span data-stu-id="25782-153">Shows the last presence state set by the user, and presence changes will now be reflected.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25782-154">Disponibilité de la liste de contacts et du Service de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="25782-154">Contacts list and Address Book Service availability</span></span></p></td>
<td><p><span data-ttu-id="25782-155">Non disponibles</span><span class="sxs-lookup"><span data-stu-id="25782-155">Not available</span></span></p></td>
<td><p><span data-ttu-id="25782-156">Disponibles</span><span class="sxs-lookup"><span data-stu-id="25782-156">Available</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25782-157">Ensemble des sessions et modalités pair à pair</span><span class="sxs-lookup"><span data-stu-id="25782-157">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="25782-158">Disponibles</span><span class="sxs-lookup"><span data-stu-id="25782-158">Available</span></span></p></td>
<td><p><span data-ttu-id="25782-159">Disponibles</span><span class="sxs-lookup"><span data-stu-id="25782-159">Available</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a><span data-ttu-id="25782-160">Expérience utilisateur pour un utilisateur hébergé dans un pool non affecté lors de la restauration automatique d’un autre pool</span><span class="sxs-lookup"><span data-stu-id="25782-160">User Experience for a User Homed in an Unaffected Pool During Failback of Another Pool</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25782-161">Tâche utilisateur</span><span class="sxs-lookup"><span data-stu-id="25782-161">User task</span></span></th>
<th><span data-ttu-id="25782-162">Durant la restauration automatique</span><span class="sxs-lookup"><span data-stu-id="25782-162">During failback</span></span></th>
<th><span data-ttu-id="25782-163">Une fois la restauration automatique terminée</span><span class="sxs-lookup"><span data-stu-id="25782-163">After failback completion</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25782-164">Affichage de la présence de l’utilisateur affecté</span><span class="sxs-lookup"><span data-stu-id="25782-164">Viewing presence of affected user</span></span></p></td>
<td><p><span data-ttu-id="25782-165">Affiche le dernier état de présence défini par l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="25782-165">Shows the last presence state set by the affected user.</span></span></p></td>
<td><p><span data-ttu-id="25782-p112">Opérationnel. Les utilisateurs non affectés voient les mises à jour effectuées par les utilisateurs affectés.</span><span class="sxs-lookup"><span data-stu-id="25782-p112">Working. Unaffected users see updates made by affected users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25782-168">Conférences en cours organisées par un utilisateur affecté</span><span class="sxs-lookup"><span data-stu-id="25782-168">Ongoing conferences organized by affected user</span></span></p></td>
<td><p><span data-ttu-id="25782-169">Toutes les modalités de conférence sont terminées.</span><span class="sxs-lookup"><span data-stu-id="25782-169">All modalities of conference are terminated.</span></span></p></td>
<td><p><span data-ttu-id="25782-p113">Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.</span><span class="sxs-lookup"><span data-stu-id="25782-p113">All modalities now work. Every participant needs to click to rejoin the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25782-172">Conférences en cours organisées par un utilisateur non affecté</span><span class="sxs-lookup"><span data-stu-id="25782-172">Ongoing conferences organized by unaffected user</span></span></p></td>
<td><p><span data-ttu-id="25782-173">La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="25782-173">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
<td><p><span data-ttu-id="25782-174">La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.</span><span class="sxs-lookup"><span data-stu-id="25782-174">Conference continues, and affected user can stay in the conference and all modalities work.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25782-175">Ensemble des sessions et modalités pair à pair</span><span class="sxs-lookup"><span data-stu-id="25782-175">All peer-to-peer sessions and modalities</span></span></p></td>
<td><p><span data-ttu-id="25782-176">Disponibles</span><span class="sxs-lookup"><span data-stu-id="25782-176">Available</span></span></p></td>
<td><p><span data-ttu-id="25782-177">Disponibles</span><span class="sxs-lookup"><span data-stu-id="25782-177">Available</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

