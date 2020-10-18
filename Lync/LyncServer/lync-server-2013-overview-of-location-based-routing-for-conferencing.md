---
title: 'Lync Server 2013 : vue d’ensemble du routage des Location-Based pour les conférences'
description: 'Lync Server 2013 : vue d’ensemble du routage des Location-Based pour les conférences.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Location-Based Routing for conferencing
ms:assetid: 8b86740e-db95-4304-bb83-64d0cbb91d47
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362815(v=OCS.15)
ms:contentKeyID: 56335084
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a8fe9cdf4a797243c3ec04b3466011f374fb0d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577370"
---
# <a name="overview-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Vue d’ensemble du routage des Location-Based pour les conférences dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-19_

L’application de conférence de routage de Location-Based fournit aux conférences Lync un mécanisme de prévention des appels téléphoniques PSTN. L’application surveille les conférences actives et applique les restrictions de routage Location-Based en fonction de l’emplacement des utilisateurs de Lync qui participent.

L’application de conférence de routage de Location-Based détermine si le routage de Location-Based doit être appliqué à une réunion Lync si les critères suivants sont satisfaits :

  - L’organisateur de la réunion est activé pour le routage des Location-Based. Location-Based les restrictions de routage ne seront appliquées qu’aux conférences organisées par des utilisateurs qui sont activés pour le routage de Location-Based.

  - Au moins un participant à la réunion est un point de terminaison PSTN. Les restrictions de routage des Location-Based ne s’appliquent qu’aux conférences qui incluent des points de terminaison PSTN.

  - Le site réseau où se trouve la passerelle PSTN servant à relier la Conférence au RTC est disponible, ainsi que les sites réseau à partir desquels les organisateurs et les participants se connectent.

L’application de conférence de routage Location-Based empêche la participation des utilisateurs Lync et des points de terminaison RTC de différents sites réseau à la même conférence. Si l’organisateur d’une réunion est activé pour le routage de Location-Based, l’application de conférence applique les restrictions suivantes :

  - Les points de terminaison pouvant rejoindre une réunion Lync dépendent des points de terminaison qui ont déjà rejoint la Conférence, et cette restriction s’ajuste en tant que points de terminaison joints et de nouveaux points de terminaison joignent la Conférence. Si les organisateurs et les participants rejoignent une réunion Lync à partir du même site réseau, un point de terminaison PSTN, un autre participant du même site réseau, un autre participant d’un site réseau différent ou un participant d’un site réseau inconnu sont autorisés à rejoindre.

  - Si les organisateurs et les participants rejoignent la réunion à partir de sites réseau différents ou inconnus, un point de terminaison PSTN n’est pas autorisé à rejoindre la réunion si l’appel RTC pénètre dans une jonction SIP activée pour le routage de Location-Based.

  - Si les organisateurs et les participants rejoignent la réunion à partir du même site réseau et que des participants rejoignent la même réunion à partir du RTC, un point de terminaison Lync provenant d’un site réseau différent n’est pas autorisé à rejoindre la réunion.

Ces restrictions de routage des Location-Based de conférence sont résumées dans le tableau suivant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Utilisateur (s) dans une conférence à tout moment</p></td>
<td><p>Utilisateur (s) autorisé à rejoindre la Conférence</p></td>
<td><p>Utilisateur (s) non autorisé à rejoindre la Conférence</p></td>
</tr>
<tr class="even">
<td><p>Utilisateur (s) de client VoIP Lync à partir d’un site réseau unique</p></td>
<td><p>Utilisateur de client VoIP Lync à partir du même site réseau</p>
<p>Utilisateur de client VoIP Lync à partir d’un autre site réseau</p>
<p>Utilisateur de client VoIP Lync à partir d’un site réseau inconnu</p>
<p>Utilisateur client VoIP fédéré de Lync</p>
<p>Appartenance d’un utilisateur à partir d’un point de terminaison PSTN</p></td>
<td><p>Aucune</p></td>
</tr>
<tr class="odd">
<td><p>Utilisateur (s) de client VoIP Lync à partir d’un site réseau inconnu</p></td>
<td><p>Utilisateur de client VoIP Lync à partir de n’importe quel site</p>
<p>Utilisateur de client VoIP Lync à partir d’un site inconnu</p>
<p>Utilisateur client VoIP fédéré de Lync</p></td>
<td><p>Appartenance d’un utilisateur via un point de terminaison PSTN</p></td>
</tr>
<tr class="even">
<td><p>Utilisateurs de clients VoIP Lync provenant de sites réseau différents</p></td>
<td><p>Utilisateur de client VoIP Lync à partir de n’importe quel site réseau</p>
<p>Utilisateur de client VoIP Lync à partir d’un site réseau inconnu</p>
<p>Utilisateur client VoIP fédéré de Lync</p></td>
<td><p>Appartenance d’un utilisateur via un point de terminaison PSTN</p></td>
</tr>
<tr class="odd">
<td><p>Utilisateurs de clients VoIP Lync à partir d’un site réseau unique et utilisateurs qui rejoignent un point de terminaison PSTN</p></td>
<td><p>Utilisateur de client VoIP Lync à partir du même site réseau</p></td>
<td><p>Utilisateur de client VoIP Lync à partir d’un autre site réseau</p>
<p>Utilisateur de client VoIP Lync à partir d’un site réseau inconnu</p>
<p>Utilisateur client VoIP fédéré de Lync</p></td>
</tr>
</tbody>
</table>


Les caractéristiques supplémentaires de l’application de conférence de routage de Location-Based sont les suivantes :

  - Lorsqu’un utilisateur n’est pas autorisé à participer à une conférence donnée Location-Based les restrictions de routage, les utilisateurs qui appellent la Conférence sont rejetés et son client Lync signale que l’appel n’a pas abouti ou s’est terminé.

  - Un point de terminaison PSTN joignant une conférence avec Location-Based l’application de routage n’est pas limité à la participation à la Conférence, quel que soit son état si le point de terminaison se joint via une jonction qui n’est pas activée pour le routage de Location-Based.

  - Un système PBX connecté à un serveur de médiation par le biais d’une jonction SIP qui ne sort pas les appels vers le RTC aura les mêmes mises en œuvre que les utilisateurs Lync situés dans le même site réseau où la jonction SIP est définie. Par exemple, un point de terminaison PSTN pourra rejoindre une conférence avec un utilisateur PBX et un utilisateur Lync s’il se trouve dans le même site réseau ; dans le cas contraire, le point de terminaison PSTN ne sera pas autorisé à rejoindre la Conférence si l’utilisateur PBX se trouve dans un autre site réseau que l’utilisateur Lync.

</div>

<span> </span>

</div>

</div>

</div>

