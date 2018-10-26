---
title: "Lync Server 2013 : Top. et comp. util. pr serv. frontaux, mess. Inst. et prés."
TOCTitle: Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412996(v=OCS.15)
ms:contentKeyID: 49299285
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Les seuls composants requis pour la messagerie instantanée et la présence sont :

  - Les serveurs frontaux et ou Standard Edition Server de votre organisation. Les fonctionnalités de messagerie instantanée et de présence sont toujours activées sur ces serveurs.

  - Un programme d’équilibrage de la charge, si vous avez un pool de serveurs frontauxEnterprise Edition. Pour plus d’informations, reportez-vous à [Configuration requise pour l’équilibrage de charge dans Lync Server 2013](lync-server-2013-load-balancing-requirements.md).

## Planification du déploiement des pools frontaux

Dans Lync Server 2013, l’architecture de pool de serveurs frontaux a été modifiée, et ces modifications affectent la méthode de planification et de maintenance de votre pools de serveurs frontaux.

Nous vous recommandons de faire en sorte que vos pools de serveurs frontauxEnterprise Edition incluent au moins trois serveurs frontaux. Dans Lync Server, l’architecture de pools de serveurs frontaux utilise un modèle de systèmes distribués, où les données de chaque utilisateur sont conservées sur trois serveurs frontaux dans le pool. Pour plus d’informations sur cette nouvelle architecture, reportez-vous à [Modifications de la topologie dans Lync Server 2013](lync-server-2013-topology-changes.md).

