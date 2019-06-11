---
title: 'Lync Server 2013: routage par emplacement et transferts d’appel consultatifs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7c7b73efb670c5569b8c4600c1759e981cda211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Routage par emplacement et transferts d’appels de consultation dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-31_

En plus d’appliquer le routage par emplacement aux réunions Lync, l’application de conférence de routage basée sur l’emplacement applique les restrictions de routage basées sur les emplacements aux points de terminaison RTC. Un transfert d’appel consultatif est un appel établi entre deux parties dans lequel une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Lync). Un utilisateur A détermine que l’utilisateur RTC doit être renvoyé à l’utilisateur B (utilisateur Lync). L’utilisateur A passe l’appel avec l’utilisateur PSTN en attente, et appelle l’utilisateur B. L’utilisateur B accepte de parler à l’utilisateur PSTN. L’utilisateur A transfère l’appel en attente à l’utilisateur B.

**Flux des transferts d’appel consultatifs**

![Routage basé sur l’emplacement pour le diagramme de conférence] (images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Routage basé sur l’emplacement pour le diagramme de conférence")

Lorsqu’un utilisateur a activé le routage de géolocalisation, le transfert d’appel d’un point de terminaison PSTN (tel qu’indiqué dans la figure ci-dessus) entraîne la création de deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur de Lync et l’utilisateur Lync B. le comportement suivant est appliqué par l’application de conférence de routage basée sur l’emplacement:

  - Si le routage SIP Trunk est autorisé à rediriger l’appel RTC vers le site du réseau sur lequel l’utilisateur de Lync B (c.-à-d. destination du transfert) se trouve, le transfert d’appel sera autorisé. dans le cas contraire, le transfert d’appel consultatif sera bloqué. Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée sur le même site réseau que le Trunk SIP qui achemine l’appel actif vers le point de terminaison RTC.

  - Si le routage SIP à l’origine de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site du réseau sur lequel la partie transférée (utilisateur Lync B) est située ou si la partie transférée est située sur un site réseau inconnu, le transfert d’appel vers le RTC le point de terminaison (par exemple, cible de transfert d’appel) sera bloqué.

Le tableau suivant décrit la façon dont les restrictions de routage basées sur les emplacements sont appliquées par l’application de conférence de routage basée sur l’emplacement pour les transferts d’appel. Si les points de terminaison PBX ne sont pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Site réseau de la partie dont l’appel est transféré</p></td>
<td><p>Site réseau de la cible de transfert d’appel</p></td>
<td><p>Comportement</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync sur le même site réseau (par exemple, site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans différents sites réseau (par exemple, site 2)</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans un site réseau inconnu</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur fédéré de Lync</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Point de terminaison PBX dans le même site (site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Point de terminaison PBX dans un autre site (site 2)</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans le même site (site 1)</p></td>
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un autre site (site 2)</p></td>
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert consultatif n’est pas autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync sur le même site réseau (par exemple, site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync dans différents sites réseau (par exemple, site 2)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur Lync dans un site réseau inconnu</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un site quelconque</p></td>
<td><p>Utilisateur fédéré de Lync</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

