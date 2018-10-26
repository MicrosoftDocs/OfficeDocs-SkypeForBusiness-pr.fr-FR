---
title: 'Lync Server 2013 : Rapport de répartition des défaillances'
TOCTitle: Rapport de répartition des défaillances
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558635(v=OCS.15)
ms:contentKeyID: 49296851
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de répartition des défaillances dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport de répartition des défaillances classe les sessions ayant échoué selon les catégories suivantes :

  - Motifs de diagnostic principaux

  - Modalités principales

  - Pools principaux

  - Sources principales

  - Composants principaux

  - Utilisateurs émetteurs principaux

  - Utilisateurs destinataires principaux

  - Agents utilisateurs émetteurs principaux

Vous pouvez utiliser ces catégories pour rechercher exactement le problème et, dans certains cas, déterminer la raison de ce problème. Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo ayant échoué au cours d’une journée donnée. Si vous examinez le rapport de répartition des défaillances, il peut indiquer que 237 de ces sessions ont eu lieu dans le pool Dublin. C’est un bon point de départ pour rechercher et diagnostiquer les causes à l’origine de ces défaillances. Si vous cliquez sur le pool Dublin sous la catégorie **Pools principaux** , vous y trouverez un rapport de répartition des défaillances spécifique à ce pool. Vous pouvez ensuite commencer à analyser les raisons qui ont entraîné autant de difficultés dans le pool.

## Affichage du rapport de répartition des défaillances

Vous pouvez accéder au rapport de répartition des défaillances à partir de n’importe lequel des rapports suivants en cliquant sur la mesure **Nombre d’échecs attendus** ou **Nombre d’échecs inattendus**  :

  - [Rapport des principales défaillances dans Lync Server 2013](lync-server-2013-top-failures-report.md)

  - [Rapport de diagnostic de conférence dans Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)

  - [Rapport de diagnostic des activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

Dans le rapport de répartition des défaillances, vous pouvez cliquer sur l’une des mesures suivantes pour afficher le [Rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md):

  - Motifs de diagnostic principaux (sessions)

  - Modalités principales (sessions)

  - Pools principaux (sessions)

  - Sources principales (sessions)

  - Composants principaux (sessions)

  - Utilisateurs émetteurs principaux (sessions)

  - Utilisateurs destinataires principaux (sessions)

  - Agents utilisateurs émetteurs principaux (sessions)

## Utilisation du rapport de répartition des défaillances

Selon la taille de votre moniteur et sa résolution d’écran, il est possible que certaines des données indiquées dans le rapport de répartition des défaillances soient tronquées à l’écran. Cela se vérifie en particulier pour les mesures comme les agents utilisateurs qui ont des libellés très longs. Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut ne s’afficher que partiellement à l’écran :

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...

Fort heureusement, vous pouvez voir le libellé en entier en maintenant votre souris au-dessus de la valeur tronquée.

L’ID de diagnostic est une mesure intéressante sur laquelle vous pouvez filtrer dans le rapport de répartition des défaillances. Si le même ID de diagnostic s’affiche dans d’autres rapports, vous pouvez filtrer sur cet ID dans le rapport de répartition des défaillances et obtenir des informations très détaillées sur l’emplacement exact où a été signalé cet ID pendant une session ayant échoué et sa fréquence.

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de répartition des défaillances vous permet de filtrer sur des critères tels que le type d’activité (session entre homologues ou session de conférence) ou à l’aide de l’ID de diagnostic qui a accompagné chaque session ayant échoué.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.

### Filtres du rapport de répartition des défaillances

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>De</strong></p></td>
<td><p>Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou serveur Edge. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</p></td>
</tr>
<tr class="even">
<td><p><strong>Type d’activité</strong></p></td>
<td><p>Type d’activité sur laquelle filtrer. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>P2P</p></li>
<li><p>Conférence</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Catégorie de session</strong></p></td>
<td><p>Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Opération réussie</p></li>
<li><p>Échec attendu</p></li>
<li><p>Échec inattendu</p></li>
</ul>
<p>Un « échec attendu » est un échec prévisible. Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue. Un « échec inattendu » est un échec qui se produit dans un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui fournit souvent des informations utiles pour résoudre des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible que des sessions SIP n’incluent pas ces en-têtes) et les ID de diagnostic sont uniquement signalés pour les sessions qui ont rencontré des problèmes, quels qu’ils soient.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les motifs de diagnostic principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base de l’ID de diagnostic le plus fréquemment signalé.

### Mesures pour les motifs de diagnostic principaux

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base des ID de diagnostic. Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles à l’identification et à la résolution des erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Motifs de diagnostic principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>ID de diagnostic généré dans une session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué où l’ID de diagnostic spécifié a été généré.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les modalités principales

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des modalités de session ayant rencontré le plus d’échecs.

### Mesures pour les modalités principales

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers entre homologues).</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalités principales</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué impliquant la modalité spécifiée.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les pools principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des pools ayant rencontré le plus d’échecs.

### Mesures pour les pools principaux

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base du pool de serveurs d’inscriptions ou du serveur Edge où la session a eu lieu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pools principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom du pool de serveurs d’inscriptions ou serveur Edge.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par pool de serveurs d’inscriptions ou serveur Edge.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les sources principales

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des ordinateurs ayant rencontré le plus d’échecs.

### Mesures pour les sources principales

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué par ordinateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sources principales</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom de l’ordinateur impliqué dans la session ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par ordinateur.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les composants principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des composants Microsoft Lync Server 2010 ayant rencontré le plus d’échecs.

### Mesures pour les composants principaux

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base du composant Lync Server 2010 (par exemple, ExumRouting, GroupChat ou MediationServer).</p></td>
</tr>
<tr class="even">
<td><p><strong>Composants principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom du composant impliqué dans la session ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par composant.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les utilisateurs émetteurs principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant connu le plus d’échecs en essayant d’appeler quelqu’un d’autre (dénommés utilisateurs « De »).

### Mesures pour les utilisateurs émetteurs principaux

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a été invité à se joindre à la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utilisateurs émetteurs principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur invité à se joindre à la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par utilisateur.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les utilisateurs destinataires principaux

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant connu le plus d’échecs après avoir été appelés par quelqu’un d’autre (dénommés utilisateurs « À »).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utilisateurs destinataires principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur ayant initié la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par utilisateur.</p></td>
</tr>
</tbody>
</table>


## Mesures pour les principaux agents d’utilisateur

Le tableau ci-dessous liste les informations fournies dans le rapport de répartition des défaillances sur la base du logiciel de point de terminaison ayant rencontré le plus d’échecs.

### Mesures pour les principaux agents d’utilisateur

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Classement</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base de l’agent d’utilisateur (logiciel) impliqué dans la session. Par exemple : RTCC/4.0.0.0 Inbound Routing/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principaux agents d’utilisateurs</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom de l’agent d’utilisateur impliqué dans la session ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par agent.</p></td>
</tr>
</tbody>
</table>

