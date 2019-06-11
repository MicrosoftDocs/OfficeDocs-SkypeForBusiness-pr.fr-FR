---
title: 'Lync Server 2013: rapport de synthèse des activités d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62bdd1203db471de770ed56cf6377d7a3c651649
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Rapport de synthèse des activités d’égal à égal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-21_

Le rapport de synthèse des activités P2P fournit un aperçu de vos sessions de communication d?’P2P. Une session d’égal à égal implique généralement deux utilisateurs uniquement et ne nécessite pas l’utilisation des services de conférence Lync Server. En comparaison, une conférence implique généralement plus de deux utilisateurs et nécessite l’utilisation de Microsoft Lync Server 2013 Conferencing services. L’activité de conférence est reportée sur le rapport de synthèse de conférence.

Le rapport de synthèse des activités P2P vous aide à répondre à des questions telles que :

  - Combien de messages instantanés P2P mes utilisateurs envoient-ils généralement par jour ?

  - L’un de mes utilisateurs tire-t-il réellement parti des capacités de partage d’application et de transfert de fichiers de Lync Server?

  - Les utilisateurs ont signalé que le réseau semblait lent à certains moments de la journée. Combien de minutes sont consacrées à des sessions audio et vidéo P2P durant ces périodes ?

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Accès au rapport de synthèse des activités P2P

Vous pouvez accéder au rapport de synthèse des activités P2P à partir de la page d’accueil des rapports de surveillance. Pour ouvrir le [rapport de messagerie instantanée d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-im-report.md) , cliquez sur l’une des mesures suivantes:

  - Nombre total de sessions d'égal à égal de messagerie instantanée

  - Nombre total de messages de messagerie instantanée P2P

De même, vous pouvez ouvrir le rapport vocal et vidéo P2P en cliquant sur l’une de ces mesures :

  - Nombre total de sessions d'égal à égal audio

  - Nombre total de minutes par session audio P2P

  - Nombre total de sessions audio P2P

  - Nombre total de minutes par session audio P2P

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Utilisation optimale du rapport de synthèse des activités P2P

En bas du rapport de synthèse des activités P2P, vous trouverez les totaux des mesures telles que le Nombre total de sessions de messagerie instantanée P2P et le Nombre total de messages de messagerie instantanée P2P. Vous obtenez ainsi un rapide résumé des informations détaillées contenues dans le corps du rapport.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse des activités P2P vous permet de choisir le mode de groupement des données. Dans ce cas, les activités sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des activités P2P.

### <a name="peer-to-peer-activity-summary-report-filters"></a>Filtres du rapport de synthèse des activités P2P

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
<p>7/17/12012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/17/12012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/13/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>7/17/12012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/17/12012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/13/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalle</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/17/12012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/12012 12:00 AM à 9/7/12012 12:00 AM (c’est-à-dire un total de 31 jours de données).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des activités P2P.

### <a name="peer-to-peer-activity-summary-report-metrics"></a>Mesures du rapport de synthèse des activités P2P

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
<td><p><strong>Toutes les heures</strong></p>
<p><strong>Jour</strong></p>
<p><strong>Toutes les semaines</strong></p>
<p><strong>Mois</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle quotidien et que vous cliquez sur 7/17/12012, vous pouvez voir une répartition horaire de l’activité d’inscription des utilisateurs à cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de sessions P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions P2P menées, quel qu’en soit le type.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions de messagerie instantanée P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions de messagerie instantanée (IM) P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée P2P pour la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de messages de messagerie instantanée P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de messages instantanés envoyés lors des sessions P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport de messagerie instantanée P2P pour la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions audio P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels audio P2P. Lorsque vous cliquez sur ce champ, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de minutes par session audio P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps total passé dans les sessions audio P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre moyen de minutes par session audio P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps moyen passé dans les sessions audio P2P. Calculé en divisant le temps total des sessions audio par le nombre total de sessions audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de sessions vidéo P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels vidéo P2P. Notez que les sessions vidéo sont également comptées comme des sessions audio : chaque session vidéo est comptée comme une seule session vidéo et une seule session audio. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de minutes par session vidéo P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps total passé dans les sessions vidéo P2P. Lorsque vous cliquez sur cet élément, le rapport vous présente le rapport vocal et vidéo P2P pour la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre moyen de minutes par session vidéo P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps moyen passé dans les sessions vidéo P2P. Calculé en divisant le temps total des sessions vidéo par le nombre total de sessions vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de sessions de transfert de fichiers P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions P2P qui ont inclus des transferts de fichiers.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de sessions de partage d’application P2P</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions P2P qui ont inclus un partage d’application.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

