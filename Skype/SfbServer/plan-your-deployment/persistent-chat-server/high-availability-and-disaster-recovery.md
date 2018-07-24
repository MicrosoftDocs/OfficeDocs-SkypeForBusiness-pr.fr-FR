---
title: Plan de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 90f01de0ca7efef8fdcda4f03fa4bfaa28bd4fcc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971654"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plan de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment planifier une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015.
  
Haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente nécessitent des ressources supplémentaires au-delà de ce qui est généralement nécessaire pour l’opération complète. 
  
> [!NOTE]
> L'utilisation de groupes de disponibilité SQL AlwaysOn n'est pas prise en charge avec les bases de données de serveur de conversations permanentes. 

> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
  
## <a name="resource-requirements"></a>Ressources requises

Avant de configurer le serveur de conversation permanente pour la haute disponibilité et de récupération d’urgence, assurez-vous que vous disposez des ressources supplémentaires suivantes. 
  
- Une instance de base de données dédiée située dans le même centre de données physique dans laquelle se trouve le frontal d’accueil du service serveur de conversation permanente. Cette base de données sera utilisée comme la mise en miroir SQL Server pour la base de données primaire conversation permanente. Si vous le souhaitez, désigner un serveur SQL supplémentaire qui agira comme le témoin de mise en miroir, si vous souhaitez un basculement automatisé à la base de données miroir.
    
- Une instance dédiée de la base de données, située dans l’autre centre de données physique. Cette base de données sera utilisée comme l’envoi de journaux SQL Server base de données secondaire pour la base de données du centre de données principal.
    
- Une instance de base de données dédiée en guise de miroir SQL Server pour la base de données secondaire. Si vous le souhaitez, désignez un serveur SQL à un serveur comme le témoin de mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.
    
- Si la conformité du serveur de conversation permanente est activée, une instance de base de données dédiée trois supplémentaires est nécessaires. La distribution est la même que celles décrites précédemment pour la base de données de conversation permanente. S’il est possible que la base de données de conformité partager la même instance de SQL Server comme base de données de conversation permanente, instances autonomes pour la haute disponibilité et récupération d’urgence sont recommandées.
    
- Un partage de fichiers doit être créé et défini pour les fichiers journaux des transactions de journaux SQL Server. Tous les serveurs SQL Server dans les deux centres de données qui exécutent des bases de données de conversation permanente doit avoir accès en lecture/écriture à ce partage de fichiers. Celui-ci n’est pas défini avec un rôle FileStore.
    
- Un partage de fichiers sur le serveur de base de données secondaire en guise de dossier de destination pour les journaux de transactions SQL Server qui sont copiés à partir du partage de fichiers du serveur principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Solutions de haute disponibilité et de récupération d’urgence

Skype pour Business Server prend en charge plusieurs modes de haute disponibilité pour vos serveurs principaux, y compris la mise en miroir de base de données. Pour plus d’informations, voir [planifier la haute disponibilité et de récupération d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solution de récupération d’urgence pour les serveurs de conversation permanente décrite dans cette rubrique est basée sur un pool de serveurs de conversation permanente étiré. Aucun réseau local virtuel (VLAN) étiré n’est requis. Par étirement un pool de serveurs de conversation permanente, vous configurez un pool dans la topologie logique, mais vous placez physiquement les serveurs du pool dans deux différents centres de données. Configurez la mise en miroir SQL Server pour la base de données de la même manière, puis déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le second centre de données (avec un miroir éventuel pour assurer la haute disponibilité pendant la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence. 
  
Pour plus d’informations sur la configuration de haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente, voir [configurer une haute disponibilité et récupération d’urgence pour les serveurs de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Les illustrations suivantes montrent comment configurer le pool de serveurs de conversation permanente dans les deux topologies de pool étirées :
  
- Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence.
    
- Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante/latence élevée.
    
La figure 1 illustre une topologie de pool de serveurs de conversation permanente étirée où les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence. Supposons que ce qui suit pour les topologies physiques et logiques :
  
- La topologie logique se compose des éléments suivants :
    
  - Un pool de conversation permanente sur les Sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Un pool de serveurs frontaux, une base de données de conversation permanente, une base de données en miroir, et, éventuellement, une base de données témoin (non affiché dans le diagramme) qui résident physiquement sur Site 1. 
    
  - Un deuxième pool de serveur frontal et une base de données de sauvegarde résidant physiquement sur le Site 2.
    
- La topologie physique se compose des Sites 1 et 2, comme suit :
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, deux actifs, deux inactifs sur le Site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, deux actifs, deux inactifs sur le Site 2.
    
  - Un pool de serveurs frontaux, une base de données de conversation permanente, une base de données en miroir et, éventuellement, un témoin de base de données (non affiché dans le diagramme) sur Site 1.
    
  - Un pool de serveur frontal, et une base de données de sauvegarde, qui est la cible de l’envoi de journaux SQL, sur le Site 2.
    
**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.**

![Pool de conversation permanente étiré faisant état d’une bande passante élevée/latence réduite](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figure 2 illustre une topologie de pool de serveurs de conversation permanente étirée où les centres de données sont localisés géographiquement avec une bande passante/latence élevée.
  
- La topologie logique se compose des éléments suivants :
    
  - Un pool de conversation permanente sur les Sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Un pool de serveurs frontaux, une base de données de conversation permanente, une base de données en miroir, et, éventuellement, une base de données témoin (non affiché dans le diagramme) qui résident physiquement sur Site 1. 
    
  - Un deuxième pool de serveur frontal et une base de données de sauvegarde résidant physiquement sur le Site 2.
    
- La topologie physique se compose des Sites 1 et 2, comme suit :
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, tous actifs sur le Site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, tous inactifs sur le Site 2.
    
  - Un pool de serveurs frontaux, une base de données de conversation permanente, une base de données en miroir et, éventuellement, un témoin de base de données (non affiché dans le diagramme) sur Site 1.
    
  - Un pool de serveur frontal, et une base de données de sauvegarde, qui est la cible de l’envoi de journaux SQL, sur le Site 2.
    
**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.**

![Pool de conversation permanente étiré faisant état d’une bande passante réduite/latence élevée](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

