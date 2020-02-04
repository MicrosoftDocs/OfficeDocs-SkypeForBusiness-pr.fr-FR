---
title: 'Lync Server 2013 : Prise en charge des clients et des serveurs pour le routage géodépendant'
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
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Prise en charge des clients et des serveurs pour le routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-06-18_

Le routage basé sur l’emplacement est appliqué par Lync Server. Lync Server peut identifier les sites réseau dans lesquels les utilisateurs se connectent au sein du réseau d’entreprise. Comme les utilisateurs distants sont situés en dehors du réseau d’entreprise, leur emplacement est considéré comme inconnu.

<div>

## <a name="lync-server-support"></a>Prise en charge de Lync Server

Le routage basé sur l’emplacement nécessite le déploiement de Lync Server 2013 CU1 sur tous les pools frontaux et les serveurs Standard Edition dans une topologie donnée. Si Lync Server 2013 CU1 n’est pas installé sur certains composants Lync dans la topologie, les restrictions de routage basées sur l’emplacement ne peuvent pas être entièrement appliquées.

Le tableau suivant identifie la combinaison des rôles de serveur et des versions prises en charge pour le routage par emplacement.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Version du pool</th>
<th>Version de serveur de médiation</th>
<th>Pris en charge</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>Mise à jour cumulative de Lync Server 2013 février 2013</p></td>
<td><p>Oui</p></td>
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
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>Quelconque</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>Quelconque</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Quelconque</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Prise en charge du client Lync

Le tableau suivant identifie les clients pris en charge par le routage de l’emplacement.


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
<td><p>Lync 2013</p></td>
<td><p>Oui</p></td>
<td><p>Y compris la mise à jour cumulative de Lync 2013 février 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Non</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync pour Windows 8</p></td>
<td><p>Non</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>2013 mobile Lync</p></td>
<td><p>Non</p></td>
<td><p>VoIP doit être désactivée pour les clients 2013 mobiles Lync, s’il est utilisé par les utilisateurs avec le routage par emplacement activé.</p></td>
</tr>
<tr class="even">
<td><p>2010 mobile Lync</p></td>
<td><p>Oui</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Pour désactiver la voix sur IP (VoIP) pour les clients 2013 Lync mobile, attribuez une stratégie de mobilité avec le paramètre, audio/vidéo IP désactivé pour tous les utilisateurs activés pour le routage en fonction de l’emplacement. Pour plus d’informations sur la stratégie de mobilité, reportez-vous à <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



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

