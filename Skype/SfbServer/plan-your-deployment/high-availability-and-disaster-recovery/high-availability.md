---
title: Haute disponibilité et gestion du pool frontal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Découvrez la gestion des pools frontux dans Skype Entreprise Server, notamment la gestion des pools, la perte de quorum et les étapes spéciales pour les pools avec seulement deux serveurs frontux.
ms.openlocfilehash: 5d9eef2a027131db960b05508ece28cf95b992dc
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737680"
---
# <a name="front-end-pool-high-availability-and-management"></a>Haute disponibilité et gestion du pool frontal
 
Découvrez la gestion des pools frontux dans Skype Entreprise Server, notamment la gestion des pools, la perte de quorum et les étapes spéciales pour les pools avec seulement deux serveurs frontux.
  
Dans Skype Entreprise Server, l’architecture des pools frontaux utilise un modèle de systèmes distribués, avec les données de chaque utilisateur conservées sur jusqu’à trois serveurs frontaux dans le pool. Il est recommandé que tous vos pools front Êdition Entreprise comprennent au moins trois serveurs frontux.

> [!NOTE]
> Skype Entreprise Server 2019 ne prend pas en charge les pools front Êdition Entreprise avec deux serveurs frontux et n’autorise pas la publication de la topologie dans ce scénario.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des pools frontux

 Skype Entreprise Server utilise un modèle de systèmes distribués basé sur Windows Fabric. Dans ce modèle, les données importantes pour chaque utilisateur et conférence sont stockées sur trois serveurs frontux dans un pool frontal. Ces trois serveurs stockant un certain ensemble de données sont appelés « réplicas ».
  
Avec le modèle distribué pour les pools frontux, un certain nombre de serveurs d’un pool doit être en cours d’exécution pour que le pool fonctionne. Il existe deux modes de perte pour un pool.
  
- Perte de quorum au niveau du groupe de routage, due à un nombre insuffisant de serveurs réplicas pour un groupe de routage particulier. Un groupe de routage est un ensemble d’utilisateurs homed dans le pool. Chaque groupe de routage possède trois réplicas dans le pool : un réplica principal et deux réplicas secondaires.
    
- Perte de quorum au niveau du pool, provoquée par un nombre insuffisant de serveurs d’amorçage en cours d’exécution dans le pool. 
    
### <a name="routing-group-level-quorum-loss"></a>Perte de quorum au niveau du groupe de routage

La première fois que vous démarrez un nouveau pool frontal, il est essentiel que 85 % des serveurs soient opérationnels, comme indiqué dans le tableau suivant. Si moins de serveurs sont en cours d’exécution, les services peuvent être bloqués à l’état de départ et le pool risque de ne pas démarrer.
  
