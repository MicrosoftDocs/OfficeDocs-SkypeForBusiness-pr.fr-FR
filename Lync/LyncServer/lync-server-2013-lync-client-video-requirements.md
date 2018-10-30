---
title: "Skype Entreprise Server 2015 : conf. req. pr vidéo du client Skype Entreprise"
TOCTitle: Configuration requise pour la vidéo du client Skype Entreprise
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49891443
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour la vidéo du client Skype Entreprise pour Skype Entreprise Server 2015

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section décrit la configuration prise en charge pour le matériel vidéo dans le cadre des appels vidéo Lync 2013, ainsi que la façon de déterminer la qualité vidéo attendue pour différentes configurations d’ordinateur, de tablette et d'appareil mobile.

## Configuration requise et fonctionnalités vidéo pour les ordinateurs et les tablettes Windows

Lync 2013 propose désormais l\\rquote accélération matérielle pour l\\rquote encodage et le décodage vidéo basés sur la norme H.264/MPEG-4 Part 10 AVC (Advanced Video Coding). Cette fonctionnalité permet aux ordinateurs dont la vitesse d\\rquote horloge du processeur est faible d\\rquote encoder et de décoder des vidéos avec des résolutions supérieures. La configuration requise pour le matériel vidéo dépend de la configuration de l\\rquote ordinateur et de la résolution vidéo souhaitée.

## Configuration requise du matériel vidéo


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonctionnalité</th>
<th>Configuration requise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)</p></td>
<td><ul><li><p>La carte graphique doit prendre en charge DirectX 9.0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT.</p></li><li><p>Le tout dernier pilote de carte graphique doit être installé.</p></li></ul>
<div>

> [!NOTE]  
> Pour plus d’informations sur les modes de décodage, voir <a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a>.
</div></td>
</tr>
<tr class="even">
<td><p>Encodage matériel accéléré H.264 : chipset requis</p></td>
<td><p>Les solutions d’encodage vidéo matériel accéléré Intel prises en charge sont les suivantes :</p><ul><li><p>Chipsets Intel HD Graphics 2000, 2500, 3000, et 4000 de deuxième ou troisième générations (ou versions ultérieures) avec encodeurs vidéo matériel intégrés. L\rquote installation du pilote 15.28.9.2884 Intel HD Graphics ou version ultérieure contenant les éléments suivants est requise :</p><ul><li><p>Pilote d’affichage 9.17.10.2884 ou version ultérieure ;</p></li><li><p>HMFT (Hardware Media Foundation Transform) 3.12.10.31 ou version ultérieure.</p></li></ul></li></ul>
<p>Les solutions d’encodage vidéo matériel accéléré AMD suivantes sont prises en charge (nécessitent les mises à jour CU1 pour Lync Server 2013) :</p><ul><li><p>AMD Video Codec Engine, disponible dans plusieurs cartes graphiques discrètes et les unités de traitement accéléré intégrées des processeurs accélérés AMD série A. Le pilote 9.12.0.0 AMD Video Codec Engine ou une version ultérieure doit être installé.</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Encodage matériel accéléré H.264 : caméra requise</p></td>
<td><p>Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 prend en charge les caméras UVC 1.5 avec Windows 8 ou Windows 8.1, qui inclut la prise en charge d\rquote UVC 1.5. Dans la mesure où Windows 7 ne prend pas en charge UVC 1.5, Lync 2013 considère les caméras UVC 1.5 comme des caméras génériques sans prise en charge de l\rquote encodage matériel.
</div></td>
</tr>
<tr class="even">
<td><p>Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)</p></td>
<td><ul><li><p>La carte graphique doit prendre en charge DirectX 9.0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT.</p></li><li><p>Le tout dernier pilote de carte graphique doit être installé.</p></li></ul>
<div>

> [!NOTE]  
> Pour plus d’informations sur les modes de décodage, voir <a href="http://go.microsoft.com/fwlink/p/?linkid=268530">http://go.microsoft.com/fwlink/p/?LinkId=268530</a>.
</div></td>
</tr>
<tr class="odd">
<td><p>Encodage matériel accéléré H.264 : chipset requis</p></td>
<td><p>Les solutions d’encodage vidéo matériel accéléré Intel prises en charge sont les suivantes :</p><ul><li><p>Chipsets Intel HD Graphics 2000, 2500, 3000, et 4000 de deuxième ou troisième générations (ou versions ultérieures) avec encodeurs vidéo matériel intégrés. L\rquote installation du pilote 15.28.9.2884 Intel HD Graphics ou version ultérieure contenant les éléments suivants est requise :</p><ul><li><p>Pilote d’affichage 9.17.10.2884 ou version ultérieure ;</p></li><li><p>HMFT (Hardware Media Foundation Transform) 3.12.10.31 ou version ultérieure.</p></li></ul></li></ul>
<p>Les solutions d’encodage vidéo matériel accéléré AMD suivantes sont prises en charge (nécessitent les mises à jour CU1 pour Lync Server 2013) :</p><ul><li><p>AMD Video Codec Engine, disponible dans plusieurs cartes graphiques discrètes et les unités de traitement accéléré intégrées des processeurs accélérés AMD série A. Le pilote 9.12.0.0 AMD Video Codec Engine ou une version ultérieure doit être installé.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Encodage matériel accéléré H.264 : caméra requise</p></td>
<td><p>Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 prend en charge les caméras UVC 1.5 avec Windows 8 ou Windows 8.1, qui inclut la prise en charge d\rquote UVC 1.5. Dans la mesure où Windows 7 ne prend pas en charge UVC 1.5, Lync 2013 considère les caméras UVC 1.5 comme des caméras génériques sans prise en charge de l\rquote encodage matériel.
</div></td>
</tr>
</tbody>
</table>


