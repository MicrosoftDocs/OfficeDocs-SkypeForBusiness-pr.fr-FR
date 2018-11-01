﻿---
title: 'Lync Server 2013 : Rapport des activités de conférence'
TOCTitle: Rapport des activités de conférence
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558627(v=OCS.15)
ms:contentKeyID: 49296513
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport des activités de conférence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport des activités de conférence vous permet de répondre facilement à des questions telles que : combien y a-t-il de conférences organisées chaque jour et à quel moments ces conférences sont-elles organisées ? Ce genre d’information n’est pas seulement utile en tant que tel, il peut également permettre de résoudre des problèmes. Par exemple, imaginons que des utilisateurs se plaignent de la lenteur du réseau en milieu de journée. Un coup d’œil rapide aux rapports des activités de conférence vous permet de voir une raison possible : un plus grand nombre de conférences sont planifiées entre 10:00 et 14:00 qu’à tout autre moment de la journée.

Si la lenteur du réseau engendre des problèmes, vous pouvez encourager les utilisateurs à replanifier certaines de leurs conférences à un moment de la journée où le trafic est moins important.

## Accès au rapport des activités de conférence

Vous pouvez accéder au rapport des activités de conférence à partir du [Rapport de synthèse de conférence dans Lync Server 2013](lync-server-2013-conference-summary-report.md) en cliquant sur l’une des métriques suivantes :

  - Nombre total de conférences

  - Nombre total de participants

## Utilisation optimale du rapport des activités de conférence

Par défaut, le rapport des activités de conférence indique le nombre total de conférences pour une période spécifiée (par exemple, le nombre total de conférences par jour ou le nombre total de conférences par heure pour une journée). Cependant, vous pouvez choisir d’afficher également le nombre total de participants pour cette même période ou le nombre total de minutes de participant. Pour ce faire, cliquez sur le bouton Afficher/Masquer les paramètres pour afficher les options de filtrage, puis en sélectionner une dans la liste déroulante Établir un rapport par :

  - Nombre de participants

  - Minutes de participant

  - Nombre de conférences

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport des activités de conférence.

### Filtres du rapport des activités de conférence

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
<tr class="even">
<td><p><strong>Établir un rapport par</strong></p></td>
<td><p>Indique les valeurs qu’il convient d’utiliser dans le rapport. Vous pouvez sélectionner l’une des valeurs suivantes :</p>
<ul>
<li><p>Nombre de participants</p></li>
<li><p>Minutes de participant</p></li>
<li><p>Nombre de conférences</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Mesure des conférences par pool

Le tableau qui suit répertorie les informations dans le rapport des activités de conférence pour chaque pool.

### Mesure des conférences par pool

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
<td><p><strong>Pool</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom du pool de serveurs d’inscriptions ou du serveur Edge utilisés dans la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles la conférence s’est tenue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de participants, nombre total de minutes par participant ou nombre total de conférences.</p></td>
</tr>
</tbody>
</table>


## Mesure des conférences par type de serveur

Le tableau qui suit répertorie les informations dans le rapport des activités de conférence pour chaque type de serveur.

### Mesure des conférences par type de serveur

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
<td><p><strong>Type de serveur de conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Type de serveur utilisé dans la conférence, généralement l’un des types suivants :</p>
<ul>
<li><p>Serveur de conférence web</p></li>
<li><p>Service de conférence de messagerie instantanée</p></li>
<li><p>Service de téléconférence</p></li>
<li><p>Serveur de conférence A/V</p></li>
<li><p>Partage d’application</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles la conférence s’est tenue.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de participants, nombre total de minutes par participant ou nombre total de conférences.</p></td>
</tr>
</tbody>
</table>

