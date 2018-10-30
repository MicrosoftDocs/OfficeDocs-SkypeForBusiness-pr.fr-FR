---
title: 'Lync Server 2013 : Table Registration'
TOCTitle: Table Registration
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398114(v=OCS.15)
ms:contentKeyID: 49296134
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Registration dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

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
<th>Clé/Index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. Reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>Int</p></td>
<td><p>Primaire, étrangère</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID de l’utilisateur. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>GUID pour identifier un point de terminaison d’inscription. Généralement, l’événement d’inscription d’un même ordinateur et d’un même utilisateur aura le même ID de point de terminaison. Des ordinateurs différents ont un ID de point de terminaison différent.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>ID utilisé pour différencier des inscriptions qui impliquent le même utilisateur et le même point de terminaison.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Version du client de l’utilisateur actuel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-clientversions-table.md">Table ClientVersions dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegistrarId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du serveur d’inscriptions utilisé pour l’inscription. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-servers-table.md">Table Servers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du pool dans lequel la session a été capturée. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-pools-table.md">Table Pools dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur Edge sur lequel l’inscription a lieu. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-edgeservers-table.md">Table EdgeServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsInternal</strong></p></td>
<td><p>Bit</p></td>
<td><p></p></td>
<td><p>Si l’utilisateur est connecté en interne ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Si UserService est disponible ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Si l’inscription est effectuée sur le serveur d’inscriptions principal ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrarCentral</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indique si l’utilisateur est inscrit ou non avec un Survivable Branch Appliance.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
<tr class="even">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Heure d’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTime</strong></p></td>
<td><p>DateHeure</p></td>
<td><p></p></td>
<td><p>Heure de désinscription.</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>Code de réponse de la demande d’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>Int</p></td>
<td><p></p></td>
<td><p>ID de diagnostic de la demande d’inscription. Indique les informations du type de diagnostic.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceId</strong></p></td>
<td><p>Int</p></td>
<td><p>Étrangère</p></td>
<td><p>L’appareil à partir duquel est émise la demande d’inscription. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-devices-table.md">Table Devices dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Étrangère</p></td>
<td><p>Raison de désinscription, telle que « initiative du client », « expiration de l’inscription », « échec du client », etc. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-deregistertype-table.md">Table DeRegisterType dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p></p></td>
<td><p>Adresse IP du point de terminaison avec laquelle l’utilisateur s’est inscrit. Il peut s’agir d’une adresse IPv4 ou d’une adresse IPv6.</p>
<p>Ce champ a été présenté dans Microsoft Lync Server 2013.</p></td>
</tr>
</tbody>
</table>

