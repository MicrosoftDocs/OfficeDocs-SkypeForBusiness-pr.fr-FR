---
title: 'Lync Server 2013 : planification de la capacité pour le prélèvement d’appels de groupe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Planification de la capacité pour le prélèvement d’appels de groupe dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-12_

<div id="sectionSection0" class="section">

Le tableau suivant décrit le modèle d’utilisateur de capture d’appel de groupe que vous pouvez utiliser comme base pour les exigences de planification de capacité.

<div>


> [!IMPORTANT]  
> Le prélèvement d’appels de groupe est basé sur l’application de parc d’appels. N’oubliez pas que, pour la planification de la capacité de reprise après sinistre, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail pour les services de parking d’appel, y compris le regroupement des appels de groupe, dans les deux pools.



</div>

### <a name="group-call-pickup-user-model"></a>Modèle utilisateur de cueillette d’appel de groupe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Mesure</th>
<th>Par pool frontal (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre recommandé d’utilisateurs par groupe</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Nombre recommandé de groupes</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Nombre maximum d’utilisateurs par pool autorisé pour la prise d’appel de groupe</p></td>
<td><p>25 000</p></td>
<td><p>3 000</p></td>
</tr>
<tr class="even">
<td><p>Rapport maximal entre le nombre d’appels entrants et le nombre total d’utilisateurs autorisé pour la prise d’appel de groupe par pool et par minute</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute</p></td>
<td><p>200</p></td>
<td><p>1,25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Pour les pools front-end possédant moins de huit serveurs frontaux, calculez les métriques de manière linéaire. Par exemple, si votre pool frontal comporte un serveur frontal, calculez le chargement maximum comme 1/8 de valeurs affichées dans le tableau.</P>
> <LI>
> <P>Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre d’utilisateurs maximal par pool. Par exemple, votre serveur édition standard peut avoir des groupes 120 avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la capture d’appels de groupe est toujours au maximum au niveau du modèle utilisateur (c’est-à-dire, 120 3 000 groupes).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

