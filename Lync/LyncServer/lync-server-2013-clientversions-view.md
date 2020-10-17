---
title: 'Lync Server 2013 : vue ClientVersions'
description: 'Lync Server 2013 : vue ClientVersions.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42ede7107a59db3162ac7f5344e47e81a80d57df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542800"
---
# <a name="clientversions-view-in-lync-server-2013"></a>Vue ClientVersions dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-01_

L’affichage ClientVersions stocke des informations sur les différents types et versions de clients qui ont participé à des sessions enregistrées dans la base de données. Chaque enregistrement de la vue représente une version du client. Cette vue a été introduite dans Microsoft Lync Server 2013.

<div>


> [!NOTE]  
> Il peut y avoir plusieurs enregistrements pour certaines colonnes.



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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>Numéro unique identifiant le type et la version de ce client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Représente l’agent utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>Type de client.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie à laquelle appartient le client. Par exemple, le client Conferencing_Attendant_1.0 appartient au ClientCategory CAA.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

