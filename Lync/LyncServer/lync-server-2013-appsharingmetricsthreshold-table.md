---
title: 'Tableau Lync Server 2013: AppSharingMetricsThreshold'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a>Table AppSharingMetricsThreshold dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-12-08_

La table AppSharingMetricsThreshold contient des valeurs optimales et acceptables pour la qualité de mesure d’utilisation utilisée avec le partage d’application. Ces seuils sont utilisés pour déterminer si l’utilisation du partage d’application doit être considérée comme médiocre.

Ce tableau a été présenté dans Microsoft Lync Server 2013.


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
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Type d’appel placé.</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limite maximale de bande passante pour le partage d’application. La valeur par défaut est 1 million.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Limitation de bande passante acceptable pour le partage d’application. La valeur par défaut est 500000.</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>Taux de pourcentage optimal pour les vignettes «abîmées» permettant de classer une qualité de partage d’application. Cette valeur correspond au pourcentage du contenu du partageur n’ayant pas atteint la visionneuse. Le contenu est susceptible d’être ignoré (ou abîmé) lorsque le partage annule les vignettes à partir de la source graphique ou que les vignettes ASMCU ignorent les vignettes du partage respectivement. La valeur par défaut est 11%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>décimale (5; 2)</p></td>
<td></td>
<td><p>taux de cceptable pour les vignettes «abîmées» permettant de classer une qualité de partage d’application. Cette valeur correspond au pourcentage du contenu du partageur n’ayant pas atteint la visionneuse. Le contenu est susceptible d’être ignoré (ou abîmé) lorsque le partage annule les vignettes à partir de la source graphique ou que les vignettes ASMCU ignorent les vignettes du partage respectivement. La valeur par défaut est 36%.</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Cette colonne n’est pas utilisée dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valeur optimale pour le retard relatif unidirectionnel entre les deux points de terminaison multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,0 secondes.</p>
<p>La colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valeur optimale pour le retard relatif unidirectionnel entre les deux points de terminaison multimédias impliqués dans le partage d’application. Il s’agit d’une mesure de latence sur un seul tronçon. La valeur par défaut est 1,75 secondes.</p>
<p>La colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valeur optimale de la latence moyenne du traitement de vignettes RDP sur le serveur de conférence en tant que serveur de conférence en fonction de la durée de la session d’affichage. La latence correspond au temps entre le moment où l’image de début est encodé sur le serveur (le partage ou la MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.</p>
<p>Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est 200 millions.</p>
<p>La colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Valeur acceptable de la latence moyenne du traitement de vignettes RDP sur le serveur de conférence en tant que serveur de conférence en fonction de la durée de la session d’affichage. La latence correspond au temps entre le moment où l’image de début est encodé sur le serveur (le partage ou la MCU en fonction du scénario) et la même image de démarrage est décodée sur la visionneuse.</p>
<p>Une moyenne élevée indique un délai plus long pour l’expérience de visionnage. Un serveur de conférence surchargé peut rencontrer des délais moyens plus élevés. La valeur par défaut est 200 millions.</p>
<p>La colonne a été introduite dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

