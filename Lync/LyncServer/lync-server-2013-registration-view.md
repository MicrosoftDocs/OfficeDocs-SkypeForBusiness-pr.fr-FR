---
title: Vue Registration
TOCTitle: Vue Registration
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49891432
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue Registration

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’affichage Inscription stocke les informations relatives à l’inscription de l’utilisateur. Cette vue est une nouveauté de Lync Server 2013.


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
<td><p>Date/heure</p></td>
<td><p>Heure de la demande de session. Utilisée avec SessionIdSeq pour identifier de manière unique une session. Pour plus d’informations, voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro d’identification de la session. Utilisé avec SessionIdTime pour identifier de manière unique une session. Pour plus d’informations, voir la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>RegisterTime</strong></p></td>
<td><p>Date/heure</p></td>
<td><p>Heure de l’enregistrement.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’utilisateur inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Type d’URI de l’utilisateur inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-uritypes-table.md">Table UriTypes dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Locataire de l’utilisateur inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-tenants-table.md">Table Tenants dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique du point de terminaison auprès duquel l’utilisateur est inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>EndpointEra</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Identificateur unique utilisé pour différencier les inscriptions du même utilisateur auprès du même point de terminaison.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeRegisterType</strong></p></td>
<td><p>Date/heure</p></td>
<td><p>Heure à laquelle la désinscription a eu lieu.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeRegisterReason</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Raison de la désinscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version du client utilisé par l’utilisateur inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Client utilisé par l’utilisateur inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table.md">Table UserAgentDef dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>Catégorie du client utilisée par l’utilisateur inscrit.</p></td>
</tr>
<tr class="even">
<td><p><strong>IpAddress</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Adresse IP avec laquelle l’utilisateur s’est inscrit. Il peut s’agit d’une adresse IPv4 ou IPv6.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>ID de dialogue SIP. Le format est :</p>
<p>dialogue;de-balise;à-balise</p></td>
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
<td><p><strong>Registrar</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du serveur d’inscriptions.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet (FQDN) du pool qui a capturé les données de la session.</p></td>
</tr>
<tr class="even">
<td><p><strong>EdgeServer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du serveur Edge utilisé par l’utilisateur inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’utilisateur s’est connecté à partir du réseau interne ou non.</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserServiceAvailable</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si UserService était disponible au moment de l’inscription.</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsPrimaryRegistrar</strong></p></td>
<td><p>bit</p></td>
<td><p>Indique si l’inscription a eu lieu auprès du serveur d’inscriptions principal.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceMacAddress</strong></p></td>
<td><p>bigint</p></td>
<td><p>Adresse MAC de l’appareil inscrit.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DeviceManufacturer</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Fabricant de l’appareil inscrit. Pour plus d’informations, voir la <a href="lync-server-2013-manufacturers-table.md">Table Manufacturers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceHardwareVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Version matérielle de l’appareil inscrit. Pour plus d’informations, voir <a href="lync-server-2013-hardwareversions-table.md">Table HardwareVersions dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

