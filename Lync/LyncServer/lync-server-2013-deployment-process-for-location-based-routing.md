---
title: 'Lync Server 2013 : processus de déploiement du routage géodépendant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08def9741ad6ba4f91759e88a38fccdea0d44333
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Processus de déploiement pour le routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-09_

Cette rubrique fournit une vue d’ensemble du processus de configuration du routage géodépendant. Vous devez déployer Lync Server Enterprise Edition ou Standard Edition avec voix entreprise avant de configurer le routage géodépendant. Les composants requis par le routage géodépendant sont déjà installés et activés lorsque vous déployez voix entreprise.

### <a name="location-based-routing-deployment-process"></a>Processus de déploiement de routage géodépendant

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Groupes et rôles requis</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Déployer voix entreprise</p></td>
<td><ul>
<li><p>Configuration des jonctions</p></li>
<li><p>Créer des stratégies de voix</p></li>
<li><p>Définir les itinéraires des communications vocales</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Déploiement de Voix Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Vérifier le déploiement de voix entreprise</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurer des régions réseau, des sites et des sous-réseaux</p></td>
<td><ul>
<li><p>Créer des régions réseau</p></li>
<li><p>Créer des sites réseau</p></li>
<li><p>Associe des sous-réseaux à des sites réseau</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>À propos des régions réseau, sites et sous-réseaux<br />
Créer ou modifier une région réseau<br />
Créer ou modifier un site réseau<br />
Associer un sous-réseau à un site réseau</p></td>
</tr>
<tr class="even">
<td><p>Configurer le routage géodépendant</p></td>
<td><ul>
<li><p>Créer des stratégies de routage des communications vocales</p></li>
<li><p>Définir une configuration de jonction distincte par jonction</p></li>
<li><p>Modifier des stratégies de voix</p></li>
<li><p>Activer la configuration du routage basé sur l’emplacement</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>Exemple de déploiement

Le déploiement suivant est utilisé pour illustrer les mécanismes activés par le routage géodépendant.

