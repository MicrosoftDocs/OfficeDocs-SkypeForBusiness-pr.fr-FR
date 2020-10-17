---
title: 'Lync Server 2013 : configuration vidéo requise pour les clients Lync'
description: 'Lync Server 2013 : configuration vidéo requise pour les clients Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync client video requirements
ms:assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688132(v=OCS.15)
ms:contentKeyID: 49733731
ms.date: 01/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea1d4a993650ec8102d8b66ea5aa936ad1613f20
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570480"
---
# <a name="lync-client-video-requirements-for-lync-server-2013"></a>Configuration requise pour la vidéo client Lync pour Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-01-29_

Cette section décrit la prise en charge du matériel vidéo pour les appels vidéo Lync 2013 et explique comment déterminer la qualité vidéo attendue pour différentes configurations d’ordinateur, de tablette et d’appareil mobile.

<div>

## <a name="windows-desktop-and-tablet-video-requirements-and-capabilities"></a>Caractéristiques et fonctionnalités des ordinateurs de bureau et tablette Windows

Lync 2013 introduit l’accélération matérielle pour le codage et le décodage vidéo en fonction de la norme H. 264/MPEG-4 part 10 Advanced Video Coding standard. Cette fonctionnalité permet aux ordinateurs dont la vitesse d’horloge du processeur est faible d’encoder et de décoder des vidéos avec des résolutions supérieures. La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.

<div>

## <a name="video-hardware-requirements"></a>Configuration requise du matériel vidéo


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Fonctionnalité</th>
<th>Conditions requises</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)</p></td>
<td><ul>
<li><p>La carte graphique doit prendre en charge DirectX 9.0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT.</p></li>
<li><p>Le pilote de carte graphique le plus récent doit être installé.</p></li>
</ul>
<div>

> [!NOTE]  
> Pour plus d’informations sur les modes de décodage, voir <A href="https://go.microsoft.com/fwlink/p/?linkid=268530">https://go.microsoft.com/fwlink/p/?LinkId=268530</A> .


</div></td>
</tr>
<tr class="even">
<td><p>Encodage matériel accéléré H.264 : chipset requis</p></td>
<td><p>Les solutions de codage vidéo avec accélération matérielle Intel suivantes sont prises en charge :</p>
<ul>
<li><p>Chipsets Intel HD Graphics 2000, 2500, 3000, et 4000 de deuxième ou troisième générations (ou versions ultérieures) avec encodeurs vidéo matériel intégrés. L’installation du pilote Intel HD Graphics 15.28.9.2884 ou le pilote le plus récent contenant les éléments suivants sont requis :</p>
<ul>
<li><p>Pilote d’affichage 9.17.10.2884 ou le pilote le plus récent</p></li>
<li><p>Version de Hardware Media Foundation Transform (HMFT) 3.12.10.31 ou la dernière HMFT</p></li>
</ul></li>
</ul>
<p>Les solutions de codage vidéo avec accélération matérielle AMD suivantes sont prises en charge (nécessite des mises à jour CU1 pour Lync Server 2013) :</p>
<ul>
<li><p>Le moteur de codec vidéo AMD, qui est disponible dans plusieurs cartes graphiques discrètes et dans des unités de traitement accélérées intégrées de processeurs accélérés de la série AMD. Le pilote du moteur de codec vidéo AMD 9.12.0.0 ou une version ultérieure doit être installé.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Encodage matériel accéléré H.264 : caméra requise</p></td>
<td><p>Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.</p>
<div>

> [!NOTE]  
> Lync 2013 prend en charge les caméras UVC 1,5 avec Windows 8 ou Windows 8,1, qui inclut la prise en charge de UVC 1,5. Dans la mesure où Windows 7 ne prend pas en charge UVC 1.5, Lync 2013 considère les caméras UVC 1.5 comme des caméras génériques sans prise en charge de l’encodage matériel.


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Identification des fonctionnalités d’encodage et de décodage vidéo H.264

En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :

  - Prise en charge du décodage matériel accéléré avec DXVA

  - Prise en charge de l’encodage matériel accéléré

  - Nombre de cœurs physiques

  - Indice de performance Windows (WEI)

