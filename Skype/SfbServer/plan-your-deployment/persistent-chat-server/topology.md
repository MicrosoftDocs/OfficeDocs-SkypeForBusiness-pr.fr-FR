---
title: Planification de la topologie du serveur de conversation permanente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les composants de serveur de conversation permanente et topologies dans Skype pour Business Server 2015.'
ms.openlocfilehash: 6d385477256150e35b305c996dccbab7ab22f4ba
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879236"
---
# <a name="plan-persistent-chat-server-topology"></a>Planification de la topologie du serveur de conversation permanente
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les composants de serveur de conversation permanente et topologies dans Skype pour Business Server 2015.
  
Persistent Chat Server prend en charge les configurations de serveur unique ou sur plusieurs serveurs. Vous pouvez installer le serveur de conversation permanente sur soit un Skype pour Business Server 2015 Enterprise Edition ou Standard Edition Server. 

> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Composants de serveur de conversation permanentes

Le serveur de conversation permanente comprend les composants suivants :
  
- Un ou plusieurs ordinateurs exécutant le serveur de conversation permanente et fournissant les services suivants :
    
  - Service de conversation permanent
    
  - Service de conformité, activé si la conformité est activée
    
- Un ou plusieurs serveurs (plusieurs cas d’utilisation de la mise en miroir) qui exécute la base de données principale SQL Server pour héberger la base de données de contenu de conversation permanente où le contenu de la salle de conversation, les salles et les catégories sont stockés.
    
    > [!NOTE]
    > La base de données principale stocke les données de l’historique de conversation, notamment des informations sur les catégories et salles de conversation permanente qui sont créées. 
  
- Si la conformité est activée, un ou plusieurs serveurs (plusieurs cas d’utilisation de la mise en miroir) qui exécute la base de données principale SQL Server pour héberger la base de données de conformité de conversation permanente, où des événements de conformité et de conversation de contenu pour les besoins de conformité sont stockés.
    
