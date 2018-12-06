﻿---
title: 'Lync Server 2013 : Rapport de messagerie instantanée P2P'
TOCTitle: Rapport de messagerie instantanée P2P
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558620(v=OCS.15)
ms:contentKeyID: 49296404
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de messagerie instantanée P2P dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport de messagerie instantanée P2P fournit les tendances des sessions de messagerie instantanée P2P, par pool et par type d’authentification. Le rapport peut afficher le nombre total de sessions tenues pendant une période donnée (par exemple, jour par jour ou heure par heure) ou le nombre total de messages instantanés envoyés au cours de cette période.

## Accès au rapport de messagerie instantanée P2P

Vous pouvez accéder au rapport de messagerie instantanée P2P en ouvrant le [Rapport de synthèse des activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) et en cliquant sur une des mesures suivantes :

  - Nombre total de sessions de messagerie instantanée P2P

  - Nombre total de messages de messagerie instantanée P2P

## Utilisation optimale du rapport de messagerie instantanée P2P

Par défaut, le rapport de messagerie instantanée P2P vous montre le nombre de messages par heure (ou par jour, selon vos paramètres). Vous pouvez toutefois également afficher le nombre de sessions par heure sur une journée. Pour ce faire, cliquez sur **Afficher/Masquer les paramètres** dans l’angle supérieur droit de la fenêtre Rapports, puis cliquez sur **Nombre de sessions** dans la liste **Établir un rapport par** .

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau ci-dessous dresse la liste des filtres que vous pouvez utiliser avec le rapport de messagerie instantanée P2P.

### Filtres du rapport de messagerie instantanée P2P

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
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
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
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début 7/8/2012 et une date de fin 28/9/2012, les données sont affichées pour les jours compris entre le 7/8/2012 à 12 h 00 et le 7/9/2012 à 12 h 00 (c’est-à-dire un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Établir un rapport par</strong></p></td>
<td><p>Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Nombre de sessions</p></li>
<li><p>Nombre de messages</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Mesure d’une session de messagerie instantanée P2P par pool

Le tableau qui suit répertorie les informations fournies dans le rapport de messagerie instantanée P2P.

### Mesure d’une session de messagerie instantanée P2P par pool

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
<td><p>Nom du pool de serveurs d’inscriptions ou serveur Edge.</p></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure des sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ou de messages.</p></td>
</tr>
</tbody>
</table>


## Mesure d’une session de messagerie instantanée P2P par type d’authentification

Le tableau ci-dessous dresse la liste des informations fournies dans le rapport de messagerie instantanée P2P pour chaque type d’authentification utilisé par les participants dans une session P2P.

### Mesure d’une session de messagerie instantanée P2P par type d’authentification

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
<td><p><strong>Type d’authentification</strong></p></td>
<td><p>Non</p></td>
<td><p>Type d’authentification utilisé par les participants de la session. Les valeurs sont généralement l’une des valeurs suivantes :</p>
<ul>
<li><p>Entreprise</p></li>
<li><p>Fédéré</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure des sessions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions ou de messages.</p></td>
</tr>
</tbody>
</table>