L’Outil d’évaluation système Windows (WinSAT) détermine l’indice WEI. Lorsque vous exécutez l’outil WinSAT, il génère un document XML formel. Assessment sur l’ordinateur dans le répertoire% windir% \\ \\ WinSAT \\ datastore. Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d’encodage et de décodage :

  - La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.

  - La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.

Les trois tableaux suivants expliquent les capacités d’encodage et de décodage maximales pour différents types de PC en fonction de l’accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d’images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d’images maximale prise en charge est de 15 i/s.

### <a name="computer-without-dxva-and-without-hardware-accelerated-encoder"></a>Ordinateur sans DXVA et sans encodeur matériel accéléré

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
<th>Conditions requises</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)</p></td>
<td><p>1 cœur et VideoEncodeScore ≥ 4,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>640x360</p></td>
<td><p>2 cœurs et VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>640x360</p></td>
<td><p>1280x720</p></td>
<td><p>2 cœurs et VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>4 cœurs et VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1280x720</p></td>
<td><p>4 cœurs et VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 cœurs et VideoEncodeScore ≥ 7,3</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>N/A</p></td>
</tr>
</tbody>
</table>


### <a name="computer-with-dxva-but-without-hardware-accelerated-encoder"></a>Ordinateur avec DXVA mais sans encodeur matériel accéléré

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
<th>Conditions requises</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>424x240</p></td>
<td><p>1920x1080</p></td>
<td><p>1 cœur et VideoEncodeScore ≥ 3,0</p></td>
</tr>
<tr class="even">
<td><p>640x360</p></td>
<td><p>1920x1080</p></td>
<td><p>2 cœurs et VideoEncodeScore ≥ 4,5</p></td>
</tr>
<tr class="odd">
<td><p>960x540</p></td>
<td><p>1920x1080</p></td>
<td><p>2 cœurs et VideoEncodeScore ≥ 6,0</p></td>
</tr>
<tr class="even">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>4 cœurs et VideoEncodeScore ≥ 6,7</p></td>
</tr>
<tr class="odd">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>4 cœurs et VideoEncodeScore ≥ 8,2</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. Par conséquent, la fonctionnalité de codage pour un ordinateur dépourvu de codeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8,1, où le score WinSAT maximal est de 9,9.



</div>

### <a name="computer-with-dxva-and-with-intel-hd-graphics-hardware-accelerated-encoder"></a>Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics

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
<th>Conditions requises</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1280x720</p></td>
<td><p>1920x1080</p></td>
<td><p>Intel HD Graphics deuxième et troisième générations</p></td>
</tr>
<tr class="even">
<td><p>1920x1080</p></td>
<td><p>1920x1080</p></td>
<td><p>Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="mobile-device-video-capabilities"></a>Fonctionnalités de vidéo d’appareil mobile

Le tableau suivant décrit les capacités vidéo maximales pour les appareils mobiles pris en charge. Pour plus d’informations sur la prise en charge des appareils mobiles, voir [Planning for mobile clients in Lync Server 2013](lync-server-2013-planning-for-mobile-clients.md).


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
<th>Fonctionnalité</th>
<th>Windows Phone</th>
<th>iPhone</th>
<th>iPad</th>
<th>Android</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Résolution maximale de H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA : iPhone-n</p>
<p>VGA : iPhone 5</p>
<p>720p : iPhone 5S et versions ultérieures</p></td>
<td><p>VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures</p>
<p>720p : iPad air/iPad mini 2/iPad Pro et version ultérieure</p></td>
<td><p>Jusqu’à VGA en fonction du modèle d’appareil</p></td>
</tr>
<tr class="even">
<td><p>Résolution de décodage maximale H. 264</p></td>
<td><p>VGA</p></td>
<td><p>QVGA : iPhone-n</p>
<p>VGA : iPhone 5</p>
<p>720p : iPhone 5S et versions ultérieures</p></td>
<td><p>VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures</p>
<p>720p : iPad air/iPad mini 2/iPad Pro et version ultérieure</p></td>
<td><p>Jusqu’à VGA en fonction du modèle d’appareil</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

