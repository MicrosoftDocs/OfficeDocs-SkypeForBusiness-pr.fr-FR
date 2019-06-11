---
title: Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response group experience during pool failure
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204886(v=OCS.15)
ms:contentKeyID: 48184116
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90911bebc7c3e60847f5b3fcb8f69523697af0f8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-experience-in-lync-server-2013-during-pool-failure"></a>Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-30_

Cette section décrit en détail la façon dont l’activité du groupe de réponses est affectée aux étapes suivantes:

  - Une panne se produit dans le pool principal, mais le basculement n’est pas encore lancé.

  - Le service est en échec sur le pool de sauvegarde.

  - Le service n’a pas pu revenir au pool principal.

<div>

## <a name="user-experience-when-outage-occurs"></a>Utilisation de l’interface utilisateur en cas d’interruption

En cas d’interruption d’une réserve ou d’un site, mais que l’administrateur n’a pas encore lancé le basculement, l’activité du groupe de réponses est gérée comme décrit dans le tableau suivant.

<div>


> [!NOTE]  
> Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération. Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.



</div>

### <a name="outage-occurs"></a>Une panne survient

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’appel ou d’action de l’utilisateur</th>
<th>Pendant la période d’interruption</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels connectés à un agent</p></td>
<td><ul>
<li><p>Les appels ordinaires restent connectés.</p></li>
<li><p>Les appels anonymes sont déconnectés.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels en cours non encore connectés à un agent</p></td>
<td><p>Les appels sont déconnectés.</p></td>
</tr>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><ul>
<li><p>Les appels sont déconnectés.</p></li>
<li><p>Si les groupes de réponse étaient importés, les appels se connectent à un pool de sauvegarde, mais les agents hébergés dans le pool principal sont injoignables.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels d’agent de la part de Response Group</p></td>
<td><p>Cette fonctionnalité est désactivée pendant cette étape.</p></td>
</tr>
<tr class="odd">
<td><p>Informations de connexion et d’agent</p></td>
<td><ul>
<li><p>Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</p></li>
<li><p>Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</p></li>
<li><p>Les groupes d’agent importés ne sont pas affichés dans la console de l’agent.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuration de Response Group</p></td>
<td><ul>
<li><p>Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</p></li>
<li><p>Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</p></li>
<li><p>Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failover"></a>Utilisation de l’interface utilisateur pendant le basculement

Lorsqu’un administrateur appelle le basculement vers un pool de sauvegarde, l’activité du groupe de réponses est gérée durant et après le basculement, comme décrit dans le tableau suivant. La première colonne décrit le type d’activité qui peut avoir lieu. La colonne du milieu décrit la façon dont chaque activité est gérée au cours de la période de reprise du pool de sauvegarde. La dernière colonne décrit le mode de gestion de l’activité pour la durée, une fois le processus de basculement terminé et le pool de sauvegarde en cours pour le pool principal.

<div>


> [!NOTE]  
> Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération. Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.



</div>

### <a name="failover-is-initiated"></a>Le basculement est lancé

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’appel ou d’action de l’utilisateur</th>
<th>Lors du basculement</th>
<th>Après le basculement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels connectés à un agent</p></td>
<td><ul>
<li><p>Les appels ordinaires restent connectés.</p></li>
<li><p>Les appels anonymes sont déconnectés.</p></li>
</ul></td>
<td><ul>
<li><p>Les appels ordinaires restent connectés.</p></li>
<li><p>Pour les groupes de réponse importés, les appels anonymes ayant atteint le pool de sauvegarde restent connectés.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels en cours non encore connectés à un agent</p></td>
<td><p>Les appels sont déconnectés.</p></td>
<td><ul>
<li><p>Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</p></li>
<li><p>Pour les groupes de réponse importés, les appels ayant atteint le pool de sauvegarde restent connectés.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><ul>
<li><p>Les appels sont déconnectés.</p></li>
<li><p>S’il s’agit de groupes de réponse importés, les appels se connectent au pool de sauvegarde, mais les agents hébergés dans le pool principal sont injoignables.</p></li>
</ul></td>
<td><ul>
<li><p>Si les Response Groups n’ont pas été importés, les appels sont interrompus.</p></li>
<li><p>Pour les groupes de réponse importés, les appels se connectent au pool de sauvegarde.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels d’agent de la part de Response Group</p></td>
<td><p>Cette fonctionnalité est désactivée pendant cette étape</p></td>
<td><ul>
<li><p>Si les Response Groups n’ont pas été importés, les appels échouent.</p></li>
<li><p>Pour les groupes de réponse importés, les appels aboutissent.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Informations de connexion et d’agent</p></td>
<td><ul>
<li><p>Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</p></li>
<li><p>Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</p></li>
<li><p>Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</p></li>
</ul></td>
<td><ul>
<li><p>Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</p></li>
<li><p>Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</p></li>
<li><p>Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuration de Response Group</p></td>
<td><ul>
<li><p>Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</p></li>
<li><p>Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</p></li>
<li><p>Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</p></li>
</ul></td>
<td><ul>
<li><p>En fonction de la disponibilité de la base de données principale, vous pouvez afficher les groupes de réponses détenus par le pool principal, mais ils ne peuvent pas être modifiés.</p></li>
<li><p>Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</p></li>
<li><p>Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-experience-during-failback"></a>Utilisation des utilisateurs lors du retour arrière

