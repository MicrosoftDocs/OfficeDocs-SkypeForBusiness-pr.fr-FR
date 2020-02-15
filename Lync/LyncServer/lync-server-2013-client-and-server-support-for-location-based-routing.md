---
title: 'Lync Server 2013 : prise en charge des clients et des serveurs pour le routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efdb03adbdf1392e27c3107eef4aaf97f3708e66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-18_

Le routage géodépendant est appliqué par Lync Server. Lync Server peut identifier les sites réseau sur lesquels les utilisateurs se connectent à partir du réseau d’entreprise. Étant donné que les utilisateurs distants se trouvent à l’extérieur du réseau d’entreprise, leur emplacement est considéré comme inconnu.

<div>

## <a name="lync-server-support"></a>Prise en charge de Lync Server

Le routage géodépendant nécessite que Lync Server 2013 CU1 soit déployé sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée. Si Lync Server 2013 CU1 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage géodépendant ne peuvent pas être entièrement appliquées.

Le tableau suivant identifie les combinaisons de rôles serveur et de versions prises en charge pour le routage géodépendant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Version du pool</th>
<th>Version du serveur de médiation</th>
<th>Pris en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>oui</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>indifférent</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>indifférent</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>indifférent</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Prise en charge des clients Lync

Le tableau suivant identifie les clients pris en charge par le routage géodépendant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de client</th>
<th>Pris en charge</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>oui</p></td>
<td><p>Y compris la mise à jour cumulative de Lync 2013 février 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>oui</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Non</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>oui</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>oui</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync pour Windows 8</p></td>
<td><p>Non</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync mobile 2013</p></td>
<td><p>Non</p></td>
<td><p>La voix sur IP doit être désactivée pour les clients Lync mobile 2013 si elle est utilisée par des utilisateurs dont le routage géodépendant est activé.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>oui</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Pour désactiver VoIP pour les clients Lync mobile 2013, affectez une stratégie de mobilité avec le paramètre, audio/vidéo IP, désactivé pour tous les utilisateurs activés pour le routage géodépendant. Pour plus d’informations sur la stratégie de mobilité, consultez la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

