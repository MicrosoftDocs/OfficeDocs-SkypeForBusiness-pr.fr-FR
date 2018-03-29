---
title: Planification de la topologie du serveur de conversation permanente
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les composants du serveur de conversation permanents et les topologies dans Skype pour Business Server 2015.'
ms.openlocfilehash: 11d12283c3ee302c8133b0a56bbea53315508aec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-persistent-chat-server-topology"></a>Planification de la topologie du serveur de conversation permanente
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les composants du serveur de conversation permanents et les topologies dans Skype pour Business Server 2015.
  
Serveur de Chat persistant prend en charge les configurations de serveur unique et de plusieurs serveurs. Vous pouvez installer serveur de Chat persistant sur soit un Skype pour Business Server 2015 Enterprise Edition ou Standard Edition Server. 
  
## <a name="persistent-chat-server-components"></a>Composants serveur Chat permanents

Le serveur de conversation permanente comprend les composants suivants :
  
- Un ou plusieurs ordinateurs exécutant serveur de Chat persistant et fournit les services suivants :
    
  - Service Chat persistant
    
  - Service de conformité, activé si la conformité est activée
    
- Un ou plusieurs serveurs (plusieurs si la mise en miroir est utilisé) exécutant la base de données back-end de SQL Server pour héberger la base de données de contenu de conversation permanents où sont stockés les contenus de la salle de conversation, des locaux et des catégories.
    
    > [!NOTE]
    > La base de données back-end stocke les données d’historique de conversation, y compris les informations sur les catégories et les salles de conversation permanents qui sont créées. 
  
- Si la conformité est activée, un ou plusieurs serveurs (plusieurs si la mise en miroir est utilisé) exécutant la base de données back-end de SQL Server pour héberger la base de données de conformité de conversation permanent, où des événements de conformité et de discuter du contenu aux fins de la conformité sont stockés.
    
