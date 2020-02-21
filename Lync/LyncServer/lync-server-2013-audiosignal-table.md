---
title: 'Lync Server 2013 : table table audiosignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de07393ef9f43346d0c1b4c96dcfdcf33f00513a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195837"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Table table audiosignal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-12_

Chaque enregistrement représente les mesures de signal audio pour un point de terminaison. En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelé.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Représente le niveau de signal audio post-analogue de contrôle de gain. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit s’élever à 30 dBmo au moins. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Voir SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Représente le niveau de bruit post-analogique de contrôle de gain. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Voir SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Mesure d’amélioration de la perte d’écho. L’unité de mesure est dB. Des valeurs inférieures représentent moins d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre moyen de problèmes par cinq minutes pour le rendu du haut-parleur. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre moyen de problèmes par cinq minutes pour la capture du microphone. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>décimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Vitesse de dérive de l’horloge du microphone, par rapport à l’horloge de l’UC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>décimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Taux de dérive de l’horloge du périphérique haut-parleur par rapport à l’horloge de l’UC.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>décimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Taux de dérive de l’horloge du périphérique haut-parleur par rapport à l’horloge de l’UC.</p>
<p>Durée moyenne d’erreur d’horodatage du flux de capture du microphone, en millisecondes, au cours des 20 dernières secondes de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>décimal (9, 2)</p></td>
<td><p> </p></td>
<td><p>Nombre moyen d’erreurs d’horodatage de flux de rendu, en millisecondes, au cours des 20 dernières secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>type</p></td>
<td><p> </p></td>
<td><p>Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée. Causes de l’entrée de commutateur vocal :</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La cause peut être une combinaison de ces causes. ENTER_VS_FORCEORCONVERGENCE ne peut être activé que par la fonction RegKey à des fins de test.</p>
<p>Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>entier très petit</p></td>
<td><p> </p></td>
<td><p>Causes d’un événement ECHO :</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>La cause peut être une combinaison de ces causes.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td><p> </p></td>
<td><p>Pourcentage de temps pendant lequel l’écho a été détecté dans le flux de capture du microphone. En règle générale, les valeurs sont faibles pour les casques ou les combinés, et supérieures pour les téléphones de haut-parleur ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge l’annulation de l’écho acoustique intégré, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>décimal (5, 2)</p></td>
<td></td>
<td><p>Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé. Un pourcentage d’écho élevé lors de l’envoi est une indication de fuite d’écho.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Niveau de signal reçu sur le serveur de médiation à partir de la passerelle ; Cela s’applique uniquement au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être de -30 à -18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Niveau de signal reçu sur le serveur de médiation à partir de la passerelle. Cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Contrôle de gain automatique (AGC) sur le côté serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>flottant</p></td>
<td><p> </p></td>
<td><p>La moyenne quadratique (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de signal reçu sur le canal 1.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de signal reçu sur le canal 2.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de bruit reçu sur le canal 1.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau sonore reçu sur le canal 2.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de signal tel qu’il est envoyé sur le canal 1.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de signal tel qu’il est envoyé sur le canal 2.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de bruit tel qu’il est envoyé sur le canal 1.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau de bruit tel qu’il est envoyé sur le canal 2.</p>
<p>Cette chronique a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

