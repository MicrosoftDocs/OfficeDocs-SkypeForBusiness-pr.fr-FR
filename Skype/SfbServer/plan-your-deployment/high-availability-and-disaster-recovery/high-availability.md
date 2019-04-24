---
title: Haute disponibilité et gestion du pool frontal
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: En savoir plus sur la gestion de pool frontal dans Skype pour Business Server, notamment la gestion des pools, la perte de quorum et étapes spéciales pour les pools avec seulement deux serveurs frontaux.
ms.openlocfilehash: 43c8e3fffb010bf268f94970b5cca25ecee7cd58
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214074"
---
# <a name="front-end-pool-high-availability-and-management"></a>Haute disponibilité et gestion du pool frontal
 
En savoir plus sur la gestion de pool frontal dans Skype pour Business Server, notamment la gestion des pools, la perte de quorum et étapes spéciales pour les pools avec seulement deux serveurs frontaux.
  
Dans Skype pour Business Server, l’architecture des pools frontaux utilise un modèle de systèmes distribués, avec les données de chaque utilisateur conservées sur trois serveurs frontaux du pool. Il est recommandé que tous les pools frontaux Enterprise Edition incluent au moins trois serveurs frontaux. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des pools frontaux

 Skype pour Business Server utilise un modèle de systèmes distribués basé sur Windows Fabric. Dans ce modèle, les données importantes pour chaque utilisateur et de conférence sont stockées sur les trois serveurs frontaux dans un pool frontal. Ces trois serveurs stocker un ensemble de données sont calledreplicas.
  
Avec le modèle distribué pour les pools frontaux, un certain nombre de serveurs d’un pool doit être exécuté pour le pool à la fonction. Il existe deux modes de perte d’un pool.
  
- Perte de quorum au niveau du groupe de routage, provoquée par lʼinsuffisance des serveurs réplica pour un groupe de routage particulier. Un groupe de routage correspond à un ensemble dʼutilisateurs hébergés dans le pool. Chaque groupe possède trois réplicas dans le pool : un primaire et deux secondaires.
    
- Perte de quorum au niveau du pool, provoquée par une insuffisance du nombre de serveurs d’amorçage en cours d’exécution dans le pool. 
    
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
   
Chaque fois que le pool est démarré ultérieurement, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). Si ce nombre de serveurs ne peut pas être démarré (mais suffisamment de serveurs peut être démarrés afin que vous n’êtes pas à la perte de quorum au niveau du pool), vous pouvez utiliser la `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` applet de commande pour activer le pool à récupérer à partir de cette perte quorum au niveau de groupe de routage et progressent. Pour plus d’informations sur l’utilisation de cette applet de commande, voir <link Reset-CsPoolRegistrarState>.
  
> [!NOTE]
> Dans les pools disposant dʼun nombre égal de serveurs, Skype Entreprise Server utilise la base de données SQL principale. Dans un tel pool, si vous arrêtez la base de donnée principale, basculez vers la copie miroir et arrêtez suffisamment de serveurs frontaux de sorte quʼun nombre insuffisant de serveurs soient exécutés conformément au tableau précédent, le pool entier s’arrête. Pour plus d’informations, voir le [Témoin de mise en miroir de base de données](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour un pool frontal fonctionner, il ne peut pas être perte quorum au niveau du pool. Si le nombre de serveurs exécutés passe en dessous du niveau fonctionnel indiqué dans le tableau ci-après, les serveurs restants dans le pool arrêtent tous les services Skype Entreprise Server. Notez que les numéros dans le tableau suivant supposent que les serveurs principaux du pool sont en cours d’exécution.
  
|Nombre total de serveurs frontaux du pool  <br/> |Nombre de serveurs devant être exécutés pour que le pool soit opérationnel  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |2 (n’importe lesquels)  <br/> |
|5-6  <br/> |3 (n’importe lesquels)  <br/> |
|7  <br/> |4 (n’importe lesquels)  <br/> |
|8-9  <br/> |4 (n’importe lesquels parmi les 7 premiers serveurs)  <br/> |
|10-12  <br/> |5 (n’importe lesquels parmi les 9 premiers serveurs)  <br/> |
   
Dans le tableau précédent, les « premier « serveurs sont les serveurs qui ont été introduits configurer tout d’abord, dans l’ordre chronologique, lorsque le pool a été démarré pour la première fois. Pour déterminer ces serveurs, vous pouvez utiliser la `Get-CsComputer` applet de commande avec la ` -PoolFqdn` option. Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et celles en haut de la liste sont les serveurs en premier.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires pour vérifier que les pools sont opérationnels

Vous devez prêter attention à deux autres facteurs pour vous assurer que vos pools frontaux restent opérationnels.
  
- Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, veillez au moins que trois des serveurs frontaux sont en cours d’exécution.
    
- Si vous établissez une relation couplée entre ce pool et un autre pour pouvoir bénéficier de la récupération après incident, puis qu’une fois cette relation établie, vous devez vérifier que ce pool contient trois serveurs frontaux étant simultanément en cours d’exécution à un moment précis pour synchroniser correctement vos données avec le pool de sauvegarde. Pour plus d’informations sur les fonctionnalités de récupération d’urgence et de jumelage de pool, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool frontal avec deux serveurs frontaux

Il n’est pas recommandé de déployer un pool frontal qui contient seulement deux serveurs frontaux. En effet, ce petit pool ne fournit pas une solution fiable à haute disponibilité comme le ferait un pool plus grand et il nécessite une gestion plus précautionneuse. En outre, si le serveur principal d’un pool de deux serveurs s’est arrêté, le pool entier lui-même bientôt fera probablement vers le bas ainsi. Si vous souhaitez déployer une ou deux serveurs Skype pour Business Server, nous vous recommandons de que les déployer en tant que serveurs Standard Edition Server.
  
Si vous avez jamais besoin déployer un pool avec deux serveurs frontaux, procédez comme suit :
  
- Si un des serveurs frontaux deux tombe en panne, il est conseillé de rétablir le serveur en panne dès que possible. De même, si vous devez mettre à niveau l’un de ces serveurs, remettez-le en ligne dès la fin de la mise à niveau.
    
- Si, pour une raison ou une autre, vous devez arrêter les deux serveurs en même temps procédez comme suit lorsque l’interruption de service du pool est terminé :
    
  - La meilleure pratique consiste à redémarrer les deux serveurs frontaux en même temps. 
    
  - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leurs arrêts.
    
  - Si vous ne pouvez pas les rétablir dans cet ordre, utilisez la cmdlet suivante avant de mettre le pool de sauvegarde :`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Défaillances et modifications de la configuration du pool frontal

Si un serveur frontal rencontre une défaillance et ne peut pas être remplacé avant plusieurs jours, supprimez ce serveur de la topologie. Rajoutez-le à la topologie dès qu’il est de nouveau disponible.
  
Lorsque vous modifiez la configuration dʼun pool frontal, comme en cas d’ajout ou de suppression des serveurs, vous devez suivre la procédure suivante :
  
- Après avoir publié la nouvelle topologie, vous devez redémarrer chaque serveur dans le pool. Redémarrez-les un par autre.
    
- Si l’intégralité du pool a été enfoncée lors de la modification de configuration, puis exécutez la cmdlet suivante une fois la nouvelle topologie est publiée :`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

