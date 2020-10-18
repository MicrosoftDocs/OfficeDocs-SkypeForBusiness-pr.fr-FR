---
title: 'Lync Server 2013 : vue d’inscription'
description: 'Lync Server 2013 : vue d’inscription.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578524"
---
# <a name="registration-view-in-lync-server-2013"></a>Vue d’enregistrement dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

L’affichage Inscription stocke les informations relatives à l’inscription de l’utilisateur. Cet affichage a été introduit dans Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type de données</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de la session. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de l’enregistrement.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type d’URI de l’utilisateur inscrit. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locataire de l’utilisateur inscrit. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>unique</p></td>
<td><p>Identificateur unique du point de terminaison auprès duquel l’utilisateur est inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>unique</p></td>
<td><p>Identificateur unique utilisé pour différencier les inscriptions du même utilisateur auprès du même point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure à laquelle la désinscription a eu lieu.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Raison de la désinscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version du client utilisé par l’utilisateur inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client utilisé par l’utilisateur inscrit. Pour plus d’informations, consultez la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie du client utilisée par l’utilisateur inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>IP</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Adresse IP avec laquelle l’utilisateur s’est inscrit. Il peut s’agit d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (775)</p></td>
<td><p>ID de dialogue SIP. Le format est :</p>
<p>boîte de dialogue ; balise ; à-tag</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Code de réponse SIP à l’invitation de session. Ce champ est généralement renseigné avec des données issues du message INVITE initial de la session. En l’absence de message INVITE, le champ est renseigné avec la date et l’heure du premier message SIP pertinent (BYE, CANCEL, MESSAGE ou INFO).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic capturé à partir de l’en-tête SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Inscriptions</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du serveur d’inscriptions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom de domaine complet du serveur Edge utilisé par l’utilisateur inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Indique si UserService était disponible au moment de l’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Indique si l’inscription a eu lieu auprès du serveur d’inscriptions principal.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>comportant</p></td>
<td><p>Adresse MAC de l’appareil inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Fabricant de l’appareil inscrit. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-manufacturers-table.md">table constructeurs dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version matérielle de l’appareil inscrit. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-hardwareversions-table.md">table table hardwareversions dans Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