|Nombre total de serveurs dans le pool  <br/> |Nombre de serveurs devant être en cours d’exécution pour que le pool soit démarré pour la première fois  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4   <br/> |3  <br/> |
|5  <br/> |4   <br/> |
|6   <br/> |5  <br/> |
|7   <br/> |5  <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10  <br/> |8   <br/> |
|11  <br/> |9   <br/> |
|12   <br/> |10  <br/> |
|16 **pour Skype Entreprise Server 2019** <br/> |12   <br/> |


   
Chaque fois que le pool est démarré, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). Si ce nombre de serveurs ne peut pas être démarré (mais que suffisamment de serveurs peuvent être démarrés afin de ne pas être en perte de quorum au niveau du pool), vous pouvez utiliser la cmdlet pour permettre au pool de récupérer de cette perte de quorum au niveau du groupe de routage et  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` d’avancer. Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> Dans les pools avec un nombre de serveurs Skype Entreprise Server utilise la base de données SQL comme témoin. Dans un pool comme celui-ci, si vous fermez la base de données principale et que vous basculez vers la copie miroir, et que vous fermez suffisamment de serveurs frontux afin que suffisamment de serveurs ne fonctionnent pas en fonction du tableau précédent, tout le pool est arrêté. Pour plus d’informations, [voir Témoin de mise en miroir de bases de données.](/sql/database-engine/database-mirroring/database-mirroring-witness) 
  
#### <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour qu’un pool frontal fonctionne, il ne peut pas se trouver dans une perte de quorum au niveau du pool. Si le nombre de serveurs en cours d’exécution est inférieur au niveau fonctionnel indiqué dans le tableau suivant, les serveurs restants du pool arrêteront tous les services Skype Entreprise Server serveur. Notez que les nombres du tableau suivant supposent que les serveurs du pool sont en cours d’exécution.
  
|Nombre total de serveurs frontaux dans le pool  <br/> |Nombre de serveurs devant s’exécuter pour que le pool soit opérationnel  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |N’importe quel 2  <br/> |
|5-6  <br/> |N’importe quel 3  <br/> |
|7   <br/> |N’importe quel 4  <br/> |
|8-9  <br/> |4 des 7 premiers serveurs  <br/> |
|10-12  <br/> |5 des 9 premiers serveurs  <br/> |
|12-16 **pour Skype Entreprise Server 2019**  <br/> |7 des 12 premiers serveurs  <br/> |
   
Dans le tableau précédent, les « premiers serveurs » sont les serveurs qui ont été élevés en premier, dans l’ordre chronologique, lorsque le pool a été démarré pour la première fois. Pour déterminer ces serveurs, vous pouvez utiliser la  `Get-CsComputer` cmdlet avec `-PoolFqdn` l’option. Cette applet de commande affiche les serveurs dans l’ordre où ils apparaissent dans la topologie, et ceux en haut de la liste sont les premiers serveurs.
  
> [!IMPORTANT]
> Le nombre maximal de serveurs frontux a été augmenté jusqu’à 16 [Skype Entreprise Server 2019](../../../SfBServer2019/plan/user-model-2019.md)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires pour s’assurer que les pools sont fonctionnels

Vous devez surveiller quelques autres facteurs pour vous assurer que vos pools frontaux restent fonctionnels.
  
- Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.
    
- Si vous établissez une relation de jumelage entre ce pool et un autre pool à des fins de récupération d’urgence, après avoir établi cette relation, vous devez vous assurer que ce pool dispose de trois serveurs frontaux en cours d’exécution simultanément à un moment donnée pour synchroniser correctement les données avec le pool de sauvegarde. Pour plus d’informations sur les fonctionnalités de jumelage de pool et de récupération d’urgence, voir Planifier la haute disponibilité et la récupération d’urgence [dans Skype Entreprise Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool frontal avec deux serveurs frontux

Nous vous déconseillons de déployer un pool frontal qui ne contient que deux serveurs frontux. Ce petit pool ne fournit pas de solution de haute disponibilité robuste comme le ferait un pool plus important et nécessite une attention supplémentaire en ce qui a été fait. En outre, si le serveur principal d’un pool à deux serveurs est en panne, il est probable que l’intégralité du pool proprement dit soit bientôt également en panne. Si vous souhaitez déployer un ou deux serveurs exécutant Skype Entreprise Server, nous vous recommandons de les déployer en tant que Édition Standard serveurs.
  
Si vous avez besoin de déployer un pool avec deux serveurs frontux, suivez les instructions suivantes :
  
- Si l’un des deux serveurs frontux est en panne, essayez de le faire revenir en panne dès que possible. De même, si vous devez mettre à niveau l’un des deux serveurs, le remettre en ligne dès que la mise à niveau est terminée.
    
- Si, pour une raison quelconque, vous devez mettre les deux serveurs en panne en même temps, à l’issue du temps d’arrêt du pool, faites les choses suivantes :
    
  - La meilleure pratique consiste à redémarrer les deux serveurs frontux en même temps. 
    
  - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les faire revenir dans l’ordre inverse de l’ordre dans le sens où ils ont été arrêtés.
    
  - Si vous ne pouvez pas les faire revenir dans cet ordre, utilisez l’cmdlet suivante avant de faire revenir le pool :  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Échecs et modifications de configuration du pool frontal

Si un serveur frontal tombe en panne et qu’il est peu probable qu’il soit remplacé pendant quelques jours ou plus, supprimez-le de la topologie. Ajoutez le nouveau serveur frontal à la topologie lorsqu’il est de nouveau disponible.
  
Chaque fois que vous modifiez la configuration d’un pool frontal, comme l’ajout ou la suppression de serveurs, vous devez suivre les instructions suivantes :
  
- Une fois la nouvelle topologie publiée, vous devez redémarrer chaque serveur frontal du pool. Redémarrez-les un par un.
    
- Si l’intégralité du pool a été mise en panne pendant la modification de configuration, exécutez l’cmdlet suivante après la publication de la nouvelle topologie :  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
