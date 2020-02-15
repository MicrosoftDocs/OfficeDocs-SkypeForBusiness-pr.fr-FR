---
title: 'Lync Server 2013 : vue FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc6790766d68ee478cf1b80326c974f7c15f1f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Vue FileTransfers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

L’affichage FileTransfer stocke des informations sur les sessions de transfert de fichiers P2P. Cette vue a été introduite dans Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> La vue FileTransfers contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes indiquées ci-dessous.



</div>


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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nom du fichier transféré.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Utilisé pour identifier chaque message de suivi comme étant associé à celui-ci.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>unique</p></td>
<td><p>Identificateur unique permettant de différencier les transferts de fichiers concernant le même nom de fichier.</p></td>
</tr>
<tr class="even">
<td><p><strong>Accept</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Reject et Cancel seront NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Reject</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Accept et Cancel seront NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cancel</strong></p></td>
<td><p>légèrement</p></td>
<td><p>Peut-être TRUE ou NULL. Si TRUE, alors Accept et Reject seront NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

