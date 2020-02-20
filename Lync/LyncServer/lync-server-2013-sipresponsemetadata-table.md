---
title: 'Lync Server 2013 : table SIPResponseMetaData'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bbfec0e3d1dae6d4799fbb109e081a8f7a1a299
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142790"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a>Table SIPResponseMetaData dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-28_

La table SIPResponseMetaDataTable contient la liste des codes de réponse SIP et les classification et définition de chacun de ces codes. Ceux-ci sont générés en réponse aux événements affectant les périphériques SIP et les sessions de communication SIP. Par exemple, le code de réponse 403 est généré quand un périphérique SIP effectue une requête, mais que le serveur refuse d’honorer cette requête.

Cette table a été introduite dans Microsoft Lync Server 2013.


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
<th>Clé/index</th>
<th>Détails</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>Primaire</p></td>
<td><p>Valeur numérique qui représente le code de réponse SIP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Classe</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>Classification générale pour le code de réponse. Les classifications comprennent :</p>
<ul>
<li><p>1 – Réponses informatives</p></li>
<li><p>2 – Réponses réussies</p></li>
<li><p>3 – Réponses de redirection</p></li>
<li><p>4 – Réponses d’échec de client</p></li>
<li><p>5--réponses d’échec de serveur</p></li>
<li><p>6 – Réponse d’échec global</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td></td>
<td><p>Description du code de réponse SIP. Par exemple, le code de réponse 181 a la description suivante :</p>
<p>L’appel est en cours de transfert</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