Pour plus d’informations sur la configuration matérielle et logicielle pour serveur de Chat persistant, consultez [configuration du serveur pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et [matérielle et logicielle requise pour le serveur Chat persistant dans Skype pour Business Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologies de serveur Chat persistants

Vous pouvez déployer le serveur de Chat persistant dans des pools d’un serveur ou sur plusieurs serveurs et topologie-pool unique ou multiple. Serveur de conversation permanent prend en charge les topologies suivantes :
  
-  Serveur Standard Edition avec serveur de conversation permanente colocalisé sur le serveur frontal
    
-  Serveur Standard Edition avec serveur Chat persistant sur un serveur distinct
    
-  Serveur Enterprise Edition avec un seul persistant Chat Server sur un serveur distinct
    
-  Le serveur Enterprise Edition Server avec plus d’un serveur Chat persistant sur des serveurs distincts
    
Bien que vous pouvez déployer le serveur Chat persistant sur un serveur Standard Edition, gardez à l’esprit que les performances et évolutivité seront affectés, et haute disponibilité n’est pas une option. Par conséquent, il est recommandé de déployer Chat permanentes sur un serveur Standard Edition principalement pour la preuve de concept et l’évaluation des besoins. 
  
Skype pour Business Server 2015 prend en charge une variété de scénarios de colocalisation, vous offrant la possibilité d’enregistrer les coûts de matériel en exécutant plusieurs composants sur un seul serveur (si vous avez une petite entreprise), ou pour exécuter des composants individuels sur des serveurs différents ( Si vous disposez d’une grande entreprise qui a besoin de l’évolutivité et les performances). Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants. Scénarios de colocalisation diffèrent pour Skype pour serveurs Business Server 2015 Enterprise Edition et Standard Edition. 
  
Les sections suivantes décrivent les topologies plus en détail, notamment les scénarios de colocalisation et les options des serveurs de base de données principale. Pour plus d’informations sur la colocalisation de tous les rôles de serveur et les bases de données, consultez [Notions fondamentales de la topologie pour Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Serveur Standard Edition avec serveur de conversation permanente colocalisé sur le serveur frontal

Avec Standard Edition, vous pouvez colocaliser la conversation permanente sur le serveur frontal. Il s’agit de la configuration la plus simple et la plus basique. Vous devez vous assurer que le serveur frontal existant possède une capacité suffisante en termes de ressources physiques : CPU, mémoire, espace disque et ainsi de suite.
  
En outre, vous pouvez colocaliser le serveur dorsal persistant Chat Server et la base de données de conformité de conversation permanent (si activée) sur le serveur principal de SQL Server Express local. Vous pouvez également choisir d’utiliser un serveur SQL Server distinct avec une instance dédiée. 
  
> [!IMPORTANT]
> Impossible d’ajouter des serveurs supplémentaires à un pool de serveurs de conversation permanent si le premier serveur de conversation permanent est colocalisé avec un Standard Edition serveur frontal. Il est recommandé d’installer le premier serveur comme instance autonome afin que vous pouvez ajouter davantage de serveurs par la suite, si nécessaire. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Serveur Standard Edition avec serveur de conversation permanente installé sur un serveur distinct

Avec Standard Edition, vous pouvez installer le serveur de conversation permanente en tant qu’instance autonome et ajouter d’autres serveurs ultérieurement si besoin.   
  
Vous pouvez colocaliser le serveur dorsal persistant Chat Server et la base de données de conformité de conversation permanent (si activée) sur le serveur principal de SQL Server Express local. Vous pouvez également choisir d’utiliser un serveur SQL Server distinct avec une instance dédiée. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Serveur Enterprise Edition avec un seul serveur de conversation permanente

Avec Enterprise Edition, vous devez installer le serveur de conversation permanente sur un ordinateur distinct. Ainsi, vous ne pouvez pas colocaliser le serveur de conversation permanente sur le serveur frontal Enterprise Edition. Ce déploiement nécessite un serveur distinct qui exécute persistant Chat Server et le service de mise en conformité (si activée).
  
Vous pouvez, toutefois, colocaliser la base de données SQL Server pour le serveur de conversation permanent sur la base de données back-end d’un pool Enterprise Edition Front-End.
  
> [!NOTE]
> Si vous prévoyez d'utiliser des groupes de disponibilité AlwaysOn SQL pour la récupération d’urgence de haute disponibilité, notez que cette fonctionnalité n'est pas prise en charge pour les bases de donnés de serveur de conversation permanente. 
  
Si vous colocaliser la base de données avec la base de données back-end conversation permanents, vous pouvez utiliser une instance unique de SQL Server pour tout ou partie des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données.
  
> [!IMPORTANT]
> Le serveur qui héberge la base de données de conversation permanent peut héberger d’autres bases de données. Toutefois, lorsque vous envisagez la COLLOCATION de la base de données Chat permanente avec les autres bases de données, gardez à l’esprit que si vous stockez les messages de plus de quelques utilisateurs, l’espace disque requis par la base de données de conversation permanent peut devenir très volumineux. Pour cette raison, nous ne recommandons pas COLLOCATION de la base de données avec la base de données back-end conversation permanent. 
  
La figure suivante montre tous les composants d’une topologie pour un seul serveur de conversation permanent avec respect de la réglementation activé (facultatif).
  
**Topologie à serveur unique**

![Serveur de conversation permanente - Topologie à serveur unique](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Serveur Enterprise Edition avec plusieurs serveurs de conversation permanente

Avec Enterprise Edition, vous pouvez déployer une topologie de plusieurs serveurs pour une plus grande capacité et la fiabilité. Une topologie à serveurs multiples est la même que la topologie de serveur unique mais plusieurs serveurs hôte serveur de Chat persistant et peuvent franchir. La topologie à serveurs multiples peut inclure jusqu'à quatre ordinateurs active persistante Chat Server en cours d’exécution (configurations de récupération après sinistre et de disponibilité élevées autorise jusqu'à huit, mais seuls quatre peut être actif et le restant de quatre en mode veille). Chaque serveur peut prendre en charge jusqu'à 20 000 utilisateurs simultanés, pour un total de 80 000 utilisateurs simultanés, connectés à un pool de serveurs de conversation permanent avec 4 serveurs. Plusieurs ordinateurs exécutant serveur de Chat persistant doivent résider dans le même domaine des Services de domaine Active Directory en tant que Skype pour Business Server et le service de mise en conformité.
  
La figure suivante illustre les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant persistant Chat Server, le service de mise en conformité facultatif et une base de données de conformité distinctes.
  
**Topologie à serveur multiple**

![Serveur de conversation permanente - Topologie à plusieurs serveurs](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de conversation permanent communiquent et partagent des données. Par exemple, l’historique de conversation qui a initialement été validée pour un service de conversation permanent est disponible à partir de n’importe quel service de conversation permanent dans le système. Un fichier est téléchargé via un service de Chat permanente est accessible par n’importe quel service Chat persistant. Les utilisateurs peuvent être connectés à différents persistant Chat Server serveurs frontaux et peuvent communiquer avec eux. Le port par défaut de TCP 8011 connecte un serveur à un pool de serveurs et est utilisé par les services de conversation permanent pour communiquer entre eux, ou à des fins administratives.
  
Par exemple, dans un serveur de Chat persistant à quatre serveurs, déploiement, où 80 000 utilisateurs peuvent être connecté simultanément à et à l’aide de conversation permanent, la charge est répartie uniformément à 20 000 utilisateurs par serveur. Si un serveur devient indisponible, les utilisateurs qui sont connectés à ce serveur seront perdues leur accès au serveur de conversation permanent. Ces utilisateurs déconnectés sont alors automatiquement transférés vers les serveurs restants jusqu’à ce que le serveur indisponible soit restauré. 
  

