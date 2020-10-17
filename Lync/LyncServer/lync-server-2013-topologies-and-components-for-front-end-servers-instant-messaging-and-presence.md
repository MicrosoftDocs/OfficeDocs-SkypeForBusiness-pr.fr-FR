---
title: 'Lync Server 2013 : topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence'
description: 'Lync Server 2013 : topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence.'
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
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550290"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Topologies et composants pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-24_

Les seuls composants requis pour la messagerie instantanée et la présence sont les suivants :

  - Les serveurs frontaux ou les serveurs Standard Edition de votre organisation. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs.

  - Un équilibreur de charge, si vous disposez d’un pool frontal Enterprise Edition. Pour plus d’informations, reportez-vous à [Load Balancing Requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a>Planification du déploiement des pools frontaux

Dans Lync Server 2013, l’architecture de pool frontal a changé et les modifications apportées affectent la planification et la gestion de vos pools frontaux.

Nous recommandons que tous les pools frontaux Enterprise Edition incluent au moins trois serveurs frontaux. Dans Lync Server, l’architecture des pools frontaux utilise un modèle de systèmes distribués, les données de chaque utilisateur étant conservées sur trois serveurs frontaux dans le pool. Pour plus d’informations sur cette nouvelle architecture, consultez la rubrique [modifications de la topologie dans Lync Server 2013](lync-server-2013-topology-changes.md).

Si vous ne souhaitez pas déployer trois serveurs frontaux Enterprise Edition et que vous souhaitez une récupération d’urgence, nous vous recommandons d’utiliser Lync Server Standard Edition et de créer deux pools avec une relation de sauvegarde couplée. Cette opération fournit une solution de récupération d’urgence avec seulement deux serveurs. Pour plus d’informations sur les topologies et les fonctionnalités de haute disponibilité et de récupération d’urgence, reportez-vous à la rubrique [planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des pools frontaux

Pour les pools frontaux, suivez les instructions de cette section.

<div>

## <a name="ensuring-that-pools-are-functional"></a>Vérifier que les pools sont fonctionnels

Avec le nouveau modèle distribué pour les pools frontaux, certains numéros des serveurs d’un pool doivent être en cours d’exécution pour que le pool fonctionne. Il existe deux modes de perte pour un pool

  - Perte de quorum au niveau du groupe de routage, causée par des serveurs de réplication insuffisants pour un groupe de routage particulier. Un groupe de routage est une agrégation d’un ensemble d’utilisateurs hébergés dans le pool. Chaque groupe de routage dispose de trois réplicas dans le pool : un principal et deux secondaires.

  - Perte de quorum au niveau du pool, provoqué lorsque le pool ne comporte pas suffisamment de serveurs d’amorçage.

<div>

## <a name="routing-group-level-quorum-loss"></a>Perte de quorum au niveau du groupe de routage

La première fois que vous démarrez un nouveau pool frontal, il est essentiel que 85% des serveurs soient opérationnels, comme indiqué dans le tableau suivant. Si le nombre de serveurs en cours d’exécution est moindre, les services peuvent être bloqués dans l’état de démarrage et le pool peut ne pas démarrer.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs dans le pool</th>
<th>Nombre de serveurs qui doivent être en cours d’exécution pour que le pool démarre pour la première fois</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>n°2</p></td>
<td><p>0,1</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>3</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>4 </p></td>
</tr>
<tr class="odd">
<td><p>6 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>5 </p></td>
</tr>
<tr class="odd">
<td><p>8 </p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>9 </p></td>
<td><p>7 </p></td>
</tr>
<tr class="odd">
<td><p>10 </p></td>
<td><p>8 </p></td>
</tr>
<tr class="even">
<td><p>a4</p></td>
<td><p>9 </p></td>
</tr>
<tr class="odd">
<td><p>12 </p></td>
<td><p>10 </p></td>
</tr>
</tbody>
</table>


Chaque fois que le pool est démarré, 85% des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). Si ce nombre de serveurs ne peut pas être démarré (mais que les serveurs peuvent être démarrés de manière à ne pas être au même niveau que la perte de quorum au niveau du pool), vous pouvez utiliser l’applet de commande **Reset-CsPoolRegistrarState – ResetType QuorumLossRecovery** pour permettre au pool de récupérer à partir de cette perte de quorum au niveau du groupe de routage et de progresser. Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).

<div>


> [!NOTE]  
> Étant donné que Lync Server utilise la base de données SQL principale comme témoin, si vous arrêtez la base de données principale et basculez vers la copie miroir, et que vous arrêtez suffisamment de serveurs frontaux pour qu’ils soient insuffisants en fonction du tableau précédent, le pool entier sera inactif. Pour plus d’informations, voir <A href="https://go.microsoft.com/fwlink/?linkid=393672">témoin de mise en miroir de bases de données</A>.



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour qu’un pool frontal fonctionne du tout, il ne peut pas faire l’objets d’une perte de quorum au niveau du pool. Si le nombre de serveurs en cours d’exécution tombe en dessous du niveau fonctionnel, comme indiqué dans le tableau suivant, les autres serveurs du pool arrêtent tous les services Lync Server. Notez que les chiffres du tableau suivant partent du principe que les serveurs principaux du pool sont en cours d’exécution.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs frontaux dans le pool</th>
<th>Nombre de serveurs devant s’exécuter pour que le pool soit opérationnel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>n°2</p></td>
<td><p>0,1</p></td>
</tr>
<tr class="even">
<td><p>3-4</p></td>
<td><p>Any 2</p></td>
</tr>
<tr class="odd">
<td><p>5-6</p></td>
<td><p>Any 3</p></td>
</tr>
<tr class="even">
<td><p>7 </p></td>
<td><p>N’importe quel 4</p></td>
</tr>
<tr class="odd">
<td><p>8-9</p></td>
<td><p>Un 4 des 7 premiers serveurs</p></td>
</tr>
<tr class="even">
<td><p>10-12</p></td>
<td><p>Un 5 des premiers serveurs</p></td>
</tr>
</tbody>
</table>


