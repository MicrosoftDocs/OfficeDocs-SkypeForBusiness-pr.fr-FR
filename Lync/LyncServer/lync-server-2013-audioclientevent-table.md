---
title: 'Lync Server 2013 : Table AudioClientEvent'
TOCTitle: Table AudioClientEvent
ms:assetid: fef73d8f-7261-4e5b-9769-82435b007979
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg413086(v=OCS.15)
ms:contentKeyID: 49299452
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table AudioClientEvent dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement contient un événement client pour un point de terminaison dans un appel audio. En général, un appel a deux enregistrements, un pour l’appelant et un pour l’appelé.


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
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>FromCaller</strong></p></td>
<td><p>bit</p></td>
<td><p>Principal</p></td>
<td><p>0 : Données de l’appelé</p>
<p>1 : Données de l’appelant</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkSendQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement NetworkSendQuality a été déclenché pour cause d’état « incorrect ».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est lourde et elle a des répercussions sur la qualité de l’audio envoyé.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkReceiveQualityEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement ReceiveSendQuality a été déclenché pour cause d’état « incorrect ».</p>
<p>La qualité du réseau en termes de gigue ou de perte de paquets est lourde et elle a des répercussions sur la qualité de l’audio reçu.</p></td>
</tr>
<tr class="odd">
<td><p><strong>NetworkDelayEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement Delay a été déclenché pour cause d’état « incorrect ». La latence du réseau est lourde et elle a des répercussions sur l’utilisation en empêchant la communication interactive.</p></td>
</tr>
<tr class="even">
<td><p><strong>NetworkBandwidthLowEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement LowBandwidth a été déclenché pour cause d’état « incorrect ». La bande passante disponible est insuffisante pour une utilisation acceptable de la voix.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPUInsufficientEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement CPU a été déclenché pour cause d’état « incorrect ». Les cycles de processeur sont insuffisants pour traiter les modalités et applications actuelles en cours d’utilisation. Cette insuffisance provoque des distorsions dans le canal audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHalfDuplexAECEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceHalfDuplexAEC a été déclenché pour cause d’état « incorrect ». Pour éviter l’écho, le système est entré en mode semi-duplex.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceRenderNotFunctioning a été déclenché pour cause d’état « incorrect ». Le périphérique de rendu actuellement utilisé pour la session ne fonctionne pas correctement. Ce mauvais fonctionnement peut engendrer des problèmes audio unidirectionnels.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCaptureNotFunctioningEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceCaptureNotFunctioning a été déclenché pour cause d’état « incorrect ». Le périphérique de capture actuellement utilisé pour la session ne fonctionne pas correctement. Ce mauvais fonctionnement peut engendrer des problèmes audio unidirectionnels.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceGlitchesEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceGlitches a été déclenché pour cause d’état « incorrect ». Il existe de graves problèmes dans le rendu de l’audio, ce qui provoque des distorsions. Ces problèmes peuvent être dus à des problèmes de pilotes, un déferlement d’appels de procédure différés (DPC) et une utilisation processeur élevée.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceLowSNREventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceLowSNR a été déclenché pour cause d’état « incorrect ». La qualité de la capture est très faible, soit à cause du bruit, soit parce que l’utilisateur ne parle pas assez près du microphone. Ce problème engendre des distorsions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceLowSpeechLevelEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceLowSpeechLevel a été déclenché pour cause d’état « incorrect ». Le niveau de voix d’un utilisateur est trop faible et le système ne parvient pas à l’augmenter davantage. Cela peut engendrer des distorsions ou des problèmes audio unidirectionnels.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceClippingEventRatio</strong></p></td>
<td><p>Décimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceClipping a été déclenché pour cause d’état « incorrect ».</p>
<p>Lorsque la voix en fin de ligne écrête le microphone, l’extrémité entend des distorsions en raison de l’écrêtage. Il est important d’éviter tout écrêtage du microphone en fin de ligne.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceEchoEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceEchoEvent a été déclenché pour cause d’état « incorrect ». Le périphérique ou la configuration est à l’origine d’un écho que le système n’est pas capable de compenser.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceNearEndToEchoRatioEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de session auquel l’événement DeviceNearEndToEchoRatio a été déclenché pour cause d’état « incorrect ». La voix de l’utilisateur est trop faible par rapport à l’écho capturé, lequel a des répercussions sur l’expérience des utilisateurs car il limite la facilité avec laquelle il est possible d’interrompre un utilisateur. Réduisez le volume du haut-parleur, déplacez le microphone plus près de la personne qui parle.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceMultipleEndpointsEventCount</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Nombre de fois au cours de la session que l’événement DeviceMultipleEndpoints a été déclenché pour cause d’état « incorrect ». Plusieurs points de terminaison audio ont été détectés dans la même session et le système a compensé en réduisant le volume du rendu.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHowlingEventCount</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>Nombre de fois au cours de la session que l’événement DeviceHowlingEvent a été déclenché pour cause d’état « incorrect ». Une boucle d’effet larsen a été détectée (provoquée par le partage du chemin audio par plusieurs points de terminaison).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceRenderZeroVolumeEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Pourcentage de session auquel l’événement DeviceRenderZeroVolume a été déclenché pour cause d’état « incorrect ». Le volume du périphérique de rendu a été défini sur zéro.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceRenderMuteEventRatio</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Pourcentage de session auquel l’événement DeviceRenderMute a été déclenché pour cause d’état « incorrect ». Le volume du périphérique de rendu a été désactivé.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