## Identification des fonctionnalités d’encodage et de décodage vidéo H.264

En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :

  - Prise en charge du décodage matériel accéléré avec DXVA

  - Prise en charge de l’encodage matériel accéléré

  - Nombre de cœurs physiques

  - Indice de performance Windows (WEI)

L\\rquote Outil d\\rquote évaluation système Windows (WinSAT) détermine l\\rquote indice WEI. Quand vous exécutez l\\rquote outil WinSAT, il génère un document XML d\\rquote évaluation formelle sur l\\rquote ordinateur dans le dossier %windir%\\Performance\\WinSAT\\DataStore. Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d\\rquote encodage et de décodage :

  - La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.

  - La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.

Les trois tableaux suivants expliquent les capacités d\\rquote encodage et de décodage maximales pour différents types de PC en fonction de l\\rquote accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d\\rquote images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d\\rquote images maximale prise en charge est de 15 i/s.

### Ordinateur sans DXVA et sans encodeur matériel accéléré

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Résolution d’encodeur compatible</th>
<th>Résolution de décodeur compatible</th>
<th>Configuration requise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>424 x 240 (640 x 360 à 15 i/s pour des scénarios de réception uniquement)</p></td>
<td><p>1 cœur et VideoEncodeScore = 4,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1 280 x 720</p></td>
<td><p>2 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1 280 x 720</p></td>
<td><p>1 280 x 720</p></td>
<td><p>4 cœurs et VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="even">
<td><p>1 280 x 720</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1 920 x 1 080</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>N/A</p></td>
</tr>
<tr class="even">
<td><p>424 x 240</p></td>
<td><p>424 x 240 (640 x 360 à 15 i/s pour des scénarios de réception uniquement)</p></td>
<td><p>1 cœur et VideoEncodeScore = 4,0</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>640 x 360</p></td>
<td><p>2 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1 280 x 720</p></td>
<td><p>2 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>1 280 x 720</p></td>
<td><p>1 280 x 720</p></td>
<td><p>4 cœurs et VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1 280 x 720</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 7,3</p></td>
</tr>
<tr class="even">
<td><p>1 920 x 1 080</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>N/A</p></td>
</tr>
</tbody>
</table>


### Ordinateur avec DXVA mais sans encodeur matériel accéléré

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Résolution d’encodeur compatible</th>
<th>Résolution de décodeur compatible</th>
<th>Configuration requise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424 x 240</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>1 cœur et VideoEncodeScore = 3,0</p></td>
</tr>
<tr class="even">
<td><p>640 x 360</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>2 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960 x 540</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>2 cœurs et VideoEncodeScore = 6,0</p></td>
</tr>
<tr class="even">
<td><p>1 280 x 720</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1 920 x 1 080</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 8,2</p></td>
</tr>
<tr class="even">
<td><p>424 x 240</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>1 cœur et VideoEncodeScore = 3,0</p></td>
</tr>
<tr class="odd">
<td><p>640 x 360</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>2 cœurs et VideoEncodeScore = 4,5</p></td>
</tr>
<tr class="even">
<td><p>960 x 540</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>2 cœurs et VideoEncodeScore = 6,0</p></td>
</tr>
<tr class="odd">
<td><p>1 280 x 720</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 6,7</p></td>
</tr>
<tr class="even">
<td><p>1 920 x 1 080</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>4 cœurs et VideoEncodeScore = 8,2</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. C\rquote est pourquoi la capacité d\rquote encodage d\rquote un ordinateur sans encodeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8.1, pour lequel le score WinSAT est de 9,9 au maximum.

### Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Résolution d’encodeur compatible</th>
<th>Résolution de décodeur compatible</th>
<th>Condition requise</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1 280 x 720</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>Intel HD Graphics deuxième et troisième générations</p></td>
</tr>
<tr class="even">
<td><p>1 920 x 1 080</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>Intel HD Graphics deuxième et troisième générations avec GraphicsScore = 5,0</p></td>
</tr>
<tr class="odd">
<td><p>1 280 x 720</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>Intel HD Graphics deuxième et troisième générations</p></td>
</tr>
<tr class="even">
<td><p>1 920 x 1 080</p></td>
<td><p>1 920 x 1 080</p></td>
<td><p>Intel HD Graphics deuxième et troisième générations avec GraphicsScore = 5,0</p></td>
</tr>
</tbody>
</table>


## Fonctions vidéo sur les appareils mobiles

Le tableau ci-dessous décrit les capacités vidéo maximales pour les appareils mobiles pris en charge. Pour plus d’informations sur la prise en charge des appareils mobiles, voir [Planification des clients mobiles dans Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonctionnalité</th>
<th>Windows Phone</th>
<th>iPhone et iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Résolution maximale de l'encodage H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone 4 : 192 x 144</p>
<p>iPad et tous les autres modèles iPhone pris en charge : 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="even">
<td><p>Résolution maximale du décodage H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone et iPad : 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="odd">
<td><p>Résolution maximale de l'encodage H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone 4 : 192 x 144</p>
<p>iPad et tous les autres modèles iPhone pris en charge : 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
<tr class="even">
<td><p>Résolution maximale du décodage H.264</p></td>
<td><p>640 x 480</p></td>
<td><p>iPhone et iPad : 352 x 288</p></td>
<td><p>320 x 2401</p></td>
</tr>
</tbody>
</table>


1Pour les appareils Android dotés d’un processeur Qualcomm Snapdragon S3 ou S4 utilisant une puce 8 x 60, l’envoi et la réception à une résolution de 640 x 480 sont pris en charge.

