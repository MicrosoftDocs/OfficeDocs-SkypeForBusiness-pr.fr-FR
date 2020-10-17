---
title: Expérience utilisateur Lync Server 2013 en cas de défaillance du pool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User experience during pool failure
ms:assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205184(v=OCS.15)
ms:contentKeyID: 48185166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd2d6733f2db3a988f604554df55a25f866f5099
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530191"
---
# <a name="user-experience-during-pool-failure-in-lync-server-2013"></a>Expérience utilisateur en cas de défaillance du pool dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-03_

Si un pool est basculé, tous les utilisateurs du pool affecté sont obligés de se déconnecter, puis de se reconnecter au pool de sauvegarde. Pendant quelques instants, les utilisateurs qui se connectent au pool de sauvegarde peuvent être en mode Résistance. En mode résistance, les utilisateurs ne peuvent pas effectuer des tâches qui provoqueraient une modification permanente sur Lync Server, comme l’ajout d’un contact. Une fois le basculement terminé, tous les utilisateurs peuvent obtenir tous les services du pool de sauvegarde.

Toutes les sessions en cours d’un utilisateur au moment de la défaillance du pool sont interrompues, et l’utilisateur doit rétablir ces sessions après le basculement pour continuer.

Les utilisateurs ne sont pas rapatriés pendant le basculement ou la restauration automatique. Les utilisateurs hébergés sur un pool qui subit une défaillance sont temporairement pris en charge par le pool de sauvegarde. Lorsque le pool d’accueil est restauré, l’administrateur peut restaurer ces utilisateurs afin qu’ils soient pris en charge par leur pool d’accueil d’origine.

Remarque dans Lync 2013, la base de données du serveur d’informations d’emplacement n’est pas répliquée dans le pool de sauvegarde. Il est recommandé que l’administrateur sauvegarde régulièrement la base de données LIS et utilise la dernière copie de sauvegarde pour la restaurer dans le pool de sauvegarde après le basculement.

<div>

## <a name="user-experience-during-failover"></a>Expérience utilisateur durant le basculement

Lorsqu’un utilisateur se trouve dans un pool subissant une défaillance, il est déconnecté. Toute session d’égal à égal à laquelle l’utilisateur participait est terminée, de même que les conférences organisées par cet utilisateur. L’utilisateur ne peut se reconnecter qu’après l’expiration du minuteur de résistance du serveur d’inscriptions avancé ou lorsque l’administrateur initie des procédures de basculement. Lorsque l’utilisateur se reconnecte, il se connecte au pool de sauvegarde. S’il se connecte avant que le basculement soit terminé, il sera en mode Résistance jusqu’à la fin du basculement. C’est seulement alors que l’utilisateur peut établir de nouvelles sessions pour rétablir des sessions précédentes.

</div>

<div>

## <a name="user-experience-during-failback"></a>Expérience utilisateur durant la restauration

La restauration automatique du pool peut survenir pendant qu’un utilisateur affecté est connecté au pool de sauvegarde ; l’utilisateur reste connecté et opérationnel pendant la restauration. Notez que l’exécution du processus de restauration automatique prend plusieurs minutes. À titre de référence, il devrait prendre jusqu’à 60 minutes pour un pool de 20 000 utilisateurs.

Les tableaux suivants présentent des détails supplémentaires sur la façon dont un utilisateur avec un client Lync 2013 ou un client Microsoft Lync 2010 est concerné pendant et après la restauration automatique, ainsi que la façon dont les utilisateurs d’autres pools voient et interagissent avec un utilisateur d’un pool qui est en cours d’échec. Les utilisateurs disposant de clients Microsoft Office Communicator 2007 R2 ne peuvent pas se connecter tant que le pool frontal n’est pas complètement restauré.)

Le terme *utilisateur affecté* fait référence à tous les utilisateurs qui ont été basculés à partir du pool d’accueil et qui sont pris en charge par le pool de sauvegarde. Par définition, tout utilisateur initialement hébergé sur le pool de sauvegarde n’est pas un utilisateur affecté.

