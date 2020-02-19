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
ms.openlocfilehash: e6d9fe9db5ad22a0d6ad2d68d0afdbd5b0969608
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a>Liste des tables de serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Le schéma de la base de données de conversation permanente se compose des tableaux suivants.

<div>

## <a name="active-directory-sync"></a>Synchronisation Active Directory


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladcookie.md">tblADCookie dans Lync Server 2013</a></p></td>
<td><p>Contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs. Chaque ligne correspond à un domaine des services de domaine Active Directory dont le serveur de conversation permanente surveille activement les modifications. (Seuls les domaines Active Directory qui sont pertinents pour le serveur de conversation permanente sont représentés dans ce tableau.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference dans Lync Server 2013</a></p></td>
<td><p>Contient les modifications d’appartenance aux groupes (membres ajoutés et supprimés) qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory et est l’une des tables temporaires (avec la table tblADUpdates) qui est utilisée dans la première étape de la synchronisation Active Directory.</p>
<p>Les modifications d’appartenance sont stockées, traitées ou les deux, uniquement pour les groupes qui sont répertoriés dans la table tblPrincipal ou qui contiennent déjà des membres répertoriés dans cette dernière.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates dans Lync Server 2013</a></p></td>
<td><p>Contient les modifications apportées aux services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory et est l’une des tables temporaires (avec la table tblPrincipalMemberDifference) qui est utilisée dans la première étape d’Active Directory Synchroni.</p>
<p>Les modifications apportées à Active Directory sont stockées, traitées ou les deux uniquement pour les principaux qui sont déjà répertoriés dans le tableau tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers dans Lync Server 2013</a></p></td>
<td><p>Contient les appartenances de Principal.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta dans Lync Server 2013</a></p></td>
<td><p>Contient les principaux qui doivent être actualisés à partir d’Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations dans Lync Server 2013</a></p></td>
<td><p>Contient des affiliations qui n’ont pas pu être actualisées pour une raison quelconque, généralement en raison d’erreurs d’accès à Active Directory.</p>
<p>Cette table est fournie uniquement à titre indicatif. Son contenu n’est pas utilisé.</p>
<p>Les principaux avec affiliations qui n’ont pas pu être correctement actualisés sont conservés dans la table tblPrincipalMeta et peuvent de nouveau être actualisés.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a>Principaux, affiliations, nœuds, étendues et rôles


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType dans Lync Server 2013</a></p></td>
<td><p>Contient les types principaux qui permettent de catégoriser le contenu de la table tblPrincipal. Cette table est statique. Elle est configurée lors de la création de la base de données et n’est pas modifiée.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipal.md">tblPrincipal dans Lync Server 2013</a></p></td>
<td><p>Contient tous les principaux (utilisateurs, dossiers, groupes, etc.). Le serveur de conversation permanente gère cela en tant que liste hétérogène plate. De nombreuses colonnes sont basées sur le type de chaque principal.</p>
<p>La plupart de ces principaux sont des copies mises en cache d’objets stockés dans Active Directory. La création de la copie mise en cache dans la table principale de ces objets Active Directory est appelée <em>mise en service</em>.</p>
<p>Certains principaux sont créés de manière plus agressive que d’autres, et certains objets Active Directory ne sont pas pris en compte.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations dans Lync Server 2013</a></p></td>
<td><p>Contient les affiliations principales qui décrivent les appartenances aux groupes de sécurité Active Directory, aux conteneurs Active Directory, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode dans Lync Server 2013</a></p></td>
<td><p>Contient le nœud Category, tel qu’il est géré dans le panneau de configuration Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType dans Lync Server 2013</a></p></td>
<td><p>Contient des types de rôles et leurs jeux d’autorisations associées. Cette table de consultation est statique.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal dans Lync Server 2013</a></p></td>
<td><p>Contient des étendues assignées à des nœuds.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole dans Lync Server 2013</a></p></td>
<td><p>Contient des rôles assignés à des nœuds.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList dans Lync Server 2013</a></p></td>
<td><p>Contient les compléments inscrits qui peuvent être associés à des nœuds.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute dans Lync Server 2013</a></p></td>
<td><p>Contient uniquement les attributs &quot;de&quot; visibilité &quot;et&quot; de comportement codés en dur utilisés dans la table tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue dans Lync Server 2013</a></p></td>
<td><p>Contient les valeurs des attributs de &quot;comportement&quot; « et » de visibilité codés en dur utilisés dans la table tblNode.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a>Prises en charge des invitations, des conversations et d’autres clients


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites dans Lync Server 2013</a></p></td>
<td><p>Contient les invitations de tous les utilisateurs mis en service dans le système pour tous les nœuds ayant la fonction d’invitation automatique activée.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblchat.md">tblChat dans Lync Server 2013</a></p></td>
<td><p>Contient tous les messages de conversations.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId dans Lync Server 2013</a></p></td>
<td><p>Contient le dernier ID d’invitation généré (et utilisé dans la table tblPrincipalInvites) pour chaque utilisateur.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbllastchatid.md">tblLastChatId dans Lync Server 2013</a></p></td>
<td><p>Contient le dernier ID de conversation généré (et utilisé dans la table tblChat) pour chaque utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblpreference.md">tblPreference dans Lync Server 2013</a></p></td>
<td><p>Contient les préférences du client utilisateur (utilisées par les clients hérités uniquement).</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblfiletoken.md">tblFileToken dans Lync Server 2013</a></p></td>
<td><p>Contient des jetons temporaires pour le transfert de fichiers. Chaque fois qu’un fichier est chargé ou téléchargé, le service de conversation permanente génère un jeton que le client utilise pour accéder au magasin de fichiers du service Web.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a>Prise en charge du serveur


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Table</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity dans Lync Server 2013</a></p></td>
<td><p>Contient les serveurs actifs dans le pool de serveurs de conversation permanente.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tbladminlock.md">tblAdminLock dans Lync Server 2013</a></p></td>
<td><p>Contient le verrou d’administrateur permettant d’exécuter des commandes d’administrateur. L’entrée de révision du système dans la table tblSystemRevision est incrémentée après chaque libération de verrou.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision dans Lync Server 2013</a></p></td>
<td><p>Contient l’entrée du numéro de révision utilisée (avec la table tblAdminLock) pour harmoniser plusieurs serveurs administrateurs.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblactivepeers.md">tblActivePeers dans Lync Server 2013</a></p></td>
<td><p>Contient les connexions P2P actuelles entre les services de conversation permanente.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblconfig.md">tblConfig dans Lync Server 2013</a></p></td>
<td><p>Contient la configuration du serveur de conversation permanente non prise en charge.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

