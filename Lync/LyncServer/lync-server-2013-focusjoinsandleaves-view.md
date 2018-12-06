---
title: Vue FocusJoinsAndLeaves
TOCTitle: Vue FocusJoinsAndLeaves
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49891264
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue FocusJoinsAndLeaves

 

_**Dernière rubrique modifiée :** 2015-03-09_

La vue FocusJoinsAndLeaves stocke des informations sur la participation à une conférence ainsi qu’à son abandon. Chaque conférence est représentée dans cette vue par un enregistrement renseigné chaque fois qu’un utilisateur rejoint et quitte la conférence. Cette vue est une nouveauté de Microsoft Lync Server 2013.


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
<td><p>Heure de l’instance de conférence. Utilisé conjointement avec SessionIdSeq pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de l’instance de conférence. Utilisé conjointement avec SessionIdTime pour identifier de manière unique une instance de conférence. Pour plus d’informations, voir la <a href="lync-server-2013-conferences-table.md">Table Conferences dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locataire de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique de l’utilisateur dont les informations de participation/d’abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version de client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client de l’utilisateur dont les informations de participation/abandon de conférence ont été capturées. Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Nom de la catégorie du client utilisé par l’utilisateur dont les informations de participation/abandon de conférence ont été capturées.</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Bit qui indique si l’utilisateur est un utilisateur interne ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Heure de la demande de session. Utilisée conjointement avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Si un utilisateur est connecté sur plusieurs ordinateurs ou périphériques en même temps, la colonne UserInstance permet d’identifier de manière unique la combinaison utilisateur/périphérique.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
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
<td><p>nvarchar(256)</p></td>
<td><p>Rôle de l’utilisateur dans la conférence, tel que présentateur ou participant.</p></td>
</tr>
</tbody>
</table>

