---
title: 'Lync Server 2013 : Rapport de synthèse des conférences RTC'
TOCTitle: Rapport de synthèse des conférences RTC
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615014(v=OCS.15)
ms:contentKeyID: 49298030
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de synthèse des conférences RTC dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Dans Microsoft Lync Server 2013, une conférence RTC est une conférence dans laquelle au moins un participant se connecte à la partie audio en utilisant un téléphone RTC (réseau téléphonique commuté). (Un téléphone RTC est une ligne fixe, un téléphone mobile ou un autre téléphone qui n’utilise pas Voice over IP.) Ces conférences RTC indiquées dans les rapports de surveillance, sont plus connues sous le nom de conférences rendez-vous.

Le rapport de synthèse de conférence RTC fournit des informations sur toutes les conférences RTC qui ont lieu au sein de votre organisation (c’est-à-dire, toutes les conférences comportant au moins un utilisateur connecté). Ce rapport comprend des informations sur le nombre total de conférences RTC, le nombre total de personnes ayant participé à ces conférences, et, peut-être plus important, le nombre total d’utilisateurs connectés (la mesure Nombre total de participants RTC).

## Accès au rapport de synthèse de conférence RTC

Le rapport de synthèse de conférence RTC est accessible uniquement à partir de la page d’accueil Rapports de surveillance. Ce rapport n’est lié à aucun autre rapport. Vous ne pouvez pas obtenir d’informations détaillées sur les appels pour une conférence RTC, en partie parce que les points de terminaison individuels sont responsables de l’envoi de ces informations. Les téléphones RTC ne sont pas capables d’effectuer le suivi ou d’envoyer des informations détaillées sur les appels.

## Utilisation efficace du rapport de synthèse de conférence RTC

Pour déterminer le pourcentage de vos conférences qui comportent des utilisateurs connectés, comparez la valeur de la mesure Nombre total de participants RTC et la mesure Nombre total de conférences du [Rapport de synthèse de conférence dans Lync Server 2013](lync-server-2013-conference-summary-report.md).

Si les conférences RTC que vous vous attendiez à voir ne s’affichent pas, n’oubliez pas que la possibilité d’organiser une conférence qui autorise les utilisateurs connectés dépend de la stratégie de conférence affectée à un utilisateur : si peu d’utilisateurs sont autorisés à organiser des conférences RTC, vous verrez peu de conférences RTC. Vous pouvez vérifier rapidement les stratégies de conférence qui autorisent les utilisateurs à planifier des conférences RTC en exécutant la commande suivante avec Lync Server Management Shell :

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

Des données semblables à ceci sont renvoyées :

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

Des données semblables à ceci sont renvoyées :

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de synthèse des conférences RTC vous permet de choisir la façon dont les données doivent être groupées. Dans ce cas, les conférences sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse des conférences RTC.

### Filtres du rapport de synthèse des conférences RTC

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
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
<li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de synthèse des conférences RTC

### Mesures du rapport de synthèse des conférences RTC

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
<p><strong>Tous les jours</strong></p>
<p><strong>Toutes les semaines</strong></p>
<p><strong>Tous les mois</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps sélectionné. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, une répartition par jour de l’activité d’enregistrement utilisateur est affichée pour cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de conférences RTC</strong></p></td>
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
<td><p><strong>Nombre total de participants RTC</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs qui se sont connectés à des conférences ayant autorisé l’accès de rendez-vous.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nombre total de minutes par participant RTC</strong></p></td>
<td><p>Non</p></td>
<td><p>Durée totale de conférence passée par les utilisateurs de rendez-vous. Par exemple, si un participant de rendez-vous a passé cinq minutes dans une conférence et qu’un autre participant a passé trois minutes dans la même conférence, la durée totale de participants RTC sera de huit minutes.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organisateurs de conférence uniques</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’utilisateurs qui ont organisé au moins une conférence ayant autorisé l’accès de rendez-vous. Les utilisateurs qui ont organisé plusieurs conférences sont comptabilisés comme un organisateur unique, tout comme les utilisateurs ayant organisé une seule conférence.</p></td>
</tr>
</tbody>
</table>

