---
title: 'Lync Server 2013: rapport de synthèse des conférences'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde91a25d33bac5af8b1759b1fbfc90cfb9bc0ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Rapport de synthèse de conférence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-09-03_

Le rapport de synthèse de conférence fournit une vue d’ensemble de vos sessions de conférence en ligne. En règle générale, une conférence implique plus de 2 utilisateurs et nécessite l’utilisation de Microsoft Lync Server 2013 Conferencing services. En comparaison, une session d’égal à égal implique généralement 2 utilisateurs et ne nécessite pas l’utilisation des services de conférence de Lync Server. Les activités d’égal à égal sont signalées sur le [rapport de synthèse des activités d’égal à égal dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md).

Le rapport de synthèse de conférences ne vous indique pas seulement le nombre de conférences qui ont été tenues au cours d’une période donnée (horaire, quotidienne, hebdomadaire, mensuelle), mais vous indique également le nombre total de personnes qui ont participé à ces conférences et le nombre total de conférences uniques. réunions.

Un organisateur « unique » est une personne qui planifie au moins une conférence. Par exemple, si Pilar Ackerman planifie une conférence, elle compte comme un organisateur unique. Si Ken Myer planifie 148 conférences, il compte aussi comme un organisateur unique. Par exemple, le tableau ci-dessous montre huit conférences programmées, mais uniquement trois organisateurs uniques (Ken Myer, Pilar Arès et David AHS).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organisateur de la conférence</th>
<th>Date de la conférence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Le rapport de synthèse de conférence indique également le nombre de conférences incluant l’audio et/ou la vidéo.

<div>

## <a name="accessing-the-conference-summary-report"></a>Accès au rapport de synthèse de conférence

Le rapport de synthèse de conférence est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez accéder au rapport des activités de conférence en cliquant sur l’une ou l’autre des mesures suivantes :

  - Nombre total de conférences

  - Nombre total de participants

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>Exploiter au mieux le rapport de synthèse de conférence

Les valeurs totales pour la plupart des métriques utilisées sur le rapport de synthèse de la Conférence sont accessibles au bas du rapport. Faites défiler vers le bas pour afficher les valeurs telles que le nombre total de conférences organisées pendant la période spécifiée et le nombre total de personnes ayant participé à ces conférences. Une métrique qui n’est pas totalisée en bas du rapport est le nombre total d’organisateurs de conférences uniques. Pourquoi ? Voici une raison. Imaginons que vous recherchiez un mois de données. Le jour 1, vous avez obtenu 34 organisateurs de conférences uniques. le jour 2, vous avez 27 organisateurs de conférences uniques. Est-ce que cela signifie que vous avez 61 de conférences de conférences uniques depuis deux jours? Pas nécessairement. Après tout, les 27 personnes qui ont organisé des conférences le jour 2 peuvent être parmi les 34 personnes qui ont organisé des conférences le jour 1. Par exemple, dans ce rapport simple, vous remarquerez les conférences de Ken Myer et Pilar Arès programmées sur 7/7/2012 et 7/2/2012:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Organisateur de la conférence</th>
<th>Date de la conférence</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


Pour vous faire une meilleure idée du nombre total d’utilisateurs uniques qui ont organisé des conférences, modifiez votre intervalle de temps. Par exemple, au lieu d’examiner les données par mois, examinez-les par jour.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le Rapport de synthèse de conférence vous permet de choisir le type de groupement des données. Dans le cas présent, les conférences sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de conférence.

### <a name="conference-summary-report-filters"></a>Filtres du rapport de synthèse de conférence

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
<td><p><strong>Intervalle</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau ci-dessous contient les informations fournies par le rapport de synthèse de conférence.

### <a name="conference-summary-report-metrics"></a>Mesures du rapport de synthèse de conférence

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
<td><p>Indique l’intervalle de temps que vous avez sélectionné dans la barre d’outils des filtres. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle quotidien et que vous cliquez sur 7/7/2012, vous pouvez voir une répartition horaire de l’activité d’inscription des utilisateurs à cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de conférences</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences (de quelque type que ce soit) qui se sont tenues. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de participants</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de personnes ayant participé aux conférences. Lorsque vous cliquez sur cet élément, le rapport vous montre le Rapport des activités de conférence pour la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre moyen de participants par conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre moyen de personnes ayant assisté à une conférence donnée. Valeur obtenue en divisant le nombre total de conférences par le nombre total de participants.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de conférences A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences ayant fait usage de son ou de vidéo.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de minutes par conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de minutes consacrées à la conférence audio/vidéo.</p>
<p>Le nombre total de minutes de conférence A/V résume l’ensemble des types de conférences audio/vidéo, y compris: conférences A/V; Conférences de messagerie instantanée; Conférences de partage d’application; Conférences de données; et conférences RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de minutes par participant à la conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de minutes consacrées par les participants à la conférence audio/vidéo. Supposons par exemple, qu’un utilisateur passe 5 minutes dans une conférence audio/vidéo et qu’un deuxième utilisateur y passe 3 minutes, nous obtenons un total de 8 minutes de participant.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre moyen de minutes par conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre de minutes moyen par conférence audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total d’organisateurs uniques de conférences</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs ayant organisé au moins une conférence. Les utilisateurs ayant organisé plusieurs conférences sont comptabilisés comme des organisateurs uniques, à l’instar de ceux qui n’en ont organisées qu’une seule.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de messages de conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de messages instantanés envoyés au cours des conférences.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

