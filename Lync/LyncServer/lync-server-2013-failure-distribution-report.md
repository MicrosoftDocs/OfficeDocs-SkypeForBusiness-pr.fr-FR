---
title: 'Lync Server 2013 : rapport de répartition des défaillances'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure Distribution Report
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558635(v=OCS.15)
ms:contentKeyID: 48183849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 291097d645884d4c5146b48a69e5355db71e2193
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failure-distribution-report-in-lync-server-2013"></a>Rapport de répartition des défaillances dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-21_

Le rapport de répartition des défaillances classe les sessions ayant échoué selon les catégories suivantes :

  - Principales raisons de diagnostic

  - Modalités principales

  - Pools principaux

  - Principales sources

  - Composants principaux

  - Utilisateurs principaux

  - Principaux pour les utilisateurs

  - Principaux des agents utilisateurs

Vous pouvez utiliser ces catégories pour déterminer exactement où un problème se produit et, dans certains cas, pourquoi le problème se produit. Par exemple, supposons que vous avez enregistré 242 sessions audio/vidéo ayant échoué au cours d’une journée donnée. Si vous examinez le rapport de répartition des défaillances, il peut indiquer que 237 de ces échecs de session ont eu lieu dans votre pool Dublin. Cela vous permet de commencer quand il s’agit d’effectuer un suivi et de diagnostiquer les causes de ces échecs. Si vous cliquez sur le pool Dublin sous la catégorie **Pools supérieur** , un rapport de répartition des défaillances s’affiche uniquement pour ce pool. Vous pouvez ensuite commencer à analyser la raison pour laquelle le pool de Dublin rencontrait tellement de difficultés.

<div>

## <a name="viewing-the-failure-distribution-report"></a>Affichage du rapport de répartition des défaillances

Vous pouvez accéder au rapport de répartition des défaillances à partir de l’un des rapports suivants en cliquant sur le **volume d’échec attendu** ou la mesure de **volume d’échec inattendu** :

  - [Rapport des principales défaillances dans Lync Server 2013](lync-server-2013-top-failures-report.md)

  - [Rapport de diagnostic de conférence dans Lync Server 2013](lync-server-2013-conference-diagnostic-report.md)

  - [Rapport de diagnostic des activités d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

Dans le rapport de répartition des défaillances, vous pouvez cliquer sur l’une des mesures suivantes pour afficher le [rapport de liste des échecs dans Lync Server 2013](lync-server-2013-failure-list-report.md):

  - Motifs de diagnostic principaux (sessions)

  - Modalités principales (sessions)

  - Pools principaux (sessions)

  - Sources principales (sessions)

  - Composants principaux (sessions)

  - Utilisateurs émetteurs principaux (sessions)

  - Utilisateurs destinataires principaux (sessions)

  - Agents utilisateurs émetteurs principaux (sessions)

</div>

<div>

## <a name="using-the-failure-distribution-report"></a>Utilisation du rapport de répartition des défaillances

En fonction de la taille de votre moniteur et de la résolution de l’écran, il est possible que certaines données affichées dans le rapport de répartition des défaillances soient tronquées lors de l’affichage à l’écran. Cela est particulièrement vrai pour les mesures telles que les agents utilisateur, qui peuvent avoir des étiquettes très longues. Par exemple, un agent utilisateur dont le nom est « UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013) » peut seulement partiellement apparaître à l’écran :

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft EP...

Heureusement, vous pouvez voir l’intégralité de l’étiquette en maintenant votre souris au-dessus de la valeur tronquée.

L’ID de diagnostic est une mesure intéressante que vous pouvez filtrer à l’aide du rapport de répartition des défaillances. Si vous voyez le même ID de diagnostic découpé dans d’autres rapports, vous pouvez filtrer cet ID dans le rapport de répartition des défaillances et obtenir un aperçu très détaillé de l’emplacement exact, et de la fréquence à laquelle cet ID a été signalé pendant une session ayant échoué.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de distribution en échec vous permet de filtrer des éléments tels que le type d’activité (session P2P ou session de conférence) ou par l’ID de diagnostic qui accompagnait chaque session ayant échoué.

Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de répartition des défaillances.

