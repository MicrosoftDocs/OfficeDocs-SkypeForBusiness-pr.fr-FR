---
title: 'Lync Server 2013 : rapport de diagnostic de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Diagnostic Report
ms:assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615042(v=OCS.15)
ms:contentKeyID: 48185901
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c4489e13f794a924e1512a1e6ed7b32f73da8f1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525991"
---
# <a name="conference-diagnostic-report-in-lync-server-2013"></a>Rapport de diagnostic de conférence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Le rapport de diagnostic de conférence fournit des informations sur la réussite et l’échec de toutes les sessions de conférence. Notez que Microsoft Lync Server différencie les différents types de défaillances :

  - **Échec attendu**. Un échec attendu est en général un échec considéré comme strictement technique. Par exemple, supposons qu’un utilisateur démarre une conférence mais raccroche avant que quiconque puisse s’y joindre. Techniquement, c’est une erreur : la Conférence a été lancée, mais n’a pas été terminée. Toutefois, cela peut se produire : si l’organisateur annule la Conférence avant que tout le monde ne puisse participer, vous ne vous attendez pas à ce que la Conférence soit terminée.

  - **Échec inattendu**. Comme son nom l’indique, une erreur inattendue est une erreur que vous  n’attendiez pas selon les circonstances. Par exemple, supposons qu’une conférence n’a pas pu être maintenue car la stratégie de réunion de l’organisateur n’a pas pu être récupérée. Il s’agit d’une erreur inattendue : après tout, vous devriez toujours pouvoir récupérer la stratégie de réunion d’un utilisateur.

Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, vous pouvez voir les valeurs suivantes dans le rapport :


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Réussites</th>
<th>Échecs attendus</th>
<th>Échecs inattendus</th>
<th>Total des sessions</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2024</p></td>
<td><p>469</p></td>
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Si vous ajoutez 2024 + 469 + 16, vous obtenez un total de 2 509 sessions et pourtant, la colonne nombre total de sessions affiche un total de 2 521 sessions. Les 12 sessions « manquantes » pour les sessions que le système n’a pas pu catégoriser comme réussies ou infructueuses. C’est parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier du serveur de surveillance. Lorsque cela arrive, les appels effectués à l’aide de ce produit, et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.

<div>

## <a name="accessing-the-conference-diagnostic-report"></a>Accès au rapport de diagnostic de conférence

Le rapport de diagnostic de conférence est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) en cliquant sur l’une des mesures suivantes :

  - Volume d’échecs inattendus

  - Volume d’échecs attendus

</div>

<div>

## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Utilisation optimale du rapport de diagnostic de conférence

Le rapport de diagnostic de conférence inclut une série de graphiques. Chacune des colonnes affichées dans le graphique est un lien hypertexte. Si vous cliquez sur une colonne, vous accédez au rapport de [répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) pendant cette période de temps et ce type de conférence.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de diagnostic de conférence vous permet de filtrer des éléments tels que le type de conférence en cours (par exemple, une conférence basée sur le focus) ou par le serveur Edge utilisé dans la Conférence. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.

Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de diagnostic de conférence.

### <a name="conference-diagnostic-report-filters"></a>Filtres du rapport de diagnostic de conférence

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
<td><p><strong>Interval</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions. Vous pouvez soit sélectionner un pool particulier, soit cliquer sur <strong>[Tous]</strong> pour afficher les données de tous les pools. Cette liste déroulante se renseigne automatiquement en fonction des enregistrements que contient la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sessions de conférence</strong></p></td>
<td><p>Indique le type de session de conférence. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Sessions Focus</p></li>
<li><p>Toutes les sessions MCU</p></li>
<li><p>Conférence par messagerie instantanée</p></li>
<li><p>Partage d’application</p></li>
<li><p>Conférence A/V</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le rapport de diagnostic de conférence pour chaque type de session de conférence.

### <a name="conference-diagnostic-report-metrics"></a>Mesures du rapport de diagnostic de conférence

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
<td><p><strong>Volume d’opération réussie</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences réussies.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’opération réussie</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences qui ont rencontré des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume d’échec attendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences pour lesquelles une &quot; défaillance attendue &quot; s’est produite.</p>
<p>Un échec attendu est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec attendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences ayant rencontré une erreur attendue. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume d’échec inattendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences pour lesquelles une &quot; défaillance inattendue &quot; s’est produite.</p>
<p>Un échec inattendu se produit dans un système sain. Par exemple, un appel ne doit pas se terminer si l’appelant l’a mis en attente. Le cas échéant, cela serait marqué comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec inattendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences ayant rencontré une erreur inattendue. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences, y compris les conférences réussies, les conférences ayant échoué (échecs attendus et échecs inattendus) et les conférences non classées.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

