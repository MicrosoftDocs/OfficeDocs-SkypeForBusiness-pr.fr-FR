---
title: 'Lync Server 2013: affichage d’inscription'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823825"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a>Affichage inscription dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Le mode d’enregistrement enregistre des informations sur l’inscription des utilisateurs. Cet affichage a été présenté dans Lync Server 2013.


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
<td><p>Durée de la demande de session. Utilisé conjointement avec SessionIdSeq pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec SessionIdTime pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure à laquelle l’inscription s’est produite.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI de l’utilisateur inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">table UriTypes dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Client de l’utilisateur inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">table locataires dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>identificateur</p></td>
<td><p>Identificateur unique du point de terminaison de l’utilisateur enregistré avec.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>identificateur</p></td>
<td><p>Identificateur unique utilisé pour différencier les inscriptions qui impliquent le même utilisateur et le même point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure à laquelle l’annulation de l’inscription s’est produite.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Raison de l’annulation de l’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version du client utilisée par l’utilisateur inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>TypeClient</strong></p></td>
<td><p>int</p></td>
<td><p>Client utilisé par l’utilisateur inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">table UserAgentDef dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie du client utilisée par l’utilisateur qui est inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>Grat</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Adresse IP de l’utilisateur avec lequel il a été enregistré. Il s’agit éventuellement d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring (LGA775)</p></td>
<td><p>ID de boîte de dialogue SIP. Le format de:</p>
<p>boîte de dialogue; à partir d’une balise</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Code de réponse SIP à l’invitation de la session. Ce champ est généralement rempli par des données générées à partir du message d’invitation initial dans la session. S’il n’y a pas de message d’invitation, le champ est peuplé de la date et de l’heure du premier message SIP approprié (BYE, annuler, MESSAGE ou informations).</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p>ID de diagnostic capturé à partir de l’en-tête SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>serveur d’inscriptions</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du Bureau d’enregistrement.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du serveur Edge utilisé par l’utilisateur qui est inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’utilisateur s’est connecté à partir du réseau interne.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’UserService a été disponible au moment de l’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’inscription a été apportée au bureau d’enregistrement principal.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p>Adresse MAC de l’appareil inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Fabricant de l’appareil inscrit. Pour plus d’informations, reportez-vous <a href="lync-server-2013-manufacturers-table.md">à la table fabricants dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version matérielle de l’appareil inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-hardwareversions-table.md">table HardwareVersions dans Lync Server 2013</a> .</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

