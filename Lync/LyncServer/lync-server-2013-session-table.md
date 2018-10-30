---
title: 'Lync Server 2013 : Table Session'
TOCTitle: Table Session
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398635(v=OCS.15)
ms:contentKeyID: 49297876
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Table Session dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Chaque enregistrement représente une session qui implique l’audio ou l’audio et la vidéo. Il contient des informations générales sur la session. Une session est définie comme un dialogue SIP (Session Initiation Protocol) audio ou vidéo entre deux points de terminaison.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Colonne</strong></th>
<th><strong>Type de données</strong></th>
<th><strong>Clé/Index</strong></th>
<th><strong>Détails</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-dialog-table.md">Table Dialog dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Principal</p></td>
<td><p>Référencée depuis la <a href="lync-server-2013-dialog-table.md">Table Dialog dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Clé de conférence. Référencée depuis la <a href="lync-server-2013-conference-table.md">Table Conference dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Clé de corrélation. Référencée depuis la <a href="lync-server-2013-sessioncorrelation-table.md">Table SessionCorrelation dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogCategory</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>Catégorie de dialogue ; 0 correspond à Lync Server vers la partie Serveur de médiation ; 1 correspond à Serveur de médiation vers la partie passerelle RTC.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediationServerBypassFlag</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Indicateur signalant si l’appel a été contourné ou non.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaBypassWarningFlag</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>Ce champ, s’il est présent, indique pourquoi un appel n’a pas été contourné même si les ID de contournement correspondaient. Pour Lync Server, une seule valeur est définie.</p>
<p>0x0001 – ID de contournement inconnu pour la carte réseau par défaut.</p></td>
</tr>
<tr class="even">
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Heure de début de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>EndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>Heure de fin de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPool</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Pool de l’appelant. Référencé depuis la <a href="lync-server-2013-pool-table.md">Table Pool dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePool</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Pool du récepteur de l’appel. Référencé depuis la <a href="lync-server-2013-pool-table.md">Table Pool dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleePAI</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI SIP dans l’identité PAI (p-asserted identity) SIP du point de terminaison récepteur. Référencée depuis la <a href="lync-server-2013-user-table.md">Table User dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerURI</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI de l’appelant. Référencée depuis la <a href="lync-server-2013-user-table.md">Table User dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Point de terminaison de l’appelant. Référencé depuis la <a href="lync-server-2013-endpoint-table.md">Table Endpoint dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerUserAgent</strong></p></td>
<td><p>bit</p></td>
<td><p>Étrangère</p></td>
<td><p>Agent utilisateur de l’appelant. Référencé depuis la <a href="lync-server-2013-useragent-table.md">Table UserAgent dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallPriority</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>Priorité de cet appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>Cette colonne est déconseillée et n’est pas utilisée dans Microsoft Lync Server 2013. À la place, ces informations sont indiquées en fonction d’une ligne de média. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-medialine-table.md">Table MediaLine dans Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPAI</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>PAI (P-Asserted-Identity) de l’utilisateur qui a passé l’appel. La PAI sert à transmettre la vraie identité de l’utilisateur qui a passé l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeEndpoint</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Point de terminaison qui a reçu l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeUserAgent</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>Agent utilisateur utilisé par l’utilisateur qui a reçu l’appel. Les agents utilisateurs représentent l’appareil de point de terminaison client.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeUri</strong></p></td>
<td><p>int</p></td>
<td><p>Étrangère</p></td>
<td><p>URI SIP de l’utilisateur qui a reçu l’appel.</p></td>
</tr>
</tbody>
</table>