Pour plus d’informations sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente, voir [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et la [configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype pour Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologies de serveur de conversation permanentes

Vous pouvez déployer des serveurs de conversation permanente avec topologie-pool unique ou multiple-pool et pools de serveur unique ou de plusieurs serveurs. Persistent Chat Server prend en charge les topologies suivantes :
  
-  Serveur Standard Edition avec serveur de conversation permanente colocalisé sur le serveur frontal
    
-  Le serveur Standard Edition Server avec un serveur de conversation permanente sur un serveur distinct
    
-  Serveur Enterprise Edition avec un seul Persistent Chat Server sur un serveur distinct
    
-  Serveur Enterprise Edition avec plusieurs serveurs de conversation permanente sur des serveurs distincts
    
Bien que vous pouvez déployer des serveurs de conversation permanente sur un serveur Standard Edition Server, sachez que les performances et échelle seront affectés, et haute disponibilité n’est pas une option. Par conséquent, il est recommandé de déployer la conversation permanente sur un serveur Standard Edition Server principalement pour la preuve de concept et évaluation à des fins. 
  
Skype pour Business Server 2015 prend en charge divers scénarios de colocalisation, vous offrant la souplesse nécessaire pour enregistrer les coûts matériels par plusieurs composants en cours d’exécution sur un serveur (si vous avez une petite organisation), ou pour exécuter des composants individuels sur des serveurs différents ( Si vous disposez d’une plus grande organisation qui a besoin de l’évolutivité et les performances). Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants. Scénarios de colocalisation diffèrent pour Skype pour Business Server 2015 Enterprise Edition et Standard Edition Server. 
  
Les sections suivantes décrivent les topologies plus en détail, notamment les scénarios de colocalisation et les options des serveurs de base de données principale. Pour plus d’informations sur la colocalisation de tous les rôles de serveur et les bases de données, voir [Les concepts de topologie pour Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Serveur Standard Edition avec serveur de conversation permanente colocalisé sur le serveur frontal

Avec Standard Edition, vous pouvez colocaliser la conversation permanente sur le serveur frontal. Il s’agit de la configuration la plus simple et la plus basique. Vous devez vous assurer que le serveur frontal existant dispose de suffisamment de capacité en termes de ressources physiques : processeur, mémoire, espace disque et ainsi de suite.
  
En outre, vous pouvez colocaliser le serveur dorsal Persistent Chat Server et la base de données de conformité de conversation permanente (si activée) sur le serveur principal de SQL Server Express local. Vous pouvez également choisir d’utiliser un serveur SQL Server distinct avec une instance dédiée. 
  
> [!IMPORTANT]
> Vous ne pouvez pas ajouter des serveurs supplémentaires à un pool de serveurs de conversation permanente si le premier serveur de conversation permanente est colocalisé avec un serveur Standard Edition serveur frontal. Il est recommandé d’installer le premier serveur comme instance autonome afin que vous pouvez ajouter d’autres serveurs ultérieurement, si nécessaire. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Serveur Standard Edition avec serveur de conversation permanente installé sur un serveur distinct

Avec Standard Edition, vous pouvez installer le serveur de conversation permanente en tant qu’instance autonome et ajouter d’autres serveurs ultérieurement si besoin.   
  
Vous pouvez colocaliser le serveur dorsal Persistent Chat Server et la base de données de conformité de conversation permanente (si activée) sur le serveur principal de SQL Server Express local. Vous pouvez également choisir d’utiliser un serveur SQL Server distinct avec une instance dédiée. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Serveur Enterprise Edition avec un seul serveur de conversation permanente

Avec Enterprise Edition, vous devez installer le serveur de conversation permanente sur un ordinateur distinct. Ainsi, vous ne pouvez pas colocaliser le serveur de conversation permanente sur le serveur frontal Enterprise Edition. Ce déploiement requiert un serveur distinct qui exécute Persistent Chat Server et le service de conformité (si activée).
  
Vous pouvez, toutefois, colocaliser la base de données SQL Server pour le serveur de conversation permanente sur la base de données principale d’un pool frontal Enterprise Edition.
  
> [!NOTE]
> Si vous prévoyez d'utiliser des groupes de disponibilité AlwaysOn SQL pour la récupération d’urgence de haute disponibilité, notez que cette fonctionnalité n'est pas prise en charge pour les bases de donnés de serveur de conversation permanente. 
  
Si vous colocalisez la base de données de conversation permanente avec la base de données principale, vous pouvez utiliser une seule instance de SQL Server pour tout ou partie des bases de données, ou vous pouvez utiliser une instance de SQL Server distincte pour chaque base de données.
  
> [!IMPORTANT]
> Le serveur qui héberge la base de données de conversation permanente peut héberger d’autres bases de données. Toutefois, lorsque vous envisagez de colocaliser la base de données avec les autres bases de données de conversation permanente, sachez que si vous stockez les messages de plus de quelques utilisateurs, l’espace disque nécessaire à la base de données de conversation permanente peut devenir très volumineux. Pour cette raison, nous ne recommandons pas colocaliser la base de données de conversation permanente avec la base de données principale. 
  
La figure suivante présente tous les composants d’une topologie pour un seul serveur de conversation permanente avec la conformité activée (facultatif).
  
**Topologie à serveur unique**

![Serveur de conversation permanente - Topologie à serveur unique](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Serveur Enterprise Edition avec plusieurs serveurs de conversation permanente

Avec Enterprise Edition, vous pouvez déployer une topologie à plusieurs serveurs pour une capacité et la fiabilité. Une topologie à plusieurs serveurs est identique à la topologie à serveur unique, sauf que plusieurs serveurs hébergent Persistent Chat Server et mettre à l’échelle supérieure. La topologie à plusieurs serveurs peut inclure jusqu'à quatre ordinateurs active Persistent Chat Server en cours d’exécution (configurations de récupération haute disponibilité et reprise après sinistre autorisera jusqu'à huit, mais que de quatre peut être actif et le restant de quatre en mode veille). Chaque serveur peut prendre en charge jusqu'à 20 000 utilisateurs simultanés, pour un total de 80 000 utilisateurs simultanés connectés à un pool de serveurs de conversation permanente avec 4 serveurs. Plusieurs ordinateurs exécutant le serveur de conversation permanente doivent résider dans le même domaine des Services de domaine Active Directory en tant que Skype pour Business Server et le service de conformité.
  
La figure suivante illustre les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant le serveur de conversation permanente, le service de conformité facultatif et une base de données de conformité distincte.
  
**Topologie à plusieurs serveurs**

![Serveur de conversation permanente - Topologie à plusieurs serveurs](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de conversation permanente communiquent et partagent des données. Par exemple, l’historique des conversations qui a été publié à un seul service de conversation permanente sont disponible à partir de n’importe quel service de conversation permanente dans le système. Un fichier est téléchargé via un service de conversation permanente est accessible par n’importe quel service de conversation permanente. Les utilisateurs peuvent être connectés à différentes Persistent Chat Server serveurs frontaux et peuvent communiquer entre eux. La valeur par défaut le port TCP 8011, qui connecte un serveur à un pool de serveurs et est utilisé par les services de conversation permanente pour communiquer entre eux ou à des fins administratives.
  
Par exemple, dans un déploiement de serveurs de conversation permanente à quatre serveurs, où 80 000 utilisateurs peuvent être simultanément connectés à la conversation permanente, la charge est équitablement à 20 000 utilisateurs par serveur. Si un serveur devient indisponible, les utilisateurs qui sont connectés à ce serveur seront perdent leur accès au serveur de conversation permanente. Ces utilisateurs déconnectés sont alors automatiquement transférés vers les serveurs restants jusqu’à ce que le serveur indisponible soit restauré. 
  