![e1bd2230-44DA-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44DA-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Appels RTC entrants

Un administrateur peut activer la jonction définie pour acheminer les appels vers « site 1 Gateway » pour le routage géodépendant et associer la passerelle « site 1 » au site 1. Une fois activés, les appels routés via la passerelle « site 1 » seront acheminés uniquement vers les utilisateurs situés dans le site 1. Tous les appels acheminés via la jonction « passerelle de site 1 » destiné aux utilisateurs dans un autre site, tel que le site 2, sont bloqués pour empêcher le contournement de numéro de téléphone PSTN.

Tous les appels PSTN entrants via la passerelle « site 1 » seront uniquement autorisés à acheminer vers les points de terminaison situés dans le site 1. Par exemple, lorsque « Lync User 1 » se déplace vers le site 2, tous les appels RTC entrants via « passerelle de site 1 » ne sont pas routés vers les points de terminaison « Lync User 1 » situés dans le site 2. La règle de routage s’applique si « Lync User 1 » se déplace vers un site réseau inconnu où l’emplacement de l’utilisateur ne peut pas être déterminé.

Le tableau suivant décrit l’expérience utilisateur de « Lync User 1 » dans ce contexte.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Points de terminaison de Lync User 1 situés dans le site réseau 1</th>
<th>Points de terminaison de Lync User 1 situés dans le site réseau 2</th>
<th>Points de terminaison de Lync User 1 situés dans un site réseau inconnu</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels RTC entrants vers Lync User 1</p></td>
<td><p>Les appels sont routés vers les points de terminaison à cet emplacement</p></td>
<td><p>Les appels ne sont pas routés vers les points de terminaison à cet emplacement</p></td>
<td><p>Les appels ne sont pas routés vers les points de terminaison à cet emplacement</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Appels RTC sortants

Les itinéraires des communications vocales sont référencés dans les stratégies vocales attribuées directement aux utilisateurs, et les stratégies de routage des communications vocales affectées aux sites réseau. Les deux stratégies contiennent des références à des itinéraires, qui peuvent être utilisées pour acheminer un appel différemment. Par exemple, un administrateur peut définir une stratégie de routage des communications vocales pour tous les utilisateurs se trouvant dans le site réseau 1 pour acheminer tous les appels sortants via la passerelle « site 1 » tandis que la stratégie de voix de certains utilisateurs définit un itinéraire pour tous les appels sortants via la passerelle « site 2 ». Bien que ces utilisateurs se trouvent dans le site réseau 1, leurs appels sortants sont acheminés via la passerelle « site 1 ».

Lorsqu’un utilisateur se trouve dans un site réseau configuré pour le routage géodépendant, l’itinéraire des stratégies de routage des communications vocales du site réseau remplace le chemin de la stratégie de voix de l’utilisateur. Cette règle est particulièrement utile pour les utilisateurs qui se déplacent temporairement sur un autre site. Dans ce cas particulier, un utilisateur utilisera toujours une passerelle locale pour son emplacement ; Si « Lync User 3 » se trouve sur « site 2 », tous ses appels sortants sont acheminés via « site 2 Gateway », mais s’il transite sur le site 1, tous les appels sortants passés alors qu’il se trouve sur le site 1 sont acheminés via « passerelle de site 1 ».

Le tableau suivant illustre l’expérience utilisateur de Lync User 1 à effectuer un appel sortant à partir des sites réseau suivants.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site réseau 1</th>
<th>Site réseau 2</th>
<th>Site réseau inconnu ou non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisation des appels sortants</p></td>
<td><p>Stratégie de voix de Lync User 1</p></td>
<td><p>Stratégie de voix de Lync User 1</p></td>
<td><p>Stratégie de voix de Lync User 1</p></td>
</tr>
<tr class="even">
<td><p>Routage des appels sortants</p></td>
<td><p>Stratégie de routage des communications vocales du site 1</p></td>
<td><p>Stratégie de routage des communications vocales du site 2</p></td>
<td><p>Stratégie de voix de l’utilisateur et uniquement aux systèmes non activés pour le routage géodépendant</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Transferts et transferts d’appels

Lorsque les appels sont transférés ou transférés, le routage des appels est affecté par le routage géodépendant.

Le tableau suivant représente l’utilisateur Lync 1 qui transfère ou transfère un appel RTC à un autre utilisateur Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Envoi ou transfert d’appel par un utilisateur</th>
<th>Lync utilisateur 2</th>
<th>Lync User 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync utilisateur 1</p></td>
<td><p>Le transfert d’appel ou le transfert est autorisé</p></td>
<td><p>Le transfert d’appel ou le transfert n’est pas autorisé</p></td>
<td><p>Le transfert d’appel ou le transfert n’est pas autorisé</p></td>
</tr>
</tbody>
</table>

  
Le tableau suivant illustre l’impact du routage géodépendant sur la façon dont l’appel est acheminé en fonction de l’emplacement de transfert de l’utilisateur Lync (Lync user 2, Lync User 4, etc.) vers un point de terminaison PSTN.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Point de terminaison où l’appel est transféré ou transféré vers</th>
<th>Lync utilisateur 2</th>
<th>Lync User 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert d’appel ou le transfert est acheminé via le site 1 stratégie de routage des communications vocales et sortie via la passerelle site 1</p></td>
<td><p>Le transfert d’appel ou le transfert est acheminé via le site 2 stratégie de routage des communications vocales et sortie via la passerelle site 2</p></td>
<td><p>Le transfert d’appel ou le transfert est acheminé via la stratégie de voix de l’utilisateur Lync et la sortie via une passerelle non activée pour le routage géodépendant (le cas échéant).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Sonnerie simultanée

Une fois le routage géodépendant configuré dans l’exemple de topologie, les interactions suivantes sont appliquées.

Le tableau suivant indique si le routage géodépendant autorise la sonnerie simultanée pour différents utilisateurs Lync (par exemple, Lync user 2, Lync User 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible d’appel RTC entrant</th>
<th>Lync utilisateur 2</th>
<th>Lync User 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync utilisateur 1</p></td>
<td><p>Sonnerie simultanée autorisée</p></td>
<td><p>Sonnerie simultanée non autorisée</p></td>
<td><p>Sonnerie simultanée non autorisée</p></td>
</tr>
</tbody>
</table>

  
Le tableau suivant indique si le routage géodépendant autorise la sonnerie simultanée à un point de terminaison PSTN à partir de différents utilisateurs Lync (par exemple, Lync user 2, Lync User 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible annulaire simultanée</th>
<th>Lync utilisateur 2</th>
<th>Lync User 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage géodépendant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Téléphone mobile Lync User 1 (point de terminaison PSTN)</p></td>
<td><p>Appel acheminé via la stratégie de routage des communications vocales du site réseau 1 et sortie via la passerelle site 1</p></td>
<td><p>Appel acheminé via la stratégie de routage des communications vocales du site Network 2 et sortie via la passerelle site 2</p></td>
<td><p>Appel acheminé via la stratégie de voix de l’appelant et sortie via une passerelle PSTN non activée pour le routage géodépendant</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

