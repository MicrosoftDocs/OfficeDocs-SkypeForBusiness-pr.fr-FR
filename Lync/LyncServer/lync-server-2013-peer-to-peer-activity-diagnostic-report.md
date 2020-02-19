---
title: 'Lync Server 2013 : rapport de diagnostic des activités d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Diagnostic Report
ms:assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558602(v=OCS.15)
ms:contentKeyID: 48183242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b72e9caec70a31280001875063cd6b7d233c500
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140027"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-diagnostic-report-in-lync-server-2013"></a>Rapport de diagnostic des activités d’égal à égal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Le rapport de diagnostic des activités d’égal à égal fournit des informations sur la réussite ou l’échec des sessions de communication d’égal à égal. Notez que Microsoft Lync Server 2013 différencie les différents types de défaillance :

  - **Échec attendu**. Un échec attendu est en général un échec considéré comme strictement technique. Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit absente de son bureau et ne puisse donc répondre à votre appel. Étant donné que l’appel n’a pas été répondu, il est techniquement considéré comme un échec. En revanche, il s’agit d’un échec attendu : Microsoft Lync Server 2013 ne s’attend pas à ce que vous répondiez au téléphone si vous n’êtes pas disponible pour répondre au téléphone. De même, un échec attendu se produira si vous tentez d’envoyer un message instantané à un utilisateur qui est hors ligne ou qui est connecté à un téléphone qui ne prend pas les messages instantanés.

  - **Échec inattendu**. Comme son nom l’indique, une erreur inattendue est une erreur que vous  n’attendiez pas selon les circonstances. Par exemple, supposons que vous appeliez quelqu’un et que cette personne soit disponible pour répondre à l’appel ; Toutefois, lorsque Lync Server 2013 tente d’acheminer votre appel vers la messagerie vocale, l’appel échoue car la connectivité à la messagerie unifiée Exchange a été perdue. Il s’agit d’une erreur inattendue : car vous vous attendiez à ce que les appels soient toujours dirigés vers la messagerie vocale. En règle générale, les échecs inattendus sont de vrais échecs : ce sont des problèmes auxquels il n’est pas possible de remédier en formant les utilisateurs ou à l’aide de mesures similaires.

Notez que le compte des succès et des échecs attendus et inattendus ne correspond pas nécessairement au compte total des sessions. Par exemple, l’illustration précédente indique les valeurs suivantes :


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
<td><p>16 </p></td>
<td><p>2521</p></td>
</tr>
</tbody>
</table>


Si vous additionnez 2024 + 469 + 16 vous obtenez un total de 2 509 sessions alors que la colonne du total des sessions indique 2 521 sessions. Les 12 sessions « manquantes » sont des sessions que le système n’est pas parvenu à classer comme des succès ou des échecs. C’est parfois le cas lorsqu’un produit tiers introduit un nouveau code de diagnostic qui n’est pas familier à Lync Server. Lorsque cela arrive, les appels effectués à l’aide de ce produit, et qui indiquent ce code de diagnostic, ne peuvent pas toujours être classés comme des succès ou des échecs attendus ou inattendus.

<div>

## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Accès au rapport de diagnostic des activités d’égal à égal

Le rapport de diagnostic des activités d’égal à égal est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au [rapport de répartition des défaillances dans Lync Server 2013](lync-server-2013-failure-distribution-report.md) en cliquant sur l’une des mesures suivantes :

  - Volume d’échecs inattendus

  - Volume d’échecs attendus

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Utilisation optimale du rapport de diagnostic des activités d’égal à égal

Il existe plusieurs manières de filtrer le rapport de diagnostic des activités d’égal à égal mais, par défaut, les options de filtrage sont masquées. Pour les afficher, cliquez sur le bouton Afficher/Masquer les paramètres dans le coin supérieur droit de la fenêtre des rapports. Les options de filtrage s’affichent alors.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de diagnostic des activités d’égal à égal vous permet de filtrer selon des éléments précis, tels que la modalité de session (à savoir messagerie instantanée, transfert de fichiers ou partage d’application). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.

Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de diagnostic des activités d’égal à égal.

### <a name="peer-to-peer-activity-diagnostic-report-filters"></a>Filtres du rapport de diagnostic des activités d’égal à égal

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
<td><p>Nom de domaine complet (FQDN) du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez soit sélectionner un pool individuel soit cliquer sur <strong>[Tous]</strong> pour afficher les données pour tous les pools. La liste déroulante est automatiquement renseignée en fonction des enregistrements de la base de données.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Modalités</strong></p></td>
<td><p>Indique le type d’activité de communication qui a eu lieu. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Messagerie instantanée</p></li>
<li><p>Transfert de fichiers</p></li>
<li><p>Partage d’application</p></li>
<li><p>Audio</p></li>
<li><p>Vidéo</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-per-modality"></a>Mesures (par modalité)

Le tableau suivant dresse la liste des informations fournies dans le rapport de diagnostic des activités d’égal à égal pour chaque modalité.

### <a name="metrics-per-modality"></a>Mesures (par modalité)

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
<td><p>Nombre total des sessions d’égal à égal réussies.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’opération réussie</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage des sessions d’égal à égal qui se sont terminées avec des problèmes importants. Calculé en divisant le volume des opérations réussies par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume d’échec attendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions où une &quot;défaillance&quot; attendue s’est produite.</p>
<p>Un échec attendu est un échec prévisible. Par exemple, si un utilisateur a défini son statut sur Ne pas déranger, les appels passés à cet utilisateur échouent.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec attendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions d’égal à égal lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume d’échec inattendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions où une &quot;défaillance&quot; inattendue s’est produite.</p>
<p>Un échec inattendu se produit dans un système sain. Par exemple, un appel ne doit pas se terminer si l’appelant l’a mis en attente. Le cas échéant, cela serait marqué comme un échec inattendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’échec inattendu</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions d’égal à égal lors desquelles une erreur attendue s’est produite. Calculé en divisant le volume d’échec attendu par le nombre total de sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions qui comprend les sessions réussies, les sessions qui ont échoué (à la fois les échecs attendus et les échecs inattendus) et les sessions non catégorisées.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

