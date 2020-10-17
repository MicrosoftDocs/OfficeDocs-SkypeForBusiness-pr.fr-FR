---
title: 'Lync Server 2013 : rapport de tendance de la qualité des médias serveur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b40f2c316216b01415b3e58d5d59c97421439d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510301"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a>Rapport de tendance de la qualité des médias serveur dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-12_

Le rapport de tendance générale de la qualité des médias serveur vous permet de comparer de façon graphique la qualité de l’expérience sur 5 serveurs maximum, par exemple le volume d’appel, le pourcentage d’appels médiocres, la perte de paquet et la gigue. Cela permet d’identifier plus facilement les serveurs dont les performances sont médiocres, les serveurs qui sont sous-utilisés ou sur-utilisés.

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a>Accès au rapport de tendance générale de la qualité des médias serveur

Le rapport de tendance générale de la qualité des médias serveur est accessible à partir de l’un des rapports suivants :

  - [Rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure tendance)

  - [Rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) (en cliquant sur la mesure serveur Edge A/V. Si l’appelant ou l’appelé est un serveur, vous pouvez également accéder au rapport de tendance des médias de qualité serveur en cliquant sur le nom du point de terminaison.)

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a>Utilisation efficace du rapport de tendance de la qualité des médias serveur

Lorsque vous cliquez sur la mesure tendance dans le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) pour un serveur spécifique, le rapport de tendance de la qualité des médias serveur s’ouvre. Cependant, vous obtenez une instance vide de ce rapport ; le serveur que vous sélectionnez ne sera pas affiché à l’écran. Vous devez sélectionner ce serveur dans la liste déroulante Serveurs. Notez que la liste déroulante Serveurs propose une option Tout sélectionner. Cette option ne sera pas disponible si vous avez plus de 5 serveurs, en effet le rapport de tendance de la qualité des médias serveur ne peut afficher que 5 serveurs à la fois.

Sur les graphiques affichés par le rapport de tendance de la qualité des médias serveur, les points étiquetés volume d’appels et pourcentage d’appels médiocres sont des lien hypertexte ; un clic sur un point de la courbe ouvre une instance du [rapport de liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) affichant le nombre total d’appels (ou d’appels médiocres) pendant la période spécifiée.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport de tendance de la qualité des médias serveur.

### <a name="server-media-quality-trend-report-filters"></a>Filtres du rapport de tendance de la qualité des médias serveur

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
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec le 7/8/2012 comme date de début et le 28/9/2012 comme date de fin, les données s’affichent pour les jours compris entre le 7/8/2012 12:00 AM et le 7/9/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>Type de serveur</strong></p></td>
<td><p>Type de serveur de l’appel. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>Serveur de médiation</p></li>
<li><p>Serveur de conférence A/V</p></li>
<li><p>Serveur Edge A/V</p></li>
<li><p>Passerelle (serveur de médiation)</p></li>
<li><p>Passerelle (contournement du serveur de médiation)</p></li>
<li><p>Serveur de conférence AS</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Servers</strong></p></td>
<td><p>Nom du serveur de la session ; cette liste déroulante est automatiquement remplie en fonction de la valeur du filtre Type de serveur. Vous pouvez sélectionner jusqu’à 5 serveurs différents lors de la création d’un rapport.</p></td>
</tr>
<tr class="even">
<td><p><strong>Type d’accès</strong></p></td>
<td><p>Indique si le participant était connecté au réseau interne ou à partir d’un réseau externe. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Interne</p></li>
<li><p>Externe</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le participant était connecté. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>Circuit</p></li>
<li><p>Fil</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indique si un participant externe utilisait une connexion VPN lors de la session. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>Tous les</p></li>
<li><p>VPN</p></li>
<li><p>Non VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de tendance de la qualité des médias serveur.

### <a name="server-media-quality-trend-report-metrics"></a>Mesures du rapport de tendance de la qualité des médias serveur

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
<td><p><strong>Volume d’appels</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dégradation (MOS)</strong></p></td>
<td><p>Non</p></td>
<td><p>Taux moyen de dégradation de la note MOS (note moyenne d’opinion) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée) ; une valeur inférieure ou égale à 0,5 indique une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion étaient calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</p>
<p>Les valeurs de dégradation élevées peuvent avoir plusieurs causes : une congestion, un dépassement de la bande passante disponible, une congestion/interférence dans la liaison sans fil ou bien la surcharge d’un serveur multimédia ou d’un système d’extrémité. Ces valeurs se traduisent par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pourcentage d’appels médiocres</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</p></td>
</tr>
<tr class="even">
<td><p><strong>Boucle (ms)</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un point de terminaison. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</p>
<p>Des boucles de durée plus élevée peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les durées d’aller-retour élevées créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perte de paquets</strong></p></td>
<td><p>Non</p></td>
<td><p>Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gigue (ms)</strong></p></td>
<td><p>Non</p></td>
<td><p>Gigue moyenne détectée entre les arrivées de paquets RTP. (L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux de masquage de la réparation</strong></p></td>
<td><p>Non</p></td>
<td><p>Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’étirement de la réparation</strong></p></td>
<td><p>Non</p></td>
<td><p>Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux de compression de la réparation</strong></p></td>
<td><p>Non</p></td>
<td><p>Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

