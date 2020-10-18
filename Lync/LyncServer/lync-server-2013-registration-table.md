---
title: 'Lync Server 2013 : table d’enregistrement'
description: 'Lync Server 2013 : table d’inscription.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578523"
---
# <a name="registration-table-in-lync-server-2013"></a>Table Registration dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Chaque enregistrement représente un événement relatif à l’inscription d’un utilisateur.


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée conjointement avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID pour identifier la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>ID de l’utilisateur. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-users-table.md">tableau utilisateurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>unique</p></td>
<td></td>
<td><p>GUID pour identifier un système d’extrémité d’inscription. Généralement, l’événement d’inscription d’un même ordinateur et d’un même utilisateur aura le même ID de système d’extrémité. Des ordinateurs différents ont un ID de système d’extrémité différent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>Unique</p></td>
<td></td>
<td><p>ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Version du client de l’utilisateur actuel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">table ClientVersions dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>ID du serveur d’inscriptions utilisé pour l’inscription. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-servers-table.md">tableau des serveurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-pools-table.md">tableau pools dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>Serveur Edge sur lequel l’inscription a lieu. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">table table edgeservers dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Légèrement</p></td>
<td></td>
<td><p>Si l’utilisateur est connecté en interne ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Si UserService est disponible ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Si l’inscription est effectuée sur le serveur d’inscriptions principal ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>légèrement</p></td>
<td></td>
<td><p>Indique si l’utilisateur est inscrit ou non avec un Survivable Branch Appliance.</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure d’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td></td>
<td><p>Heure de désinscription.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Code de réponse de la demande d’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>ID de diagnostic de la demande d’inscription. Indique les informations du type de diagnostic.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger</p></td>
<td><p>L’appareil à partir duquel est émise la demande d’inscription. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-devices-table.md">tableau périphériques dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>entier très petit</p></td>
<td><p>Etranger</p></td>
<td><p>La raison de l’annulation de l’inscription, par exemple « initié par l’utilisateur », « expiration de l’inscription », « échec du client », et bien plus encore. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-deregistertype-table.md">table DeRegisterType dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Adresse IP du point de terminaison avec laquelle l’utilisateur s’est inscrit. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</p>
<p>Ce champ a été introduit dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

