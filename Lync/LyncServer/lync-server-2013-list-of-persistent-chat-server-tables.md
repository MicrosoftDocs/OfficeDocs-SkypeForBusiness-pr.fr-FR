---
title: 'Lync Server 2013 : liste des tables de serveur de conversation permanente'
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
ms.openlocfilehash: 4327e2a72f91e17fd71cd198940ea01d10423b00
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="0f764-102">Liste des tables de serveur de conversation permanente dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f764-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f764-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0f764-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0f764-104">Le schéma de la base de données de conversation permanente se compose des tableaux suivants.</span><span class="sxs-lookup"><span data-stu-id="0f764-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="0f764-105">Synchronisation Active Directory</span><span class="sxs-lookup"><span data-stu-id="0f764-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f764-106">Table</span><span class="sxs-lookup"><span data-stu-id="0f764-106">Table</span></span></th>
<th><span data-ttu-id="0f764-107">Description</span><span class="sxs-lookup"><span data-stu-id="0f764-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f764-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-109">Contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs.</span><span class="sxs-lookup"><span data-stu-id="0f764-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="0f764-110">Chaque ligne correspond à un domaine des services de domaine Active Directory dont le serveur de conversation permanente surveille activement les modifications.</span><span class="sxs-lookup"><span data-stu-id="0f764-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="0f764-111">(Seuls les domaines Active Directory qui sont pertinents pour le serveur de conversation permanente sont représentés dans ce tableau.)</span><span class="sxs-lookup"><span data-stu-id="0f764-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-113">Contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory et est l’une des tables temporaires (avec la table tblADUpdates) qui est utilisée dans la première étape de la synchronisation Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f764-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="0f764-114">Les modifications d’appartenance sont stockées, traitées ou les deux, uniquement pour les groupes qui sont répertoriés dans la table tblPrincipal ou qui contiennent déjà des membres répertoriés dans cette dernière.</span><span class="sxs-lookup"><span data-stu-id="0f764-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-116">Contient les modifications apportées aux services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory et est l’une des tables temporaires (avec la table tblPrincipalMemberDifference) qui est utilisée dans la première étape d’Active Directory Synchroni.</span><span class="sxs-lookup"><span data-stu-id="0f764-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="0f764-117">Les modifications apportées à Active Directory sont stockées, traitées ou les deux uniquement pour les principaux qui sont déjà répertoriés dans le tableau tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="0f764-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-119">Contient les appartenances de Principal.</span><span class="sxs-lookup"><span data-stu-id="0f764-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-121">Contient les principaux qui doivent être actualisés à partir d’Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f764-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-123">Contient des affiliations qui n’ont pas pu être actualisées pour une raison quelconque, généralement en raison d’erreurs d’accès à Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f764-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="0f764-p102">Cette table est fournie uniquement à titre indicatif. Son contenu n’est pas utilisé.</span><span class="sxs-lookup"><span data-stu-id="0f764-p102">This table is for informational purposes only. Its content is not used.</span></span></p>
<p><span data-ttu-id="0f764-126">Les principaux avec affiliations qui n’ont pas pu être correctement actualisés sont conservés dans la table tblPrincipalMeta et peuvent de nouveau être actualisés.</span><span class="sxs-lookup"><span data-stu-id="0f764-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="0f764-127">Principaux, affiliations, nœuds, étendues et rôles</span><span class="sxs-lookup"><span data-stu-id="0f764-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f764-128">Table</span><span class="sxs-lookup"><span data-stu-id="0f764-128">Table</span></span></th>
<th><span data-ttu-id="0f764-129">Description</span><span class="sxs-lookup"><span data-stu-id="0f764-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f764-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-p103">Contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal. Cette table est statique. Elle est configurée lors de la création de la base de données et n’est pas modifiée.</span><span class="sxs-lookup"><span data-stu-id="0f764-p103">Contains principal types to categorize what is in the tblPrincipal table. This table is static. It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-135">Contient tous les principaux (utilisateurs, dossiers, groupes, etc.).</span><span class="sxs-lookup"><span data-stu-id="0f764-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="0f764-136">Le serveur de conversation permanente gère cela en tant que liste hétérogène plate.</span><span class="sxs-lookup"><span data-stu-id="0f764-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="0f764-137">De nombreuses colonnes sont basées sur le type de chaque principal.</span><span class="sxs-lookup"><span data-stu-id="0f764-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="0f764-138">La plupart de ces principaux sont des copies mises en cache d’objets stockés dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f764-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="0f764-139">La création de la copie mise en cache dans la table principale de ces objets Active Directory est appelée <em>mise en service</em>.</span><span class="sxs-lookup"><span data-stu-id="0f764-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="0f764-140">Certains principaux sont créés de manière plus agressive que d’autres, et certains objets Active Directory ne sont pas pris en compte.</span><span class="sxs-lookup"><span data-stu-id="0f764-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-142">Contient les affiliations principales qui décrivent les appartenances aux groupes de sécurité Active Directory, aux conteneurs Active Directory, etc.</span><span class="sxs-lookup"><span data-stu-id="0f764-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-143"><a href="lync-server-2013-tblnode.md">tblNode dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-144">Contient le nœud Category, tel qu’il est géré dans le panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0f764-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-145"><a href="lync-server-2013-tblroletype.md">tblRoleType dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-146">Contient des types de rôles et leurs jeux d’autorisations associées.</span><span class="sxs-lookup"><span data-stu-id="0f764-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="0f764-147">Cette table de consultation est statique.</span><span class="sxs-lookup"><span data-stu-id="0f764-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-149">Contient des étendues assignées à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="0f764-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-151">Contient des rôles assignés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="0f764-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-153">Contient les compléments inscrits qui peuvent être associés à des nœuds.</span><span class="sxs-lookup"><span data-stu-id="0f764-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-155">Contient uniquement les attributs &quot;de&quot; visibilité &quot;et&quot; de comportement codés en dur utilisés dans la table tblNode.</span><span class="sxs-lookup"><span data-stu-id="0f764-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-157">Contient les valeurs des attributs de &quot;comportement&quot; « et » de visibilité codés en dur utilisés dans la table tblNode.</span><span class="sxs-lookup"><span data-stu-id="0f764-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="0f764-158">Prises en charge des invitations, des conversations et d’autres clients</span><span class="sxs-lookup"><span data-stu-id="0f764-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f764-159">Table</span><span class="sxs-lookup"><span data-stu-id="0f764-159">Table</span></span></th>
<th><span data-ttu-id="0f764-160">Description</span><span class="sxs-lookup"><span data-stu-id="0f764-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f764-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-162">Contient les invitations de tous les utilisateurs mis en service dans le système pour tous les nœuds ayant la fonction d’invitation automatique activée.</span><span class="sxs-lookup"><span data-stu-id="0f764-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-163"><a href="lync-server-2013-tblchat.md">tblChat dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-164">Contient tous les messages de conversations.</span><span class="sxs-lookup"><span data-stu-id="0f764-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-166">Contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f764-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-168">Contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0f764-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-169"><a href="lync-server-2013-tblpreference.md">tblPreference dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-170">Contient les préférences du client utilisateur (utilisées par les clients hérités uniquement).</span><span class="sxs-lookup"><span data-stu-id="0f764-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-172">Contient des jetons temporaires pour le transfert de fichiers.</span><span class="sxs-lookup"><span data-stu-id="0f764-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="0f764-173">Chaque fois qu’un fichier est chargé ou téléchargé, le service de conversation permanente génère un jeton que le client utilise pour accéder au magasin de fichiers du service Web.</span><span class="sxs-lookup"><span data-stu-id="0f764-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="0f764-174">Prise en charge du serveur</span><span class="sxs-lookup"><span data-stu-id="0f764-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f764-175">Table</span><span class="sxs-lookup"><span data-stu-id="0f764-175">Table</span></span></th>
<th><span data-ttu-id="0f764-176">Description</span><span class="sxs-lookup"><span data-stu-id="0f764-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f764-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-178">Contient les serveurs actifs dans le pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="0f764-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-p108">Contient le verrou d’administrateur permettant d’exécuter des commandes d’administrateur. L’entrée de révision du système dans la table tblSystemRevision est incrémentée après chaque libération de verrou.</span><span class="sxs-lookup"><span data-stu-id="0f764-p108">Contains the administrator lock to run some administrator commands. The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-183">Contient l’entrée du numéro de révision utilisée (avec la table tblAdminLock) pour harmoniser plusieurs serveurs administrateurs.</span><span class="sxs-lookup"><span data-stu-id="0f764-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f764-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-185">Contient les connexions P2P actuelles entre les services de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="0f764-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f764-186"><a href="lync-server-2013-tblconfig.md">tblConfig dans Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0f764-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0f764-187">Contient la configuration du serveur de conversation permanente non prise en charge.</span><span class="sxs-lookup"><span data-stu-id="0f764-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