Dans le tableau précédent, les « premiers serveurs » sont les serveurs qui ont été mis en avant pour la première fois, de façon chronologique, au moment du premier démarrage du pool. Pour déterminer ces serveurs, vous pouvez utiliser la cmdlet **Get-CsComputer** avec l’option **– PoolFqdn** . Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et ceux en haut de la liste sont les premiers serveurs.

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a>Pools frontaux avec deux serveurs frontaux

Nous vous déconseillons de déployer un pool frontal qui ne contient que deux serveurs frontaux. Si vous devez déployer un tel pool, suivez les instructions ci-dessous :

  - Si l’un des deux serveurs frontaux tombe en panne, vous devez essayer de le remettre dès que possible. De même, si vous devez mettre à niveau l’un des deux serveurs, remettez-le en ligne dès que la mise à niveau est terminée.

  - Si, pour une raison quelconque, vous devez mettre les deux serveurs en même temps, procédez comme suit lorsque le temps d’arrêt du pool est terminé :
    
      - La meilleure pratique consiste à redémarrer les deux serveurs frontaux en même temps.
    
      - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leur ordre d’arrêt.
    
      - Si vous ne pouvez pas les rétablir dans cet ordre, utilisez l’applet de commande suivante avant de rétablir le pool :.
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires permettant de s’assurer que les pools sont fonctionnels

Vous devez surveiller deux autres facteurs afin de vous assurer que vos pools frontaux demeurent fonctionnels.

  - Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.

  - Si vous établissez une relation de jumelage entre ce pool et un autre pool à des fins de récupération d’urgence, après avoir établi cette relation, vous devez vous assurer que ce pool dispose de trois serveurs frontaux exécutés simultanément à un moment donné pour synchroniser correctement les données avec le pool de sauvegarde. Pour plus d’informations sur les paires de pools et les fonctionnalités de récupération d’urgence, voir [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a>Amélioration de la fiabilité des mises à niveau de pool

Lorsque vous devez mettre à niveau ou appliquer des correctifs aux serveurs dans un pool frontal, suivez le flux de travail indiqué dans [Upgrade ou Update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), ainsi que les instructions suivantes :

  - Lorsque vous passez d’un domaine de mise à niveau à un autre pour les mises à niveau (après le flux de travail à la [mise à niveau ou la mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), vous allez utiliser la cmdlet **Get-CsPoolUpgradeReadinessState** et vérifier que l’État est prêt. L’ajout d’une attente de 20 minutes entre chaque domaine de mise à niveau après avoir atteint « prêt » rendra les mises à niveau plus fiables. S’il **n’est pas prêt** pendant cette période de 20 minutes, redémarrez le minuteur de 20 minutes. Vous pouvez également exécuter la cmdlet **Get-applet cspoolfabricstate ne** avant et après le début de l’intervalle de 20 minutes et vous assurer qu’aucune modification n’est apportée aux principaux et aux secondaires des groupes de routage.

  - Ne passez pas au domaine de mise à niveau suivant si l’un des serveurs du dernier domaine de mise à niveau corrigé est bloqué ou ne redémarre pas. Cela s’applique également si l’un des serveurs au sein d’une mise à niveau ne peut pas démarrer. Exécutez **Get-applet cspoolfabricstate ne** pour vous assurer que tous les groupes de routage ont un principal et au moins un secondaire ; Cela permet de vérifier si tous les utilisateurs disposent d’un service.

  - Si certains utilisateurs ont un service et d’autres non, exécutez **Get-applet cspoolfabricstate ne** avec l’option – verbose pour vérifier les groupes de routage qui ont des réplicas manquants. Ne redémarrez pas l’intégralité du pool en tant que première étape de dépannage. Pour plus d’informations sur cette applet de commande, consultez la rubrique [Get-applet cspoolfabricstate ne](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).

  - Assurez-vous que toutes les instances des fenêtres de l’observateur d’événements ou de l’analyseur de performances sont fermées pour les installations/désinstallations de Windows fabric.

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a>Modification de la configuration d’un pool frontal

Chaque fois que vous ajoutez des serveurs frontaux à un pool, ou que vous les supprimez du pool, puis que vous publiez la nouvelle topologie, suivez ces instructions :

  - Une fois la nouvelle topologie publiée, vous devez redémarrer chaque serveur frontal dans le pool. Redémarrez-les une à la fois.

  - Si le pool entier est inactif lors de la modification de la configuration, exécutez l’applet de commande suivante après la publication de la nouvelle topologie :
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Si un serveur frontal tombe en panne et qu’il n’est probablement pas remplacé pendant quelques jours ou plus, supprimez le serveur de la topologie. Ajoutez le nouveau serveur frontal à la topologie lorsqu’il est de nouveau disponible.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

