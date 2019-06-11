---
title: 'Rapport de distribution de métriques de qualité multimédia Lync Server 2013:'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1d814fd001f3510a7ae83e63746bdc1265932e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Rapport de distribution des métriques de qualité multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-06-06_

Le rapport de distribution des mesures de qualité des médias vous permet de consulter un graphique qui affiche les valeurs de distribution pour une mesure de la qualité de l’expérience, comme la gigue ou la perte de paquets. Par exemple, supposons que vos utilisateurs passent un total de 10 appels téléphoniques. Ces 10 appels présentent les délais d’aller-retour suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numéro de l’appel</th>
<th>Durée d’aller-retour (millisecondes)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>version8</p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>09</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>0,10</p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


La moyenne de ces temps d’aller-retour est de 500 millisecondes (5000 divisée par 10). 500 millisecondes est une durée de roundtrip très importante; par conséquent, il est possible que vous rencontriez un problème sérieux avec la congestion du réseau. (Les temps de roundtrip longs sont généralement le résultat de réseaux surchargés.)

Pour le moment, le nombre de fois que 90% de vos appels avait des temps d’aller-retour exceptionnels. il vous suffit d’un appel incorrect qui a faussé les résultats globaux. Si vous observez uniquement la durée de l’aller-retour moyenne, vous risquez de sauter une erreur de conclusion.

Le rapport de distribution des mesures de qualité des médias vous permet de ne pas tirer de conclusions hâtives et erronées : il vous présente une répartition graphique d’une mesure précise (comme le délai d’aller-retour). Ces graphiques permettent de clarifier la situation, à savoir que vous avez passé neuf appels de très bonne qualité et un de mauvaise qualité. Vous souhaitez peut-être examiner plus en détail cet appel-ci. Cependant, le fait que 9 appels sur 10 étaient de bonne qualité semble indiquer qu’il n’existe aucune raison d’apporter des modifications radicales à votre réseau, au moins pas pour l’instant.

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.

### <a name="media-quality-metrics-distribution-report-filters"></a>Filtres du rapport de distribution des mesures de qualité des médias

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
<td><p><strong>Minimum sur l’axe x</strong></p></td>
<td><p>Plus petite valeur à afficher sur l’axe X du graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>Maximum sur l’axe x</strong></p></td>
<td><p>Plus grande valeur à afficher sur l’axe X du graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type d’accès</strong></p></td>
<td><p>Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Interne</p></li>
<li><p>Externe</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>VPN</p></li>
<li><p>Non-VPN</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Câblé</p></li>
<li><p>Sans fil</p></li>
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

