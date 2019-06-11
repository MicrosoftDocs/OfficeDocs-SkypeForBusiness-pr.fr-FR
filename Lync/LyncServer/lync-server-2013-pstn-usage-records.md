---
title: 'Lync Server 2013 : Enregistrements d’utilisation RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN usage records
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412878(v=OCS.15)
ms:contentKeyID: 48185188
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e32000f1664591a3e054d058ced4f996a98f27cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-usage-records-in-lync-server-2013"></a>Enregistrements d’utilisation RTC dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-23_

La planification des enregistrements d’utilisation PSTN consiste principalement à répertorier toutes les autorisations d’appel actuellement en vigueur dans votre organisation, du PDG aux travailleurs temporaires, consultants et subordonnés. Ce processus donne également la possibilité de revérifier les autorisations d’appel existantes et de les modifier. Vous pouvez créer des enregistrements d’utilisation RTC uniquement pour les autorisations d’appel qui s’appliquent aux utilisateurs vocaux de votre entreprise, mais une meilleure solution de grande gamme peut être de créer des enregistrements d’utilisation RTC pour toutes les autorisations d’appel, qu’il soit ou non Appliquez au groupe d’utilisateurs à activer pour voix entreprise. Si les autorisations d’appel changent ou que de nouveaux utilisateurs avec des autorisations d’appel différentes sont ajoutés, vous aurez déjà créé les enregistrements d’utilisation PSTN requis.

Le tableau ci-dessous présente un exemple d’utilisation PSTN standard :

### <a name="pstn-usage-records"></a>Enregistrements d’utilisation PSTN

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut de téléphone</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Appels locaux</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>Appels longue distance</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>Appels internationaux</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Employés à temps plein à Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Employés à temps plein à Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Employés temporaires à Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Employés à temps plein à Zurich</p></td>
</tr>
</tbody>
</table>


Les enregistrements d’utilisation PSTN n’effectuent aucune action par eux-mêmes. Pour qu’ils fonctionnent, vous devez les associer aux éléments suivants :

  - des stratégies de voix, affectées aux utilisateurs ;

  - des itinéraires, affectés aux numéros de téléphone.

Pour plus d’informations sur les stratégies et les itinéraires vocaux, voir [stratégies vocales dans Lync server 2013](lync-server-2013-voice-policies.md) et [itinéraires vocaux dans Lync Server 2013](lync-server-2013-voice-routes.md). Pour plus d’informations sur la création et la configuration de celles-ci, reportez-vous à la rubrique [Configuration des itinéraires vocaux pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

</div>

<span> </span>

</div>

</div>

</div>

