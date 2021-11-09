---
title: Planifier la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Résumé : Lisez cette rubrique pour découvrir comment planifier la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 042080aebf57a14554820eea9b5bb9d5c9bb1f71
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836226"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planifier la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment planifier la haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente Skype Entreprise Server 2015.
  
La haute disponibilité et la récupération d’urgence pour le serveur de conversation permanente nécessitent des ressources supplémentaires au-delà de ce qui est généralement nécessaire pour un fonctionnement complet. 
  
> [!NOTE]
> L’utilisation SQL groupes de disponibilité AlwaysOn n’est pas prise en charge avec les bases de données du serveur de conversation permanente. 

> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
  
## <a name="resource-requirements"></a>Besoins en ressources

Avant de configurer le serveur de conversation permanente pour la haute disponibilité et la récupération d’urgence, assurez-vous que vous disposez des ressources supplémentaires suivantes. 
  
- Une instance de base de données dédiée située dans le même centre de données physique dans lequel se trouve l’extrémité principale du service serveur de conversation permanente. Cette base de données servira de miroir SQL Server pour la base de données de conversation permanente principale. Si vous le souhaitez, désignez une SQL Server supplémentaire qui servira de témoin de mise en miroir si vous souhaitez un failover automatisé vers la base de données miroir.
    
- Une instance dédiée de la base de données, située dans l’autre centre de données physique. Cette base de données servira de base SQL Server base de données secondaire de livraison des journaux de bord pour la base de données dans le centre de données principal.
    
- Une instance de base de données dédiée qui sert de miroir SQL Server pour la base de données secondaire. Désignez éventuellement une SQL Server serveur en tant que témoin de mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.
    
- Si la conformité du serveur de conversation permanente est activée, trois instances de base de données dédiées supplémentaires sont requises. Leur distribution est identique à celle précédemment décrite pour la base de données de conversation permanente. Bien qu’il soit possible pour la base de données de conformité de partager la même instance SQL Server que la base de données de conversation permanente, des instances autonomes pour la haute disponibilité et la récupération d’urgence sont recommandées.
    
- Un partage de fichiers doit être créé et désigné pour les journaux de transaction de SQL Server journaux de transaction. Tous SQL serveurs des deux centres de données qui exécutent des bases de données de conversation permanente doivent avoir un accès en lecture/écriture à ce partage de fichiers. Il n’est pas défini avec un rôle FileStore.
    
- Partage de fichiers sur le serveur de base de données secondaire qui sert de dossier de destination pour les journaux de transactions SQL Server qui sont copiés à partir du partage de fichiers du serveur principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Solutions de haute disponibilité et de récupération d’urgence

Skype Entreprise Server prend en charge plusieurs modes de haute disponibilité pour vos serveurs principaux, y compris la mise en miroir de bases de données. Pour plus d’informations, voir [Plan for high availability and disaster recovery in Skype Entreprise Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solution de récupération d’urgence pour le serveur de conversation permanente décrite dans cette rubrique est conçue sur un pool de serveurs de conversation permanente étiré. Il n’est pas nécessaire d’avoir un réseau local virtuel étendu (VLAN). En étirant un pool de serveurs de conversation permanente, vous configurez logiquement un pool dans la topologie, mais vous placez physiquement les serveurs du pool dans deux centres de données différents. Vous configurez SQL Server la base de données de la même manière et déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le centre de données secondaire (avec un miroir facultatif pour fournir une haute disponibilité pendant la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le failover lors de la récupération d’urgence. 
  
Pour plus d’informations sur la configuration de la haute disponibilité et de la récupération d’urgence pour le serveur de conversation permanente, voir [Configure high availability and disaster recovery for Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Les figures suivantes montrent comment le pool de serveurs de conversation permanente peut être configuré dans deux topologies de pool étirée différentes :
  
- Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.
    
- Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.
    
La figure 1 illustre une topologie de pool de serveurs de conversation permanente étirée dans laquelle les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence. Supposons que les topologies logiques et physiques sont les suivantes :
  
- La topologie logique se compose des suivants :
    
  - Pool de conversation permanente sur les sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Un pool de serveurs frontux, une base de données de conversation permanente, une base de données en miroir et, éventuellement, une base de données témoin (non représentée dans le diagramme) résidant physiquement sur le site 1. 
    
  - Un deuxième pool de serveurs frontux et une base de données de sauvegarde résidant physiquement sur le site 2.
    
- La topologie physique se compose des sites 1 et 2 comme suit :
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, deux actifs, deux inactifs sur site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, deux actifs, deux inactifs sur site 2.
    
  - Un pool de serveurs frontux, une base de données de conversation permanente, une base de données en miroir et, éventuellement, une base de données témoin (non représentée dans le diagramme) sur le site 1.
    
  - Un pool de serveurs frontux et une base de données de sauvegarde, qui est la cible SQL copie des journaux de livraison, sur le site 2.
    
**Pool de serveurs de conversation permanente étiré lorsque les centres de données sont localisés géographiquement avec une bande passante élevée/faible latence**

![Pool étendu de conversation permanente avec bande passante élevée/faible latence.](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figure 2 illustre une topologie de pool de serveurs de conversation permanente étirée dans laquelle les centres de données sont localisés géographiquement avec une bande passante faible/latence élevée.
  
- La topologie logique se compose des suivants :
    
  - Pool de conversation permanente sur les sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Un pool de serveurs frontux, une base de données de conversation permanente, une base de données en miroir et, éventuellement, une base de données témoin (non représentée dans le diagramme) résidant physiquement sur le site 1. 
    
  - Un deuxième pool de serveurs frontux et une base de données de sauvegarde résidant physiquement sur le site 2.
    
- La topologie physique se compose des sites 1 et 2 comme suit :
    
  - Pool de conversation permanente, contenant les serveurs 1 à 4, tous actifs, sur le site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, tous inactifs, sur le site 2.
    
  - Un pool de serveurs frontux, une base de données de conversation permanente, une base de données en miroir et, éventuellement, une base de données témoin (non représentée dans le diagramme) sur le site 1.
    
  - Un pool de serveurs frontux et une base de données de sauvegarde, qui est la cible SQL copie des journaux de réception, sur le site 2.
    
**Pool de serveurs de conversation permanente étiré lorsque les centres de données sont localisés géographiquement avec une bande passante faible/latence élevée**

![Pool étendu de conversation permanente avec faible bande passante/latence élevée.](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

