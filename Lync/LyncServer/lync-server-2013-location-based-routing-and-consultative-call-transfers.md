---
title: 'Lync Server 2013 : routage géodépendant et transfert d’appel consultatif'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bf1f9ca57366a3fc5b2ac1d13bd44336f3e2aeb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Routage basé sur l’emplacement et transferts d’appels consultatifs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-31_

En plus de mettre en place le routage géodépendant vers des réunions Lync, l’application de conférence de routage basée sur l’emplacement applique les restrictions de routage basées sur l’emplacement sur les transferts d’appel consultatifs qui sont sortants vers des points de terminaison PSTN. Un transfert d’appel consultatif est un appel établi entre deux parties où une des parties transfère l’appel vers un nouvel utilisateur. Par exemple, un point de terminaison PSTN appelle l’utilisateur A (appelé Lync). L’utilisateur A détermine que l’utilisateur RTC doit être transféré à l’utilisateur B (utilisateur Lync). L’utilisateur A passe l’appel avec l’utilisateur RTC en conservation et appelle l’utilisateur B. l’utilisateur B accepte de communiquer avec l’utilisateur RTC. L’utilisateur A transfère l’appel en attente à l’utilisateur B.

**Flux d’appels consultatifs de transfert d’appel**

![Routage géodépendant pour le diagramme de conférence](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Routage géodépendant pour le diagramme de conférence")

Lorsqu’un utilisateur activé pour le routage géodépendant lance un transfert d’appel consultatif d’un point de terminaison PSTN (comme illustré dans la figure précédente), cela crée deux appels actifs, un appel entre l’utilisateur RTC et l’utilisateur Lync A, et l’autre entre Lync User A et Lync User B. le comportement suivant est appliqué par l’application de conférence de routage basée sur l’emplacement :

  - Si le routage des jonctions SIP est autorisé à réacheminer l’appel RTC vers le site réseau où se trouve l’utilisateur Lync B (c.-à-d. cible de transfert), le transfert d’appel sera autorisé ; dans le cas contraire, le transfert consultatif est bloqué. Cette autorisation est effectuée en fonction de l’emplacement de la partie transférée dans le même site réseau que la jonction SIP qui achemine l’appel actif vers le point de terminaison PSTN.

  - Si le routage de jonction SIP de l’appel RTC entrant n’est pas autorisé à acheminer les appels vers le site réseau où se trouve la partie transférée (Lync User B) ou la partie transférée dans un site réseau inconnu, le transfert d’appel consultatif vers le RTC le point de terminaison (par exemple, la cible de transfert d’appel) sera bloqué.

Le tableau suivant décrit la façon dont les restrictions de routage basées sur l’emplacement sont appliquées par l’application de conférence de routage basée sur l’emplacement pour les transferts d’appels consultatifs. Bien que les points de terminaison PBX ne soient pas directement associés à un site réseau, la jonction SIP à laquelle le PBX est connecté peut être affectée à un site réseau. Par conséquent, le point de terminaison PBX peut être indirectement associé à un site réseau.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Site réseau de la partie transférée d’appel</p></td>
<td><p>Site réseau de la cible de transfert d’appel</p></td>
<td><p>Comportement</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans le même site réseau (par exemple, site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans différents sites réseau (par exemple, site 2)</p></td>
<td><p>Le transfert consultatif est interdit</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync dans un site réseau inconnu</p></td>
<td><p>Le transfert consultatif est interdit</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Utilisateur Lync fédéré</p></td>
<td><p>Le transfert consultatif est interdit</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Point de terminaison PBX dans le même site (par exemple, site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Point de terminaison PBX dans différents sites (par exemple, site 2)</p></td>
<td><p>Le transfert consultatif est interdit</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans le même site (par exemple, site 1)</p></td>
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans un autre site (par exemple, site 2)</p></td>
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert consultatif est interdit</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans n’importe quel site</p></td>
<td><p>Utilisateur Lync dans le même site réseau (par exemple, site 1)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans n’importe quel site</p></td>
<td><p>Utilisateur Lync dans différents sites réseau (par exemple, site 2)</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="even">
<td><p>Point de terminaison PBX dans n’importe quel site</p></td>
<td><p>Utilisateur Lync dans un site réseau inconnu</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
<tr class="odd">
<td><p>Point de terminaison PBX dans n’importe quel site</p></td>
<td><p>Utilisateur Lync fédéré</p></td>
<td><p>Le transfert consultatif est autorisé</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

