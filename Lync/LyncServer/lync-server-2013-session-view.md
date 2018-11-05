---
title: Vue Session
TOCTitle: Vue Session
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49891338
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue Session

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’affichage Session stocke des informations sur les sessions pour lesquelles il existe des enregistrements dans la base de données. Cette vue est une nouveauté de Microsoft Lync Server 2013.


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
<td><p>ConferenceDateTime</p></td>
<td><p>datetime</p></td>
<td><p>Référencé depuis la table MediaLine.</p></td>
</tr>
<tr class="even">
<td><p>ConferenceURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de conférence s’il s’agit d’une conférence, ou DialogID s’il s’agit d’une session d’égal à égal.</p></td>
</tr>
<tr class="odd">
<td><p>Correlation</p></td>
<td><p>varchar(max)</p></td>
<td><p>ID de corrélation de la session.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>Catégorie de dialogue ; 0 correspond à Lync Server vers Serveur de médiation ; 1 correspond à Serveur de médiation vers branche de passerelle PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>Indique si l’appel a été contourné ou non.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Pour Lync Server, une seule valeur est définie :</p>
<p>0x0001 – ID de contournement inconnu pour la carte réseau par défaut</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Heure de début de l’appel.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Heure de fin de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du pool des appelants.</p></td>
</tr>
<tr class="even">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom de domaine complet du pool des appelés.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI P-Asserted-Identity (PAI) de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleePAI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI P-Asserted-Identity (PAI) de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Nom du point de terminaison de l’appelant.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Type de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">Table UserAgent dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelant. Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table-qoe.md">Table UserAgentDef (QoE) dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Chaîne de l’agent utilisateur de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Type de l’agent utilisateur de l’appelé. Pour plus d’informations, voir la <a href="lync-server-2013-useragent-table.md">Table UserAgent dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie de l’agent utilisateur de l’appelé. Pour plus d’informations, voir la <a href="lync-server-2013-useragentdef-table-qoe.md">Table UserAgentDef (QoE) dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>CallerURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p>CalleeURI</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>URI de l’appelé.</p></td>
</tr>
<tr class="odd">
<td><p>CallPrioirty</p></td>
<td><p>int</p></td>
<td><p>Priorité de l’appel.</p></td>
</tr>
</tbody>
</table>

