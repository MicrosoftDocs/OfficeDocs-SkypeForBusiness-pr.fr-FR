---
title: 'Lync Server 2013 : table AudioSignal'
TOCTitle: Table AudioSignal
ms:assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398064(v=OCS.15)
ms:contentKeyID: 49296048
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table AudioSignal de Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente les mesures du signal audio d’un point de terminaison. En règle générale, chaque appel a deux enregistrements, l’un pour l’appelant et l’autre pour l’appelé.²²


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
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
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
<td><p>0 : données de l’appelé</p>
<p>1 : données de l’appelant</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Représente le niveau de signal audio du réglage de puissance post-analogique. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit au moins s’élever à 30 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consultez SendSignalLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Représente le niveau de bruit audio du réglage de puissance post-analogique. L’unité de mesure est dBmo. Pour une qualité acceptable, il doit être inférieur à 35 dBmo. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Consultez SendNoiseLevel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoReturn</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Mesure de l’amélioration de la perte du retour d’écho. L’unité de mesure est dB. Plus la valeur est faible, moins il y a d’écho. Cette mesure n’est pas signalée par le serveur de conférence A/V ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSpeakerGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre moyen de problèmes audio par période de 5 minutes pour le rendu des haut-parleurs. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioMicGlitchRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Nombre moyen de problèmes audio par période de 5 minutes pour la capture du microphone. Pour une bonne qualité, il doit être inférieur à un par période de 5 minutes. Non signalé par les serveurs de conférence A/V, les serveurs de médiation ou les téléphones IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampDriftRateMic</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Débit de dérive de l’horloge du microphone, relativement à l’horloge de l’UC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampDriftRateSpk</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Débit de dérive de l’horloge des haut-parleurs, relativement à l’horloge de l’UC.</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioTimestampErrorMicMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Débit de dérive de l’horloge des haut-parleurs, relativement à l’horloge de l’UC.</p>
<p>Nombre moyen d’erreurs d’horodatage du flux de capture du microphone, en millisecondes, dans les 20 dernières secondes de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioTimestampErrorSpkMs</strong></p></td>
<td><p>decimal(9,2)</p></td>
<td><p> </p></td>
<td><p>Nombre moyen d’erreurs d’horodatage du flux de capture du rendu des haut-parleurs, en millisecondes, dans les 20 dernières secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>VsEntryCauses</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>Un commutateur vocal est un mode semi-duplex avec une capacité d’interruption limitée. Causes de l’entrée du commutateur vocal :</p>
<p>ENTER_VS_BADTS 0x01</p>
<p>ENTER_VS_ECHO 0x02</p>
<p>ENTER_VS_FORCEORCONVERGENCE 0x04</p>
<p>ENTER_VS_DNLP 0x08</p>
<p>La cause peut être une combinaison de ces causes individuelles. ENTER_VS_FORCEORCONVERGENCE peut uniquement être activé par regkey à des fins de test.</p>
<p>Le type des données pour cette colonne a été changé dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoEventCauses</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>Causes d’un événement d’écho :</p>
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
<td><p>decimal(5,2)</p></td>
<td><p> </p></td>
<td><p>Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EchoPercentSend</strong></p></td>
<td><p>decimal(5,2)</p></td>
<td><p></p></td>
<td><p>Temps en pourcentage lors de la détection d’un écho dans le flux d’envoi. Un pourcentage d’écho élevé lors de l’envoi transmet une indication de fuite d’écho.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAGCSignalLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Niveau de signal reçu sur le serveur de médiation à partir de la passerelle ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être [-30 à -18] dBoV.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RxAGCNoiseLevel</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Niveau de signal reçu sur le serveur de médiation à partir de la passerelle ; cela ne s’applique qu’au serveur de médiation. L’unité de mesure est dBoV. Pour une bonne qualité, la plage acceptable doit être inférieure à -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p><strong>RxAvgAGCGain</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Réglage de la puissance automatique côté serveur de médiation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>InitialSignalLevelRMS</strong></p></td>
<td><p>float</p></td>
<td><p> </p></td>
<td><p>Valeur quadratique moyenne du signal d’entrée jusqu’aux 30 premières secondes de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau du signal reçu sur le canal 1.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau du signal reçu sur le canal 2.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau sonore reçu sur le canal 1.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau sonore reçu sur le canal 2.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendSignalLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau du signal envoyé sur le canal 1.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendSignalLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau du signal envoyé sur le canal 2.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>SendNoiseLevelCh1</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau sonore envoyé sur le canal 1.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendNoiseLevelCh2</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Niveau sonore envoyé sur le canal 2.</p>
<p>Cette colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

