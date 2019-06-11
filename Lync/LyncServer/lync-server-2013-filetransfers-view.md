---
title: 'Affichage Lync Server 2013: FileTransfers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4228bbe42f2e7bcf88b26f9147e514f09c106ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Affichage FileTransfers dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Le mode FileTransfer stocke les informations sur les sessions d’égal à égal de transfert de fichiers. Cet affichage a été présenté dans Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Le mode FileTransfers contient toutes les colonnes de la <A href="lync-server-2013-sessiondetails-view.md">vue SessionDetails dans Lync Server 2013</A> , en plus des colonnes répertoriées ci-dessous.



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
<td><p>nvarchar(256)</p></td>
<td><p>Nom du fichier transféré.</p></td>
</tr>
<tr class="even">
<td><p><strong>Sans</strong></p></td>
<td><p>nvarchar(128</p></td>
<td><p>Permet de détecter chaque message de suivi associé à celui-ci.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>identificateur</p></td>
<td><p>Identificateur unique permettant de faire la distinction entre les transferts de fichiers impliquant le même nom de fichier.</p></td>
</tr>
<tr class="even">
<td><p><strong>Valide</strong></p></td>
<td><p>bit</p></td>
<td><p>Peut être vrai ou nul. Si vrai, l’argument refuser et annuler est nul.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Rejeter</strong></p></td>
<td><p>bit</p></td>
<td><p>Peut être vrai ou nul. Si vrai, l’argument accepter et annuler est nul.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annuler</strong></p></td>
<td><p>bit</p></td>
<td><p>Peut être vrai ou nul. Si vrai, l’argument accepter et refuser est nul.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

