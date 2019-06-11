---
title: 'Lync Server 2013: modifications apportées par la préparation du domaine'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a>Modifications apportées par la préparation du domaine dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2010-10-18_

Le tableau suivant répertorie les entrées de contrôle d’accès (ACE) créées par la préparation du domaine à la racine du domaine. Toutes les entrées ACE sont héritées sauf mention contraire.

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a>ACE ajoutés à la racine du domaine

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
<th>MAILLOTS</th>
<th>RTCUniversal-UserReadOnly-groupe</th>
<th>RTCUniversal-ServerReadOnly-groupe</th>
<th>RTCUniversal-UserAdmins</th>
<th>RTCHSUniversal-services</th>
<th>Utilisateurs authentifiés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lire le conteneur (non hérité)</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Lire User PropertySet-compte-restrictions</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lire Personal User PropertySet-informations</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Lecture générale de User PropertySet-informations</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lire le public user PropertySet public-information</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Lecture utilisateur PropertySet RTCUserSearchProperty-Set</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Oui</strong></p></td>
</tr>
<tr class="odd">
<td><p>Lire User PropertySet RTCPropertySet</p></td>
<td><p><strong>Oui</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Écrire les adresses proxy de propriété utilisateur</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Positive</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Write User PropertySet RTCUserSearchProperty-Set</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Positive</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Écrire RTCPropertySet utilisateur</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Positive</strong></p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lecture de PropertySet DS-réplication-obtention-modification de tous les objets Active Directory</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
<td><p><strong>Positive</strong></p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


Le tableau suivant répertorie les entrées de contrôle d’accès qu’il est créé dans les trois conteneurs intégrés: utilisateurs, ordinateurs et contrôleurs de domaine. Toutes les entrées ACE sont héritées sauf mention contraire.

### <a name="aces-added-to-built-in-containers"></a>ACE ajoutés aux conteneurs intégrés

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>MAILLOTS</th>
<th>RTCUniversal-UserReadOnly-groupe</th>
<th>RTCUniversal-ServerReadOnly-groupe</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lire le conteneur (non hérité)</p></td>
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

