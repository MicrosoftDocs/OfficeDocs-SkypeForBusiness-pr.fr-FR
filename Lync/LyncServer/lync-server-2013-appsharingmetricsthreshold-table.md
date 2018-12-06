---
title: Table AppSharingMetricsThreshold dans Lync Server 2013
TOCTitle: Table AppSharingMetricsThreshold
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205018(v=OCS.15)
ms:contentKeyID: 49297795
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table AppSharingMetricsThreshold dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-12-08_

La table AppSharingMetricsThreshold contient les valeurs optimales et acceptables des mesures de qualité de l’expérience (QoE) utilisées avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’expérience de partage d’application doit être qualifiée de médiocre.

Cette table est une nouveauté de Microsoft Lync Server 2013.


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
<td><p><strong>CallType</strong></p></td>
<td><p>entier</p></td>
<td><p>Primaire</p></td>
<td><p>Type d’appel passé.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Limite de bande passante optimale pour le partage d’application. La valeur par défaut est 1 000 000.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Limite de bande passante acceptable pour le partage d’application. La valeur par défaut est 500 000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>décimal(5,2)</p></td>
<td><p></p></td>
<td><p>Pourcentage optimal de mosaïques altérées pour la classification de la qualité d’un partage d’application. Cette valeur correspond au pourcentage de contenu provenant de la personne à l’initiative du partage qui n’a pas atteint les utilisateurs. Le contenu peut être ignoré (ou altéré) lorsque la personne à l’initiative du partage ignore des mosaïques de la source des graphiques ou lorsque les mosaïques ASMCU ignorent des mosaïques provenant de la personne à l’initiative du partage. La valeur par défaut est 11.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>décimal(5,2)</p></td>
<td><p></p></td>
<td><p>Pourcentage acceptable de mosaïques altérées pour la classification de la qualité d’un partage d’application. Cette valeur correspond au pourcentage de contenu provenant de la personne à l’initiative du partage qui n’a pas atteint les utilisateurs. Le contenu peut être ignoré (ou altéré) lorsque la personne à l’initiative du partage ignore des mosaïques de la source des graphiques ou lorsque les mosaïques ASMCU ignorent des mosaïques provenant de la personne à l’initiative du partage. La valeur par défaut est 36.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>entier</p></td>
<td><p></p></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Valeur optimale du retard unidirectionnel relatif entre les deux systèmes d’extrémité multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,0 seconde.</p>
<p>La colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Valeur optimale du retard unidirectionnel relatif entre les deux systèmes d’extrémité multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 s.</p>
<p>La colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Valeur optimale de latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. Cette mesure ne couvre pas la latence du réseau.</p>
<p>Une moyenne élevée indique un délai d’affichage plus long. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.</p>
<p>La colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>flottant</p></td>
<td><p></p></td>
<td><p>Valeur acceptable de latence moyenne de traitement des mosaïques RDP sur le serveur de conférence AS par rapport à la durée de la session de visionnage. Cette mesure ne couvre pas la latence du réseau.</p>
<p>Une moyenne élevée indique un délai d’affichage plus long. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est de 200 ms.</p>
<p>La colonne est une nouveauté de Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

