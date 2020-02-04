---
title: Configuration requise pour la bande passante réseau de Lync Server 2013 pour le trafic multimédia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network bandwidth requirements for media traffic
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49733716
ms.date: 09/25/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 684f13a10c066e8902bed0024d7546017450ee9e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-bandwidth-requirements-for-media-traffic-in-lync-server-2013"></a>Exigences de bande passante réseau pour le trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-09-24_

Dans le cadre de la planification du réseau, il est important de s’assurer que votre réseau peut gérer le trafic multimédia généré par Lync Server. Cette section vous aide à planifier le trafic multimédia.

<div>

## <a name="media-traffic-network-usage"></a>Utilisation du réseau multimédia

L'utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l'utilisation du codec, la résolution et les niveaux d'activité. L’utilisation de la bande passante est une fonction du codec utilisé et de l’activité du flux, qui peut varier d’une situation à l’autre. Le tableau suivant répertorie les codecs audio fréquemment utilisés dans les scénarios 2013 de Lync Server.

### <a name="audio-codec-bandwidth"></a>Bande passante du codec audio

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec audio</th>
<th>Scénarios</th>
<th>Débit de charge utile (KBPS) audio</th>
<th>Charge utile audio de la bande passante et en-tête IP uniquement (Kbits/s)</th>
<th>Charge utile audio de la bande passante, en-tête IP, UDP, RTP et SRTP (Kbits/s)</th>
<th>Charge utile audio de la bande passante, en-tête IP, UDP, RTP, SRTP et correction d'erreur de transfert (Kbits/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Large bande RTAudio</p></td>
<td><p>Égal à égal</p></td>
<td><p>29.0</p></td>
<td><p>45.0</p></td>
<td><p>57.0</p></td>
<td><p>86.0</p></td>
</tr>
<tr class="even">
<td><p>Bande étroite RTAudio</p></td>
<td><p>D’égal à égal, RTC</p></td>
<td><p>11.8</p></td>
<td><p>27.8</p></td>
<td><p>39.8</p></td>
<td><p>51.6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>Conférence</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>95.6</p></td>
<td><p>159.6</p></td>
</tr>
<tr class="even">
<td><p>Stéréo G.722</p></td>
<td><p>D’égal à égal et de conférences</p></td>
<td><p>128.0</p></td>
<td><p>144.0</p></td>
<td><p>159.6</p></td>
<td><p>223.6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>RTC, conférence</p></td>
<td><p>64.0</p></td>
<td><p>80.0</p></td>
<td><p>92.0</p></td>
<td><p>156.0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Téléconférence</p></td>
<td><p>16.0</p></td>
<td><p>32.0</p></td>
<td><p>47.6</p></td>
<td><p>63.6</p></td>
</tr>
</tbody>
</table>


Les numéros de bande passante dans la table précédente sont basés sur la 20ms packeting (paquets 50 par seconde) et sur sirène et G. 722 incluent la surcharge de SRTP (Secure Real-Time Transport Protocol) des scénarios de conférence et supposent que le flux est 100% actif. La correction des erreurs de transfert (FEC) est utilisée de manière dynamique en cas de perte de paquets sur le lien pour garantir la qualité du flux audio.

La version stéréo du codec G. 722 est utilisée par des systèmes basés sur le système de salle Lync, qui permet la capture de microphone stéréo pour permettre aux écouteurs de mieux distinguer les différents participants dans la salle de réunion.

Pour la vidéo, le codec par défaut est le codec H. 264/MPEG-4 partie 10 Advanced Video Coding avec ses extensions de codage vidéo évolutives pour l’évolutivité temporelle. Pour préserver l’interopérabilité avec les clients Lync 2010 ou Office Communicator 2007 R2, le codec RTVideo est toujours utilisé pour les appels d’égal à égal entre Lync 2013 et les clients hérités. Dans les sessions de conférence avec les deux clients Lync 2013 et hérités, le point de terminaison 2013 de Lync risque de coder la vidéo à l’aide des codecs vidéo et 2007 2010 d’envoyer le flux binaire H. 264 aux clients Lync 2013 et RTVideo.

La bande passante requise dépend de la résolution, de la qualité et de la fréquence d’images. Pour chaque résolution, il existe deux taux binaires intéressants :

  - **Débit maximal de charge utile**   il s’agit du débit qui est utilisé par un point de terminaison 2013 Lync pour la résolution à la fréquence d’images maximale prise en charge pour cette résolution. Cette valeur est intéressante, car elle permet d’optimiser la qualité de la vidéo et de la fréquence d’images.

  - **Débit binaire**   minimal il s’agit du débit sous lequel un point de terminaison 2013 de Lync basculera sur la résolution immédiatement inférieure. Pour garantir une certaine résolution, le débit de la charge utile vidéo disponible ne doit pas être inférieur à ce débit minimal pour cette résolution. Cette valeur est intéressante de sorte que vous puissiez comprendre la valeur la plus basse possible dans les cas où le débit maximal n’est pas disponible ou pratique. Pour certains utilisateurs, une vidéo de faible débit basse peut être considérée comme une vidéo inacceptable, donc soyez prudent lors de la prise en considération de ces débits de charge vidéo minimum. Notez que pour les scènes vidéo avec peu ou pas de mouvement de l’utilisateur, le débit réel peut également être inférieur au débit minimal.

