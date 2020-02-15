---
title: 'Lync Server 2013 : rapport de synthèse de diagnostic des appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Diagnostic Summary Report
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615016(v=OCS.15)
ms:contentKeyID: 48184789
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112a21dbb131e0bd34729584b8fb58399b192f70
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-diagnostic-summary-report-in-lync-server-2013"></a>Rapport de synthèse de diagnostic des appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Le rapport de synthèse de diagnostic des appels fournit une vue d’ensemble des sessions de conférence et des sessions d’égal à égal ayant échoué. Ce rapport comprend le taux d’échecs général pour ces deux types de sessions, et détaille les informations par type de modalité de session :

  - Messagerie instantanée

  - Partage d’application

  - Transfert de fichiers

  - Audio

  - Vidéo

<div>

## <a name="accessing-the-call-diagnostic-summary-report"></a>Accès au rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels est accessible à partir de la page d’accueil Rapports de surveillance. Dans le rapport de synthèse de diagnostic des appels, vous pouvez accéder au [rapport de diagnostic des activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md) en cliquant sur la mesure taux d’échec sous la section Résumé de la session P2P du rapport. Vous pouvez également accéder au [rapport de diagnostic de conférence dans Lync Server 2013](lync-server-2013-conference-diagnostic-report.md) en cliquant sur l’une des mesures de conférence suivantes :

  - Taux d’échec global des sessions

  - Taux d’échec Focus

  - Taux d’échec MCU

</div>

<div>

## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Utilisation efficace du rapport de synthèse de diagnostic des appels

Le rapport de synthèse de diagnostic des appels inclut des graphiques qui comparent les taux d’échec pour les différentes modalités utilisées dans Microsoft Lync Server 2013. Les colonnes de ces graphiques sont en fait des lien hypertexte ; par exemple, si vous cliquez sur la colonne de messagerie instantanée pour les sessions P2P, vous accédez à une instance du rapport de diagnostic des [activités P2P dans Lync Server 2013](lync-server-2013-peer-to-peer-activity-diagnostic-report.md), un rapport qui fournit des détails supplémentaires sur toutes les sessions de messagerie instantanée incluses dans le rapport de synthèse de diagnostic des appels.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Par exemple, le rapport de synthèse de diagnostic des appels vous permet de filtrer selon des éléments tels que le pool de serveurs d’inscriptions ou le serveur Edge utilisé dans la session. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de synthèse de diagnostic des appels.

### <a name="call-diagnostic-summary-report-filters"></a>Filtres de rapport de synthèse de diagnostic des appels

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
<td><p>Nom de domaine complet du pool de serveurs d’inscriptions ou du serveur Edge. Vous pouvez sélectionner un pool spécifique ou cliquer sur <strong>[Tout]</strong> pour afficher des données pour tous les pools. Cette liste déroulante est remplie automatiquement pour vous en fonction des enregistrements de la base de données.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions d’égal à égal

Le tableau suivant décrit les informations fournies dans le rapport de synthèse de diagnostic des appels pour les sessions d’égal à égal (à savoir, celles qui n’impliquent que deux participants).

### <a name="metrics-for-peer-to-peer-sessions"></a>Mesures pour les sessions d’égal à égal

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
<td><p><strong>Nombre total de sessions</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions d’égal à égal ayant eu lieu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’échec</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions d’égal à égal ayant échoué. Lorsque vous cliquez sur cet élément, le rapport affiche le rapport de diagnostic des activités d’égal à égal, qui fournit des informations plus détaillées sur les sessions d’égal à égal ayant échoué.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

Le tableau suivant décrit les informations fournies dans le rapport de diagnostic des appels pour les sessions de conférence (à savoir, celles qui impliquent trois participants ou plus).

### <a name="metrics-for-conferencing-sessions"></a>Mesures pour les sessions de conférence

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
<td><p><strong>Nombre total de conférences</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences ayant eu lieu.</p></td>
</tr>
<tr class="even">
<td><p><strong>Nombre total de sessions de conférence</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions de conférence ayant eu lieu.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec de session global</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage du total de sessions de conférence ayant échoué.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions Focus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de sessions de conférence de focus ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec de focus</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de sessions de conférence de focus ayant échoué.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sessions MCU</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’échec MCU</strong></p></td>
<td><p>Non</p></td>
<td><p>Pourcentage de conférences basées sur un serveur de conférence (anciennement appelé Multipoint Control Unit or MCU) ayant échoué.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

