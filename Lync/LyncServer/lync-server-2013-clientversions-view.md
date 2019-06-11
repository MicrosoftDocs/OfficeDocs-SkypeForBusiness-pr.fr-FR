---
title: 'Affichage Lync Server 2013: ClientVersions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d219b8666afc0684b0d61f02f06618ea6ef60f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a>Affichage ClientVersions dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-01_

Le mode ClientVersions stocke les informations sur les différents types de clients et différentes versions ayant participé à des sessions enregistrées dans la base de données. Chaque enregistrement dans la vue représente une version du client. Cet affichage a été présenté dans Microsoft Lync Server 2013.

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
<td><p>Numéro unique identifiant ce type et version de client.</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Représente l’agent utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TypeClient</strong></p></td>
<td><p>int</p></td>
<td><p>Type de client.</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Catégorie à laquelle le client appartient. Par exemple, le client Conferencing_Attendant_ 1.0 appartient au CAA ClientCategory.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

