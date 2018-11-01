﻿---
title: 'Lync Server 2013 : Rapport d’emplacement'
TOCTitle: Rapport d’emplacement
ms:assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615035(v=OCS.15)
ms:contentKeyID: 49298871
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport d’emplacement dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le rapport d’emplacement fournit des informations sur les mesures de la qualité des appels regroupées par emplacement réseau (c’est-à-dire, par sous-réseau). Si vos utilisateurs rencontrent des problèmes avec leurs appels, ce rapport peut vous aider à déterminer si ces problèmes sont étendus ou s’ils sont largement réduits à un segment de réseau donné.

## Accès au rapport d’emplacement

Le rapport d’emplacement est accessible à partir de la page d’accueil des rapports de surveillance. Vous pouvez accéder au rapport des listes d’appels en cliquant sur l’une des mesures suivantes :

  - Volume d’appels

  - Pourcentage d’appels médiocres

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’emplacement vous permet de filtrer des éléments comme l’emplacement duquel un appel provient ou s’il s’est produit sur une connexion réseau câblée ou sans fil. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les appels sont groupés par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’emplacement.

### Filtres du rapport d’emplacement

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
<td><p><strong>Emplacement de l’appelant</strong></p></td>
<td><p>Sous-réseau IP de l’utilisateur qui a émis l’appel. Vous pouvez uniquement sélectionner <strong>[Tous]</strong> pour indiquer tous les sous-réseaux.</p></td>
</tr>
<tr class="even">
<td><p><strong>Emplacement de l’appelé</strong></p></td>
<td><p>Sous-réseau IP de l’utilisateur qui a reçu l’appel. Vous pouvez uniquement sélectionner <strong>[Tous]</strong> pour indiquer tous les sous-réseaux.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</p>
<ol>
<li><p>[Tous]</p></li>
<li><p>Câblé</p></li>
<li><p>Sans fil</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</p>
<ol>
<li><p>[Tous]</p></li>
<li><p>VPN</p></li>
<li><p>Non-VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’emplacement.

### Mesures du rapport d’emplacement

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
<td><p><strong>Sous-réseau de l’appelant</strong></p></td>
<td><p>Non</p></td>
<td><p>Sous-réseau IP de l’utilisateur qui a émis l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sous-réseau de l’appelé</strong></p></td>
<td><p>Non</p></td>
<td><p>Sous-réseau IP de l’utilisateur qui a reçu l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume d’appels</strong></p></td>
<td><p>Oui</p></td>
<td><p>Nombre total d’appels émis.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’appels médiocres</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Boucle (ms)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Temps moyen (en millisecondes) nécessaire à un package RTP (Real-Time Transport Protocol) pour effectuer un aller-retour vers un autre point de terminaison. Des boucles de 100 millisecondes ou moins sont considérées qualitativement acceptables.</p>
<p>Des boucles avec des temps plus élevés peuvent être causées par le routage international des appels, une mauvaise configuration du routage ou un serveur multimédia surchargé. Les temps d’aller-retour élevés créent des difficultés dans le cadre de conversations audio bidirectionnelles réalisées en temps réel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dégradation (MOS)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Taux moyen de dégradation de la note moyenne d’opinion (MOS) observé au cours d’un appel. Les valeurs de dégradation peuvent aller de 0,0 (la plus faible) à 5,0 (la plus élevée). Une valeur de 0,5 ou moins signifie une dégradation acceptable. Traditionnellement, les notes moyennes d’opinion sont calculées en demandant aux utilisateurs d’évaluer la qualité d’un appel sur une échelle de 1 à 5. Dans Lync Server, Lync Server se sert d’un ensemble d’algorithmes pour prédire la manière dont les utilisateurs auraient évalué un appel.</p>
<p>Les valeurs de dégradation élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou bien d’un serveur multimédia ou d’un point de terminaison surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Perte de paquets</strong></p></td>
<td><p>Oui</p></td>
<td><p>Taux moyen de pertes de paquets RTP. (La perte de paquets survient lorsque des paquets RTP, protocole employé pour la transmission audio et vidéo sur Internet, n’atteignent pas leur point de destination.) Les valeurs de perte élevées peuvent provenir d’une congestion, d’un dépassement de la bande passante disponible, d’une congestion/interférence dans la liaison sans fil ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Gigue</strong></p></td>
<td><p>Oui</p></td>
<td><p>Gigue moyenne détectée entre les arrivées de paquets RTP. (La gigue permet de mesurer les fluctuations d’un appel.) Les valeurs de gigue élevées peuvent provenir d’une congestion ou d’un serveur multimédia surchargé, ce qui se traduit par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux de masquage de la réparation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Ratio moyen d’échantillons audio masqués par rapport au nombre total d’échantillons. (Un échantillon audio masqué est une technique employée pour adoucir les effets de transition violents généralement causés par des paquets réseau perdus.) Des valeurs élevées indiquent des niveaux importants de masquage des pertes appliqués suite à la perte de paquets ou des phénomènes de gigue. Elles se traduisent par une distorsion ou une perte de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taux d’étirement de la réparation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Ratio moyen d’échantillons audio étirés par rapport au nombre total d’échantillons. (Un échantillon audio étiré est un composant audio qui a été étendu dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants d’étirement d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet de robotisation ou de distorsion de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taux de compression de la réparation</strong></p></td>
<td><p>Oui</p></td>
<td><p>Ratio moyen d’échantillons audio compressés par rapport au nombre total d’échantillons. (Un échantillon audio compressé est un composant audio qui a été compressé dans le but de maintenir la qualité des appels lorsqu’un paquet réseau perdu est détecté.) Les valeurs élevées indiquent l’existence de niveaux importants de compression d’échantillons dus au phénomène de gigue, ce qui se traduit par un effet d’accélération ou de distorsion de l’audio.</p></td>
</tr>
</tbody>
</table>

