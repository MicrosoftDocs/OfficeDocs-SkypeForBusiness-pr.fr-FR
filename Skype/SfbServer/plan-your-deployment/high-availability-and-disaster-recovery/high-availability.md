---
title: Haute disponibilité et gestion des pools frontaux
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Découvrez la gestion des pools frontaux dans Skype entreprise Server, y compris la gestion des pools, la perte de quorum et des étapes spéciales pour les pools avec deux serveurs frontaux seulement.
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098432"
---
# <a name="front-end-pool-high-availability-and-management"></a>Haute disponibilité et gestion des pools frontaux
 
Découvrez la gestion des pools frontaux dans Skype entreprise Server, y compris la gestion des pools, la perte de quorum et des étapes spéciales pour les pools avec deux serveurs frontaux seulement.
  
Dans Skype entreprise Server, l’architecture des pools frontaux utilise un modèle de systèmes distribués, dont les données de chaque utilisateur sont conservées sur un maximum de trois serveurs frontaux dans le pool. Nous recommandons que tous les pools frontaux Enterprise Edition incluent au moins trois serveurs frontaux.

> [!NOTE]
> Skype entreprise Server 2019 ne prend pas en charge les pools frontaux Enterprise Edition avec deux serveurs frontaux et n’autorise pas la publication de la topologie dans ce scénario.
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des pools frontaux

 Skype entreprise Server utilise un modèle de systèmes distribués basé sur Windows fabric. Dans ce modèle, les données importantes de chaque utilisateur et conférence sont stockées sur trois serveurs frontaux dans un pool frontal. Ces trois serveurs stockant un certain ensemble de données sont calledreplicas.
  
Avec le modèle distribué pour les pools frontaux, un certain nombre de serveurs d’un pool doivent être en cours d’exécution pour que le pool fonctionne. Il existe deux modes de perte pour un pool.
  
- Perte de quorum au niveau du groupe de routage, causée par des serveurs de réplication insuffisants pour un groupe de routage particulier. Un groupe de routage est un ensemble d’utilisateurs hébergés dans le pool. Chaque groupe de routage dispose de trois réplicas dans le pool : un réplica principal et deux réplicas secondaires.
    
- Perte de quorum au niveau du pool, provoqué lorsque le pool ne comporte pas suffisamment de serveurs d’amorçage. 
    
### <a name="routing-group-level-quorum-loss"></a>Perte de quorum au niveau du groupe de routage

La première fois que vous démarrez un nouveau pool frontal, il est essentiel que 85% des serveurs soient opérationnels, comme indiqué dans le tableau suivant. Si le nombre de serveurs en cours d’exécution est moindre, les services peuvent être bloqués dans l’état de démarrage et le pool peut ne pas démarrer.
  
|Nombre total de serveurs dans le pool  <br/> |Nombre de serveurs qui doivent être en cours d’exécution pour que le pool démarre pour la première fois  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **pour Skype entreprise Server 2019** <br/> |12   <br/> |


   
Chaque fois que le pool est démarré, 85% des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). Si ce nombre de serveurs ne peut pas être démarré (mais que les serveurs peuvent être démarrés de manière à ne pas être au même niveau que la perte de quorum au niveau du pool), vous pouvez utiliser l' `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` applet de commande pour permettre au pool de récupérer à partir de cette perte de quorum au niveau du groupe de routage et de progresser. Pour plus d’informations sur l’utilisation de cette cmdlet, voir [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps). 
  