Si vous ne souhaitez pas déployer trois serveurs frontauxEnterprise Edition tout en voulant bénéficier d’une récupération d’urgence, nous vous recommandons d’utiliser Lync ServerStandard Edition et de créer deux pools dotés d’une relation de sauvegarde couplée. Celle-ci fournit une solution de récupération d’urgence avec seulement deux serveurs. Pour plus d’informations sur les topologies et les fonctionnalités de haute disponibilité et de récupération d’urgence, voir [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Planification de la gestion des pools frontaux

Pour les pools de serveurs frontaux, suivez les instructions données dans cette section.

## Vérifier que les pools sont opérationnels

Avec le nouveau modèle distribué pour les pools de serveurs frontaux, certains serveurs d’un pool doivent être en cours d’exécution pour que le pool fonctionne. Il existe deux modes de perte pour un pool :

  - Perte de quorum au niveau du groupe de routage, provoquée par une insuffisance du nombre de serveurs réplicas dans un groupe de routage particulier. Un groupe de routage est un regroupement d’un ensemble d’utilisateurs hébergés dans le pool. Chaque groupe de routage possède trois réplicas dans le pool : un primaire et deux secondaires.

  - Perte de quorum au niveau du pool, provoquée par une insuffisance du nombre de serveurs d’amorçage en cours d’exécution dans le pool.

## Perte de quorum au niveau du groupe de routage

Lors du premier démarrage d’un nouveau pool de serveurs frontaux, il est primordial que 85 % des serveurs soient opérationnels, comme indiqué dans le tableau ci-après. Si un pourcentage inférieur de serveurs est en cours d’exécution, les services risquent de rester bloqués dans leur état de démarrage et le pool risque de ne pas démarrer.


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
<td><p>2</p></td>
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
<td><p>8</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>9</p></td>
<td><p>7</p></td>
</tr>
<tr class="odd">
<td><p>10</p></td>
<td><p>8</p></td>
</tr>
<tr class="even">
<td><p>11</p></td>
<td><p>9</p></td>
</tr>
<tr class="odd">
<td><p>12</p></td>
<td><p>10</p></td>
</tr>
</tbody>
</table>


Chaque fois que le pool est démarré ultérieurement, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). S’il n’est pas possible de démarrer ce nombre de serveurs (mais que suffisamment de serveurs peuvent être démarrés pour éviter une perte de quorum au niveau du pool), vous pouvez utiliser l’applet de commande **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** pour permettre au pool de récupérer de cette perte de quorum au niveau du groupe de routage afin d’avancer. Pour plus d’informations sur la manière d’utiliser cette applet de commande, voir [Reset-CsPoolRegistrarState](https://docs.microsoft.com/en-us/powershell/module/skype/Reset-CsPoolRegistrarState).

> [!NOTE]  
> Comme Lync Server utilise la base de données SQL principale comme témoin, si vous fermez la base de données principale pour basculer sur la copie Miroir, puis arrêtez suffisamment de serveurs frontaux pour qu’un nombre insuffisant soit en cours d’exécution comme indiqué dans le tableau précédent, le pool tout entier s’arrête. Pour plus d’informations, voir <a href="http://go.microsoft.com/fwlink/?linkid=393672">Témoin de mise en mémoire de base de données</a>.

## Perte de quorum au niveau du pool

Pour qu’un pool de serveurs frontaux fonctionne, il ne peut pas être en perte de quorum au niveau du pool. Si le nombre de serveurs en cours d’exécution passe en dessous du niveau fonctionnel indiqué dans le tableau ci-après, les serveurs restants dans le pool arrêtent tous les services Lync Server. Notez que les nombres indiqués dans le tableau ci-après présupposent que les serveurs principaux dans le pool sont en cours d’exécution.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre total de serveurs frontaux dans le pool</th>
<th>Nombre de serveurs devant être exécutés pour que le pool soit opérationnel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
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


Dans le tableau précédent, les « premiers serveurs » sont les serveurs qui ont été proposés en premier, chronologiquement, lors du premier démarrage du pool. Pour déterminer ces serveurs, vous pouvez utiliser l’applet de commande **Get-CsComputer** avec l’option **–PoolFqdn**. Cette applet de commande indique les serveurs dans leur ordre d’apparition dans la topologie, et ceux qui figurent au début de la liste sont les premiers serveurs.

## Pools frontaux avec deux serveurs frontaux

Nous ne recommandons pas le déploiement d’un pool frontal contenant uniquement deux serveurs frontaux. Cependant, si vous devez déployer un tel pool, procédez comme suit :

  - Si l’un des deux serveurs frontaux est arrêté, vous devriez essayer de le redémarrer aussi vite que possible. De même, si vous devez mettre à niveau l’un de ces serveurs, remettez-le en ligne dès la fin de la mise à niveau.

  - Si, pour une raison ou une autre, vous devez arrêter les deux serveurs en même temps procédez comme suit lorsque l’interruption de service du pool est terminé :
    
      - La meilleure pratique consiste à redémarrer les deux serveurs frontaux en même temps.
    
      - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leurs arrêts.
    
      - Si vous ne pouvez pas les rétablir dans cet ordre, utilisez l’applet de commande suivante avant de rétablir le pool :
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

## Étapes supplémentaires pour vérifier que les pools sont opérationnels

Vous devez prêter attention à deux autres facteurs pour veiller à ce que vos pools de serveurs frontaux restent opérationnels.

  - Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, vérifiez qu’au moins trois serveurs frontaux sont en cours d’exécution.

  - Si vous établissez une relation couplée entre ce pool et un autre pour pouvoir bénéficier de la récupération après incident, puis qu’une fois cette relation établie, vous devez vérifier que ce pool contient trois serveurs frontaux étant simultanément en cours d’exécution à un moment précis pour synchroniser correctement vos données avec le pool de sauvegarde. Pour plus d’informations sur les fonctionnalités de couplage de pools et de récupération après incident, reportez-vous à [Planification de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).

## Amélioration de la fiabilité des mises à niveau de pools

Quand vous avez besoin d’appliquer des mises à niveau ou des correctifs aux serveurs dans un pool de serveurs frontaux, suivez le flux de travail indiqué dans [Mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), ainsi que les instructions ci-après :

  - Quand vous passez d’un domaine de mise à niveau à un autre (en suivant le flux de travail précisé dans [Mise à niveau ou mise à jour des serveurs frontaux dans Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), vous utilisez l’applet de commande **Get-CsPoolUpgradeReadinessState** et recherchez l’état Ready. Ajoutez une attente de 20 minutes entre chaque domaine de mise à niveau une fois l’état Ready atteint pour rendre les mises à niveau plus fiables. Si l’état passe à **Not Ready** au cours de ces 20 minutes, redémarrez le délai de 20 minutes. De plus, vous pouvez exécuter l’applet de commande **Get-CsPoolFabricState** avant et après le démarrage du délai de 20 minutes pour vérifier qu’aucune modification n’a été apportée aux primaires et secondaires des groupes de routage.

  - Ne passez pas au domaine de mise à niveau suivant si l’un des serveurs inclus dans le dernier domaine de mise à niveau avec correctifs est bloqué ou n’a pas redémarré. Cela s’applique également si l’un des serveurs inclus dans une mise à niveau ne parvient pas à redémarrer. Exécutez **Get-CsPoolFabricState** pour vérifier que tous les groupes de routage ont un primaire et au moins un secondaire. Cela permet de confirmer si tous les utilisateurs disposent du service.

  - Si certains utilisateurs disposent du service et pas d’autres, exécutez **Get-CsPoolFabricState** avec l’option –Verbose pour rechercher les groupes de routage dans lesquels il manque des réplicas. Ne redémarrez pas tout le pool à titre de première étape de résolution du problème. Pour plus d’informations sur cette applet de commande, voir [Get-CsPoolFabricState](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPoolFabricState).

  - Vérifiez que toutes les instances des fenêtres Observateur d’événements ou Analyseur de performances sont fermées pour les installations/désinstallations de Windows Fabric.

## Modification de la configuration d’un pool frontal

Que vous ajoutiez ou supprimiez des serveurs frontaux d’un pool avant de publier une nouvelle topologie, procédez comme suit :

  - Une fois la nouvelle topologie publiée, vous devez redémarrer chaque serveur frontal dans le pool. Redémarrez-les un par un.

  - Si l’intégralité du pool est arrêté durant la modification de la configuration, exécutez l’applet de commande suivante une fois la nouvelle topologie publiée :
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

Si un serveur frontal ne fonctionne pas et que vous ne pouvez pas le remplacer avant plusieurs jours, supprimez ce serveur de la topologie. Lorsque le serveur sera de nouveau disponible, rajoutez-le à la topologie.