### <a name="user-experience-for-an-affected-user-in-a-pool-in-failback"></a>Expérience utilisateur pour un utilisateur affecté dans un pool en restauration automatique

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Statut de l’utilisateur ou tâche</th>
<th>Pendant la restauration automatique</th>
<th>Une fois la restauration automatique terminée</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Statut d’un utilisateur déjà connecté</p></td>
<td><p>L’utilisateur reste connecté au pool de sauvegarde. À un certain moment, l’utilisateur sera déconnecté et reconnecté au pool d’accueil d’origine, en mode Résistance.</p></td>
<td><p>L’utilisateur reste connecté et passe en mode normal.</p></td>
</tr>
<tr class="even">
<td><p>Connexion d’un nouvel utilisateur</p></td>
<td><p>L’utilisateur peut se connecter au pool d’accueil en mode Résistance.</p></td>
<td><p>L’utilisateur peut se connecter au pool d’accueil d’origine en mode normal.</p></td>
</tr>
<tr class="odd">
<td><p>Conférences en cours organisées par un utilisateur affecté</p></td>
<td><p>Toutes les modalités de conférence sont terminées. Le bouton Rejoindre s’affiche, mais aucun utilisateur ne peut rejoindre la conférence tant que l’utilisateur affecté est en mode Résistance.</p></td>
<td><p>Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.</p></td>
</tr>
<tr class="even">
<td><p>Conférences en cours organisées par un utilisateur non affecté</p></td>
<td><p>La conférence se poursuit et l’utilisateur affecté peut rester dans la conférence. L’utilisateur affecté est limité à ce qu’il peut faire en mode Résistance.</p></td>
<td><p>La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent une fois que l’utilisateur a quitté le mode Résistance.</p></td>
</tr>
<tr class="odd">
<td><p>Planification ou modification de réunions planifiées, création de conférences ad hoc</p></td>
<td><p>Impossibles pendant que l’utilisateur est en mode Résistance.</p></td>
<td><p>Disponibles pour toutes les modalités.</p></td>
</tr>
<tr class="even">
<td><p>Présence telle qu’elle est vue par les autres utilisateurs du même pool</p></td>
<td><p>Présence inconnue pendant que l’utilisateur est connecté au pool de sauvegarde en mode Résistance.</p></td>
<td><p>Affiche le dernier état de présence défini par l’utilisateur, et les changements du statut de présence sont maintenant reflétés.</p></td>
</tr>
<tr class="odd">
<td><p>Disponibilité de la liste de contacts et du Service de carnet d’adresses</p></td>
<td><p>Non disponibles</p></td>
<td><p>Available</p></td>
</tr>
<tr class="even">
<td><p>Ensemble des sessions et modalités pair à pair</p></td>
<td><p>Available</p></td>
<td><p>Available</p></td>
</tr>
</tbody>
</table>


### <a name="user-experience-for-a-user-homed-in-an-unaffected-pool-during-failback-of-another-pool"></a>Expérience utilisateur pour un utilisateur hébergé dans un pool non affecté pendant la restauration automatique d’un autre pool

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tâche utilisateur</th>
<th>Pendant la restauration automatique</th>
<th>Une fois la restauration automatique terminée</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Affichage de la présence de l’utilisateur affecté</p></td>
<td><p>Affiche le dernier état de présence défini par l’utilisateur.</p></td>
<td><p>Opérationnel. Les utilisateurs non affectés voient les mises à jour effectuées par les utilisateurs affectés.</p></td>
</tr>
<tr class="even">
<td><p>Conférences en cours organisées par un utilisateur affecté</p></td>
<td><p>Toutes les modalités de conférence sont terminées.</p></td>
<td><p>Toutes les modalités fonctionnent à présent. Chaque participant doit cliquer pour participer à la conférence.</p></td>
</tr>
<tr class="odd">
<td><p>Conférences en cours organisées par un utilisateur non affecté</p></td>
<td><p>La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.</p></td>
<td><p>La conférence se poursuit. L’utilisateur affecté peut rester dans la conférence et toutes les modalités fonctionnent.</p></td>
</tr>
<tr class="even">
<td><p>Ensemble des sessions et modalités pair à pair</p></td>
<td><p>Available</p></td>
<td><p>Available</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