> [!NOTE]
> Dans les pools avec un nombre de serveurs pairs, Skype entreprise Server utilise la base de données SQL principale comme témoin. Dans un pool de ce type, si vous arrêtez la base de données principale et basculez vers la copie miroir, et que vous arrêtez suffisamment de serveurs frontaux pour qu’ils fonctionnent insuffisants en fonction du tableau précédent, le pool entier sera inactif. Pour plus d’informations, voir [témoin de mise en miroir de bases de données](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour qu’un pool frontal fonctionne du tout, il ne peut pas faire l’objets d’une perte de quorum au niveau du pool. Si le nombre de serveurs en cours de fonctionnement est inférieur au niveau fonctionnel, comme indiqué dans le tableau suivant, les autres serveurs du pool arrêtent tous les services Skype entreprise Server. Notez que les chiffres du tableau suivant partent du principe que les serveurs principaux du pool sont en cours d’exécution.
  
|Nombre total de serveurs frontaux dans le pool  <br/> |Nombre de serveurs devant s’exécuter pour que le pool soit opérationnel  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |Any 2  <br/> |
|5-6  <br/> |Any 3  <br/> |
|7   <br/> |N’importe quel 4  <br/> |
|8-9  <br/> |Un 4 des 7 premiers serveurs  <br/> |
|10-12  <br/> |Un 5 des premiers serveurs  <br/> |
|12-16 **pour Skype entreprise Server 2019**  <br/> |N’importe quel 7 des 12 premiers serveurs  <br/> |
   
Dans le tableau précédent, les « premiers serveurs » sont les serveurs qui ont été mis en avant pour la première fois, de façon chronologique, au moment du premier démarrage du pool. Pour déterminer ces serveurs, vous pouvez utiliser l' `Get-CsComputer` applet de commande avec l' `-PoolFqdn` option. Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et ceux en haut de la liste sont les premiers serveurs.
  
> [!IMPORTANT]
> Le nombre maximal de serveurs frontaux a été porté à 16 dans [Skype entreprise Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires permettant de s’assurer que les pools sont fonctionnels

Vous devez surveiller deux autres facteurs afin de vous assurer que vos pools frontaux demeurent fonctionnels.
  
- Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.
    
- Si vous établissez une relation de jumelage entre ce pool et un autre pool à des fins de récupération d’urgence, après avoir établi cette relation, vous devez vous assurer que ce pool dispose de trois serveurs frontaux exécutés simultanément à un moment donné pour synchroniser correctement les données avec le pool de sauvegarde. Pour plus d’informations sur les paires de pools et les fonctionnalités de récupération d’urgence, reportez-vous à la rubrique [plan for High Availability and Disaster Recovery in Skype for Business Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool frontal avec deux serveurs frontaux

Nous vous déconseillons de déployer un pool frontal qui ne contient que deux serveurs frontaux. Ce petit pool ne fournira pas de solution de haute disponibilité fiable, comme un pool plus grand, et nécessite des soins supplémentaires pour la gestion de. En outre, si le serveur principal d’un pool à deux serveurs est tombé en panne, tout le pool lui-même risque de descendre. Si vous souhaitez déployer un seul ou deux serveurs exécutant Skype entreprise Server, nous vous recommandons de les déployer en tant que serveurs Standard Edition.
  
Si vous n’avez jamais besoin de déployer un pool avec deux serveurs frontaux, suivez ces instructions :
  
- Si l’un des deux serveurs frontaux tombe en panne, vous devez essayer de le remettre dès que possible. De même, si vous devez mettre à niveau l’un des deux serveurs, remettez-le en ligne dès que la mise à niveau est terminée.
    
- Si, pour une raison quelconque, vous devez mettre les deux serveurs en même temps, procédez comme suit lorsque le temps d’arrêt du pool est terminé :
    
  - La meilleure pratique consiste à redémarrer les deux serveurs frontaux en même temps. 
    
  - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leur ordre d’arrêt.
    
  - Si vous ne pouvez pas les rétablir dans cet ordre, utilisez l’applet de commande suivante avant de rétablir le pool :`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Échecs et modifications de la configuration du pool frontal

Si un serveur frontal tombe en panne et qu’il n’est probablement pas remplacé pendant quelques jours ou plus, supprimez le serveur de la topologie. Ajoutez le nouveau serveur frontal à la topologie lorsqu’il est de nouveau disponible.
  
Chaque fois que vous modifiez la configuration d’un pool frontal, comme l’ajout ou la suppression de serveurs, vous devez suivre les instructions suivantes :
  
- Une fois la nouvelle topologie publiée, vous devez redémarrer chaque serveur frontal dans le pool. Redémarrez-les une à la fois.
    
- Si le pool entier est inactif lors de la modification de la configuration, exécutez l’applet de commande suivante après la publication de la nouvelle topologie :`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

