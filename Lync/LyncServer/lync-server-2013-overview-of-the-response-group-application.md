---
title: 'Lync Server 2013 : Vue d’ensemble de l’application Response Group'
TOCTitle: Vue d’ensemble de l’application Response Group
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398513(v=OCS.15)
ms:contentKeyID: 49297534
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de l’application Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Lorsqu’un appelant appelle un groupe de réponses, l’appel est acheminé vers un agent basé sur un groupement de postes ou vers les réponses vocales interactives (IVR) aux questions de l’appelant. L’application Response Group utilise des méthodes standard de routage du groupe de réponses pour acheminer l’appel vers le prochain agent disponible. Parmi les méthodes de routage d’appel figurent notamment le routage de série, parallèle, le plus longuement inactif, tourniquet (round robin) et le nouveau routage Attendant dans lequel tous les agents sont appelés en même temps pour tous les appels entrants, quelle que soit leur présence actuelle. Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère. Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel. Si la file d’attente est pleine, ou si l’appel arrive à expiration dans la file d’attente, l’appelant entendra probablement un message, puis sera déconnecté ou transféré vers une autre destination. Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses. Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.

> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé en ligne, les appels Response Group sont acheminés vers cet agent.

> [!NOTE]  
> L’application Response Group utilise un service interne, appelé service d’établissement des correspondances (Match Making), pour mettre les appels en file d’attente et rechercher les agents disponibles. Chaque ordinateur exécutant l’application Response Group exécute le service d’établissement des correspondances, mais un seul service d’établissement des correspondances par pool Lync Server est actif à la fois, tous les autres sont passifs. En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif. L’application Response Group fait le maximum pour s’assurer que le routage des appels et la mise en file d’attente se poursuivent sans interruption. Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus. Par exemple, si la transition est due à une panne du serveur frontal, tous les appels actuellement gérés par le service d’établissement des correspondances actif sur ce serveur frontal sont également perdus.

Dans Lync Server 2013, deux rôles d’administration sont disponibles pour gérer les groupes Response Group : gestionnaire Response Group et administrateur Response Group. Les administrateurs Response Group peuvent gérer tous les aspects de tous les groupes Response Group. Les gestionnaires Response Group peuvent uniquement gérer certains aspects et uniquement pour les groupes Response Group dont ils sont propriétaires. Le nouveau rôle de gestionnaire permet de réduire les coûts d’administration, car il permet de déléguer des responsabilités limitées pour des groupes Response Group spécifiques à un utilisateur pour lequel la solution Voix Entreprise est activée.

Pour adapter le nouveau rôle de gestionnaire, l’application Response Group de Lync Server 2013 intègre un **Type de flux de travail** dont la valeur est Géré ou Non géré. Le tableau ci-dessous décrit les groupes Response Group gérés et non gérés.

### Groupes Response Group gérés et non gérés

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de groupe Response Group</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Non géré</p></td>
<td><ul><li><p>Aucun gestionnaire n’est affecté aux groupes Response Group non gérés. Seul l’administrateur Response Group peut configurer ces groupes Response Group.</p></li><li><p>Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents.</p></li><li><p>Lors de la migration de groupes Response Group depuis une version antérieure vers Lync Server 2013, le type prend la valeur Non géré.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Géré</p></td>
<td><ul><li><p>Les administrateurs Response Group peuvent configurer tous les aspects des groupes Response Group gérés.</p></li><li><p>Les gestionnaires Response Group ne peuvent pas afficher ou modifier les groupes Response Group qui ne leur sont pas explicitement affectés.</p></li><li><p>Les gestionnaires Response Group peuvent configurer uniquement certains paramètres des groupes Response Group qui leur sont explicitement affectés.</p></li><li><p>Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés.</p></li></ul></td>
</tr>
</tbody>
</table>


Le tableau ci-dessous décrit les actions que les gestionnaires Response Group peuvent et ne peuvent pas effectuer pour les groupes Response Group qui leur sont affectés.

### Fonctions du gestionnaire Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Peut configurer :</th>
<th>Peut créer, supprimer ou configurer :</th>
<th>Ne peut pas :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul><li><p>Agents</p></li><li><p>Message d’accueil</p></li><li><p>Nom de l’Response Group</p></li><li><p>Description</p></li><li><p>Numéro affiché</p></li><li><p>Heures d’ouverture</p></li><li><p>Attente musicale</p></li><li><p>Statut (actif/inactif)</p></li><li><p>Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR)</p></li></ul></td>
<td><ul><li><p>Groupes d’agents</p></li><li><p>Files d’attente</p></li><li><p>Périodes de congé</p></li></ul></td>
<td><ul><li><p>Créer ou supprimer un type de flux de travail</p></li><li><p>Modifier les paramètres principaux des groupes Response Group, tels que : <strong>URI SIP</strong> , <strong>Numéro de téléphone</strong> ou <strong>Type de flux de travail</strong></p></li></ul></td>
</tr>
</tbody>
</table>


Les gestionnaires Response Group peuvent utiliser les outils suivants pour gérer leurs groupes Response Group désignés.

  - Panneau de configuration Lync Server
    
    > [!NOTE]  
    > Les gestionnaires Response Group peuvent uniquement gérer les paramètres Response Group avec cet outil. Les autres paramètres Lync Server ne sont pas disponibles pour les gestionnaires.

  - outil de configuration Response Group

  - Lync Server Management Shell

Response Group est bien dimensionné pour les environnements de services ou de groupes de travail (pour plus d’informations, reportez-vous à [Planification de capacité de Response Group dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) et peut être déployé dans de toutes nouvelles installations téléphoniques. Il prend en charge les appels entrants provenant du déploiement de Voix Entreprise et du réseau de l’opérateur local. Les agents peuvent utiliser Lync 2013, Lync 2010, Intendant Lync 2010 ou Lync Phone Edition pour prendre les appels qui leur sont acheminés.

L’application application Response Group est un composant de Voix Entreprise. L’application Response Group est automatiquement installée et activée quand vous déployez Voix Entreprise.

