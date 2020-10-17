---
title: 'Lync Server 2013 : planification de la capacité pour la prise d’appel de groupe'
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
ms.openlocfilehash: c073ea360e00b196e6cf30b6bb6f204d37532ae0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512811"
---
# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Planification de la capacité pour la prise d’appel de groupe dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-12_

<div id="sectionSection0" class="section">

Le tableau suivant décrit le modèle utilisateur de prise d’appel de groupe que vous pouvez utiliser comme base pour les exigences de planification de capacité.

<div>


> [!IMPORTANT]  
> La prise d’appel de groupe est basée sur l’application de parcage d’appel. N’oubliez pas que, pour la planification de la capacité de récupération d’urgence, chaque pool d’un pool couplé doit être en mesure de gérer les charges de travail des services de parcage d’appel, y compris la prise d’appel de groupe, dans les deux pools.



</div>

### <a name="group-call-pickup-user-model"></a>Modèle utilisateur de prise d’appel de groupe

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrique</th>
<th>Par pool frontal (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre d’utilisateurs par groupe recommandé</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Nombre recommandé de groupes</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Nombre maximal d’utilisateurs par pool activé pour la prise d’appel de groupe</p></td>
<td><p>25 000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>Taux maximal d’appels entrants vers le total des utilisateurs activés pour la prise d’appel de groupe par pool et par minute</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Taux maximal d’appels récupérés par les utilisateurs avec la prise d’appel de groupe par pool et par minute</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Pour les pools frontaux qui ont moins de huit serveurs frontaux, calculez les mesures de manière linéaire. Par exemple, si votre pool frontal dispose d’un serveur frontal, calculez la charge maximale sur 1/8 des valeurs indiquées dans le tableau.</P>
> <LI>
> <P>Vous pouvez augmenter ou diminuer le nombre d’utilisateurs par groupe et le nombre de groupes recommandés tant que vous ne dépassez pas le nombre maximal d’utilisateurs par pool. Par exemple, votre serveur Standard Edition peut avoir 120 groupes avec 25 utilisateurs par groupe, car le nombre d’utilisateurs activés pour la prise d’appel de groupe se trouve toujours dans le maximum du modèle utilisateur (autrement dit, 120 groupes fois que 25 utilisateurs 3 000 sont activés pour la prise d’appel de groupe).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

