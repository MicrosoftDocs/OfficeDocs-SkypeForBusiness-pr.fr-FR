---
title: Haute disponibilité et gestion du pool frontal
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Obtenir des informations sur la gestion de pool de Front-End dans Skype pour Business Server, notamment la gestion des pools, la perte du quorum et des mesures spéciales pour les pools avec seulement deux serveurs frontaux.
ms.openlocfilehash: f348fcc4fee6a48a41265da88fe432d9e4550b6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-high-availability-and-management"></a>Haute disponibilité et gestion du pool frontal
 
Obtenir des informations sur la gestion de pool de Front-End dans Skype pour Business Server, notamment la gestion des pools, la perte du quorum et des mesures spéciales pour les pools avec seulement deux serveurs frontaux.
  
Dans Skype pour le serveur de l’entreprise, l’architecture de pools de Front-End utilise un modèle de systèmes distribués avec les données de chaque utilisateur sur trois serveurs Front-End dans le pool. Nous conseillons d’incluent au moins trois serveurs frontaux tous vos pools Enterprise Edition Front-End. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des pools frontaux

 Skype pour Business Server utilise un modèle de systèmes distribués basé sur Fabric de Windows. Dans ce modèle, les données importantes pour chaque utilisateur et de la conférence sont stockées sur trois serveurs frontaux dans un pool frontal. Ces trois serveurs stockant un ensemble de données sont calledreplicas.
  
Avec le modèle distribué pour les pools de Front-End, un certain nombre de serveurs d’un pool doit exécuter pour le pool de la fonction. Il existe deux modes de perte d’un pool.
  
- Routage perte de quorum de niveau groupe, provoqué par des serveurs de réplicas n’est pas suffisant pour un groupe de routage particulier. Un groupe de routage correspond à un ensemble dʼutilisateurs hébergés dans le pool. Chaque groupe possède trois réplicas dans le pool : un primaire et deux secondaires.
    
- Perte de quorum au niveau pool, a provoqué lorsque pas suffisamment semences de serveurs sont en cours d’exécution dans le pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perte de quorum au niveau du groupe de routage

Lors du premier démarrage d’un nouveau nouveau pool frontal, il est primordial que 85 % des serveurs soient opérationnels, comme indiqué dans le tableau ci-après. Si un pourcentage inférieur de serveurs est en cours d’exécution, les services risquent de rester bloqués dans leur état de démarrage et le pool risque de ne pas démarrer.
  
|Nombre total de serveurs dans le pool  <br/> |Nombre de serveurs devant être en cours d’exécution pour que le pool démarre la première fois  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|8  <br/> |6  <br/> |
|9  <br/> |7  <br/> |
|10  <br/> |8  <br/> |
|11  <br/> |9  <br/> |
|12  <br/> |10  <br/> |
   
