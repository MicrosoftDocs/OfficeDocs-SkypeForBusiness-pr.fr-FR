---
title: 'Lync Server 2013 : rapport de messagerie instantanée d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e2cf987c40279a4854b9fe776c1585247d24e55
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Rapport de messagerie instantanée d’égal à égal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Le rapport de messagerie instantanée d’égal à égal fournit des informations de tendance sur les sessions de messagerie instantanée d’égal à égal, ventilées par pool et par type d’authentification. Le rapport peut indiquer le nombre total de sessions détenues pendant la période spécifiée (par exemple, Day-by-Day ou Hour-on-Hour) ou le nombre total de messages instantanés envoyés au cours de cette période.

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>Accès au rapport de messagerie instantanée P2P

Vous pouvez accéder au rapport de messagerie instantanée d’égal à égal uniquement en ouvrant le [rapport de synthèse des activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-summary-report.md) , puis en cliquant sur l’une des mesures suivantes :

  - Nombre total de sessions de messagerie instantanée d’égal à égal

  - Nombre total de messages de messagerie instantanée d’égal à égal

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>Utilisation optimale du rapport de messagerie instantanée d’égal à égal

Par défaut, le rapport de messagerie instantanée d’égal à égal vous indique le nombre de messages par heure (ou jour, selon vos paramètres). Toutefois, vous pouvez également choisir d’afficher le jour par sessions par heure. Pour ce faire, cliquez sur **Masquer/afficher les paramètres** dans le coin supérieur droit de la fenêtre rapports, puis cliquez sur **nombre de sessions** dans la liste **rapport par** .

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de messagerie instantanée d’égal à égal.

### <a name="peer-to-peer-im-report-filters"></a>Filtres de rapport de messagerie instantanée d’égal à égal

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
<td><p>Date et heure de début de la période. Pour afficher les données par heure, entrez à la fois la date et l’heure de début comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>7/7/2012</p>
<p>Pour afficher les valeurs par semaine ou mois, entrez une date située n’importe où dans la semaine ou le mois (vous n’avez pas besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>07/07/2012 13:00</p>
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
<p>Si les dates de début et de fin dépassent le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début 7/8/2012 et une date de fin 28/9/2012, les données sont affichées pour les jours 7/8/2012 12:00 AM à 7/9/2012 12:00 AM (c’est-à-dire un total de 31 jours de données pertinentes).</p></td>
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


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Mesures pour une session de messagerie instantanée d’égal à égal par pool

Le tableau suivant répertorie les informations fournies dans le rapport de messagerie instantanée d’égal à égal.

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>Mesures pour une session de messagerie instantanée d’égal à égal par pool

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
<td><p>Nom du pool de serveurs d’inscriptions ou du serveur Edge.</p></td>
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


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Mesures de la session de messagerie instantanée d’égal à égal par type d’authentification

Le tableau suivant répertorie les informations fournies dans le rapport de messagerie instantanée d’égal à égal pour chaque type d’authentification utilisé par les participants dans une session d’égal à égal.

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>Mesures de la session de messagerie instantanée d’égal à égal par type d’authentification

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
<td><p><strong>Type d’authentification type</strong></p></td>
<td><p>Non</p></td>
<td><p>Type d’authentification utilisé par les participants de la session. Les valeurs correspondent généralement à l’une des options suivantes :</p>
<ul>
<li><p>Entreprise</p></li>
<li><p>Fédération</p></li>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

