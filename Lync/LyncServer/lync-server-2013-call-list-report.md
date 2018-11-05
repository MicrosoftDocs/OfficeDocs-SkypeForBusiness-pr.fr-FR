---
title: 'Lync Server 2013 : Rapport de la liste d’appels'
TOCTitle: Rapport de la liste d’appels
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615020(v=OCS.15)
ms:contentKeyID: 49298160
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de la liste d’appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport Liste des appels fournit des métriques de Qualité de l’expérience pour chaque appel émis et reçu dans votre organisation. Notez que les mesures réelles indiquées dépendent de la façon dont vous accédez au rapport Liste des appels. Par exemple, si vous ouvrez ce rapport à partir du [Rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md), vous obtiendrez des mesures semblables aux suivantes, également signalées dans le Rapport de périphérique :

  - Microphone de l’appelant

  - Haut-parleur de l’appelant

  - Microphone de l’appelé

  - Haut-parleur de l’appelé

  - Ratio de la durée du basculement vocal

En revanche, si vous ouvrez le rapport Liste des appels à partir du [Rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md), vous ne verrez aucune de ces mesures, mais plutôt des mesures telles que les suivantes :

  - Boucle (ms)

  - Dégradation (MOS)

  - Perte de paquets

  - Gigue (ms)

Il s’agit des mesures signalées dans le Rapport d’emplacement. Cependant, dans le rapport Liste des appels, vous pouvez toujours cliquer sur la mesure Détail pour fournir des informations de qualité de l’expérience complète pour n’importe quel appel.

## Accès au rapport Liste des appels

Le rapport Liste des appels est accessible à partir des rapports suivants :

  - le [Rapport d’emplacement dans Lync Server 2013](lync-server-2013-location-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres).

  - le [Rapport de périphérique dans Lync Server 2013](lync-server-2013-device-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres).

  - le [Rapport de synthèse de la qualité des médias dans Lync Server 2013](lync-server-2013-media-quality-summary-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres).

  - le [Rapport de performances du serveur dans Lync Server 2013](lync-server-2013-server-performance-report.md) (en cliquant sur la mesure Volume d’appels ou Pourcentage d’appels médiocres).

À partir du rapport Liste des appels, vous pouvez accéder au [Rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) en cliquant sur la mesure Détail.

## Utilisation optimale du rapport Liste des appels

Si vous ne vous souvenez pas de la signification de certaines des mesures du rapport Liste des appels (par exemple, Ratio de la durée du basculement vocal), maintenez le pointeur de la souris sur l’étiquette de la mesure ; une info-bulle s’affiche et fournit une brève description de la mesure.

## Filtres

Aucun. Il est impossible de filtrer le rapport de liste d’appels.

## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de liste d’appels pour chaque appel.

### Mesures du rapport de liste d’appels

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
<td><p><strong>Détails</strong></p></td>
<td><p>Non</p></td>
<td><p>Lorsque vous cliquez sur cet élément, le rapport affiche des informations supplémentaires sur l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appelant</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse IP de la personne ayant initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appelé</strong></p></td>
<td><p>Oui</p></td>
<td><p>Adresse IP de la personne qui a été appelée.</p></td>
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
<td><p>Logiciel utilisé par le point de terminaison de la personne ayant initié l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agent utilisateur de l’appelé</strong></p></td>
<td><p>Oui</p></td>
<td><p>Logiciel utilisé par le point de terminaison de la personne qui a été appelée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Boucle (ms)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</p>
<p>Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dégradation (MOS)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Lync Server, Lync Server se sert d’un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</p>
<p>Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Perte de paquets</strong></p></td>
<td><p>Oui</p></td>
<td><p>Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Gigue</strong></p></td>
<td><p>Oui</p></td>
<td><p>Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
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
<td><p>Type de liaison de communication sans fil. Il s’agit en général de l’un des types suivants :</p>
<ul>
<li><p>Relais</p></li>
<li><p>Direct</p></li>
</ul></td>
</tr>
</tbody>
</table>

