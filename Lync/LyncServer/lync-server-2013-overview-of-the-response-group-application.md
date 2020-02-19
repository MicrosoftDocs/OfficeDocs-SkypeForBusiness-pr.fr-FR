---
title: 'Lync Server 2013 : vue d’ensemble de l’application Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3bb7b9260e85326718bf388da977833c6e87ea
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Vue d’ensemble de l’application Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Lorsqu’un appelant appelle un groupe de réponses, l’appel est acheminé vers un agent basé sur un groupement de postes ou vers les réponses vocales interactives (IVR) aux questions de l’appelant. L’application Response Group utilise des méthodes de routage Response Group standard pour acheminer l’appel vers le prochain agent disponible. Parmi les méthodes de routage d’appel figurent notamment le routage de série, parallèle, le plus longuement inactif, tourniquet (round robin) et le nouveau routage Attendant dans lequel tous les agents sont appelés en même temps pour tous les appels entrants, quelle que soit leur présence actuelle. Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère. Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel. Si la file d’attente est pleine, ou si l’appel arrive à expiration dans la file d’attente, l’appelant entendra probablement un message, puis sera déconnecté ou transféré vers une autre destination. Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses. Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.

<div>


> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels Response Group ne sont pas acheminés vers cet agent.



</div>

<div>


> [!NOTE]  
> L’application Response Group utilise un service interne, appelé faire correspondre les appels, pour mettre en file d’attente des appels et trouver des agents disponibles. Chaque ordinateur qui exécute l’application Response Group exécute le service de mise en correspondance, mais un seul service correspondant est actif par pool Lync Server, les autres étant passifs. En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif. L’application Response Group fait de son mieux pour s’assurer que le routage des appels et la mise en file d’attente se poursuivent sans interruption. Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus. Par exemple, si la transition est due au fait que le serveur frontal descend, les appels actuellement traités par le service de correspondance active sur ce serveur frontal sont également perdus.



</div>

Dans Lync Server 2013, deux rôles de gestion sont disponibles pour la gestion des groupes Response Group : Response Group Manager et l’administrateur Response Group. Les administrateurs de Response Group peuvent gérer tous les aspects de n’importe quel groupe Response Group. Les gestionnaires Response Group ne peuvent gérer que certains aspects, et uniquement pour les groupes Response Group qu’ils possèdent. Le nouveau rôle de gestionnaire peut aider à réduire les coûts d’administration, car vous pouvez déléguer des responsabilités limitées pour des groupes Response Group spécifiques à tout utilisateur activé pour voix entreprise.

Pour prendre en charge le nouveau rôle de gestionnaire, l’application Response Group Lync Server 2013 introduit un **type de flux de travail** géré ou non géré. Le tableau suivant décrit les groupes Response Group gérés et non gérés.

### <a name="managed-and-unmanaged-response-groups"></a>Groupes Response Group gérés et non gérés

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
<td><p>Non gérés</p></td>
<td><ul>
<li><p>Aucun gestionnaire n’est affecté aux groupes Response Group non gérés. Seul l’administrateur de groupe de réponse peut configurer ces groupes Response Group.</p></li>
<li><p>Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents.</p></li>
<li><p>Lorsque vous migrez des groupes Response Group d’une version antérieure vers Lync Server 2013, le type est défini sur non géré.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Géré</p></td>
<td><ul>
<li><p>Les administrateurs de Response Group peuvent configurer tous les aspects des groupes Response Group gérés.</p></li>
<li><p>Les gestionnaires Response Group ne peuvent pas afficher ou modifier les groupes Response Group qui ne leur sont pas explicitement affectés.</p></li>
<li><p>Les responsables de groupes Response Group peuvent configurer uniquement certains paramètres des groupes Response Group qui leur sont explicitement affectés.</p></li>
<li><p>Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Le tableau suivant décrit les actions que les gestionnaires de groupe de réponse peuvent et ne peuvent pas effectuer pour les groupes Response Group qui leur sont attribués.

### <a name="response-group-manager-capabilities"></a>Fonctions du gestionnaire Response Group

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
<th>Pouvant</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Représentants</p></li>
<li><p>Message d’accueil</p></li>
<li><p>Nom du groupe Response Group</p></li>
<li><p>Description</p></li>
<li><p>Numéro affiché</p></li>
<li><p>Heures d’ouverture</p></li>
<li><p>Attente musicale</p></li>
<li><p>Statut (actif/inactif)</p></li>
<li><p>Flux de travail de groupe de recherche ou flux de travail de réponse vocale interactive (IVR)</p></li>
</ul></td>
<td><ul>
<li><p>Groupes d’agents</p></li>
<li><p>Files d’attente</p></li>
<li><p>Périodes de congé</p></li>
</ul></td>
<td><ul>
<li><p>Créer ou supprimer un type de flux de travail</p></li>
<li><p>Modifier les paramètres principaux des groupes Response Group, tels que : <strong>URI SIP</strong>, <strong>Numéro de téléphone</strong> ou <strong>Type de flux de travail</strong></p></li>
</ul></td>
</tr>
</tbody>
</table>


Les responsables des groupes Response Group peuvent utiliser les outils suivants pour gérer leurs groupes Response Group désignés.

  - Panneau de commande Lync Server
    
    <div>
    

    > [!NOTE]  
    > Les gestionnaires Response Group peuvent gérer uniquement les paramètres Response Group à l’aide de cet outil. Les autres paramètres de Lync Server ne sont pas disponibles pour les responsables.

    
    </div>

  - outil de configuration Response Group

  - Lync Server Management Shell

Response Group est adapté aux environnements de service ou de groupe de travail (pour plus d’informations, consultez la rubrique [Capacity Planning for Response Group in Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) et peut être déployé dans des installations de téléphonie entièrement nouvelles. Il prend en charge les appels entrants du déploiement voix entreprise et du réseau de l’opérateur local. Les agents peuvent utiliser Lync 2013, Lync 2010, Lync 2010 attendant ou Lync Phone Edition pour prendre les appels qui leur sont routés.

L’application Response Group est un composant de voix entreprise. Lorsque vous déployez voix entreprise, l’application Response Group est installée et activée automatiquement.

</div>

<span> </span>

</div>

</div>

</div>

