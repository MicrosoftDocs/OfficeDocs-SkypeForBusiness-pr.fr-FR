---
title: 'Lync Server 2013 : Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-24_

Les seuls composants requis pour la messagerie instantanée et la présence sont :

  - Serveurs frontaux de votre organisation ou serveurs Standard Edition. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs.

  - Un programme d’équilibrage de la charge, si vous avez un pool frontal Enterprise Edition. Pour plus d’informations, reportez-vous [à configuration requise pour l’équilibrage de charge pour Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planification du déploiement de pools front-end

Dans Lync Server 2013, l’architecture du pool frontal a changé, et ces modifications affectent la manière dont vous devez planifier et mettre à jour vos pools frontaux.

Nous vous recommandons d’inclure au moins trois serveurs front-end dans votre version Enterprise Edition. Dans Lync Server, l’architecture des pools front-end utilise un modèle de systèmes distribués, dont les données sont conservées sur trois serveurs front-end de la liste. Pour plus d’informations sur cette nouvelle architecture, voir [modifications de topologie dans Lync Server 2013](lync-server-2013-topology-changes.md).

Si vous ne voulez pas déployer trois serveurs frontaux Enterprise Edition et que vous souhaitez effectuer une reprise d’urgence, nous vous conseillons d’utiliser Lync Server Standard Edition et de créer deux pools avec une relation de sauvegarde couplée. Cela fournit une solution de reprise après sinistre avec deux serveurs uniquement. Pour plus d’informations sur les topologies et les fonctionnalités de haute disponibilité et de récupération d’urgence, reportez-vous à la section [planification d’une haute disponibilité et d’une reprise après sinistre dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des regroupements front-end

Pour les listes frontales, suivez les instructions de cette section.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Vérification du bon fonctionnement des pools

Avec le nouveau modèle distribué pour les pools front-end, certains numéros des serveurs d’un pool doivent être en cours d’exécution pour que le pool fonctionne. Il existe deux modes de perte pour une réserve

  - Perte de quorum au niveau du groupe de routage, provoquée par lʼinsuffisance des serveurs réplica pour un groupe de routage particulier. Un groupe de routage est une agrégation d’un ensemble d’utilisateurs hébergés dans le pool. Chaque groupe de routage comporte trois réplicas du pool : un seul et deux secondaires.

  - Perte de quorum au niveau du pool, provoquée par une insuffisance du nombre de serveurs d’amorçage en cours d’exécution dans le pool.

<div>

## <a name="routing-group-level-quorum-loss"></a>Perte de quorum au niveau du groupe de routage

Lors du premier démarrage d’un nouveau nouveau pool frontal, il est primordial que 85 % des serveurs soient opérationnels, comme indiqué dans le tableau ci-après. Si un pourcentage inférieur de serveurs est en cours d’exécution, les services risquent de rester bloqués dans leur état de démarrage et le pool risque de ne pas démarrer.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs dans le pool</th>
<th>Nombre de serveurs devant être en cours d’exécution pour que le pool démarre la première fois</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>deuxième</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>6</p></td>
<td><p>5</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>5</p></td>
</tr>
<tr class="odd">
<td><p>version8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>09</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>0,10</p></td>
<td><p>version8</p></td>
</tr>
<tr class="even">
<td><p>27,9</p></td>
<td><p>09</p></td>
</tr>
<tr class="odd">
<td><p>midi</p></td>
<td><p>0,10</p></td>
</tr>
</tbody>
</table>


Chaque fois que le pool est démarré ultérieurement, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). S’il n’est pas possible de démarrer ce nombre de serveurs (mais que suffisamment de serveurs peuvent être démarrés pour éviter une perte de quorum au niveau du pool), vous pouvez utiliser l’applet de commande **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** pour permettre au pool de récupérer de cette perte de quorum au niveau du groupe de routage et d’avancer. Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Dans la mesure où Lync Server utilise la base de données SQL principale comme témoin, si vous fermez la base de données principale et que vous basculez vers la copie miroir et que vous arrêtez les serveurs frontaux suffisants pour qu’ils soient insuffisants en fonction de la table précédente, le pool entier est déplacée vers le bas. Pour plus d’informations, voir <A href="http://go.microsoft.com/fwlink/?linkid=393672">témoin de mise en miroir de base de données</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour qu’un pool frontal puisse fonctionner, il ne peut pas être dans la perte de quorum au niveau du pool. Si le nombre de serveurs en cours de passe est inférieur au niveau fonctionnel, comme indiqué dans le tableau suivant, les serveurs restants du pool arrêtent tous les services Lync Server. Notez que les nombres figurant dans le tableau ci-dessous partent du principe que les serveurs dorsaux du pool s’exécutent.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs frontaux de la liste</th>
<th>Nombre de serveurs devant être exécutés pour que le pool soit opérationnel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>deuxième</p></td>
<td><p>1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>2 (n’importe lesquels)</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>3 (n’importe lesquels)</p></td>
</tr>
<tr class="even">
<td><p>7</p></td>
<td><p>4 (n’importe lesquels)</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>4 (n’importe lesquels parmi les 7 premiers serveurs)</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>5 (n’importe lesquels parmi les 9 premiers serveurs)</p></td>
</tr>
</tbody>
</table>


Dans le tableau ci-dessus, le « premier serveur » est le serveur qui s’est affiché en premier, dans l’ordre chronologique, lorsque le pool a été démarré pour la première fois. Pour déterminer ces serveurs, vous pouvez utiliser l’applet de commande **Get-CsComputer** avec l’option **– PoolFqdn** . Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et ceux situés en haut de la liste sont les premiers serveurs.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pools front-end avec deux serveurs front-end

Nous déconseillons le déploiement d’un pool frontal qui ne contient que deux serveurs frontaux. Si vous avez besoin de déployer une telle réserve, suivez les instructions ci-après :

  - Si l’un des deux serveurs frontaux est en panne, vous devez essayer de remettre le serveur en panne dès que vous le pouvez. De même, si vous devez mettre à niveau l’un de ces serveurs, remettez-le en ligne dès la fin de la mise à niveau.

  - Si, pour une raison ou une autre, vous devez arrêter les deux serveurs en même temps procédez comme suit lorsque l’interruption de service du pool est terminé :
    
      - Il est recommandé de redémarrer à la fois les serveurs front-end en même temps.
    
      - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leurs arrêts.
    
      - Si vous ne pouvez pas les remettre dans cet ordre, utilisez l’applet de commande suivante avant de remettre le pool à nouveau :.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires pour garantir le fonctionnement des pools

Vous devez prêter attention à deux autres facteurs pour vous assurer que vos pools frontaux restent opérationnels.

  - Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.

  - Si vous établissez une relation de jumelage entre ce pool et un autre pool à des fins de reprise après sinistre, après avoir établi la relation, vous devez vous assurer que ce pool comporte trois serveurs frontaux s’exécutant simultanément pour une synchronisation correcte. données avec le pool de sauvegarde. Pour plus d’informations sur les fonctionnalités de jumelage de pool et de récupération d’urgence, reportez-vous à la rubrique [planification d’une haute disponibilité et de récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Amélioration de la fiabilité des mises à niveau de pool

Lorsque vous avez besoin de mettre à niveau ou de mettre à jour les serveurs dans un pool frontal, suivez le flux de travail présenté dans [mettre à niveau ou mettre à jour les serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)et les instructions suivantes :

  - Lorsque vous passez d’un domaine de mise à niveau à un autre pour les mises à niveau (suivi du flux de travail lors de la [mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), vous devez utiliser l’applet de commande **Get-CsPoolUpgradeReadinessState** et vérifier l’état Ready. L’ajout d’une attente de 20 minutes entre chaque domaine de mise à niveau après avoir atteint la « prête » permettra d’améliorer la fiabilité des mises à niveau. Si ce n’est **pas** le cas, redémarrez le minuteur de 20 minutes. Par ailleurs, vous pouvez exécuter l’applet de passe **Get-CsPoolFabricState** avant et après le démarrage de l’intervalle de 20 minutes et vérifier qu’il n’y a aucune modification apportée aux principaux et aux secondaires des groupes de routage.

  - Ne passez pas au domaine de mise à niveau suivant si l’un des serveurs du dernier domaine de mise à niveau corrigé est bloqué ou n’est pas redémarré. Cela s’applique également si l’un des serveurs au sein d’une mise à niveau ne peut pas démarrer. Exécutez **Get-CsPoolFabricState** pour vous assurer que tous les groupes de routage disposent d’une adresse principale et d’au moins un secondaire ; Cela permet de vérifier si tous les utilisateurs ont un service.

  - Si certains utilisateurs ne disposent pas d’un service, exécutez **Get-CsPoolFabricState** avec l’option – verbose pour rechercher les groupes de routage pour lesquels il manque des réplicas. Ne redémarrez pas le pool entier en tant que première étape de dépannage. Pour plus d’informations sur cette cmdlet, voir [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Assurez-vous que toutes les instances des fenêtres de l’observateur d’événements ou du moniteur de performance sont fermées pour les installations/désinstallations de Windows fabric.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Modification de la configuration d’un pool frontal

Dès lors que vous ajoutez des serveurs frontaux à un pool ou que vous les supprimez de la liste, puis que vous publiez la nouvelle topologie, vous devez suivre les instructions suivantes :

  - Après la publication de la nouvelle topologie, vous devez redémarrer chaque serveur frontal du pool. Redémarrez-les un par autre.

  - Si le pool entier est arrêté lors de la modification de la configuration, exécutez l’applet de commande suivante une fois la nouvelle topologie publiée :
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Si un serveur frontal tombe en panne et est susceptible d’être remplacé pendant quelques jours ou davantage, supprimez le serveur de la topologie. Ajoutez le nouveau serveur frontal à la topologie lorsque ce dernier est disponible.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

