---
title: 'Lync Server 2013: rapport audio et vidéo d’égal à égal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b938a5281717528143cfc077a42f51bd68f69bae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Rapport audio et vidéo d’égal à égal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-21_

Le rapport vocal et vidéo d’égal-à-égal offre un examen détaillé de la distribution des appels vocaux et vidéo sur une période donnée (par exemple, les appels par heure ou par jour). Il vous offre également la possibilité de voir tous les appels vocaux et vidéo émis, ou de voir uniquement les appels ayant abouti ou échoué. Le rapport fournit les informations d’appels réparties dans les sections suivantes :

  - Appels par pool

  - Appels par type d’appel (par exemple, appel Lync vers Lync et appel Lync vers une personne du réseau PSTN);

  - Appels par type d’accès (utilisateurs connectés au réseau interne par opposition aux utilisateurs connectés au réseau externe)

  - Appels par serveur de médiation

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Pour accéder au rapport vocal et vidéo d’égal-à-égal

Vous pouvez accéder au rapport vocal et vidéo d’égal-à-égal en ouvrant simplement le rapport de synthèse d’activité d’égal-à-égal, puis en cliquant sur l’une des mesures suivantes :

  - Nombre total de sessions audio P2P

  - Nombre total de minutes audio d’égal-à-égal

  - Nombre total de sessions vidéo P2P

  - Nombre total de minutes vidéo d’égal-à-égal

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Pour une utilisation optimale du rapport vocal et vidéo d’égal-à-égal

Vous pouvez filtrer le rapport vocal et vidéo d’égal-à-égal de différentes manières. Cependant, ces options de filtre sont masquées par défaut. Pour afficher les options de filtre disponibles, cliquez sur le bouton **Afficher/Masquer les paramètres** dans le coin supérieur droit de la fenêtre du rapport.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport vocal et vidéo P2P.

### <a name="peer-to-peer-voice-and-video-report-filters"></a>Filtres du rapport vocal et vidéo d’égal-à-égal

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
<tr class="even">
<td><p><strong>Type de média</strong></p></td>
<td><p>Indique le type de média utilisé dans la session. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Les deux</p></li>
<li><p>Audio</p></li>
<li><p>Vidéo</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Distribution des appels</strong></p></td>
<td><p>Indique la réussite ou l’échec de la session. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Appels ayant abouti</p></li>
<li><p>Appels n’ayant pas abouti</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Établir un rapport par</strong></p></td>
<td><p>Indique les valeurs à utiliser dans le rapport. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Nombre de sessions</p></li>
<li><p>Minutes d’appel</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Mesures de l’activité vocale et vidéo P2P par pool

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo P2P pour chaque pool.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Mesures de l’activité vocale et vidéo P2P par pool

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
<td><p>Nom du pool d’inscriptions ou du serveur Edge utilisés pour l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles l’appel s’est produit.</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Mesures de l’activité vocale et vidéo P2P par type d’appel

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo P2P pour chaque type d’appel émis.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Mesures de l’activité vocale et vidéo P2P par type d’appel

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
<td><p><strong>Type d’appel</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique le type d’appel émis. Les valeurs correspondent à l’une des options suivantes :</p>
<ul>
<li><p>UC à UC</p></li>
<li><p>UC à RTC</p></li>
<li><p>RTC à UC</p></li>
<li><p>RTC à RTC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles l’appel s’est produit.</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Mesures de l’activité vocale et vidéo P2P par type d’accès

Le tableau qui suit dresse la liste des informations fournies dans le rapport vocal et vidéo P2P pour chaque type d’accès réseau.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Mesures de l’activité vocale et vidéo P2P par type d’accès

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
<td><p><strong>Type d’activité</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique si les clients étaient connectés au réseau interne ou au réseau externe au moment de passer l’appel. Les valeurs correspondent généralement à l’une des options suivantes :</p>
<ul>
<li><p>Interne</p></li>
<li><p>Externe</p></li>
<li><p>Mixte</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles l’appel s’est produit.</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Mesures de l’activité vocale et vidéo P2P par serveur de médiation

Le tableau suivant répertorie les informations fournies dans le rapport audio et vidéo d’égal à égal pour chaque serveur de médiation.

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Mesures de l’activité vocale et vidéo P2P par serveur de médiation

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
<td><p><strong>Serveur de médiation</strong></p></td>
<td><p>Non</p></td>
<td><p>Nom du serveur de médiation.</p></td>
</tr>
<tr class="even">
<td><p><strong>Date/Heure</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure auxquelles l’appel s’est produit.</p></td>
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

