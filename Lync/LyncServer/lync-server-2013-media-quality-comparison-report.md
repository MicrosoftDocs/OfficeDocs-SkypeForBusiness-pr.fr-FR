---
title: 'Lync Server 2013 : rapport de comparaison de la qualité multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bcec69db6154aa346fc4545dc3b50fcfe0f2d6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Rapport de comparaison de qualité multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-04-22_

Le rapport comparatif de la qualité des médias vous permet de comparer les valeurs de qualité des appels pour différents types d’appels audio (par exemple, des appels passés sur un réseau sans fil par rapport à ceux effectués via une connexion câblée).

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>Accès au rapport comparatif de la qualité des médias

Le rapport comparatif de la qualité des médias est accessible à partir de la page d’accueil des rapports de surveillance.

</div>

<div>

## <a name="filters"></a>Filtres

Les filtres vous offrent la possibilité de retourner un ensemble de données mieux ciblées ou de visualiser les données retournées de différentes manières. Le tableau suivant dresse la liste des filtres que vous pouvez utiliser avec le rapport comparatif de la qualité des médias.

### <a name="media-quality-comparison-report-filters"></a>Filtres du rapport comparatif de la qualité des médias

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
<td><p><strong>Appels</strong></p></td>
<td><p>Type d’appel à utiliser en tant que principal élément de comparaison. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Externe</p></li>
<li><p>Interne</p></li>
<li><p>VPN</p></li>
<li><p>Non-VPN</p></li>
<li><p>Câblé</p></li>
<li><p>Sans fil</p></li>
<li><p>Externe et câblé</p></li>
<li><p>Externe et sans fil</p></li>
<li><p>Externe et VPN</p></li>
<li><p>Externe et non VPN</p></li>
<li><p>Interne et câblé</p></li>
<li><p>Interne et sans fil</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Comparer avec les appels</strong></p></td>
<td><p>Type d’appel à utiliser en tant qu’élément de comparaison secondaire. Les valeurs autorisées sont les suivantes :</p>
<ul>
<li><p>[Tous]</p></li>
<li><p>Externe</p></li>
<li><p>Interne</p></li>
<li><p>VPN</p></li>
<li><p>Non-VPN</p></li>
<li><p>Câblé</p></li>
<li><p>Sans fil</p></li>
<li><p>Externe et câblé</p></li>
<li><p>Externe et sans fil</p></li>
<li><p>Externe et VPN</p></li>
<li><p>Externe et non VPN</p></li>
<li><p>Interne et câblé</p></li>
<li><p>Interne et sans fil</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalle</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p>
<ul>
<li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li>
<li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li>
<li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li>
</ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle quotidien avec une date de début de 7/7/2012 et une date de fin de 2/28/2012, les données sont affichées pour les jours de 8/7/2012 12:00 AM à 9/7/2012 12:00 AM (c’est-à-dire un total de 31 jours de données).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport comparatif de la qualité des médias.

### <a name="media-quality-comparison-report-metrics"></a>Mesures du rapport comparatif de la qualité des médias

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
<td><p>Taux moyen de dégradation de la note MOS (note moyenne d’opinion) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée) ; une valeur inférieure ou égale à 0,5 indique une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion étaient calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Lync Server utilise un ensemble d’algorithmes pour prévoir la façon dont les utilisateurs auraient noté un appel.</p>
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
<td><p>Temps moyen (en millisecondes) nécessaire à un paquet RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 200 millisecondes ou moins sont considérées qualitativement acceptables.</p>
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
<td><p>Gigue moyenne détectée entre les arrivées de paquets RTP. (Gigue est une mesure du &quot;shakiness&quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, ce qui a pour effet de déformer ou de perdre du son.</p></td>
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

