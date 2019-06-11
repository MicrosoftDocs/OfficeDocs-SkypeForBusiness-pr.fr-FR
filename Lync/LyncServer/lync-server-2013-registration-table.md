---
title: 'Lync Server 2013 : Table Registration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a>Table Registration dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-28_

Chaque enregistrement représente un événement d’inscription utilisateur.


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
<td><p>Etranger principal</p></td>
<td><p>Durée de la demande de session. Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>IDENTIFIant de l’utilisateur. Pour plus d’informations, consultez le <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>identificateur</p></td>
<td></td>
<td><p>GUID permettant d’identifier un point de terminaison d’inscription. En règle générale, l’événement Register sur le même ordinateur que le même utilisateur aura le même ID de point de terminaison. Différents ordinateurs ont un ID de point de terminaison différent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>Identificateur</p></td>
<td></td>
<td><p>ID utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Version du client de l’utilisateur actuel. Pour plus d’informations, voir la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du serveur d’inscriptions utilisé pour l’inscription. Pour plus d’informations, voir le <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, voir la <a href="lync-server-2013-pools-table.md">table pools dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>Serveur Edge le passage à l’inscription. Pour plus d’informations, voir la <a href="lync-server-2013-edgeservers-table.md">table EdgeServers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Résolution</p></td>
<td></td>
<td><p>Si l’utilisateur est connecté à partir d’une connexion interne ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Si le UserService est disponible ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>S’il est inscrit au bureau d’enregistrement principal ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Indique si l’utilisateur est inscrit auprès d’une unité de branchement survivant.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Durée de l’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Durée de l’inscription.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Code de réponse de la demande Register.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnostic de la demande d’enregistrement. Ce type d’informations indique ce type d’informations de diagnostic.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Externes</p></td>
<td><p>L’appareil à partir duquel la requête d’enregistrement provient. Pour plus d’informations, voir le <a href="lync-server-2013-devices-table.md">tableau des appareils dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Externes</p></td>
<td><p>La raison de l’annulation de l’inscription, par exemple «initié par l’utilisateur», «inscription expirée», «échec du client», etc. Pour plus d’informations, voir la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Adresse IP du point de terminaison avec lequel l’utilisateur a été enregistré. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

