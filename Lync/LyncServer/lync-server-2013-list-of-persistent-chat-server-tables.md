---
title: 'Lync Server 2013 : liste des tables de serveur de conversation permanente'
description: 'Lync Server 2013 : liste des tables de serveur de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550050"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="99bab-103">Liste des tables de serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="99bab-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99bab-104">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="99bab-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="99bab-105">Le schéma de la base de données de conversation permanente se compose des tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="99bab-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="99bab-106">Synchronisation Active Directory</span><span class="sxs-lookup"><span data-stu-id="99bab-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99bab-107">Table</span><span class="sxs-lookup"><span data-stu-id="99bab-107">Table</span></span></th>
<th><span data-ttu-id="99bab-108">Description</span><span class="sxs-lookup"><span data-stu-id="99bab-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99bab-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-110">Contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.</span><span class="sxs-lookup"><span data-stu-id="99bab-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="99bab-111">Chaque ligne correspond à un domaine des services de domaine Active Directory dont le serveur de conversation permanente surveille activement les modifications.</span><span class="sxs-lookup"><span data-stu-id="99bab-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="99bab-112">(Seuls les domaines Active Directory qui sont pertinents pour le serveur de conversation permanente sont représentés dans ce tableau.)</span><span class="sxs-lookup"><span data-stu-id="99bab-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-114">Contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory et est l’une des tables temporaires (avec la table tblADUpdates) qui est utilisée dans la première étape de la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99bab-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="99bab-115">Les modifications d’appartenance sont stockées, traitées ou les deux, uniquement pour les groupes qui sont répertoriés dans la table tblPrincipal ou qui contiennent déjà des membres répertoriés dans cette dernière.</span><span class="sxs-lookup"><span data-stu-id="99bab-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-117">Contient les modifications apportées aux services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory et est l’une des tables temporaires (avec la table tblPrincipalMemberDifference) qui est utilisée lors de la première étape de la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99bab-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="99bab-118">Les modifications apportées à Active Directory sont stockées, traitées ou les deux uniquement pour les principaux qui sont déjà répertoriés dans le tableau tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="99bab-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-120">Contient les appartenances de Principal.</span><span class="sxs-lookup"><span data-stu-id="99bab-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-122">Contient les principaux qui doivent être actualisés à partir d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99bab-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-124">Contient des affiliations qui n’ont pas pu être actualisées pour une raison quelconque, généralement en raison d’erreurs d’accès à Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99bab-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="99bab-p102">Cette table est fournie uniquement à titre indicatif. Son contenu n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="99bab-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="99bab-127">Les principaux avec affiliations qui n’ont pas pu être correctement actualisés sont conservés dans la table tblPrincipalMeta et peuvent de nouveau être actualisés.</span><span class="sxs-lookup"><span data-stu-id="99bab-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="99bab-128">Principaux, affiliations, nœuds, étendues et rôles</span><span class="sxs-lookup"><span data-stu-id="99bab-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99bab-129">Table</span><span class="sxs-lookup"><span data-stu-id="99bab-129">Table</span></span></th>
<th><span data-ttu-id="99bab-130">Description</span><span class="sxs-lookup"><span data-stu-id="99bab-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99bab-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-p103">Contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal. Cette table est statique. Elle est configurée lors de la création de la base de données et n’est pas modifiée.</span><span class="sxs-lookup"><span data-stu-id="99bab-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-136">Contient tous les principaux (utilisateurs, dossiers, groupes, etc.).</span><span class="sxs-lookup"><span data-stu-id="99bab-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="99bab-137">Le serveur de conversation permanente gère cela en tant que liste hétérogène plate.</span><span class="sxs-lookup"><span data-stu-id="99bab-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="99bab-138">De nombreuses colonnes sont basées sur le type de chaque principal.</span><span class="sxs-lookup"><span data-stu-id="99bab-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="99bab-139">La plupart de ces principaux sont des copies mises en cache d’objets stockés dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="99bab-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="99bab-140">La création de la copie mise en cache dans la table principale de ces objets Active Directory est appelée <em>mise en service</em>.</span><span class="sxs-lookup"><span data-stu-id="99bab-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="99bab-141">Certains principaux sont créés de manière plus agressive que d’autres, et certains objets Active Directory ne sont pas pris en compte.</span><span class="sxs-lookup"><span data-stu-id="99bab-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-143">Contient les affiliations principales qui décrivent les appartenances aux groupes de sécurité Active Directory, aux conteneurs Active Directory, etc.</span><span class="sxs-lookup"><span data-stu-id="99bab-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-144"><a href="lync-server-2013-tblnode.md">tblNode dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-145">Contient le nœud Category, tel qu’il est géré dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="99bab-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-146"><a href="lync-server-2013-tblroletype.md">tblRoleType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-147">Contient des types de rôles et leurs jeux d’autorisations associées.</span><span class="sxs-lookup"><span data-stu-id="99bab-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="99bab-148">Cette table de consultation est statique.</span><span class="sxs-lookup"><span data-stu-id="99bab-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-150">Contient des étendues assignées à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="99bab-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-152">Contient des rôles assignés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="99bab-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-154">Contient les compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="99bab-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-156">Contient uniquement les &quot; attributs de visibilité et de comportement codés en dur &quot; &quot; &quot; utilisés dans la table tblNode.</span><span class="sxs-lookup"><span data-stu-id="99bab-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-158">Contient les valeurs des attributs de &quot; comportement « et » de visibilité codés &quot; en dur utilisés dans la table tblNode.</span><span class="sxs-lookup"><span data-stu-id="99bab-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="99bab-159">Prises en charge des invitations, des conversations et d’autres clients</span><span class="sxs-lookup"><span data-stu-id="99bab-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99bab-160">Table</span><span class="sxs-lookup"><span data-stu-id="99bab-160">Table</span></span></th>
<th><span data-ttu-id="99bab-161">Description</span><span class="sxs-lookup"><span data-stu-id="99bab-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99bab-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-163">Contient les invitations de tous les utilisateurs mis en service dans le système pour tous les nœuds ayant la fonction d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="99bab-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-164"><a href="lync-server-2013-tblchat.md">tblChat dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-165">Contient tous les messages de conversations.</span><span class="sxs-lookup"><span data-stu-id="99bab-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-167">Contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99bab-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-169">Contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99bab-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-170"><a href="lync-server-2013-tblpreference.md">tblPreference dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-171">Contient les préférences du client utilisateur (utilisées par les clients hérités uniquement).</span><span class="sxs-lookup"><span data-stu-id="99bab-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-173">Contient des jetons temporaires pour le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="99bab-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="99bab-174">Chaque fois qu’un fichier est chargé ou téléchargé, le service de conversation permanente génère un jeton que le client utilise pour accéder au magasin de fichiers du service Web.</span><span class="sxs-lookup"><span data-stu-id="99bab-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="99bab-175">Prise en charge du serveur</span><span class="sxs-lookup"><span data-stu-id="99bab-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99bab-176">Table</span><span class="sxs-lookup"><span data-stu-id="99bab-176">Table</span></span></th>
<th><span data-ttu-id="99bab-177">Description</span><span class="sxs-lookup"><span data-stu-id="99bab-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99bab-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-179">Contient les serveurs actifs dans le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="99bab-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-p108">Contient le verrou d’administrateur permettant d’exécuter des commandes d’administrateur. L’entrée de révision du système dans la table tblSystemRevision est incrémentée après chaque libération de verrou.</span><span class="sxs-lookup"><span data-stu-id="99bab-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-184">Contient l’entrée du numéro de révision utilisée (avec la table tblAdminLock) pour harmoniser plusieurs serveurs administrateurs.</span><span class="sxs-lookup"><span data-stu-id="99bab-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99bab-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-186">Contient les connexions P2P actuelles entre les services de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="99bab-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99bab-187"><a href="lync-server-2013-tblconfig.md">tblConfig dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="99bab-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="99bab-188">Contient la configuration du serveur de conversation permanente non prise en charge.</span><span class="sxs-lookup"><span data-stu-id="99bab-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

