---
title: >
  Lync Server 2013 : Processus de déploiement du routage géodépendant
TOCTitle: Processus de déploiement du routage géodépendant
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ994055(v=OCS.15)
ms:contentKeyID: 53095484
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement du routage géodépendant dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette rubrique fournit une vue d’ensemble du processus de configuration du routage géodépendant. Vous devez déployer Lync ServerEnterprise Edition ou Standard Edition avec Voix Entreprise avant de configurer le routage géodépendant. Les composants requis par le routage géodépendant sont déjà installés et activés lorsque vous déployez Voix Entreprise.

### Processus de déploiement du routage géodépendant

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
<td><p>Déployer Voix Entreprise</p></td>
<td><ul>
<li><p>Configurer des jonctions</p></li>
<li><p>Créer des stratégies de voix</p></li>
<li><p>Définir des itinéraires des communications vocales</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Déploiement de Voix Entreprise</p></td>
</tr>
<tr class="even">
<td><p>Vérifier votre déploiement de Voix Entreprise</p></td>
<td><p></p></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Configurer des régions réseau, sites réseau et sous-réseaux</p></td>
<td><ul>
<li><p>Créer des régions réseau</p></li>
<li><p>Créer des sites réseau</p></li>
<li><p>Associer des sous-réseaux aux sites réseau</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>À propos des régions réseau, sites réseau et sous-réseaux<br />
Créer ou modifier une région réseau<br />
Créer ou modifier un site réseau<br />
Associer un sous-réseau à un site réseau</p></td>
</tr>
<tr class="even">
<td><p>Configurer le routage géodépendant</p></td>
<td><ul>
<li><p>Créer des stratégies de routage des communications vocales</p></li>
<li><p>Définir des configurations distinctes pour les jonctions individuelles</p></li>
<li><p>Modifier les stratégies de voix</p></li>
<li><p>Activer la configuration du routage géodépendant</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## Exemple de déploiement

Le déploiement suivant permet d’illustrer les mécanismes activés par le routage géodépendant.

![Topologie de routage géodépendant](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "Topologie de routage géodépendant")

## Appels RTC entrants

Un administrateur peut activer le routage géodépendant pour la jonction définie pour acheminer les appels vers la passerelle du site 1 et associer celle-ci au site 1. Les appels acheminés via la passerelle du site 1 sont dès lors acheminés vers les utilisateurs situés dans le site 1. Tous les appels acheminés via la jonction Passerelle du site 1 destinés aux utilisateurs situés dans un autre site (par exemple, site 2) sont bloqués pour empêcher le contournement des frais de réseau téléphonique commuté.

Tous les appels RTC entrants qui transitent via la passerelle du site 1 sont uniquement autorisés à être acheminés vers les points de terminaison situés dans le site 1. Par exemple, lorsque l’utilisateur Lync 1 accède au site 2, tous les appels RTC entrants qui transitent via la passerelle du site 1 ne sont pas acheminés vers les points de terminaison de l’utilisateur Lync 1 situés dans le site 2. La même règle de routage s’applique si l’utilisateur Lync 1 accède à un site réseau inconnu dans lequel l’emplacement de l’utilisateur ne peut pas être déterminé.

Le tableau ci-dessous décrit l’expérience de l’utilisateur Lync 1 dans ce contexte.


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
<th>Points de terminaison de l’utilisateur Lync 1 situés dans le site réseau 1</th>
<th>Points de terminaison de l’utilisateur Lync 1 situés dans le site réseau 2</th>
<th>Points de terminaison de l’utilisateur Lync 1 situés dans un site réseau inconnu</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels RTC entrants destinés à l’utilisateur Lync 1</p></td>
<td><p>Les appels sont acheminés vers les points de terminaison dans cet emplacement</p></td>
<td><p>Les appels ne sont pas acheminés vers les points de terminaison dans cet emplacement</p></td>
<td><p>Les appels ne sont pas acheminés vers les points de terminaison dans cet emplacement</p></td>
</tr>
</tbody>
</table>


## Appels RTC sortants

Les itinéraires des communications vocales sont référencés dans les stratégies de voix affectées directement aux utilisateurs et les stratégies de routage des communications vocales affectées aux sites réseau. Les deux stratégies contiennent des références aux différents itinéraires qui peuvent être utilisés pour acheminer un appel. Par exemple, un administrateur peut définir une stratégie de routage des communications vocales pour tous les utilisateurs situés dans le site réseau 1 pour acheminer tous les appels sortants qui transitent via la passerelle du site 1, tandis que la stratégie de voix de certains utilisateurs définit un itinéraire pour tous les appels sortants qui transitent via la passerelle du site 2. Même si ces utilisateurs sont situés dans le site réseau 1, leurs appels entrants sont acheminés via la passerelle du site 1.