Lync 2013 prend en charge de nombreuses résolutions supplémentaires. Cela vous permet de mieux régler sur différentes bandes passantes réseau et de recevoir les fonctionnalités des clients. De plus, les proportions par défaut pour Lync 2013 ont été changées en 16:9. Le rapport hauteur/largeur 4:3 est toujours pris en charge pour les webcams qui n’autorisent pas la capture dans les proportions 16:9.

### <a name="video-resolution-bandwidth"></a>Bande passante de la résolution vidéo

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec vidéo</th>
<th>Résolution et proportions</th>
<th>Débit maximal de la surcharge vidéo (KB/s)</th>
<th>Débit minimal de la surcharge vidéo (KB/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>0,15</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424x240 (16:9)</p>
<p>320x240 (4:3)</p></td>
<td><p>350</p></td>
<td><p>100</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>480x270 (16:9)</p>
<p>424x320 (4:3)</p></td>
<td><p>450</p></td>
<td><p>200</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>640x360 (16:9)</p>
<p>640x480 (4:3)</p></td>
<td><p>800</p></td>
<td><p>300</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>848x480 (16:9)</p></td>
<td><p>1500</p></td>
<td><p>400</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>960x540 (16:9)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>1 280 x 720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1 920 x 1 080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>0,15</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1 280 x 192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1 920 x 288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


L’utilisation de la fonction Video FEC est incluse dans le débit de la surcharge vidéo lorsqu’elle est utilisée, de sorte qu’il n’y a pas de valeurs distinctes avec la vidéo FEC et sans FEC vidéo.

Les points de terminaison ne transmettent pas les paquets audio ou vidéo en continu. Selon le scénario, les niveaux d'activité de flux sont différents, ce qui indique à quelle fréquence les paquets sont envoyés pour un flux. L'activité d'un flux varie en fonction du support et du scénario et non pas du codec qui est utilisé. Dans un scénario poste à poste : 

  - Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

  - Les deux participants reçoivent des flux audio.

  - Si la vidéo est utilisée, les deux points de terminaison envoient et reçoivent des flux vidéo pendant l’appel complet.

  - Pour les scènes vidéo avec peu ou pas de mouvement, le débit réel peut être très faible, car le codec vidéo ignore les régions d’encodage de la vidéo sans modification.

Dans un scénario de conférence :

  - Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

  - Tous les participants reçoivent des flux audio.

  - Si la vidéo est utilisée, tous les participants peuvent recevoir jusqu'à cinq flux vidéo entrants et un flux panoramique (par exemple, proportions 20:3). Par défaut, les cinq flux vidéo entrants sont basés sur l'historique du haut-parleur actif, mais les utilisateurs peuvent également manuellement sélectionner les participants desquels ils souhaitent recevoir un flux vidéo.

  - Chaque participant qui active le flux vidéo d'émission de l'utilisateur enverra un ou plusieurs flux vidéo. Lync 2013 ajoute la possibilité d’envoyer jusqu’à cinq flux vidéo pour optimiser la qualité vidéo de tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l'émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes.

Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le RTCP et les différences entre les flux audio et vidéo en raison de différences entre les données de contrôle.

### <a name="rtcp-bandwidth"></a>Bande passante RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Media</th>
<th>Bande passante maximale RTCP (Kbits/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>Vidéo (uniquement H.264 ou RTVideo envoyé/reçu)</p></td>
<td><p>0,10</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo (H.264 et RTVideo envoyé/reçu)</p></td>
<td><p>0,15</p></td>
</tr>
</tbody>
</table>


Pour des raisons de planification de la capacité, les deux bandes passantes suivantes vous intéressent :

  - **Bande passante maximale sans FEC**   valeur de bande passante maximale qu’un flux utilisera, y compris l’activité type du flux et le codec standard utilisé dans le scénario sans FEC.Il s’agit de la bande passante lorsque le flux correspond à une activité de 100% et qu’il n’y a pas de perte de paquets déclenchant l’utilisation de FEC.Cela est intéressant pour le calcul de la bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné. 

  - **Bande passante maximale avec FEC**   fonction de bande passante maximale qu’un flux utilise, y compris l’activité type du flux et le codec standard utilisé dans le scénario avec FEC. Il s’agit de la bande passante lorsque le flux correspond à une activité de 100% et qu’il n’y a pas de perte de paquets déclenchant l’utilisation de FEC pour améliorer la qualité. Cela est intéressant pour le calcul de la bande passante qui doit être allouée pour permettre l’utilisation du codec dans un scénario donné et permettre l’utilisation de FEC pour préserver la qualité en conditions de perte de paquets. 

Les tableaux suivants répertorient également une valeur de bande passante supplémentaire, une **bande passante classique**. Il s’agit de la bande passante moyenne qu’un flux utilise, y compris sur l’activité type du flux et sur le codec standard utilisé dans le scénario. Cette bande passante peut être utilisée pour déterminer approximativement la quantité de bande passante utilisée par le trafic multimédia, mais ne doit pas être utilisée pour la planification de la capacité, car les appels individuels dépassent cette valeur lorsque le niveau d’activité est supérieur à la moyenne. La bande passante classique de flux vidéo dans les tableaux ci-dessous est basée sur une combinaison de résolutions vidéo différentes comme observées dans les données de clients mesurées. Par exemple, dans les sessions d’égal à égal, une majorité des utilisateurs utilisera la fenêtre de rendu vidéo par défaut, car le pourcentage d’utilisateurs augmenterait ou augmentait l’application Lync pour permettre des résolutions vidéo plus élevées.

Les tableaux suivants fournissent ces trois valeurs de bande passante pour les différents scénarios.

### <a name="audiovideo-capacity-planning-for-peer-to-peer-sessions"></a>Planification de la capacité audio/vidéo pour des sessions poste à poste

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Media</th>
<th>Codec</th>
<th>Bande passante pour un flux type ( Kbits/s)</th>
<th>Bande passante maximale sans correction d'erreur de transfert</th>
<th>Bande passante maximale avec correction d'erreur de transfert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>Large bande RTAudio</p></td>
<td><p>39.8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Bande étroite RTAudio</p></td>
<td><p>29.3</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo principale lors de l’appel de points de terminaison Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4 010 (pour une résolution maximale de 1 920 x 1 080)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Vidéo principale lors de l’appel de points de terminaison Lync 2010 ou Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2 510 (pour une résolution maximale de 1 280 x 720)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo panoramique lors de l’appel de points de terminaison Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2 010 (pour une résolution maximale de 1 920 x 288)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Vidéo panoramique lors de l’appel de points de terminaison Lync 2010 ou Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (pour une résolution maximale de 960x144)</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


### <a name="audiovideo-capacity-planning-for-conferences"></a>Planification de la capacité audio/vidéo pour les conférences

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Media</th>
<th>Codec type</th>
<th>Bande passante pour un flux type ( Kbits/s)</th>
<th>Bande passante maximale sans correction d'erreur de transfert</th>
<th>Bande passante maximale avec correction d'erreur de transfert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G.722</p></td>
<td><p>46.1</p></td>
<td><p>100.6</p></td>
<td><p>164.6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Siren</p></td>
<td><p>25.5</p></td>
<td><p>52.6</p></td>
<td><p>68.6</p></td>
</tr>
<tr class="odd">
<td><p>Réception vidéo principale</p></td>
<td><p>H. 264 et/ou RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Envoi vidéo principal</p></td>
<td><p>H. 264 et/ou RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>Réception vidéo panoramique</p></td>
<td><p>H. 264 et/ou RTVideo</p></td>
<td><p>190</p></td>
<td><p>2 010 (pour une résolution maximale de 1 920 x 288)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Envoi vidéo panoramique</p></td>
<td><p>H. 264 et/ou RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (pour l’envoi de flux binaires à l’aide de plusieurs résolutions/codecs</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


Pour la vidéo principale, la bande passante de flux moyenne et maximale est la bande passante agrégée de tous les flux vidéo reçus et de tous les flux vidéo envoyés respectivement. Même avec plusieurs flux vidéo, la bande passante vidéo classique est plus petite que dans le scénario pair à pair, car de nombreuses conférences vidéo utilisent le partage de contenu qui génère des fenêtres vidéo de plus petite taille et des résolutions vidéo plus petites. La bande passante de charge utile de la vidéo agrégée maximale prise en charge est de 8000 kbit/s pour les deux flux, d’envoi et de réception de flux qui seraient utilisés par exemple, s’il existe deux flux vidéo 1920x1080p entrants.

La bande passante de flux standard pour la vidéo panoramique est basée sur les appareils actuellement disponibles qui ne diffusent que jusqu’à 960x144 vidéo panoramique. Une fois que les appareils avec la vidéo panoramique 1920x288 deviennent disponibles, la bande passante de flux classique est censée augmenter.

### <a name="audio-capacity-planning-for-pstn"></a>Planification de la capacité audio pour PSTN

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Media</th>
<th>Codec type</th>
<th>Bande passante pour un flux type ( Kbits/s)</th>
<th>Bande passante maximale sans correction d'erreur de transfert</th>
<th>Bande passante maximale avec correction d'erreur de transfert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G. 711 (cela inclut les participants PSTN en conférences)</p></td>
<td><p>64.8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Bande étroite RTAudio</p></td>
<td><p>30.9</p></td>
<td><p>44.8</p></td>
<td><p>56.6</p></td>
</tr>
</tbody>
</table>


Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux. Pour la vidéo, le taux d’échantillonnage vidéo maximal est utilisé pour le calcul du flux maximal.

</div>

</div>

<span> </span>

</div>

</div>

</div>

