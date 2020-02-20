---
title: 'Lync Server 2013 : modifications apportées par la préparation du domaine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Modifications apportées par la préparation du domaine dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2010-10-18_

Le tableau ci-après répertorie les entrées de contrôle d’accès créées par la préparation de domaine sur la racine de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>Entrées de contrôle d’accès ajoutées à la racine de domaine

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>moteur ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-services</th>
<th>Utilisateurs authentifiés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (non héritée)</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet User-Account-Restrictions</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Personal-Information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet General-Information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet Public-Information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Read User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
</tr>
<tr class="odd">
<td><p>Read User PropertySet RTCPropertySet</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Write User Property Proxy-Addresses</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Write User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Write User PropertySet RTCPropertySet</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Read PropertySet DS-Replication-Get-Changes de tous les objets Active Directory</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


Le tableau suivant répertorie les entrées de contrôle d’accès créées par la préparation de domaine dans les trois conteneurs intégrés : Utilisateurs, Ordinateurs et Contrôleurs de domaine. Toutes les entrées de contrôle d’accès sont héritées, sauf indication contraire.

### <a name="aces-added-to-built-in-containers"></a>Entrées de contrôle d’accès ajoutées aux conteneurs intégrés

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>moteur ACE</th>
<th>RTCUniversal-UserReadOnly-Group</th>
<th>RTCUniversal-ServerReadOnly-Group</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Read Container (non héritée)</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p><strong>Oui</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

