---
title: 'Lync Server 2013 : vue FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c5c10cc90064e9ed3237dcd4cd4cbed1021d1b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a>Vue FocusJoinsAndLeaves dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon. Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue a été introduite dans Microsoft Lync Server 2013.


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
<td><p>Heure de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-conferences-table.md">tableau conférences de Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Type d’URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Locataire de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-tenants-table.md">table clients dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>unique</p></td>
<td><p>Identificateur unique de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Version de client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-useragentdef-table.md">table table useragentdef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Bit qui indique si l’utilisateur est un utilisateur interne ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, reportez-vous au <a href="lync-server-2013-dialogs-table.md">tableau boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne UserInstance permet d’identifier de manière unique la combinaison utilisateur/périphérique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar (775)</p></td>
<td><p>ID de dialogue SIP de la session. Le format est le suivant : dialogue;balise-départ;balise-destination.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure à laquelle cet utilisateur a rejoint la conférence.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure à laquelle cet utilisateur a quitté la conférence.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

