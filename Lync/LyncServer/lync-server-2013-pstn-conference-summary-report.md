---
title: 'Lync Server 2013 : rapport de synthèse de conférence RTC'
description: 'Lync Server 2013 : rapport de synthèse de conférence RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN Conference Summary Report
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615014(v=OCS.15)
ms:contentKeyID: 48184764
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3bc468e494577c229562a1cb7cfddaf839f946f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562770"
---
# <a name="pstn-conference-summary-report-in-lync-server-2013"></a>Rapport de synthèse de conférence RTC dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-22_

Dans Microsoft Lync Server 2013, une conférence RTC est une conférence dans laquelle au moins un participant se connecte à la partie audio à l’aide d’un téléphone RTC (réseau téléphonique commuté public). (Un téléphone PSTN est une « ligne fixe », un téléphone cellulaire ou tout autre téléphone qui n’utilise pas le protocole voix sur IP.) Bien qu’appelées conférences RTC dans les rapports de surveillance, ces conférences sont peut-être plus connues sous le nom de conférences rendez-vous.

Le rapport de synthèse de conférence PSTN fournit des informations sur toutes les conférences PSTN qui ont lieu au sein de votre organisation (c’est-à-dire, toutes les conférences comportant au moins un utilisateur connecté). Ce rapport comprend des informations sur le nombre total de conférences PSTN, le nombre total de personnes ayant participé à ces conférences, et, peut-être plus important, le nombre total d’utilisateurs connectés (la mesure Nombre total de participants PSTN).

<div>

## <a name="accessing-the-pstn-conference-summary-report"></a>Accès au rapport de synthèse de conférence PSTN

Le rapport de synthèse de conférence PSTN est accessible uniquement à partir de la page d’accueil Rapports de surveillance. Ce rapport n’est lié à aucun autre rapport. Vous ne pouvez pas obtenir d’informations détaillées sur les appels pour une conférence PSTN, en partie parce que les points de terminaison individuels sont responsables de l’envoi de ces informations. Les téléphones PSTN ne sont pas capables d’effectuer le suivi ou d’envoyer des informations détaillées sur les appels.

</div>

<div>

## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Utilisation efficace du rapport de synthèse de conférence PSTN

Pour déterminer le pourcentage de toutes vos conférences qui incluent des utilisateurs de rendez-vous, comparez la valeur de la mesure nombre total de conférences RTC avec la mesure nombre total de conférences trouvées dans le [rapport de synthèse de conférence dans Lync Server 2013](lync-server-2013-conference-summary-report.md).

Si les conférences PSTN que vous vous attendiez à voir ne s’affichent pas, n’oubliez pas que la possibilité d’organiser une conférence qui autorise les utilisateurs connectés dépend de la stratégie de conférence assignée à un utilisateur : si peu d’utilisateurs sont autorisés à organiser des conférences PSTN, vous verrez peu de conférences PSTN. Vous pouvez vérifier rapidement les stratégies de conférence qui autorisent les utilisateurs à planifier des conférences PSTN en exécutant la commande suivante avec Lync Server Management Shell :

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Les données retournées se présentent ainsi :

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Les données retournées se présentent ainsi :

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse des conférences PSTN vous permet de choisir la façon dont les données doivent être groupées. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des conférences PSTN.

### <a name="pstn-conference-summary-report-filters"></a>Filtres du rapport de synthèse des conférences PSTN

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
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec le 7/8/2012 comme date de début et le 28/9/2012 comme date de fin, les données s’affichent pour les jours compris entre le 7/8/2012 12:00 et le 7/9/2012 12:00 (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des conférences PSTN

### <a name="pstn-conference-summary-report-metrics"></a>Mesures du rapport de synthèse des conférences PSTN

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
<p><strong>Journalière</strong></p>
<p><strong>Hebdomadaire</strong></p>
<p><strong>Mensuelle</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps sélectionné. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, une répartition par jour de l’activité d’enregistrement utilisateur est affichée pour cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de conférences PSTN</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences ayant autorisé l’accès de rendez-vous.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de participants</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de personnes ayant participé à des conférences ayant autorisé l’accès de rendez-vous.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de minutes par conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Durée totale de conférence audio/vidéo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de minutes par participant à la conférence A/V</strong></p></td>
<td><p>Non</p></td>
<td><p>Durée totale de participants audio/vidéo. Par exemple, si un participant a passé cinq minutes dans une conférence A/V et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants de conférences A/V sera de huit minutes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de participants PSTN</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs qui se sont connectés à des conférences ayant autorisé l’accès de rendez-vous.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de minutes par participant PSTN</strong></p></td>
<td><p>Non</p></td>
<td><p>Durée totale de conférence passée par les utilisateurs de rendez-vous. Par exemple, si un participant de rendez-vous a passé cinq minutes dans une conférence et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants PSTN sera de huit minutes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisateurs de conférence uniques</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs qui ont organisé au moins une conférence ayant autorisé l’accès de rendez-vous. Les utilisateurs qui ont organisé plusieurs conférences sont comptabilisés comme un organisateur unique, tout comme les utilisateurs ayant organisé une seule conférence.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