### <a name="failure-distribution-report-filters"></a>Filtres du rapport de répartition des défaillances

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
<td><p><strong>From</strong></p></td>
<td><p>Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
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
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool individuel ou cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante est renseignée automatiquement en fonction des enregistrements de la base de données.</p></td>
</tr>
<tr class="even">
<td><p><strong>Type d’activité</strong></p></td>
<td><p>Type d’activité à filtrer. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Pair à pair</p></li>
<li><p>Salle</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Catégorie de session</strong></p></td>
<td><p>Indique si l’activité en question a réussi ou échoué. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Opération réussie</p></li>
<li><p>Échec attendu</p></li>
<li><p>Échec inattendu</p></li>
</ul>
<p>Un &quot;échec&quot; attendu est un échec qui est attendu. Par exemple, si un utilisateur a défini son statut en Ne pas déranger, vous attendez que tout appel à cette personne échoue. Un &quot;échec&quot; inattendu est un échec qui se produit dans le cas d’un système sain. Par exemple, un appel n’est pas censé s’interrompre lorsque l’appelant est mis en attente. Si cela se produit, l’incident est marqué comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Identificateur unique (sous la forme d’un en-tête ms-diagnostics) joint à un message SIP qui fournit souvent des informations utiles au dépannage des erreurs. Les en-têtes de diagnostic sont facultatifs (il est possible d’avoir des sessions SIP sans ces en-têtes), et ne sont signalés que pour les sessions ayant rencontré des problèmes d’un type ou d’un autre.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-diagnostic-reasons"></a>Mesures pour les principaux motifs de diagnostic

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base de l’ID de diagnostic le plus fréquemment signalé.

### <a name="metrics-for-top-diagnostic-reasons"></a>Mesures pour les principaux motifs de diagnostic

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base des ID de diagnostic. L’ID de diagnostic est un identificateur unique (sous la forme d’un en-tête MS-Diagnostics) joint à un message SIP qui fournit souvent des informations utiles pour résoudre les erreurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales raisons de diagnostic</strong></p></td>
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


</div>

<div>

## <a name="metrics-for-top-modalities"></a>Mesures pour les modalités principales

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des modalités de session ayant rencontré le plus d’échecs.

### <a name="metrics-for-top-modalities"></a>Mesures pour les modalités principales

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif en fonction de l’échec d’une session en fonction du type de session (par exemple, une conférence audio/vidéo ou une session de transfert de fichiers P2P).</p></td>
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


</div>

<div>

## <a name="metrics-for-top-pools"></a>Mesures pour les pools principaux

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des pools ayant rencontré le plus d’échecs.

### <a name="metrics-for-top-pools"></a>Mesures pour les pools principaux

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base du pool de serveurs d’inscriptions ou du serveur Edge sur lequel la session a été effectuée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pools principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom du pool de serveurs d’inscriptions ou du serveur Edge.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par pool de serveurs d’inscriptions ou serveur Edge.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-sources"></a>Mesures pour les principales sources

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des ordinateurs ayant rencontré le plus d’échecs.

### <a name="metrics-for-top-sources"></a>Mesures pour les principales sources

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué par ordinateur.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principales sources</strong></p></td>
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


</div>

<div>

## <a name="metrics-for-top-components"></a>Mesures pour les composants principaux

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances basé sur les composants Microsoft Lync Server 2010 ayant rencontré le plus d’échecs.

### <a name="metrics-for-top-components"></a>Mesures pour les composants principaux

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base du composant Lync Server 2010 (par exemple, ExumRouting, GroupChat ou MediationServer).</p></td>
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


</div>

<div>

## <a name="metrics-for-top-from-users"></a>Mesures pour les utilisateurs principaux

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant rencontré le plus d’échecs lorsqu’ils essaient d’appeler quelqu’un d’autre (appelé « depuis »).

### <a name="metrics-for-top-from-users"></a>Mesures pour les utilisateurs principaux

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a été invité à rejoindre la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Utilisateurs principaux</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’utilisateur invité à rejoindre la session.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par utilisateur.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-top-to-users"></a>Mesures pour les utilisateurs principaux

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base des utilisateurs ayant rencontré le plus d’échecs lorsqu’un autre utilisateur a essayé de les appeler (appelés utilisateurs « à »).


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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base de l’utilisateur qui a initié la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principaux pour les utilisateurs</strong></p></td>
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


</div>

<div>

## <a name="metrics-for-top-user-agents"></a>Mesures pour les principaux agents utilisateur

Le tableau suivant répertorie les informations fournies dans le rapport de répartition des défaillances sur la base du logiciel de point de terminaison ayant rencontré le plus d’échecs.

### <a name="metrics-for-top-user-agents"></a>Mesures pour les principaux agents utilisateur

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
<td><p><strong>Rank</strong></p></td>
<td><p>Non</p></td>
<td><p>Classement relatif des sessions ayant échoué sur la base de l’agent utilisateur (logiciel) impliqué dans la session. Par exemple : RTCC/4.0.0.0/4.0.0.0.</p></td>
</tr>
<tr class="even">
<td><p><strong>Principaux agents utilisateur</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom de l’agent utilisateur impliqué dans la session ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ayant échoué par agent utilisateur.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

