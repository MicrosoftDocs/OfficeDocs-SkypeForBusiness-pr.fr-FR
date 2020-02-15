---
title: 'Lync Server 2013 : rapport de distribution des mesures de qualité des médias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Metrics Distribution Report
ms:assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205262(v=OCS.15)
ms:contentKeyID: 48185409
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38adc41aaffcccbb27d4c9105f0fecabcae3c21c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-media-quality-metrics-distribution-report-in-lync-server-2013"></a>Le rapport de distribution des mesures de qualité des médias dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-06_

Le rapport de distribution des mesures de qualité des médias vous permet d’afficher un graphique qui indique les valeurs de distribution pour une mesure de qualité de l’expérience, comme la gigue ou la perte de paquets. Par exemple, supposons que vos utilisateurs effectuent un total de 10 appels téléphoniques ; ces 10 appels indiquent les temps d’aller-retour suivants :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Numéro d’appel</th>
<th>Temps aller-retour (millisecondes)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>2 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>3 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>4 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>5 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>6 </p></td>
<td><p>50</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>4550</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>50</p></td>
</tr>
</tbody>
</table>


La moyenne de ces temps d’aller-retour est de 500 millisecondes (5000 divisée par 10). 500 millisecondes est un temps d’aller-retour extrêmement important ; par conséquent, vous pourriez penser que vous rencontrez un problème sérieux en matière de congestion du réseau. (Les temps d’aller-retour longs sont généralement le résultat des réseaux surchargés.)

En réalité, bien évidemment, 90% de vos appels ont des temps d’aller-retour excellents ; Il y avait simplement un appel incorrect qui a faussé les résultats globaux. Si vous examinez uniquement le temps d’aller-retour moyen, vous pouvez passer à une mauvaise conclusion.

Le rapport de distribution des mesures de qualité des médias vous permet d’éviter de sauter des conclusions erronées en affichant une distribution graphique d’une mesure spécifiée (par exemple, la durée des boucles). Ces graphiques permettent de clarifier le fait que vous avez neuf appels très bons et un très mauvais appel. De la même façon, vous souhaiterez peut-être continuer à étudier cet appel ; Toutefois, le fait que 9 des 10 appels ont été très intéressants indique qu’il n’y a aucune raison de modifier radicalement votre réseau, au moins dans le temps.

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant répertorie les filtres que vous pouvez utiliser avec le rapport de distribution des mesures de qualité des médias.

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
<td><p><strong>Minimum sur l’axe x</strong></p></td>
<td><p>Plus petite valeur à afficher sur l’axe X du graphique.</p></td>
</tr>
<tr class="even">
<td><p><strong>Maximum sur l’axe x</strong></p></td>
<td><p>Valeur la plus élevée à afficher sur l’axe X du graphique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type d’accès</strong></p></td>
<td><p>Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Interne</p></li>
<li><p>Externe</p></li>
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
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Circuit</p></li>
<li><p>Fil</p></li>
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

