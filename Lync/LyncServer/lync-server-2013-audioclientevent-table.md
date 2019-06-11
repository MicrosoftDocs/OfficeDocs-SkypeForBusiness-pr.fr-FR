---
title: 'Lync Server 2013 : Table AudioClientEvent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489777458838d5e77df1f8c82ed6ab8b6c295832
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Table AudioClientEvent dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-17_

Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un appel possède deux enregistrements, un pour l’appelant et un pour l’appelant.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Principal</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Fait référence à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>0: données du destinataire</p>
<p>1: données de l’appelant</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement NetworkSendQuality pour l’état «incorrect».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est sévère et a un impact sur la qualité du son envoyé.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement ReceiveSendQuality pour l’état «incorrect».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est sérieuse et a un impact sur la qualité du son reçu.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session le déclenchement de l’événement de temporisation a été déclenché pour l’état «incorrect». La latence du réseau est sérieuse et a un impact sur l’interface en empêchant les communications interactives</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement LowBandwidth pour l’état «incorrect». La bande passante disponible est insuffisante pour obtenir une utilisation vocale acceptable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de l’événement UC insuffisant déclenché pour l’état «incorrect». Il n’y a pas assez de cycles d’UC pour le traitement avec les modalités et applications en cours d’utilisation. Cela entraîne une distorsion du canal audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceHalfDuplexAEC pour l’état «incorrect». Afin d’éviter l’écho, le système a entré Half duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceRenderNotFunctioning pour l’état «incorrect». L’appareil de rendu actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens unique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceCaptureNotFunctioning pour l’état «incorrect». L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens unique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceGlitches pour l’état «incorrect». Il y a des problèmes importants dans le rendu du son qui engendre des distorsions. Ces problèmes peuvent être causés par des problèmes de pilotes, des appels de procédures différées (DPC) Storm (pilotes) et une utilisation élevée de l’UC.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceLowSNR pour l’état «incorrect». La qualité de la capture est très médiocre, qu’elle soit très bruyante ou que l’utilisateur parle trop loin du microphone. Cela entraînera une distorsion.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceLowSpeechLevel pour l’état «incorrect». Le niveau de voix de l’utilisateur est trop faible et le système ne peut plus l’augmenter. Cela peut entraîner des distorsions ou une perception perçue comme un son à sens unique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceClipping pour l’état «incorrect».</p>
<p>Lorsque le son du microphone est proche de l’extrémité de la parole, la distorsion est audible en raison de l’écrêtage. Il est important d’éviter une capture du microphone proche de la fin.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceEchoEvent pour l’état «incorrect». L’appareil ou la configuration entraîne un écho au-delà de la capacité du système à compenser.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session de déclenchement de l’événement DeviceNearEndToEchoRatio pour l’état «incorrect». La parole de l’utilisateur est trop faible par rapport à l’écho capturé qui a un impact sur l’interface utilisateur, car il limite le niveau d’interruption d’un utilisateur. Réduire le volume des haut-parleurs, rapprochez le micro du contact.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre de fois que l’événement DeviceMultipleEndpoints a été déclenché pour l’état «incorrect». Plusieurs points de terminaison audio au sein de la même session détectés et le système a compensé en réduisant le volume de rendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre de fois que l’événement DeviceHowlingEvent a été déclenché pour l’état «incorrect». Boucle de commentaires audio détectée (provoquée par plusieurs points de terminaison partageant le chemin audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Pourcentage de session l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état «incorrect». L’appareil de rendu a été défini sur le volume zéro.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Pourcentage de session l’événement DeviceRenderMute a été déclenché pour être dans l’état «incorrect». L’appareil de rendu a été coupé.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