Lorsqu’un administrateur appelle la restauration automatique vers le pool principal, l’activité de groupe de réponses est gérée pendant et après le retour automatique comme décrit dans le tableau suivant.

<div>


> [!NOTE]  
> Lors de la récupération après incident, les appels se comportent différemment selon que les groupes de réponses de la liste principale ont été importés au pool de sauvegarde lors de la récupération. Dans le tableau suivant, les références aux groupes de réponse importés impliquent que les groupes de réponse de pool principal aient été importés dans le pool de sauvegarde lors du mode de récupération d’urgence.



</div>

### <a name="call-handling-in-failback"></a>Gestion des appels en retour automatique

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’appel ou d’action de l’utilisateur</th>
<th>Pendant la restauration automatique</th>
<th>Après la restauration automatique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels connectés à un agent</p></td>
<td><ul>
<li><p>Les appels ordinaires restent connectés.</p></li>
<li><p>Si les Response Groups n’ont pas été importés, il n’y a pas de statut anonyme.</p></li>
<li><p>Pour les groupes de réponse importés, les appels anonymes restent connectés.</p></li>
</ul></td>
<td><ul>
<li><p>Les appels ordinaires restent connectés.</p></li>
<li><p>Si les Response Groups n’ont pas été importés, il n’y a pas de statut anonyme.</p></li>
<li><p>Pour les groupes de réponse importés, les appels anonymes restent connectés.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Appels en cours non encore connectés à un agent</p></td>
<td><ul>
<li><p>Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</p></li>
<li><p>Pour les groupes de réponse importés, les appels seront déconnectés.</p></li>
</ul></td>
<td><ul>
<li><p>Si les Response Groups n’ont pas été importés, aucun appel n’est dans ce statut.</p></li>
<li><p>Pour les groupes de réponse importés, les appels seront déconnectés.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><p>Les appels se connectent au pool principal, mais les agents hébergés dans le pool principal sont injoignables.</p></td>
<td><p>Les appels se connectent à la liste principale.</p></td>
</tr>
<tr class="even">
<td><p>Appels d’agent de la part de Response Group</p></td>
<td><p>Cette fonctionnalité est désactivée pendant cette étape.</p></td>
<td><p>Appels réussis.</p></td>
</tr>
<tr class="odd">
<td><p>Informations de connexion et d’agent</p></td>
<td><ul>
<li><p>Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent, mais les agents ne peuvent pas se connecter.</p></li>
<li><p>Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</p></li>
<li><p>Les groupes d’agent importés s’affichent dans la console d’agent et les agents peuvent se connecter.</p></li>
</ul></td>
<td><ul>
<li><p>Les groupes d’agents appartenant au pool principal peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</p></li>
<li><p>Les groupes d’agents appartenant au pool de sauvegarde peuvent être affichés sur la console de l’agent et les agents peuvent se connecter.</p></li>
<li><p>Les groupes d’agent importés ne sont pas affichés dans la console de l’agent.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Configuration de Response Group</p></td>
<td><ul>
<li><p>Il est possible d’afficher les groupes de réponse appartenant au pool principal en fonction de la disponibilité de la base de données principale du pool principal, mais pas de les modifier.</p></li>
<li><p>Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</p></li>
<li><p>Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</p></li>
</ul></td>
<td><ul>
<li><p>Les groupes de réponse appartenant au pool principal peuvent être affichés et modifiés.</p></li>
<li><p>Les groupes de réponse appartenant au pool de sauvegarde peuvent être affichés et modifiés.</p></li>
<li><p>Les groupes de réponse importés ne peuvent pas être affichés dans le panneau de configuration de Lync Server ou dans l’outil de configuration de groupe de réponse, mais ils peuvent être configurés en utilisant des applets de commande Lync Server Management Shell.</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

