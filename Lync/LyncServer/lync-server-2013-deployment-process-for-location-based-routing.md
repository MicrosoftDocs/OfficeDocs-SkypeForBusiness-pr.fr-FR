---
title: >
  Lync Server 2013 : Processus de déploiement du routage géodépendant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Processus de déploiement du routage géodépendant dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-09_

Cette rubrique fournit une vue d’ensemble du processus de configuration du routage par emplacement. Vous devez déployer Lync Server Enterprise Edition ou Standard Edition avec Enterprise Voice avant de configurer le routage sur site. Les composants requis par le routage de géolocalisation sont déjà installés et activés lors du déploiement d’Enterprise Voice.

### <a name="location-based-routing-deployment-process"></a>Processus de déploiement de routage en fonction de l’emplacement

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
<td><p>Déploiement de Voix Entreprise</p></td>
<td><ul>
<li><p>Configurer des Trunks</p></li>
<li><p>Créer des stratégies vocales</p></li>
<li><p>Définir des itinéraires vocaux</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Déploiement d’Enterprise Voice</p></td>
</tr>
<tr class="even">
<td><p>Vérifier votre déploiement voix entreprise</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurer des zones, des sites et des sous-réseaux réseau</p></td>
<td><ul>
<li><p>Créer des régions réseau</p></li>
<li><p>Créer des sites réseau</p></li>
<li><p>Associe des sous-réseaux aux sites réseau</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>À propos des zones, des sites et des sous-réseaux réseau<br />
Créer ou modifier une région de réseau<br />
Créer ou modifier un site réseau<br />
Associer un sous-réseau à un site réseau</p></td>
</tr>
<tr class="even">
<td><p>Configurer le routage par emplacement</p></td>
<td><ul>
<li><p>Créer des stratégies de routage de la voix</p></li>
<li><p>Définir une configuration de Trunk séparée par Trunk</p></li>
<li><p>Modifier les stratégies vocales</p></li>
<li><p>Activer la configuration de routage basée sur l’emplacement</p></li>
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

Le déploiement suivant est utilisé pour illustrer davantage les mécanismes activés par le routage géolocalisation.

