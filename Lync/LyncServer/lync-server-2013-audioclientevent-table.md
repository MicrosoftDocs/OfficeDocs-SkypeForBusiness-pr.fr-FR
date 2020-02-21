---
title: 'Lync Server 2013 : table table audioclientevent'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioClientEvent table
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413086(v=OCS.15)
ms:contentKeyID: 48185967
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d93a9cd9276ba2bdaacf892ca0ab3f4240458503
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203460"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audioclientevent-table-in-lync-server-2013"></a>Table table audioclientevent dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-17_

Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En règle générale, un appel dispose de deux enregistrements, un pour l’appelant et un pour l’appelé.


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
<th><strong>Clé/index</strong></th>
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Primaire</p></td>
<td><p>Référencé à partir de la <a href="lync-server-2013-medialine-table.md">table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Primaire</p></td>
<td><p>0 : données de l’appelé</p>
<p>1 : données de l’appelant</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement NetworkSendQuality a été déclenché pour l’état « incorrect ».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est importante et influe sur la qualité de l’audio envoyé.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement ReceiveSendQuality a été déclenché pour l’état « incorrect ».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est importante et a un impact sur la qualité de l’audio reçu.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement de retard a été déclenché pour l’état « incorrect ». La latence du réseau est importante et a un impact sur l’expérience en empêchant la communication interactive</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement LowBandwidth a été déclenché pour l’état « incorrect ». La bande passante disponible est insuffisante pour une expérience vocale acceptable.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement d’UC insuffisant a été déclenché pour l’état « incorrect ». Il n’y a pas suffisamment de cycles d’UC pour le traitement avec les modalités et les applications en cours d’utilisation. Cela provoque des distorsions avec le canal audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceHalfDuplexAEC a été déclenché pour l’état « incorrect ». Afin d’empêcher l’écho, le système est entré en semi-duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceRenderNotFunctioning a été déclenché pour l’état « incorrect ». Le périphérique de rendu actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens unique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceCaptureNotFunctioning a été déclenché pour l’état « incorrect ». L’appareil de capture actuellement utilisé pour la session ne fonctionne pas correctement. Cela peut entraîner des problèmes audio à sens unique.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceGlitches a été déclenché pour l’état « incorrect ». Il y a des problèmes sérieux dans le rendu de l’audio qui provoque des déformations. Ces problèmes peuvent être causés par des problèmes de pilote, des appels de procédure différées (pilotes) et une utilisation intensive du processeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceLowSNR a été déclenché pour l’état « incorrect ». La qualité de capture est très médiocre, soit très bruyante, soit l’utilisateur parle trop loin du microphone. Cela entraînera des distorsions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceLowSpeechLevel a été déclenché pour l’état « incorrect ». Le niveau de voix de l’utilisateur est trop bas et le système ne peut plus en augmenter. Cela peut entraîner des distorsions ou un affichage audio unidirectionnel.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceClipping a été déclenché pour l’état « incorrect ».</p>
<p>Lorsque le microphone est terminé par des éléments vocaux de proximité, l’extrémité n’entend pas les distorsions dues à l’écrêtage. Il est important d’éviter la détourage du microphone de bas.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement écho a été déclenché pour l’état « incorrect ». Le périphérique ou le programme d’installation provoque un écho au-delà de la capacité du système à compenser.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de la session l’événement DeviceNearEndToEchoRatio a été déclenché pour l’état « incorrect ». La voix de l’utilisateur est trop faible par rapport à l’écho capturé, ce qui a un impact sur l’expérience des utilisateurs, car il limite la facilité d’interruption d’un utilisateur. Réduire le volume des haut-parleurs, rapprochez le microphone du contacteur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Nombre de fois au cours d’une session l’événement DeviceMultipleEndpoints a été déclenché pour l’état « incorrect ». Plusieurs points de terminaison audio de la même session ont été détectés et le système a compensé en réduisant le volume de rendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre de fois au cours d’une session l’événement DeviceHowlingEvent a été déclenché pour l’état « incorrect ». Boucle audio de commentaire détectée (causée par plusieurs points de terminaison partageant le chemin audio).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td></td>
<td><p>Pourcentage de la session l’événement DeviceRenderZeroVolume a été déclenché pour être dans l’état « incorrect ». Le périphérique de rendu a été défini sur zéro volume.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td></td>
<td><p>Pourcentage de la session l’événement DeviceRenderMute a été déclenché pour être dans l’état « incorrect ». Le périphérique de rendu a été muet.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