Chaque fois que le pool est démarré ultérieurement, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). Si ce nombre de serveurs ne peut pas être démarré (mais suffisamment de serveurs peut être démarré pour que vous n’êtes pas à la perte de quorum d’au niveau du pool), vous pouvez utiliser la `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` applet de commande pour activer le pool à récupérer à partir de cette perte de quorum au niveau groupe de routage et de progresser. Pour plus d’informations sur l’utilisation de cette applet de commande, voir <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> Dans les pools disposant dʼun nombre égal de serveurs, Skype Entreprise Server utilise la base de données SQL principale. Dans un tel pool, si vous arrêtez la base de donnée principale, basculez vers la copie miroir et arrêtez suffisamment de serveurs frontaux de sorte quʼun nombre insuffisant de serveurs soient exécutés conformément au tableau précédent, le pool entier s’arrête. Pour plus d’informations, consultez [Témoin de la mise en miroir de base de données](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour un pool frontal fonctionner du tout, il ne peut pas être perte de quorum d’au niveau du pool. Si le nombre de serveurs exécutés passe en dessous du niveau fonctionnel indiqué dans le tableau ci-après, les serveurs restants dans le pool arrêtent tous les services Skype Entreprise Server. Notez que les nombres dans le tableau ci-dessous supposent que les serveurs principaux de retour dans le pool sont en cours d’exécution.
  
|Nombre total de serveurs frontaux dans le pool  <br/> |Nombre de serveurs devant être exécutés pour que le pool soit opérationnel  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |2 (n’importe lesquels)  <br/> |
|5-6  <br/> |3 (n’importe lesquels)  <br/> |
|7  <br/> |4 (n’importe lesquels)  <br/> |
|8-9  <br/> |4 (n’importe lesquels parmi les 7 premiers serveurs)  <br/> |
|10-12  <br/> |5 (n’importe lesquels parmi les 9 premiers serveurs)  <br/> |
   
Dans le tableau précédent, « premiers serveurs » sont les serveurs qui ont été soulevés tout d’abord, dans l’ordre chronologique, lorsque le pool a été démarré pour la première fois. Pour déterminer ces serveurs, vous pouvez utiliser la `Get-CsComputer` applet de commande avec la ` -PoolFqdn` option. Cette applet de commande affichera les serveurs dans l’ordre où elles apparaissent dans la topologie, et celles du haut de la liste sont les premiers serveurs.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires pour vérifier que les pools sont opérationnels

Vous devez prêter attention à deux autres facteurs pour vous assurer que vos pools frontaux restent opérationnels.
  
- Lorsque vous déplacez des utilisateurs à la liste pour la première fois, veillez au moins que trois des serveurs frontaux sont en cours d’exécution.
    
- Si vous établissez une relation couplée entre ce pool et un autre pour pouvoir bénéficier de la récupération après incident, puis qu’une fois cette relation établie, vous devez vérifier que ce pool contient trois serveurs frontaux étant simultanément en cours d’exécution à un moment précis pour synchroniser correctement vos données avec le pool de sauvegarde. Pour plus d’informations sur les fonctionnalités de récupération de couplage et de reprise après sinistre pool, voir [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool frontal avec deux serveurs frontaux

Nous ne recommandons pas le déploiement d’un pool frontal qui contient uniquement deux serveurs frontaux. En effet, ce petit pool ne fournit pas une solution fiable à haute disponibilité comme le ferait un pool plus grand et il nécessite une gestion plus précautionneuse. En outre, si le serveur principal d’un pool de deux serveurs tombait en panne, le pool entier lui-même bientôt fera probablement vers le bas ainsi. Si vous souhaitez déployer une ou deux serveurs Skype pour Business Server, nous vous recommandons de que les déployer en tant que serveurs Standard Edition Server.
  
Si vous avez jamais besoin de déployer un pool avec deux serveurs frontaux, suivez ces instructions :
  
- Si un des deux serveurs frontaux tombe en panne, vous devez tenter de mettre le serveur défaillant sauvegarder dès que possible. De même, si vous devez mettre à niveau l’un de ces serveurs, remettez-le en ligne dès la fin de la mise à niveau.
    
- Si, pour une raison ou une autre, vous devez arrêter les deux serveurs en même temps procédez comme suit lorsque l’interruption de service du pool est terminé :
    
  - La meilleure solution consiste à redémarrer les deux serveurs frontaux en même temps. 
    
  - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leurs arrêts.
    
  - Si vous ne pouvez pas rétablir dans cet ordre, utilisez l’applet de commande suivant avant de mettre le pool de sauvegarde :`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Défaillances et modifications de la configuration du pool frontal

Si un serveur frontal rencontre une défaillance et ne peut pas être remplacé avant plusieurs jours, supprimez ce serveur de la topologie. Rajoutez-le à la topologie dès qu’il est de nouveau disponible.
  
Lorsque vous modifiez la configuration dʼun pool frontal, comme en cas d’ajout ou de suppression des serveurs, vous devez suivre la procédure suivante :
  
- Après avoir publié la nouvelle topologie, vous devez redémarrer chaque serveur dans le pool. Redémarrez-les un par autre.
    
- Si l’ensemble du pool a été enfoncée lors de la modification de configuration, puis exécutez l’applet de commande suivant après la publication de la nouvelle topologie :`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