![e1bd2230-44DA-4784-b359-24572b6ce02d] (images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44DA-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Appels RTC entrants

Un administrateur peut activer le Trunk défini pour acheminer les appels vers «passerelle site 1» pour le routage de l’emplacement et associer la «passerelle site 1» au site 1. Lorsque l’option est activée, les appels routés par le biais de la passerelle «site 1» ne seront routés qu’aux utilisateurs situés dans le site 1. Tous les appels routés via le Trunk «site 1 passerelle» destinés aux utilisateurs d’un site différent, comme le site 2, seront bloqués pour empêcher les détournements d’appels RTC.

Tous les appels RTC entrants par le biais de la «passerelle du site 1» ne seront autorisés à effectuer le routage qu’aux points de terminaison situés dans le site 1. Par exemple, lorsque «Lync User 1» voyage sur le site 2, tous les appels RTC entrants par le biais de «passerelle site 1» ne seront pas routés aux points de terminaison «Lync User 1» situés dans le site 2. La même règle de routage s’applique si «Lync User 1» voyage sur un site réseau inconnu où l’emplacement de l’utilisateur ne peut pas être déterminé.

Le tableau suivant décrit l’environnement utilisateur de «Lync User 1» dans ce contexte.


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
<th>Points de terminaison Lync User 1 situés dans le site réseau 1</th>
<th>Points de terminaison Lync User 1 situés dans le site réseau 2</th>
<th>Points de terminaison Lync User 1 situés dans un site réseau inconnu</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels RTC entrants vers l’utilisateur Lync 1</p></td>
<td><p>Les appels sont routés vers les points de terminaison dans cet emplacement</p></td>
<td><p>Les appels ne sont pas routés aux points de terminaison dans cet emplacement</p></td>
<td><p>Les appels ne sont pas routés aux points de terminaison dans cet emplacement</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Appels RTC sortants

Les itinéraires vocaux sont référencés dans les stratégies vocales attribuées directement aux utilisateurs et les stratégies de routage vocal affectées aux sites réseau. Les deux stratégies contiennent des références à des itinéraires qui peuvent être utilisées pour acheminer un appel différemment. Par exemple, un administrateur peut définir une stratégie de routage vocale pour tous les utilisateurs situés dans le site réseau 1 pour acheminer tous les appels sortants par le biais de la «passerelle site 1», tandis que la stratégie vocale de certains utilisateurs définit un itinéraire pour tous les appels sortants par le biais de la «passerelle site 2». Même si ces utilisateurs se trouvent dans le site réseau 1, les appels sortants sont routés par le biais de la «passerelle du site 1».

Lorsqu’un utilisateur se trouve sur un site réseau configuré pour le routage sur la base de l’emplacement, l’itinéraire de la stratégie de routage de la voix du site réseau remplace l’itinéraire de la stratégie vocale de l’utilisateur. Cette règle est particulièrement utile pour les utilisateurs qui se déplacent temporairement sur un autre site. Dans ce cas particulier, un utilisateur utilisera toujours une passerelle locale vers son emplacement. Si "Lync User 3" est situé sur "site 2", tous les appels sortants seront routés par le biais de la «passerelle site 2», mais s’il est acheminé vers le site 1, tous les appels sortants placés alors qu’il se trouve sur le site 1 seront routés par le biais de «passerelle site 1».

Le tableau suivant illustre l’utilisation de l’utilisateur Lync 1 lors du placement d’un appel sortant sur les sites réseau suivants.


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
<th>Site réseau inconnu ou non activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisation des appels sortants</p></td>
<td><p>Politique vocale utilisateur Lync 1</p></td>
<td><p>Politique vocale utilisateur Lync 1</p></td>
<td><p>Politique vocale utilisateur Lync 1</p></td>
</tr>
<tr class="even">
<td><p>Routage des appels sortants</p></td>
<td><p>Site 1 politique de routage de la voix</p></td>
<td><p>Politique de routage téléphonique de site 2</p></td>
<td><p>Politique vocale de l’utilisateur et uniquement aux systèmes non activés pour le routage sur site</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Transférer et transférer des appels

Lorsque les appels sont transférés ou transférés, le routage des appels est affecté par le routage sur la base de l’emplacement.

Le tableau suivant décrit l’utilisateur Lync 1 qui transfère ou transfère un appel PSTN vers un autre utilisateur Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Utilisateur déclenchant ou transférant un appel</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync 1</p></td>
<td><p>Le transfert ou renvoi de l’appel est autorisé</p></td>
<td><p>Le transfert ou renvoi de l’appel n’est pas autorisé</p></td>
<td><p>Le transfert ou renvoi de l’appel n’est pas autorisé</p></td>
</tr>
</tbody>
</table>

  
Le tableau suivant illustre la façon dont le routage basé sur l’emplacement affecte la façon dont l’appel est acheminé en fonction de l’emplacement du transfert de l’utilisateur Lync (utilisateur Lync 2, utilisateur Lync 4, etc.) vers un point de terminaison PSTN.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Point de terminaison pour lequel l’appel est transféré ou renvoyé vers</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison PSTN</p></td>
<td><p>Le transfert d’appel est acheminé par le biais du site 1 politique de routage de la voix et sortie via la passerelle site 1</p></td>
<td><p>Le transfert d’appel ou le transfert est acheminé via la stratégie de routage de la voix site 2 et la sortie via la passerelle site 2</p></td>
<td><p>Le transfert d’appel est routé par le biais de la stratégie vocale et de la sortie de l’utilisateur Lync via une passerelle non activée pour le routage sur site (le cas échéant).</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Sonnerie simultanée

Lorsque le routage par emplacement est configuré dans l’exemple de topologie, les interactions suivantes sont appliquées.

Le tableau suivant indique si le routage basé sur l’emplacement autorise une sonnerie simultanée pour différents utilisateurs de Lync (c’est-à-dire, utilisateur Lync 2, utilisateur Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Destination de l’appel RTC entrant</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync 1</p></td>
<td><p>Sonnerie simultanée autorisée</p></td>
<td><p>Sonnerie simultanée interdite</p></td>
<td><p>Sonnerie simultanée interdite</p></td>
</tr>
</tbody>
</table>

  
Le tableau suivant indique si le routage en fonction de l’emplacement autorise une sonnerie simultanée à un point de terminaison RTC provenant de différents utilisateurs de Lync (c’est-à-dire, utilisateur Lync 2, utilisateur Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible de la sonnerie simultanée</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans le site réseau non activé pour le routage par emplacement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync 1 téléphone mobile (point de terminaison PSTN)</p></td>
<td><p>Appels routés par le biais de la stratégie de routage vocale du site réseau 1 et de la sortie via le site 1 passerelle</p></td>
<td><p>Appels routés par le biais de la stratégie de routage de la voix du site Network 2 et de la sortie via la passerelle site 2</p></td>
<td><p>Appels routés par le biais de la stratégie vocale de l’appelant et sortie via une passerelle RTC non activée pour le routage par emplacement</p></td>
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

