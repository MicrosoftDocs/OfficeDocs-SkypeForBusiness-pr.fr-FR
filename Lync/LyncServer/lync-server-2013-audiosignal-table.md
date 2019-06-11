---
title: 'Lync Server 2013 : table AudioSignal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioSignal table
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398064(v=OCS.15)
ms:contentKeyID: 48183217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6605a25191906660bbad11908f754a81360c893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiosignal-table-in-lync-server-2013"></a>Table AudioSignal de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-12_

Chaque enregistrement représente les métriques du signal audio pour un point de terminaison. En règle générale, chaque appel comporte deux enregistrements, l’un pour l’appelant et l’autre pour l’appelant.


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
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Représente le niveau du signal audio après le contrôle du gain. L’unité de cette métrique est dBmo. Pour une qualité acceptable, il devrait représenter au moins 30 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
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
<td><p>Représente le niveau de bruit sonore du contrôle post-analogue. L’unité de cette métrique est dBmo. Pour une qualité acceptable, elle doit être inférieure à 35 dBmo. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
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
<td><p>Métrique d’amélioration de retour d’écho. L’unité de cette métrique est dB. Les valeurs inférieures représentent moins d’écho. Cette métrique n’est pas communiquée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Moyenne des problèmes par cinq minutes pour le rendu du haut-parleur. Pour une qualité optimale, cela devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Moyenne des problèmes par cinq minutes pour la capture du micro. Pour une qualité optimale, il devrait être inférieur à une par cinq minutes. Non communiquées par des serveurs de conférence A/V, des serveurs de médiation ou des téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>décimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Taux d’horloge de l’horloge du périphérique microphone par rapport à l’horloge de l’UC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>décimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Taux d’horloge du périphérique de haut-parleurs par rapport à l’horloge du processeur.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>décimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Taux d’horloge du périphérique de haut-parleurs par rapport à l’horloge du processeur.</p>
<p>Erreur d’horodatage du flux de capture de microphone moyenne, en millisecondes, au cours des dernières 20 secondes de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>décimale (9; 2)</p></td>
<td><p> </p></td>
<td><p>Erreur d’horodatage moyenne du flux de rendu du présentateur, en millisecondes, au cours des dernières 20 secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>type</p></td>
<td><p> </p></td>
<td><p>Le commutateur vocal est un mode semi-duplex présentant une capacité d’interruption réduite. Causes de l’entrée du commutateur vocal:</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La cause peut être une combinaison de ces causes individuelles. ENTER_VS_FORCEORCONVERGENCE peut uniquement être activé par RegKey à des fins de test.</p>
<p>Le type de données de cette colonne a été modifié dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Causes d’un événement ECHO:</p>
<p>ECHO_EVENT_BAD_TIMESTAMP 0x01</p>
<p>ECHO_EVENT_POSTAEC_ECHO 0x02</p>
<p>ECHO_EVENT_ANLP 0x04</p>
<p>ECHO_EVENT_DNLP 0x08</p>
<p>ECHO_EVENT_MIC_CLIPPING 0x10</p>
<p>ECHO_EVENT_BAD_STATE 0x20</p>
<p>La cause peut être une combinaison de ces causes individuelles.</p></td>
</tr>
<tr class="even">
<td><p><strong>EchoPercentMicIn</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td><p> </p></td>
<td><p>Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Pourcentage de temps pendant lequel l’écho est détecté dans le flux envoyé. Pourcentage d’écho élevé dans les flux d’envoi indicateur de fuite d’écho.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Reçu le niveau du signal sur le serveur de médiation de la passerelle; Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être comprise entre [-30 et-18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Reçu le niveau du signal sur le serveur de médiation de la passerelle. Cela s’applique uniquement au serveur de médiation. L’unité de cette valeur est dBoV. Pour une qualité optimale, la plage acceptable doit être inférieure à-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Contrôle automatique de gain sur le côté serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>Le carré moyen racine (RMS) du signal entrant jusqu’aux 30 premières secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau du signal reçu sur le canal 1.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau du signal reçu sur le canal 2.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau sonore reçu sur canal 1.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau sonore reçu sur canal 2.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau du signal envoyé sur canal 1.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau du signal envoyé sur canal 2.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau sonore tel qu’il est envoyé sur canal 1.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Niveau sonore tel qu’il est envoyé sur canal 2.</p>
<p>Cette colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

