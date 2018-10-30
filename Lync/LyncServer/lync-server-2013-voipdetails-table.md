---
title: 'Lync Server 2013 : Table VoipDetails'
TOCTitle: Table VoipDetails
ms:assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398566(v=OCS.15)
ms:contentKeyID: 49297745
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table VoipDetails dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente un appel entre deux interlocuteurs, où l’un des interlocuteurs est un utilisateur VoIP.


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
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Heure de la demande de session. Utilisée de concert avec <strong>SessionIdSeq</strong> pour identifier de manière unique une session. reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a> pour plus d’informations.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Numéro d’ID identifiant la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier de manière unique une session. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-dialogs-table.md">Table Dialogs dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p><strong>PhoneId</strong> de l’appelant. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-phones-table.md">Table !Phones dans Lync Server 2013</a>. Si non NULL et que <strong>FromGatewayId</strong> est non NULL, l’appelant était un utilisateur RTC.</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectedNumberId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p><strong>PhoneId</strong> du destinataire de l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">Table !Phones dans Lync Server 2013</a>. Si non NULL et que <strong>ToGatewayId</strong> est non NULL, le destinataire de l’appel était un utilisateur RTC.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur de médiation duquel provient l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">Table MediationServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToMediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Serveur de médiation de destination de l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-mediationservers-table.md">Table MediationServers dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Passerelle de laquelle provient l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-gateways-table.md">Table Gateways dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>ToGatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Passerelle de destination de l’appel. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-gateways-table.md">Table Gateways dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisconnectedbyURIId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de l’utilisateur ayant déconnecté l’appel, si l’utilisateur était une URI. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-users-table.md">Table Users dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DisconnectedbyPhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>ID du téléphone ayant déconnecté l’appel, si celui-ci a été déconnecté depuis un téléphone. Pour plus d’informations, reportez-vous à la <a href="lync-server-2013-phones-table.md">Table !Phones dans Lync Server 2013</a>.</p></td>
</tr>
</tbody>
</table>

