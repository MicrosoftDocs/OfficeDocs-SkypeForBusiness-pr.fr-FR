---
title: 'Lync Server 2013: vue d’ensemble de l’application Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Response Group application
ms:assetid: 6cc333e7-4029-4372-86b2-016040c415fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398513(v=OCS.15)
ms:contentKeyID: 48184453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b523a05509b0043effb8cb2b761d7ee06fd36751
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-response-group-application-in-lync-server-2013"></a>Vue d’ensemble de l’application Response Group dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-11_

Quand un appelant appelle un Response Group, l’appel est acheminé vers un agent en fonction du groupe de recherche ou des réponses de l’appelant aux questions du système de réponse vocale interactive. L’application Response Group utilise des méthodes de routage de groupe de réponse standard pour acheminer l’appel vers le prochain agent disponible. Les méthodes de routage des appels incluent le routage de série, de longue durée, parallèle, de tourniquet cyclique et le routage de l’attendant (c’est-à-dire que tous les agents sont appelés en même temps pour chaque appel entrant, quelle que soit leur présence actuelle). Si aucun agent n’est disponible, l’appel est mis en file d’attente jusqu’à ce qu’un agent se libère. Quand il est en file d’attente, l’appelant entend de la musique jusqu’à ce qu’un agent accepte l’appel. S’il s’agit d’une file d’attente complète ou si l’appel est interrompu dans la file d’attente, l’appelant peut entendre un message, puis être déconnecté ou transféré vers une autre destination. Quand un agent accepte l’appel, l’appelant peut dans certains cas voir l’identité de l’agent, selon la façon dont l’administrateur configure le groupe de réponses. Les agents peuvent être formels, c’est-à-dire qu’ils doivent se connecter au groupe avant de pouvoir accepter les appels y étant acheminés, ou informels, c’est-à-dire qu’ils n’ont pas besoin de se connecter ou déconnecter du groupe pour accepter les appels.

<div>


> [!NOTE]  
> Seuls les utilisateurs locaux peuvent être des agents. Si un agent est déplacé de local vers en ligne, les appels de groupe de réponse ne seront pas routés vers cet agent.



</div>

<div>


> [!NOTE]  
> L’application Response Group utilise un service interne appelé faire correspondre pour mettre en file d’attente les appels et rechercher les agents disponibles. Chaque ordinateur exécutant l’application Response Group exécute le service Matching, mais une seule correspondance avec le service par le pool Lync Server est active à la fois, les autres sont passives. En cas d’indisponibilité du service d’établissement des correspondances actif au cours d’une interruption de service imprévue, l’un des services passifs devient actif. L’application de groupe de réponse utilise le mieux pour s’assurer que le routage d’appel et la mise en file d’attente continuent de fonctionner sans interruption. Cependant, lorsqu’une transition du service d’établissement des correspondances se produit, tous les appels en transfert à ce moment-là sont perdus. Par exemple, si la transition est en raison du fait que le serveur frontal s’arrête, tout appel actuellement géré par le service de correspondance active sur le serveur principal est également perdu.



</div>

Dans Lync Server 2013, deux rôles de gestion sont disponibles pour gérer les groupes de réponse: responsable du groupe de réponse et administrateur du groupe de réponse. Les administrateurs de groupe de réponse peuvent gérer tout aspect de n’importe quel Response Group. Les responsables de groupe de réponse peuvent uniquement gérer certains aspects, et uniquement pour les groupes de réponse qu’ils possèdent. Le nouveau rôle de responsable peut vous aider à réduire les coûts d’administration, car vous pouvez déléguer des responsabilités limitées pour des groupes de réponse spécifiques à n’importe quel utilisateur qui est activé pour voix entreprise.

Pour prendre en charge le rôle de nouveau directeur, l’application Response Group de Lync Server 2013 introduit un **type de flux de travail de type** géré ou non géré. Le tableau ci-dessous décrit les groupes Response Group gérés et non gérés.

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
<td><p>Non géré</p></td>
<td><ul>
<li><p>Aucun gestionnaire n’est affecté aux groupes Response Group non gérés. Seul l’administrateur du groupe de réponse peut configurer ces groupes de réponse.</p></li>
<li><p>Plusieurs groupes Response Group non gérés peuvent partager une file d’attente ou un groupe d’agents.</p></li>
<li><p>Lorsque vous migrez des groupes de réponses d’une version antérieure vers Lync Server 2013, le type est défini sur non géré.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Géré</p></td>
<td><ul>
<li><p>Les administrateurs de groupe de réponse peuvent configurer n’importe quel aspect de groupes de réponse gérés.</p></li>
<li><p>Les responsables de groupe de réponse ne peuvent pas afficher ou modifier des groupes de réponse qui ne sont pas explicitement attribués.</p></li>
<li><p>Les responsables de groupe de réponse peuvent configurer uniquement certains paramètres des groupes de réponse qui leur sont explicitement affectés.</p></li>
<li><p>Les groupes Response Group gérés ne peuvent pas partager des files d’attente ou des groupes d’agents avec d’autres groupes Response Group, qu’ils soient gérés ou non gérés.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Le tableau suivant décrit les actions que les responsables de groupe de réponse peuvent exécuter et ne peuvent pas effectuer pour les groupes de réponse qui leur sont attribués.

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
<th>Ne peut pas :</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>Agents</p></li>
<li><p>Message d’accueil</p></li>
<li><p>Nom du groupe de réponse</p></li>
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


Les responsables de groupe de réponse peuvent utiliser les outils suivants pour gérer leurs groupes de réponse désignés.

  - Panneau de configuration Lync Server
    
    <div>
    

    > [!NOTE]  
    > Les responsables de groupe de réponse peuvent uniquement gérer les paramètres de groupe de réponse à l’aide de cet outil. Les autres paramètres du serveur Lync ne sont pas disponibles aux responsables.

    
    </div>

  - outil de configuration Response Group

  - Lync Server Management Shell

Response Group s’adapte bien aux environnements de services ou de groupe de travail (pour plus de détails, voir [planification de la capacité pour Response Group dans Lync Server 2013](lync-server-2013-capacity-planning-for-response-group.md)) et peut être déployé dans les nouvelles installations de téléphonie. Il prend en charge les appels entrants du déploiement voix entreprise et du réseau d’opérateur local. Les agents peuvent utiliser Lync 2013, Lync 2010, Lync 2010 attendant ou Lync Phone Edition pour prendre les appels routés vers eux.

L’application Response Group est un composant d’Enterprise Voice. Lorsque vous déployez Enterprise Voice, l’application Response Group est installée et activée automatiquement.

</div>

<span> </span>

</div>

</div>

</div>

