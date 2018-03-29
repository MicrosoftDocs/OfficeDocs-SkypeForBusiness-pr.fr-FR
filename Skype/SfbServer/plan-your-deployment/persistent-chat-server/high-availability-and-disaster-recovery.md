---
title: Plan de disponibilité et de reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier une disponibilité et de reprise après sinistre pour serveur Chat persistant dans Skype Business Server 2015.'
ms.openlocfilehash: 2730d72b47d02772bf2c5c59c819bbe23e8816db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plan de disponibilité et de reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment planifier une disponibilité et de reprise après sinistre pour serveur Chat persistant dans Skype Business Server 2015.
  
Haute disponibilité et reprise après sinistre pour serveur persistant de Chat nécessitent des ressources supplémentaires au delà de ce qui est généralement nécessaire pour l’opération complète. 
  
> [!NOTE]
> L'utilisation de groupes de disponibilité SQL AlwaysOn n'est pas prise en charge avec les bases de données de serveur de conversations permanentes. 
  
## <a name="resource-requirements"></a>Ressources requises

Avant de configurer le serveur de conversation permanent pour la haute disponibilité et reprise après sinistre, assurez-vous que vous avez les ressources supplémentaires suivantes. 
  
- Une instance de base de données dédiée qui se trouve dans le même centre de données physique dans lequel se trouve la fin avant de l’accueil du serveur de conversation permanent. Cette base de données sera utilisée comme la mise en miroir de SQL Server pour la base de données primaire Chat persistant. Vous pouvez également désigner un SQL Server supplémentaires pour servir le témoin de la mise en miroir si vous voulez un basculement automatisé à la base de données miroir.
    
- Une instance dédiée de la base de données, située dans l’autre centre de données physique. Cette base de données sera utilisée comme la base secondaire de l’envoi de journaux SQL Server pour la base de données dans le centre de données principal.
    
- Une instance de base de données dédiée pour servir à la mise en miroir de SQL Server pour la base de données secondaire. Vous pouvez également désigner un SQL Server supplémentaires au serveur comme témoin mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.
    
- Si la conformité du serveur de conversation persistant est activée, un trois instances de base de données dédiée supplémentaires sont nécessaires. Leur distribution est identique à celle précédemment décrite pour la base de données de conversation permanent. Il est possible que la base de données de conformité de partager la même instance de SQL Server que la base de données de conversation permanent, instances autonomes de haute disponibilité et reprise après sinistre sont recommandés.
    
- Un partage de fichiers doit être créé et défini pour les journaux de transaction de l’envoi de journaux SQL Server. Tous les serveurs SQL dans les deux centres de données qui exécutent les bases de données Chat persistant doit avoir accès en lecture/écriture à ce partage de fichier. Celui-ci n’est pas défini avec un rôle FileStore.
    
- Un partage de fichiers sur le serveur de base de données secondaire comme dossier de destination pour les journaux de transactions SQL Server qui sont copiés à partir du partage de fichier du serveur principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Solutions de haute disponibilité et de récupération d’urgence

Skype pour Business Server prend en charge plusieurs modes de haute disponibilité pour votre nouveau serveurs principaux, y compris la mise en miroir de base de données. Pour plus d’informations, consultez [planification de la haute disponibilité et reprise après sinistre dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solution de reprise après sinistre pour serveur Chat persistant décrites dans cette rubrique est basée sur un pool de serveurs de conversation permanent étiré. Aucun réseau local virtuel (VLAN) étiré n’est requis. En étirant un pool permanent Chat Server, vous configurez un pool dans la topologie, logiquement, mais physiquement, vous placez les serveurs dans le pool par deux différents centres de données. Configurez la mise en miroir SQL Server pour la base de données de la même manière, puis déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le second centre de données (avec un miroir éventuel pour assurer la haute disponibilité pendant la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence. 
  
Pour plus d’informations sur la configuration de haute disponibilité et reprise après sinistre pour serveur de Chat persistant, consultez [configurer la haute disponibilité et reprise après sinistre pour serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Les figures suivantes montrent comment configurer le pool de serveur de conversation permanents dans deux topologies différentes de pool étiré :
  
- Étiré pool persistant Chat Server lorsque les centres de données sont géo-localisés avec une bande passante élevée et faible latence.
    
- Étiré pool persistant Chat Server lorsque les centres de données sont géo-localisés avec une latence de bande passante basse/haute.
    
La figure 1 illustre une topologie de pool persistant Chat Server étirée où les centres de données sont géo-localisés avec une bande passante élevée et faible latence. Supposons que les informations suivantes pour les topologies physiques et logiques :
  
- La topologie logique se compose des éléments suivants :
    
  - Un pool de conversation permanente sur les Sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Un pool de serveur frontal, un Chat persistants de base de données, une base de données en miroir, et, le cas échéant, une base de données témoin (non illustré) qui résident physiquement sur Site 1. 
    
  - Un deuxième pool de serveur frontal et une base de données de sauvegarde résidant physiquement sur le Site 2.
    
- La topologie physique se compose de Sites 1 et 2, comme suit :
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, deux actifs, deux inactifs sur le Site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, deux actifs, deux inactifs sur le Site 2.
    
  - Un pool de serveur frontal, un Chat persistants de base de données, une base de données en miroir et, le cas échéant, un témoin de base de données (non illustré) sur le Site 1.
    
  - Un pool de serveur frontal, et une base de données de sauvegarde, qui est la cible de l’envoi de journaux SQL, sur le Site 2.
    
**Étiré de pool de serveur de Chat persistant lorsque les centres de données sont géo-localisés avec une bande passante élevée et faible latence**

![Pool de conversation permanente étiré faisant état d’une bande passante élevée/latence réduite](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figure 2 illustre une topologie de pool persistant Chat Server étirée où les centres de données sont géo-localisés avec une latence de bande passante basse/haute.
  
- La topologie logique se compose des éléments suivants :
    
  - Un pool de conversation permanente sur les Sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Un pool de serveur frontal, un Chat persistants de base de données, une base de données en miroir, et, le cas échéant, une base de données témoin (non illustré) qui résident physiquement sur Site 1. 
    
  - Un deuxième pool de serveur frontal et une base de données de sauvegarde résidant physiquement sur le Site 2.
    
- La topologie physique se compose de Sites 1 et 2, comme suit :
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, tous actifs sur le Site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, tous inactifs sur le Site 2.
    
  - Un pool de serveur frontal, un Chat persistants de base de données, une base de données en miroir et, le cas échéant, un témoin de base de données (non illustré) sur le Site 1.
    
  - Un pool de serveur frontal, et une base de données de sauvegarde, qui est la cible de l’envoi de journaux SQL, sur le Site 2.
    
**Étiré de pool de serveur de Chat persistant lorsque les centres de données sont géo-localisés avec une latence de bande passante basse/haute**

![Pool de conversation permanente étiré faisant état d’une bande passante réduite/latence élevée](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

