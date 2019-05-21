---
title: Prévoir une disponibilité élevée et une reprise après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Résumé: cette rubrique vous explique comment planifier la haute disponibilité et la reprise après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: b9e509b987a9fe3b8d7755ce8d92f35c82b7d386
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297077"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Prévoir une disponibilité élevée et une reprise après sinistre pour le serveur de chat permanent dans Skype entreprise Server 2015
 
**Résumé:** Pour plus d’informations sur la planification d’une haute disponibilité et d’une reprise après sinistre pour le serveur Chat permanent, voir Skype entreprise Server 2015.
  
La haute disponibilité et la reprise après sinistre pour le serveur de chat permanent nécessitent des ressources supplémentaires en plus de ce qui est en général requis pour une opération complète. 
  
> [!NOTE]
> L'utilisation de groupes de disponibilité SQL AlwaysOn n'est pas prise en charge avec les bases de données de serveur de conversations permanentes. 

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
  
## <a name="resource-requirements"></a>Ressources requises

Avant de configurer le serveur de chat permanent pour une haute disponibilité et une reprise après sinistre, assurez-vous que vous disposez des ressources supplémentaires suivantes. 
  
- Une instance de base de données dédiée située dans le même centre de données physiques dans lequel se trouve le serveur frontal principal du service de chat permanent. Cette base de données fera office de miroir SQL Server pour la base de données de chat permanent principale. Vous pouvez également désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir si vous voulez un basculement automatisé vers la base de données miroir.
    
- Une instance dédiée de la base de données, située dans l’autre centre de données physique. Cette base de données sera utilisée en tant que base de données secondaire pour l’envoi du journal SQL Server de la base de données dans le centre de données principal.
    
- Une instance de base de données dédiée à faire office de miroir SQL Server pour la base de données secondaire. Vous pouvez éventuellement désigner un serveur SQL Server supplémentaire comme témoin de mise en miroir. Elles doivent toutes deux se situer dans le même centre de données physique que la base de données secondaire.
    
- Si la conformité de serveur Chat permanent est activée, il est nécessaire d’avoir trois instances de base de données spécialisées supplémentaires. La distribution de la base de données de chat persiste est identique à celle présentée précédemment. Même si la base de données de conformité peut partager la même instance SQL Server en tant que base de données de chat permanent, il est recommandé d’effectuer des instances autonomes pour une haute disponibilité et une reprise après sinistre.
    
- Un partage de fichiers doit être créé et désigné pour les journaux de transactions d’envoi du journal SQL Server. Tous les serveurs SQL dans les centres de données exécutant des bases de données de chat permanent doivent disposer d’un accès en lecture/écriture à ce partage de fichiers. Celui-ci n’est pas défini avec un rôle FileStore.
    
- Un partage de fichiers sur le serveur de base de données secondaire servant de dossier de destination pour les journaux de transactions SQL Server copiés à partir du partage de fichiers du serveur principal.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Solutions de haute disponibilité et de récupération d’urgence

Skype entreprise Server prend en charge plusieurs modes de haute disponibilité pour votre serveur principal, y compris la mise en miroir de la base de données. Pour plus d'informations, reportez-vous à la rubrique [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
La solution de reprise après sinistre pour serveur de chat permanent décrite dans cette rubrique repose sur un pool de serveurs de chat permanent étiré. Aucun réseau local virtuel (VLAN) étiré n’est requis. Si vous étirez un pool de serveurs de chat permanent, vous configurez un pool dans la topologie logiquement, mais vous placez physiquement les serveurs dans le pool dans deux centres de données différents. Configurez la mise en miroir SQL Server pour la base de données de la même manière, puis déployez la base de données et le miroir dans le même centre de données. Vous devez configurer une base de données de sauvegarde dans le second centre de données (avec un miroir éventuel pour assurer la haute disponibilité pendant la récupération d’urgence). Il s’agit de la base de données de sauvegarde utilisée pour le basculement pendant la récupération d’urgence. 
  
Pour plus d’informations sur la configuration d’une haute disponibilité et d’une reprise après sinistre pour un serveur de chat permanent, voir [configurer une haute disponibilité et une reprise après sinistre pour le serveur de chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
Les illustrations suivantes montrent comment le pool de serveurs de chat permanent peut être configuré dans deux topologies de pool étiré différentes:
  
- Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante élevée et une latence faible.
    
- Pool de serveurs de chat permanent étiré lorsque les centres de données sont géospatiales avec une bande passante faible et une latence élevée.
    
La figure 1 illustre une topologie de pool de serveurs de chat permanent étirée dans laquelle les centres de données sont géographiques avec une bande passante élevée et une latence faible. Considérez les points suivants pour les topologies logiques et physiques:
  
- La topologie logique se compose des éléments suivants :
    
  - Un pool de conversation permanente sur les Sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Une base de données de chat frontale, une base de données de chat permanent, une base de données en miroir et, éventuellement, une base de données témoin (non affichée dans le diagramme) résidant physiquement sur le site 1. 
    
  - Un deuxième pool de serveur frontal et une base de données de sauvegarde résidant physiquement sur le Site 2.
    
- La topologie physique se compose des sites 1 et 2 comme suit:
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, deux actifs, deux inactifs sur le Site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, deux actifs, deux inactifs sur le Site 2.
    
  - Un pool de serveurs frontal, une base de données de chat permanent, une base de données en miroir et, éventuellement, une base de données témoin (non affichée dans le diagramme) sur le site 1.
    
  - Un pool de serveur frontal, et une base de données de sauvegarde, qui est la cible de l’envoi de journaux SQL, sur le Site 2.
    
**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement et font état d’une bande passante élevée/faible latence.**

![Pool de conversation permanente étiré faisant état d’une bande passante élevée/latence réduite](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
La figure 2 illustre une topologie de pool de serveurs de chat permanent étirée dans laquelle les centres de données sont localisés avec une bande passante faible et une latence élevée.
  
- La topologie logique se compose des éléments suivants :
    
  - Un pool de conversation permanente sur les Sites 1 et 2 contenant les serveurs 1 à 8.
    
  - Une base de données de chat frontale, une base de données de chat permanent, une base de données en miroir et, éventuellement, une base de données témoin (non affichée dans le diagramme) résidant physiquement sur le site 1. 
    
  - Un deuxième pool de serveur frontal et une base de données de sauvegarde résidant physiquement sur le Site 2.
    
- La topologie physique se compose des sites 1 et 2 comme suit:
    
  - Un pool de conversation permanente, contenant les serveurs 1 à 4, tous actifs sur le Site 1.
    
  - Un pool de conversation permanente, contenant les serveurs 5 à 8, tous inactifs sur le Site 2.
    
  - Un pool de serveurs frontal, une base de données de chat permanent, une base de données en miroir et, éventuellement, une base de données témoin (non affichée dans le diagramme) sur le site 1.
    
  - Un pool de serveur frontal, et une base de données de sauvegarde, qui est la cible de l’envoi de journaux SQL, sur le Site 2.
    
**Pool de serveurs de conversation permanente étiré quand les centres de données sont localisés géographiquement avec une bande passante réduite/latence élevée.**

![Pool de conversation permanente étiré faisant état d’une bande passante réduite/latence élevée](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

