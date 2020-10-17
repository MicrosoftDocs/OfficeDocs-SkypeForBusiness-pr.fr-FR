---
title: 'Lync Server 2013 : rapport de liste d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call List Report
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615020(v=OCS.15)
ms:contentKeyID: 48184921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d9d437b32907108d5666ef9e1b175c170030585
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526291"
---
# <a name="call-list-report-in-lync-server-2013"></a>Rapport de liste d’appels dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

Le rapport des listes d’appels fournit des mesures de qualité de l’expérience pour les appels individuels émis et reçus dans votre organisation. Notez que les mesures réelles indiquées dépendent de la façon dont vous accédez au rapport de liste d’appels. Par exemple, si vous ouvrez le rapport à partir du [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md), vous verrez des métriques telles que les mesures suivantes, qui sont également signalées dans le rapport de périphérique :

  - Microphone de l’appelant

  - Haut-parleur de l’appelant

  - Microphone de l’appelé

  - Haut-parleur de l’appelé

  - Ratio de la durée du basculement vocal

Toutefois, si vous ouvrez le rapport liste des appels à partir du [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md), vous ne verrez aucune de ces mesures ; au lieu de cela, vous verrez des mesures comme celles-ci :

  - Boucle (ms)

  - Dégradation (MOS)

  - Perte de paquets

  - Gigue (ms)

Il s’agit des mesures indiquées dans le rapport d’emplacement. Toutefois, à partir du rapport liste des appels, vous pouvez toujours cliquer sur la mesure détail pour fournir des informations QoE complètes pour tous les appels.

<div>

## <a name="accessing-the-call-list-report"></a>Accès au rapport de liste d’appels

Le rapport des listes d’appels est accessible à partir des rapports suivants :

  - Le [rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

  - Le [rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

  - Le [rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

  - Le [rapport de performances du serveur dans Lync server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure volume d’appels ou pourcentage d’appels médiocres)

À partir du rapport liste des appels, vous pouvez accéder au [rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) en cliquant sur la mesure détail.

</div>

<div>

## <a name="making-the-best-use-of-the-call-list-report"></a>Utilisation optimale du rapport liste des appels

Si vous ne vous souvenez pas de la mesure des mesures du rapport de liste d’appels (par exemple, temps de commutation de voix), placez votre souris sur l’étiquette de mesure ; une info-bulle s’affiche et vous donne une brève description de la mesure.

</div>

<div>

## <a name="filters"></a>Filtres

Aucun. Vous ne pouvez pas filtrer le rapport de liste d’appels.

</div>

<div>

## <a name="metrics"></a>Mesures

Le tableau suivant répertorie les informations fournies dans le rapport de liste d’appels pour chaque appel.

### <a name="call-list-report-metrics"></a>Mesures du rapport de liste d’appels

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
<td><p><strong>Details</strong></p></td>
<td><p>Non</p></td>
<td><p>Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Caller</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de la personne qui a initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appelé</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse SIP de la personne qui a été appelée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de début</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure de début de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Oui</p></td>
<td><p>Date et heure de fin de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Agent utilisateur de l’appelant</strong></p></td>
<td><p>Oui</p></td>
<td><p>Logiciel utilisé par le point de terminaison de la personne qui a initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agent utilisateur de l’appelé</strong></p></td>
<td><p>Oui</p></td>
<td><p>Logiciel utilisé par le point de terminaison de la personne qui a été appelée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Boucle (ms)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre système d’extrémité. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</p>
<p>Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dégradation (MOS)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Lync Server, Lync Server utilise un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</p>
<p>Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un système d’extrémité surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perte de paquets</strong></p></td>
<td><p>Oui</p></td>
<td><p>Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Scintill</strong></p></td>
<td><p>Oui</p></td>
<td><p>Gigue moyenne du délai d’arrivée entre les paquets RTP. (L’instabilité est une mesure de la &quot; fluctuations &quot; d’un appel.) Les valeurs de gigue élevée sont généralement provoquées par une congestion ou un serveur multimédia surchargé, et entraînent une déviation ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux de masquage de la réparation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux d’étirement de la réparation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux de compression de la réparation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connectivité</strong></p></td>
<td><p>Oui</p></td>
<td><p>Type de liaison de communication sans fil. En règle générale, il s’agit de l’une des valeurs suivantes :</p>
<ul>
<li><p>Transmettre</p></li>
<li><p>Directes</p></li>
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

