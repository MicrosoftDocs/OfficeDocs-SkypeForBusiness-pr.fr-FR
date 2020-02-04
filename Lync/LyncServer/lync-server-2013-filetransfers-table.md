---
title: 'Lync Server 2013 : Table FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743360"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>Table FileTransfers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

Chaque enregistrement représente une session de transfert de fichiers.


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
<td><p>Etranger principal</p></td>
<td><p>Durée de la demande de session. Utilisé conjointement avec <strong>SessionIdSeq</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Etranger principal</p></td>
<td><p>IDENTIFIant de la session. Utilisé conjointement avec <strong>SessionIdTime</strong> pour identifier une session de manière unique. Pour plus d’informations, voir le <a href="lync-server-2013-dialogs-table.md">tableau des boîtes de dialogue dans Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Nom de fichier</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Nom du fichier.</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>identificateur</p></td>
<td></td>
<td><p>Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Sans</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Principal</p></td>
<td><p>Permet de détecter chaque message de suivi associé à celui-ci.</p></td>
</tr>
<tr class="even">
<td><p><strong>Valide</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Peut être vrai ou nul. Si vrai, l’argument refuser et annuler est nul.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rejeter</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Peut être vrai ou nul. Si vrai, l’argument accepter et annuler est nul.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annuler</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Peut être vrai ou nul. Si vrai, l’argument accepter et refuser est nul.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

