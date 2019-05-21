---
title: Haute disponibilité et gestion du pool frontal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: Apprenez-en davantage sur la gestion du pool frontal dans Skype entreprise Server, y compris la gestion des pools, la perte de quorum et les étapes spéciales pour les pools avec deux serveurs frontaux uniquement.
ms.openlocfilehash: debc0700a142789f542e4b4357da4427ce74c050
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297469"
---
# <a name="front-end-pool-high-availability-and-management"></a>Haute disponibilité et gestion du pool frontal
 
Apprenez-en davantage sur la gestion du pool frontal dans Skype entreprise Server, y compris la gestion des pools, la perte de quorum et les étapes spéciales pour les pools avec deux serveurs frontaux uniquement.
  
Dans Skype entreprise Server, l’architecture des pools front-end utilise un modèle de systèmes distribués, dont les données sont conservées sur autant de trois serveurs frontaux dans la liste. Nous vous recommandons d’inclure au moins trois serveurs front-end dans votre version Enterprise Edition. 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>Planification de la gestion des pools frontaux

 Skype entreprise Server utilise un modèle de systèmes distribués basé sur Windows fabric. Dans ce modèle, les données importantes de chaque utilisateur et chaque conférence sont stockées sur trois serveurs front-end dans un pool frontal. Ces trois serveurs stockant un certain ensemble de données sont calledreplicas.
  
Avec le modèle distribué pour les pools front-end, un certain nombre de serveurs d’un pool doivent être exécutés pour que le pool fonctionne. Il existe deux modes de perte pour une réserve.
  
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
|version8  <br/> |6  <br/> |
|09  <br/> |7  <br/> |
|0,10  <br/> |version8  <br/> |
|27,9  <br/> |09  <br/> |
|midi  <br/> |0,10  <br/> |
   
Chaque fois que le pool est démarré ultérieurement, 85 % des serveurs doivent être démarrés (comme indiqué dans le tableau précédent). Si ce nombre de serveurs ne peut pas être démarré (mais qu’il est possible de démarrer le nombre de serveurs de sorte que vous n’ayez pas la perte de `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` quorum au niveau du pool), vous pouvez utiliser l’applet de cmdlet pour permettre au pool de récupérer la perte de quorum de niveau de groupe de routage et de progresser. Pour plus d’informations sur l’utilisation de cette cmdlet, <link Reset-CsPoolRegistrarState>voir.
  
> [!NOTE]
> Dans les pools disposant dʼun nombre égal de serveurs, Skype Entreprise Server utilise la base de données SQL principale. Dans un tel pool, si vous arrêtez la base de donnée principale, basculez vers la copie miroir et arrêtez suffisamment de serveurs frontaux de sorte quʼun nombre insuffisant de serveurs soient exécutés conformément au tableau précédent, le pool entier s’arrête. Pour plus d’informations, voir [témoin de mise en miroir de base de données](https://go.microsoft.com/fwlink/?LinkId=393672). 
  
#### <a name="pool-level-quorum-loss"></a>Perte de quorum au niveau du pool

Pour qu’un pool frontal puisse fonctionner, il ne peut pas être dans la perte de quorum au niveau du pool. Si le nombre de serveurs exécutés passe en dessous du niveau fonctionnel indiqué dans le tableau ci-après, les serveurs restants dans le pool arrêtent tous les services Skype Entreprise Server. Notez que les nombres figurant dans le tableau ci-dessous partent du principe que les serveurs dorsaux du pool s’exécutent.
  
|Nombre total de serveurs frontaux de la liste  <br/> |Nombre de serveurs devant être exécutés pour que le pool soit opérationnel  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |2 (n’importe lesquels)  <br/> |
|5-6  <br/> |3 (n’importe lesquels)  <br/> |
|7  <br/> |4 (n’importe lesquels)  <br/> |
|8-9  <br/> |4 (n’importe lesquels parmi les 7 premiers serveurs)  <br/> |
|10-12  <br/> |5 (n’importe lesquels parmi les 9 premiers serveurs)  <br/> |
   
Dans le tableau ci-dessus, le «premier serveur» est le serveur qui s’est affiché en premier, dans l’ordre chronologique, lorsque le pool a été démarré pour la première fois. Pour déterminer ces serveurs, vous pouvez utiliser l' `Get-CsComputer` applet de commande ` -PoolFqdn` avec l’option. Cette applet de commande affiche les serveurs dans l’ordre dans lequel ils apparaissent dans la topologie, et ceux situés en haut de la liste sont les premiers serveurs.
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>Étapes supplémentaires pour vérifier que les pools sont opérationnels

Vous devez prêter attention à deux autres facteurs pour vous assurer que vos pools frontaux restent opérationnels.
  
- Lorsque vous déplacez des utilisateurs vers le pool pour la première fois, assurez-vous qu’au moins trois serveurs frontaux sont en cours d’exécution.
    
- Si vous établissez une relation couplée entre ce pool et un autre pour pouvoir bénéficier de la récupération après incident, puis qu’une fois cette relation établie, vous devez vérifier que ce pool contient trois serveurs frontaux étant simultanément en cours d’exécution à un moment précis pour synchroniser correctement vos données avec le pool de sauvegarde. Pour plus d’informations sur les fonctionnalités de jumelage et de récupération d’urgence, reportez-vous à la section [planifier une disponibilité élevée et une reprise après sinistre dans Skype entreprise Server](high-availability-and-disaster-recovery.md). 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>Pool frontal avec deux serveurs frontaux

Nous déconseillons le déploiement d’un pool frontal qui ne contient que deux serveurs frontaux. En effet, ce petit pool ne fournit pas une solution fiable à haute disponibilité comme le ferait un pool plus grand et il nécessite une gestion plus précautionneuse. De plus, si le serveur principal d’un pool de deux serveurs s’est arrêté, le pool entier lui-même risque de descendre bientôt. Si vous voulez déployer seulement un ou deux serveurs exécutant Skype entreprise Server, nous vous conseillons de les déployer en tant que serveurs Standard Edition Server.
  
Si vous n’avez jamais besoin de déployer un pool avec deux serveurs frontaux, suivez les recommandations suivantes:
  
- Si l’un des deux serveurs frontaux est en panne, vous devez essayer de remettre le serveur en panne dès que vous le pouvez. De même, si vous devez mettre à niveau l’un de ces serveurs, remettez-le en ligne dès la fin de la mise à niveau.
    
- Si, pour une raison ou une autre, vous devez arrêter les deux serveurs en même temps procédez comme suit lorsque l’interruption de service du pool est terminé :
    
  - Il est recommandé de redémarrer à la fois les serveurs front-end en même temps. 
    
  - Si les deux serveurs ne peuvent pas être redémarrés en même temps, vous devez les rétablir dans l’ordre inverse de leurs arrêts.
    
  - Si vous ne pouvez pas les remettre dans l’ordre, utilisez l’applet de commande suivante avant de remettre le pool à nouveau:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>Défaillances et modifications de la configuration du pool frontal

Si un serveur frontal rencontre une défaillance et ne peut pas être remplacé avant plusieurs jours, supprimez ce serveur de la topologie. Rajoutez-le à la topologie dès qu’il est de nouveau disponible.
  
Lorsque vous modifiez la configuration dʼun pool frontal, comme en cas d’ajout ou de suppression des serveurs, vous devez suivre la procédure suivante :
  
- Après avoir publié la nouvelle topologie, vous devez redémarrer chaque serveur dans le pool. Redémarrez-les un par autre.
    
- Si le pool entier est arrêté lors de la modification de la configuration, exécutez l’applet de commande suivante une fois la nouvelle topologie publiée:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

