---
title: "Conf. requise de la bande passante pour le trafic mult. dans Lync Server 2013"
TOCtitle: "Conf. requise de la bande passante pour le trafic mult. dans Lync Server 2013"
ms:assetid: 83e83b16-0f0e-4d87-901a-0faa4618cdc2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688118(v=OCS.15)
ms:contentKeyID: 49891422
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise de la bande passante pour le trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-09-24_

Un élément important de la planification réseau consiste à vous assurer que votre réseau peut supporter le trafic multimédia généré par Lync Server. Cette section vous aide à planifier le trafic multimédia.

## Utilisation du réseau pour le trafic multimédia

L’utilisation de la bande passante par le trafic multimédia peut être difficile à calculer en raison du nombre de variables différentes, comme l’utilisation du codec, la résolution et les niveaux d’activité. L’utilisation de la bande passante est une fonction du codec utilisé et de l’activité du flux, tous deux pouvant varier d’un scénario à l’autre. Le tableau suivant répertorie les codecs audio communément utilisés dans les scénarios Lync Server 2013.

### Bande passante du codec audio

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
<th>Vitesse de transmission de la charge utile audio (Kbits/s)</th>
<th>Charge utile audio de la bande passante et en-tête IP uniquement (Kbits/s)</th>
<th>Charge utile audio de la bande passante, en-tête IP, UDP, RTP et SRTP (Kbits/s)</th>
<th>Charge utile audio de la bande passante, en-tête IP, UDP, RTP, SRTP et correction d’erreur de transfert (Kbits/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Large bande RTAudio</p></td>
<td><p>Égal à égal</p></td>
<td><p>29,0</p></td>
<td><p>45,0</p></td>
<td><p>57,0</p></td>
<td><p>86,0</p></td>
</tr>
<tr class="even">
<td><p>Bande étroite RTAudio</p></td>
<td><p>Égal à égal, PSTN</p></td>
<td><p>11,8</p></td>
<td><p>27,8</p></td>
<td><p>39,8</p></td>
<td><p>51,6</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>Conférence</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>95,6</p></td>
<td><p>159,6</p></td>
</tr>
<tr class="even">
<td><p>Stéréo G.722</p></td>
<td><p>Égal à égal, conférence</p></td>
<td><p>128,0</p></td>
<td><p>144,0</p></td>
<td><p>159,6</p></td>
<td><p>223,6</p></td>
</tr>
<tr class="odd">
<td><p>G.711</p></td>
<td><p>PSTN</p></td>
<td><p>64,0</p></td>
<td><p>80,0</p></td>
<td><p>92,0</p></td>
<td><p>156,0</p></td>
</tr>
<tr class="even">
<td><p>Siren</p></td>
<td><p>Conférence</p></td>
<td><p>16,0</p></td>
<td><p>32,0</p></td>
<td><p>47,6</p></td>
<td><p>63,6</p></td>
</tr>
</tbody>
</table>


Les valeurs de bande passante contenues dans le tableau ci-dessus reposent sur la mise en paquets 20 ms (50 paquets par seconde) et pour Siren et G.722 incluent le protocole SRTP (Secure Real-Time Transport Protocol) en plus des scénarios de conférence et supposent que le flux est entièrement actif. La correction d’erreur de transfert (FEC) est utilisée dynamiquement en cas de perte de paquet sur la liaison afin de maintenir la qualité du flux audio.

La version stéréo du codec G.722 est utilisée par les systèmes basés sur Lync Room System, qui active la capture stéréo par le micro ce qui permet aux participants de mieux distinguer les différents intervenants dans une salle de réunion.

Pour la vidéo, le codec par défaut est la norme H.264/MPEG-4 Part 10 Advanced Video Coding avec ses extensions de codage vidéo évolutives pour une extensibilité dans le temps. Pour conserver l’interopérabilité avec les clients Lync 2010 ou Office Communicator 2007 R2, le codec RTVideo est toujours utilisé pour des appels d’égal à égal entre Lync 2013 et les clients hérités. Dans des sessions de conférence comportant des clients Lync 2013 et des clients hérités, le point de terminaison Lync 2013 peut encoder la vidéo avec ces deux codecs vidéo et envoyer le flux H.264 vers Lync 2013 et le flux RTVideo vers les clients Lync 2010 ou Office Communicator 2007 R2.

La bande passante nécessaire dépend de la résolution, de la qualité et de la fréquence d’images. Pour chaque résolution, deux vitesses de transmission intéressantes sont disponibles :

  - **Vitesse de transmission de la charge utile maximale**   Il s’agit de la vitesse de transmission qui est utilisée par un point de terminaison Lync 2013 pour la résolution à la vitesse de transmission maximale prise en charge pour cette résolution. Cette valeur est intéressante car elle permet de disposer d’une vidéo d’une qualité et d’une fréquence d’images optimales.

  - **Vitesse de transmission de la charge utile minimale**   Il s’agit de la vitesse de transmission au-dessous de laquelle un point de terminaison Lync 2013 basculera à la résolution inférieure suivante. Afin de garantir une certaine résolution, la vitesse de transmission de la charge utile vidéo disponible ne doit pas être comprise dans la vitesse de transmission minimale pour cette résolution. Cette valeur est intéressante car vous pouvez comprendre la valeur la plus basse possible lorsque l’utilisation de la vitesse de transmission maximale n’est pas disponible ou pratique. Pour certains utilisateurs, cette vitesse faible peut être considérée comme inacceptable. Ces vitesses de transmission doivent donc être utilisées avec prudence. Notez que pour des vidéos avec peu ou pas de mouvements de l’utilisateur, la vitesse de transmission réelle peut temporairement être inférieure à la vitesse de transmission minimale.

Lync 2013 prend en charge de nombreuses autres résolutions. Cela permet une meilleure adaptation à différentes bandes passantes réseau et capacités des clients de réception. De plus, les proportions par défaut pour Lync 2013 sont désormais 16:9. Les proportions 4:3 sont toujours prises en charge pour les webcams qui ne permettent pas la capture 16:9.

### Bande passante de la résolution vidéo

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
<th>Vitesse de transmission de la charge utile vidéo maximale (Kbits/s)</th>
<th>Vitesse de transmission de la charge utile vidéo minimale (Kbits/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>320x180 (16:9)</p>
<p>212x160 (4:3)</p></td>
<td><p>250</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H.264/RTVideo</p></td>
<td><p>424x240 (16:9))</p>
<p>320x240 (4:3</p></td>
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
<td><p>1280x720 (16:9)</p></td>
<td><p>2500</p></td>
<td><p>700</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1920x1080 (16:9)</p></td>
<td><p>4000</p></td>
<td><p>1500</p></td>
</tr>
<tr class="odd">
<td><p>H.264/RTVideo</p></td>
<td><p>960x144 (20:3)</p></td>
<td><p>500</p></td>
<td><p>15</p></td>
</tr>
<tr class="even">
<td><p>H.264</p></td>
<td><p>1280x192 (20:3)</p></td>
<td><p>1000</p></td>
<td><p>250</p></td>
</tr>
<tr class="odd">
<td><p>H.264</p></td>
<td><p>1920x288 (20:3)</p></td>
<td><p>2000</p></td>
<td><p>500</p></td>
</tr>
</tbody>
</table>


Le FEC vidéo est intégré à la vitesse de transmission de la charge utile vidéo le cas échéant ce qui évite d’avoir des valeurs distinctes avec et sans le FEC vidéo.

Les points de terminaison ne transmettent pas les paquets audio ou vidéo en continu. Selon le scénario, les niveaux d’activité de flux sont différents, ce qui indique à quelle fréquence les paquets sont envoyés pour un flux. L’activité d’un flux varie en fonction du support et du scénario et non pas du codec qui est utilisé. Dans un scénario poste à poste :

  - Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

  - Les deux participants reçoivent des flux audio.

  - En cas d’utilisation de la vidéo, les deux points de terminaison envoient et reçoivent des flux vidéo pendant toute la durée de l’appel.

  - Pour des vidéos avec peu ou pas de mouvements, la vitesse de transmission réelle peut être temporairement très faible, car le codec vidéo n’encodera pas les régions de la vidéo qui ne sont pas modifiées.

Dans un scénario de conférence :

  - Les points de terminaison envoient des flux audio uniquement lorsque les utilisateurs parlent.

  - Tous les participants reçoivent des flux audio.

  - Si la vidéo est utilisée, tous les participants peuvent recevoir jusqu’à cinq flux vidéo entrants et un flux panoramique (par exemple, proportions 20:3). Par défaut, les cinq flux vidéo entrants sont basés sur l’historique du haut-parleur actif, mais les utilisateurs peuvent également manuellement sélectionner les participants desquels ils souhaitent recevoir un flux vidéo.

  - Chaque participant qui active le flux vidéo d’émission de l’utilisateur enverra un ou plusieurs flux vidéo. Lync 2013 permet l’envoi de cinq flux vidéo afin d’optimiser la qualité vidéo pour tous les clients de réception. Le nombre réel de flux vidéo envoyé est déterminé par l’émetteur en fonction de la capacité du processeur, de la bande passante montante disponible et du nombre de clients de réception qui demandent un flux vidéo spécifique. Dans le cas le plus courant, un flux vidéo H.264 et un flux vidéo RTVideo sont envoyés quand un client hérité participe à une conférence. Il se peut également que plusieurs flux vidéo H.264 (par exemple, avec différentes résolutions vidéo) soient envoyés pour différentes demandes.

Outre la bande passante requise pour le trafic RTP (Real-Time Transport Protocol) pour les supports audio et vidéo, le protocole RTCP (Real-Time Transport Control Protocol) a lui aussi besoin de bande passante. RTCP est utilisé pour le signalement des statistiques et le contrôle hors-bande du flux RTP. Pour la planification, utilisez les valeurs de bande passante contenues dans le tableau ci-dessous pour le trafic RTCP. Ces valeurs représentent la bande passante maximale utilisée pour le trafic RTCP et varient d’un flux audio et vidéo à l’autre en raison des différences dans les données de contrôle.

### Bande passante RTCP

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Média</th>
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
<td><p>10</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo (H.264 et RTVideo envoyé/reçu)</p></td>
<td><p>15</p></td>
</tr>
</tbody>
</table>


Pour planifier la capacité, il est intéressant de tenir compte des deux bandes passantes suivantes :

  - **Bande passante maximale sans correction d’erreur de transfert**   La bande passante maximale qui sera consommée par un flux, y compris l’activité type du flux et le codec type utilisé dans le scénario sans correction d’erreur de transfert. Il s’agit de la bande passante lorsque l’activité du flux est maximale et qu’aucune perte de paquets ne vient déclencher l’utilisation de la correction d’erreur de transfert. Ceci est intéressant pour calculer la bande passante qui sera allouée en vue d’autoriser l’utilisation du codec dans un scenario donné. 

  - **Bande passante maximale avec correction d’erreur de transfert**   La bande passante maximale qui sera consommée par un flux, y compris l’activité type du flux et le codec type utilisé dans le scenario avec correction d’erreur de transfert. Il s’agit de la bande passante lorsque l’activité du flux est maximale et qu’une perte de paquets vient déclencher l’utilisation de la correction d’erreur de transfert pour améliorer la qualité. Ceci est intéressant pour calculer la bande passante qui sera allouée en vue d’autoriser l’utilisation du codec dans un scénario donné et d’autoriser l’utilisation de la correction d’erreur de transfert pour préserver la qualité en cas de perte de paquets. 

Les tableaux ci-dessous répertorient également une valeur de bande passante supplémentaire, la **bande passante type**. Il s’agit de la bande passante moyenne consommée par un flux, y compris l’activité type du flux et le codec type utilisé dans le scénario. Cette bande passante peut être utilisée pour calculer une quantité approximative de bande passante consommée par un trafic multimédia à un moment donné, mais ne doit pas être utilisée pour planifier la capacité, car les appels individuels excéderont cette valeur dès lors que le niveau d’activité sera supérieur à cette moyenne. La vitesse de transmission du flux vidéo dans les tableaux ci-dessous est basée sur un ensemble de différentes résolutions vidéo comme cela est le plus souvent le cas. Par exemple, dans des sessions d’égal à égal, une majorité d’utilisateurs utilisent la fenêtre de rendu vidéo par défaut, tandis que d’autres agrandissent l’application Lync afin d’obtenir des résolutions vidéo supérieures.

Les tableaux ci-dessous fournissent ces trois valeurs de bande passante pour les divers scénarios.

### Planification de la capacité audio/vidéo pour des sessions poste à poste

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
<th>Média</th>
<th>Codec</th>
<th>Bande passante pour un flux type ( Kbits/s)</th>
<th>Bande passante maximale sans correction d’erreur de transfert</th>
<th>Bande passante maximale avec correction d’erreur de transfert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>Large bande RTAudio</p></td>
<td><p>39,8</p></td>
<td><p>62</p></td>
<td><p>91</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Bande étroite RTAudio</p></td>
<td><p>29,3</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo principale lors de l’appel des points de terminaison Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>460</p></td>
<td><p>4010 (pour une résolution maximale de 1920x1080)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Vidéo principale lors de l’appel des points de terminaison Lync 2010 ou Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>460</p></td>
<td><p>2510 (pour une résolution maximale de 1280x720)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>Vidéo panoramique lors de l’appel de points de terminaison Lync 2013</p></td>
<td><p>H.264</p></td>
<td><p>190</p></td>
<td><p>2010 (pour une résolution maximale de 1920x288)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Vidéo panoramique lors de l’appel de points de terminaison Lync 2010 ou Office Communicator 2007 R2</p></td>
<td><p>RTVideo</p></td>
<td><p>190</p></td>
<td><p>510 (pour une résolution maximale de 960x144)</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


### Planification de la capacité audio/vidéo pour les conférences

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
<th>Média</th>
<th>Codec type</th>
<th>Bande passante pour un flux type ( Kbits/s)</th>
<th>Bande passante maximale sans correction d’erreur de transfert</th>
<th>Bande passante maximale avec correction d’erreur de transfert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G.722</p></td>
<td><p>46,1</p></td>
<td><p>100,6</p></td>
<td><p>164,6</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Siren</p></td>
<td><p>25,5</p></td>
<td><p>52,6</p></td>
<td><p>68,6</p></td>
</tr>
<tr class="odd">
<td><p>Réception vidéo principale</p></td>
<td><p>H.264 et/ou RTVideo</p></td>
<td><p>260</p></td>
<td><p>8015</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Envoi vidéo principal</p></td>
<td><p>H.264 et/ou RTVideo</p></td>
<td><p>270</p></td>
<td><p>8015</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>Réception vidéo panoramique</p></td>
<td><p>H.264 et/ou RTVideo</p></td>
<td><p>190</p></td>
<td><p>2010 (pour une résolution maximale de 1920x288)</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Envoi vidéo panoramique</p></td>
<td><p>H.264 et/ou RTVideo</p></td>
<td><p>190</p></td>
<td><p>2515 (pour l’envoi de flux avec plusieurs résolutions/codecs</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


Pour la vidéo principale, la vitesse de transmission du flux type et maximale est la bande passante agrégée divisée respectivement par tous les flux vidéo reçus et par tous les flux vidéo envoyés. Même avec plusieurs flux vidéo, la bande passante type est plus petite que dans un scénario d’égal à égal, car de nombreuses conférences vidéo utilisent le partage de contenu, ce qui entraîne des fenêtres vidéo plus petites et donc des résolutions vidéo plus petites. La bande passante de charge utile vidéo agrégée maximum prise en charge est 8 000 Kbits/s pour les flux envoyés et reçus, par exemple pour deux flux vidéo 1920x1080p entrants.

La bande passante de flux type pour une vidéo panoramique est basée sur les appareils actuellement disponibles qui ne diffusent que des vidéos panoramiques 960x144. Quand des appareils permettant des vidéos panoramiques 1920x288 seront disponibles, la bande passante du flux augmentera.

### Planification de la capacité audio pour PSTN

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
<th>Média</th>
<th>Codec type</th>
<th>Bande passante pour un flux type ( Kbits/s)</th>
<th>Bande passante maximale sans correction d’erreur de transfert</th>
<th>Bande passante maximale avec correction d’erreur de transfert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>G.711</p></td>
<td><p>64,8</p></td>
<td><p>97</p></td>
<td><p>161</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>Bande étroite RTAudio</p></td>
<td><p>30,9</p></td>
<td><p>44,8</p></td>
<td><p>56,6</p></td>
</tr>
</tbody>
</table>


Les valeurs de bande passante pour le réseau contenues dans ces tableaux représentent uniquement le trafic unidirectionnel et incluent 5 Kbits/s pour le trafic RTCP pour chaque flux. Pour la vidéo, la vitesse de transmission vidéo maximale est utilisée pour le calcul du flux maximal.

