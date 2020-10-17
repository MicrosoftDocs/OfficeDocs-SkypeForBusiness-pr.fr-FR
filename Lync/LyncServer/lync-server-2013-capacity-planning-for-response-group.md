---
title: 'Lync Server 2013 : planification de la capacité pour Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d89e2882d3f1990a794e103849c1fa705caca98b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508111"
---
# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Planification de la capacité pour Response Group dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

<div id="sectionSection0" class="section">

Le tableau suivant décrit le modèle utilisateur Response Group que vous pouvez utiliser comme base pour les exigences de planification de capacité.

<div>


> [!NOTE]  
> Les chiffres du tableau suivant supposent que vous utilisez des fichiers 16 kHz, mono, 16 bits (.wav) pour tous les fichiers audio Response Group. Si vous utilisez d’autres formats de fichier, tels que Windows Media Audio (.wma), les chiffres peuvent changer.



</div>

<div>


> [!IMPORTANT]  
> N’oubliez pas que pour la planification de capacité de récupération d’urgence, chaque pool d’un pool associé doit être capable de gérer les charges de travail de tous les groupes de réponse des deux pools.



</div>

### <a name="response-group-user-model"></a>Modèle utilisateur de Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Métrique</th>
<th>Par pool Enterprise Edition (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels entrants par seconde</p></td>
<td><p>16 </p></td>
<td><p>n°2</p></td>
</tr>
<tr class="even">
<td><p>Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sessions anonymes simultanées (sans messagerie instantanée)</p></td>
<td><p>224</p></td>
<td><p>vingt</p></td>
</tr>
<tr class="even">
<td><p>Sessions anonymes simultanées (avec messagerie instantanée)</p></td>
<td><p>64</p></td>
<td><p>8 </p></td>
</tr>
<tr class="odd">
<td><p>Agents actifs (formels et informels)</p></td>
<td><p>1200</p></td>
<td><p>1200</p></td>
</tr>
<tr class="even">
<td><p>Nombre de groupes de recherche</p></td>
<td><p>400</p></td>
<td><p>400</p></td>
</tr>
<tr class="odd">
<td><p>Nombre de groupes de réponse vocale interactive (utilisation de la reconnaissance vocale)</p></td>
<td><p>200</p></td>
<td><p>200</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

