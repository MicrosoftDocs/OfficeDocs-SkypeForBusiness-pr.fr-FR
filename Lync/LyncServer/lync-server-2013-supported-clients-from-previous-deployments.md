---
title: 'Lync Server 2013 : Clients pris en charge provenant d’anciens déploiements'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b5cbecf45a9ea5203b3e459a895b2bddb0cfe55
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Clients pris en charge provenant d’anciens déploiements dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-12-14_

Dans un scénario de coexistence, les clients Lync Server 2013 peuvent interagir avec les clients provenant de versions antérieures de Lync Server et d’Office Communications Server. Contrairement aux versions précédentes, Lync Server 2010 prend en charge les nouveaux clients Lync 2013. Cela permet aux organisations qui effectuent la mise à niveau de Lync Server 2010 de déployer de nouveaux clients indépendamment des mises à niveau de Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Combinaisons serveur et client prises en charge

Le tableau ci-dessous indique les combinaisons prises en charge par les versions de client et serveur. Lync Server 2013 prend en charge deux versions précédentes du client et Lync Server 2010 prend en charge le nouveau client Lync 2013.


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
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Pris en charge </p></td>
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
<td><p>Lync 2010</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 attendant</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Conversation de groupe Lync 2010</p></td>
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
<td><p>Lync 2010 participant</p></td>
<td><p>Non Supported2</p></td>
<td><p>Pris en charge</p></td>
<td><p>Non pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 attendant</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non pris en charge</p></td>
<td><p>Pris en charge </p></td>
<td><p>Pris en charge</p></td>
</tr>
</tbody>
</table>


1Dans Microsoft Lync Server 2010, les fonctionnalités de discussion de groupe étaient disponibles avec le serveur de discussion de groupe, une application de confiance tierce pour Lync Server 2010. Les clients 2013 Lync ne sont pas compatibles avec Lync Server 2010 et la discussion de groupe.

2Lync Web App 2013 offre désormais une prise en compte complète de la réunion, y compris le son et la vidéo de l’ordinateur, et est considérée comme un élément de remplacement de Lync 2010 Attendee.

3La fonctionnalité de présence et de messagerie instantanée dans Office Communicator 2007 R2 est compatible avec Lync Server 2013, mais pas les fonctionnalités de conférence. Lors de la migration à partir d’Office Communications Server 2007 R2, Office Communicator 2007 R2 est approprié pour l’interopérabilité de la présence et de la messagerie instantanée, mais les utilisateurs doivent utiliser Lync Web App 2013 pour participer aux réunions Lync Server 2013.

<div>


> [!NOTE]  
> Pour plus d’informations sur la possibilité pour les clients de Lync Server 2013 de cohabiter et d’interagir avec les clients provenant de versions antérieures de Lync Server et d’Office Communications Server, voir <A href="lync-server-2013-client-interoperability-in-lync-2013.md">interopérabilité client dans lync 2013</A> dans la documentation de planification.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

