---
title: 'Lync Server 2013 : Liste des tables de serveur de conversation permanente'
TOCTitle: Liste des tables de serveur de conversation permanente
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558628(v=OCS.15)
ms:contentKeyID: 49296618
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste des tables de serveur de conversation permanente dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le schéma de base de données de conversation permanente comprend les tables suivantes.

## Synchronisation Active Directory


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
<td><p>Contient les cookies de synchronisation LDAP (Lightweight Directory Access Protocol) actifs. Chaque ligne correspond à un domaine des services de domaine Active Directory dont serveur de conversations permanentes surveille activement les modifications. (Seuls les domaines Active Directory pertinents pour serveur de conversations permanentes sont représentés dans cette table.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference dans Lync Server 2013</a></p></td>
<td><p>Contient les modifications de l’appartenance de groupe (à la fois des membres ajoutés ou supprimés) qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory ; elle est l’une des tables temporaires (avec la table tblADUpdates) utilisées dans la première étape de synchronisation Active Directory.</p>
<p>Les modifications d’appartenance sont stockées, traitées ou les deux, uniquement pour les groupes répertoriés dans la table tblPrincipal ou qui contiennent déjà des membres répertoriés dans cette dernière.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tbladupdates.md">tblADUpdates dans Lync Server 2013</a></p></td>
<td><p>Contient les modifications apportées à services de domaine Active Directory qui n’ont pas encore été traitées par les dernières étapes de synchronisation Active Directory ; elle est l’une des tables temporaires (avec la table tblPrincipalMemberDifference) utilisées dans la première étape de synchronisation Active Directory.</p>
<p>Les modifications apportées à Active Directory sont stockées, traitées ou les deux, uniquement pour les principaux déjà répertoriés dans la table tblPrincipal.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers dans Lync Server 2013</a></p></td>
<td><p>Contient les appartenances de Principal.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta dans Lync Server 2013</a></p></td>
<td><p>Contient les principaux qui doivent être actualisés à partir Active Directory.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations dans Server 2013</a></p></td>
<td><p>Contient les affiliations qui n’ont pas pu être actualisées pour une raison quelconque, généralement des erreurs d’accès Active Directory.</p>
<p>Cette table est fournie uniquement à titre indicatif. Son contenu n’est pas utilisé.</p>
<p>Les principaux avec affiliations qui n’ont pas pu être correctement actualisés sont conservés dans la table tblPrincipalMeta et peuvent de nouveau être actualisés.</p></td>
</tr>
</tbody>
</table>


## Principaux, affiliations, nœuds, étendues et rôles


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
<td><p>Contient tous les principaux (utilisateurs, dossiers, groupes, etc.). Le serveur de conversations permanentes gère cela comme une liste hétérogène plate. De nombreuses colonnes sont basées sur le type de chaque principal.</p>
<p>La plupart de ces principaux sont des copies cachées d’objets stockés dans Active Directory. La création d’une copie cachée dans la table Principal de ces objets Active Directory est appelée <em>approvisionnement</em> .</p>
<p>Certains principaux sont créés de manière plus énergique que d’autres et certains objets Active Directory sont complètement ignorés.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations dans Lync Server 2013</a></p></td>
<td><p>Contient des affiliations de principaux qui décrivent des appartenances dans les groupes de sécurité Active Directory, les conteneurs Active Directory, etc.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblnode.md">tblNode dans Lync Server 2013</a></p></td>
<td><p>Contient le nœud de catégorie tel qu’il est géré dans le Panneau de configuration Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblroletype.md">tblRoleType dans Lync Server 2013</a></p></td>
<td><p>Contient des types de rôles et leurs jeux d’autorisations associées. Cette table de consultation est statique.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal dans Lync Server 2013</a></p></td>
<td><p>Contient des étendues affectées à des nœuds.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole dans Lync Server 2013</a></p></td>
<td><p>Contient des rôles affectés à des nœuds.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList dans Lync Server 2013</a></p></td>
<td><p>Contient les compléments inscrits qui peuvent être associés à des nœuds.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute dans Lync Server 2013</a></p></td>
<td><p>Contient uniquement les attributs « Visibilité » et « Comportement » codés en dur utilisés dans la table tblNode.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblenumvalue.md">tblEnumValue dans Lync Server 2013</a></p></td>
<td><p>Contient les valeurs des attributs « Visibilité » et « Comportement » codés en dur utilisés dans la table tblNode.</p></td>
</tr>
</tbody>
</table>


## Prises en charge des invitations, des conversations et d’autres clients


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
<td><p>Contient des jetons temporaires pour le transfert de fichiers. Chaque fois qu’un fichier est téléchargé, le service de conversation permanente génère un jeton que le client utilise pour accéder au magasin de fichiers du service web.</p></td>
</tr>
</tbody>
</table>


## Prise en charge du serveur


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
<td><p>Contient les serveurs actifs du pool de serveurs de conversations permanentes.</p></td>
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
<td><p>Contient la configuration non prise en charge du serveur de conversations permanentes.</p></td>
</tr>
</tbody>
</table>

