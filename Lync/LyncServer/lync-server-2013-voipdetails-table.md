---
title: 'Lync Server 2013 : Table VoipDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VoipDetails table
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398566(v=OCS.15)
ms:contentKeyID: 48184522
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7879f5dc7d5b884dfc2d3777ed4fa800978a3cff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="voipdetails-table-in-lync-server-2013"></a>Table VoipDetails dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Chaque enregistrement 1 2 représente un appel vers un tiers, dont au moins un utilisateur est une VoIP.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Principal</p></td>
<td><p>Durée de la demande de session. Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p><strong>PhoneId</strong> de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> . Si ce n’est pas nul et que <strong>FromGatewayId</strong> n’est pas null, l’appelant était un utilisateur PSTN.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p><strong>PhoneId</strong> du destinataire de l’appel. Pour plus d’informations, voir la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> . Si ce n’est pas nul et que <strong>ToGatewayId</strong> n’est pas null, le destinataire de l’appel était un utilisateur RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur de médiation depuis lequel l’appel provient. Pour plus d’informations, voir la <a href="lync-server-2013-mediationservers-table.md">table MediationServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Le serveur de médiation appelé va. Pour plus d’informations, voir la <a href="lync-server-2013-mediationservers-table.md">table MediationServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Passerelle provenant de l’appel. Pour plus d’informations, voir le <a href="lync-server-2013-gateways-table.md">tableau passerelles dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Passerelle de destination de l’appel. Pour plus d’informations, voir le <a href="lync-server-2013-gateways-table.md">tableau passerelles dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>URI de l’utilisateur qui a déconnecté l’appel, s’il possède un URI. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du téléphone sur lequel l’appel a été déconnecté d’un téléphone. Pour plus d’informations, voir la <a href="lync-server-2013-phones-table.md">table téléphones dans Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

