---
title: 'Lync Server 2013 : clients pris en charge par les déploiements précédents'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cff76b750b2c6643ec1bf6ac3419a9892719ea4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Clients pris en charge par les déploiements précédents dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-14_

Dans un scénario de coexistence, les clients Lync Server 2013 peuvent interagir avec les clients provenant de versions antérieures de Lync Server et Office Communications Server. Contrairement aux versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013. Cela permet aux organisations qui effectuent une mise à niveau à partir de Lync Server 2010 de déployer de nouveaux clients indépendamment des mises à niveau Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Combinaisons de serveur et de client prises en charge

Le tableau suivant dresse la liste des combinaisons prises en charge selon la version du client et du serveur. Lync Server 2013 prend en charge deux versions antérieures de client, et Lync Server 2010 prend en charge le nouveau client Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>conversation de groupe Lync 2010</p></td>
<td><p>Non applicable</p></td>
<td><p>Supported1</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Non Supported2</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge</p></td>
<td><p>Pris en charge</p></td>
</tr>
</tbody>
</table>


1Dans Microsoft Lync Server 2010, la fonctionnalité de conversation de groupe était disponible avec le serveur de conversation de groupe, une application tierce approuvée pour Lync Server 2010. Les clients Lync 2013 ne sont pas compatibles avec Lync Server 2010, Group chat.

2Lync Web App 2013 offre désormais une expérience complète en matière de réunion, y compris l’audio et la vidéo de l’ordinateur, et est considérée comme le remplacement de Lync 2010 Attendee.

les fonctionnalités de présence et de messagerie instantanée d’Office Communicator 2007 R2 sont compatibles avec Lync Server 2013, mais pas les fonctionnalités de conférence. Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 convient à l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour rejoindre des réunions Lync Server 2013.

<div>


> [!NOTE]  
> Pour plus d’informations sur la capacité des clients Lync Server 2013 à coexister et à interagir avec les clients provenant de versions antérieures de Lync Server et Office Communications Server, voir <A href="lync-server-2013-client-interoperability-in-lync-2013.md">interopérabilité des clients dans lync 2013</A> dans la documentation de planification.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

