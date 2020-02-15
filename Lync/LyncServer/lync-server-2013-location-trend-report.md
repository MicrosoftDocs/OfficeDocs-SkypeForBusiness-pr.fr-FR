---
title: 'Lync Server 2013 : rapport de tendance des emplacements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e74cf4e763272f2309e358120abb12b0424aa40b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a>Rapport de tendance des emplacements dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Le rapport de tendance générale des emplacements fournit des informations de tendance sur la qualité des appels pour les emplacements réseau.

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, grâce au rapport de tendance générale des emplacements, vous pouvez filtrer les données retournées selon des éléments précis, tels que le type d’accès (à savoir « accès interne » par comparaison à « accès externe ») ou la connexion réseau câblée/sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour ou semaine.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de tendance générale des emplacements.

### <a name="location-trend-report-filters"></a>Filtres du rapport de tendance générale des emplacements

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
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 1/1/2011 et une date de fin le 28/2/2011, les données s’affichent pour les jours compris entre le 1/8/2011 à minuit et le 1/9/2011 à minuit (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Type d’accès</strong></p></td>
<td><p>Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Interne</p></li>
<li><p>Externe</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Circuit</p></li>
<li><p>Fil</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

