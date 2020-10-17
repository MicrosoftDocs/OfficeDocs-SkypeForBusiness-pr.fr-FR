---
title: 'Lync Server 2013 : tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84608b7cb701fe4c394ed413539759d9469a5a4e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509411"
---
# <a name="tblcompliancestate-in-lync-server-2013"></a>tblComplianceState dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-06-28_

tblComplianceState contient des informations d’état de conformité à l’échelle du pool.

### <a name="columns"></a>Colonnes

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonne</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>lastProcessedEntryID</p></td>
<td><p>bigint, non null</p></td>
<td><p>ID du dernier événement de conformité traité.</p></td>
</tr>
<tr class="even">
<td><p>activeServerID</p></td>
<td><p>int, non null</p></td>
<td><p>ID du serveur de conformité contenant le verrou exclusif sur la base de données, ou-1 si aucun.</p></td>
</tr>
<tr class="odd">
<td><p>lockExpirationTime</p></td>
<td><p>datetime2, non null</p></td>
<td><p>Délai d’expiration du verrouillage (si activeServerID n’est pas-1).</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

