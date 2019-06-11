---
title: 'Lync Server 2013 : Planification de capacité de Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72f3e49806dc573a4e17bc917834deba97a74ca2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a>Planification de capacité de Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-29_

<div id="sectionSection0" class="section">

Le tableau suivant décrit le modèle utilisateur de Response Group que vous pouvez utiliser comme base pour les exigences de planification de capacité.

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
<th>Mesure</th>
<th>Par pool d’éditions d’entreprise (avec 8 serveurs frontaux)</th>
<th>Par serveur Standard Edition</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels entrants par seconde</p></td>
<td><p>Seiz</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Appels simultanés connectés à la réponse vocale interactive ou à l’attente musicale</p></td>
<td><p>480</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Sessions anonymes simultanées (sans messagerie instantanée)</p></td>
<td><p>224</p></td>
<td><p>12,70</p></td>
</tr>
<tr class="even">
<td><p>Sessions anonymes simultanées (avec messagerie instantanée)</p></td>
<td><p>64</p></td>
<td><p>version8</p></td>
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