Lorsqu’un utilisateur est situé dans un site réseau configuré pour le routage géodépendant, l’itinéraire défini par la stratégie de routage des communications vocales du site réseau supplante l’itinéraire de la stratégie de voix de l’utilisateur. Cette règle est particulièrement utile pour les utilisateurs qui accèdent temporairement à un autre site. Dans ce cas, les utilisateurs utilisent toujours une passerelle locale pour cet emplacement : si l’utilisateur Lync 3 est situé dans le site 2, tous ses appels sortants sont acheminés via la passerelle du site 2, mais s’il accède au site 1, tous ses appels sortants passés alors qu’il se trouve dans le site 1 sont acheminés via la passerelle du site 1.

Le tableau ci-dessous illustre l’expérience de l’utilisateur Lync 1 passant un appel sortant à partir des sites réseau suivants.


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
<th>Site réseau 1</th>
<th>Site réseau 2</th>
<th>Site réseau inconnu ou pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisation des appels sortants</p></td>
<td><p>Stratégie de voix de l’utilisateur Lync 1</p></td>
<td><p>Stratégie de voix de l’utilisateur Lync 1</p></td>
<td><p>Stratégie de voix de l’utilisateur Lync 1</p></td>
</tr>
<tr class="even">
<td><p>Routage des appels sortants</p></td>
<td><p>Stratégie de routage des communications vocales du site 1</p></td>
<td><p>Stratégie de routage des communications vocales du site 2</p></td>
<td><p>Stratégie de voix de l’utilisateur et uniquement vers les systèmes pour lesquels le routage géodépendant n’est pas activé</p></td>
</tr>
</tbody>
</table>


## Transfert et renvoi des appels

Lorsque les appels sont transférés ou renvoyés, le routage des appels est affecté par le routage géodépendant.

Le tableau ci-dessous décrit le transfert ou le renvoi par l’utilisateur Lync 1 d’un appel RTC vers un autre utilisateur Lync.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Utilisateur lançant le transfert ou le renvoi d’appel</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans un site réseau pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync 1</p></td>
<td><p>Le transfert ou renvoi de l’appel est autorisé</p></td>
<td><p>Le transfert ou renvoi de l’appel n’est pas autorisé</p></td>
<td><p>Le transfert ou renvoi de l’appel n’est pas autorisé</p></td>
</tr>
</tbody>
</table>

  
Le tableau ci-dessous indique de quelle façon le routage géodépendant affecte l’acheminement de l’appel selon l’emplacement de l’utilisateur Lync transféré (utilisateur Lync 2, utilisateur Lync 4, etc.) vers un point de terminaison RTC


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Point de terminaison vers lequel l’appel est transféré ou renvoyé</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans un site réseau pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Point de terminaison RTC</p></td>
<td><p>Le transfert ou le renvoi d’appel est acheminé via la stratégie de routage des communications vocales du site 1 et sorti via la passerelle du site 1</p></td>
<td><p>Le transfert ou le renvoi d’appel est acheminé via la stratégie de routage des communications vocales du site 2 et sorti via la passerelle du site 2</p></td>
<td><p>Le transfert ou le renvoi d’appel est acheminé via la stratégie de voix de l’utilisateur Lync et sorti via une passerelle pour laquelle le routage géodépendant n’est pas activé (si disponible)</p></td>
</tr>
</tbody>
</table>


## Sonnerie simultanée

Une fois le routage géodépendant configuré dans l’exemple de topologie, les interactions suivantes sont appliquées.

Le tableau ci-dessous indique si le routage géodépendant autorise la sonnerie simultanée pour différents utilisateurs Lync (utilisateur Lync 2, utilisateur Lync 4, etc.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cible de l’appel RTC entrant</th>
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans un site réseau pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utilisateur Lync 1</p></td>
<td><p>La sonnerie simultanée est autorisée</p></td>
<td><p>La sonnerie simultanée n’est pas autorisée</p></td>
<td><p>La sonnerie simultanée n’est pas autorisée</p></td>
</tr>
</tbody>
</table>

  
Le tableau ci-dessous indique si le routage géodépendant autorise la sonnerie simultanée vers le point de terminaison RTC de différents utilisateurs Lync (utilisateur Lync 2, utilisateur Lync 4, etc.).


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
<th>Utilisateur Lync 2</th>
<th>Utilisateur Lync 4</th>
<th>Utilisateur Lync dans un site réseau pour lequel le routage géodépendant n’est pas activé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Téléphone mobile de l’utilisateur Lync 1 (point de terminaison RTC)</p></td>
<td><p>Appel acheminé via la stratégie de routage des communications vocales du site réseau 1 et sorti via la passerelle du site 1</p></td>
<td><p>Appel acheminé via la stratégie de routage des communications vocales du site réseau 2 et sorti via la passerelle du site 2</p></td>
<td><p>Appel acheminé via la stratégie de voix de l’appelant et sorti via une passerelle RTC pour laquelle le routage géodépendant n’est pas activé</p></td>
</tr>
</tbody>
</table>


## Voir aussi

#### Autres ressources

[Planification du routage géodépendant dans Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)

