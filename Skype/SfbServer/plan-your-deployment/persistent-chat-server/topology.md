---
title: Planifier la topologie du serveur de conversation permanente
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
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Résumé : Consultez cette rubrique pour en savoir plus sur les topologies et les composants du serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: 1b57d9d9ace6e51001acfa39101eb185a8e00939
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862071"
---
# <a name="plan-persistent-chat-server-topology"></a>Planifier la topologie du serveur de conversation permanente
 
**Résumé :** Consultez cette rubrique pour en savoir plus sur les topologies et les composants du serveur de conversation permanente Skype Entreprise Server 2015.
  
Le serveur de conversation permanente prend en charge les configurations à serveur unique et à plusieurs serveurs. Vous pouvez installer le serveur de conversation permanente sur un serveur Skype Entreprise Server 2015 Êdition Entreprise ou Édition Standard Server. 

> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Composants du serveur de conversation permanente

Le serveur de conversation permanente se compose des composants suivants :
  
- Un ou plusieurs ordinateurs exécutant le serveur de conversation permanente et fournissant les services suivants :
    
  - Service de conversation permanente
    
  - Service de conformité, qui est activé si la conformité est activée
    
- Un ou plusieurs serveurs (plusieurs en cas d’utilisation de la mise en miroir) exécutant la base de données principale SQL Server pour l’hébergement de la base de données de contenu de conversation permanente dans laquelle sont stockés le contenu, les salles et les catégories de la salle de conversation.
    
    > [!NOTE]
    > La base de données principale stocke les données d’historique des conversation, notamment des informations sur les catégories et les salles de conversation permanente qui sont créées. 
  
- Si la conformité est activée, un ou plusieurs serveurs (plusieurs si la mise en miroir est utilisée) exécutant la base de données principale SQL Server pour l’hébergement de la base de données de conformité de conversation permanente, où sont stockés les événements de conformité et le contenu de conversation à des fins de conformité.
    
Pour plus d’informations sur la configuration matérielle et logicielle requise pour le serveur de conversation permanente, voir Configuration requise pour le serveur de conversation permanente pour [Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et configuration matérielle et logicielle requise pour le serveur de conversation permanente [dans Skype Entreprise Server 2015.](hardware-and-software-requirements.md) 
  
## <a name="persistent-chat-server-topologies"></a>Topologies de serveur de conversation permanente

Vous pouvez déployer un serveur de conversation permanente dans des pools à serveur unique ou à plusieurs serveurs, et avec une topologie à pool unique ou à plusieurs pools. Le serveur de conversation permanente prend en charge les topologies suivantes :
  
-  Édition Standard Serveur avec serveur de conversation permanente cocté sur le serveur frontal
    
-  Édition Standard Serveur avec serveur de conversation permanente sur un serveur distinct
    
-  Êdition Entreprise Serveur avec un seul serveur de conversation permanente sur un serveur distinct
    
-  Êdition Entreprise Serveur avec plusieurs serveurs de conversation permanente sur des serveurs distincts
    
Bien que vous pouvez déployer un serveur de conversation permanente sur un serveur Édition Standard, sachez que les performances et l’échelle seront affectées et que la haute disponibilité n’est pas une option. Par conséquent, il est recommandé de déployer la conversation permanente sur un serveur Édition Standard principalement à des fins de preuve de concept et d’évaluation. 
  
Skype Entreprise Server 2015 prend en charge divers scénarios de césion, ce qui vous offre la possibilité d’économiser des coûts matériels en exécutant plusieurs composants sur un serveur (si vous avez une petite organisation) ou d’exécuter des composants individuels sur différents serveurs (si vous avez une grande organisation qui a besoin d’évolutivité et de performances). Vous devez tenir compte des facteurs d’évolutivité avant de décider s’il convient de cérer des composants. Les scénarios de cocation diffèrent pour Skype Entreprise Server 2015 Êdition Entreprise serveurs Édition Standard serveurs. 
  
Les sections suivantes décrivent les topologies plus en détail, y compris les scénarios de cocation et les options pour les serveurs de base de données principaux. Pour plus d’informations sur la cocation de tous les rôles serveur et bases de données, voir [Topology Basics for Skype Entreprise Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Édition Standard Serveur avec serveur de conversation permanente cocté sur le serveur frontal

Avec Édition Standard, vous pouvez céquequer la conversation permanente sur le serveur frontal. Il s’agit de la configuration la plus simple et la plus simple. Vous devez vous assurer que le serveur frontal existant dispose d’une capacité suffisante en termes de ressources physiques : processeur, mémoire, espace disque, etc.
  
En outre, vous pouvez céquequer le serveur principal du serveur de conversation permanente et la base de données de conformité de conversation permanente (si elle est activée) sur le serveur SQL Server Express principal. Vous pouvez également choisir d’utiliser une instance SQL Server avec une instance dédiée. 
  
> [!IMPORTANT]
> Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de conversation permanente si le premier serveur de conversation permanente est coqueté avec Édition Standard serveur frontal. Il est recommandé d’installer le premier serveur en tant qu’instance autonome afin de pouvoir ajouter d’autres serveurs ultérieurement, si nécessaire. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Édition Standard Serveur avec serveur de conversation permanente installé sur un serveur distinct

Avec Édition Standard, vous pouvez installer le serveur de conversation permanente en tant qu’instance autonome et ajouter d’autres serveurs ultérieurement si nécessaire. 
  
Vous pouvez céquequer le serveur principal du serveur de conversation permanente et la base de données de conformité de conversation permanente (si elle est activée) sur le serveur SQL Server Express principal. Vous pouvez également choisir d’utiliser une instance SQL Server avec une instance dédiée. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Êdition Entreprise Serveur avec un seul serveur de conversation permanente

Avec Êdition Entreprise, vous devez installer le serveur de conversation permanente sur un ordinateur distinct. C’est-à-dire que vous ne pouvez pas céquerifier le serveur de conversation permanente sur Êdition Entreprise serveur frontal. Ce déploiement nécessite un serveur distinct qui exécute le serveur de conversation permanente et le service de conformité (s’il est activé).
  
Toutefois, vous pouvez céquequer la base de données SQL Server pour le serveur de conversation permanente sur la base de données principale d’Êdition Entreprise pool frontal.
  
> [!NOTE]
> Si vous prévoyez d’SQL groupes de disponibilité AlwaysOn pour la haute disponibilité de haute disponibilité, notez qu’il n’est pas pris en charge pour les bases de données du serveur de conversation permanente. 
  
Si vous coloquez la base de données de conversation permanente avec la base de données principale, vous pouvez utiliser une instance unique de SQL Server pour une ou l’ensemble des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données.
  
> [!IMPORTANT]
> Le serveur hébergeant la base de données de conversation permanente peut héberger d’autres bases de données. Toutefois, lorsque vous envisagez de céquequer la base de données de conversation permanente avec d’autres bases de données, sachez que si vous stockez les messages de plusieurs utilisateurs, l’espace disque nécessaire à la base de données de conversation permanente peut devenir très important. C’est la raison pour laquelle nous vous déconseillons de céquequer la base de données de conversation permanente avec la base de données principale. 
  
La figure suivante montre tous les composants d’une topologie pour un serveur de conversation permanente unique avec la conformité activée (facultatif).
  
**Topologie à un seul serveur**

![Serveur de conversation permanente - Topologie à serveur unique.](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Êdition Entreprise Serveur avec plusieurs serveurs de conversation permanente

Avec Êdition Entreprise, vous pouvez déployer une topologie à plusieurs serveurs pour une capacité et une fiabilité accrues. Une topologie à plusieurs serveurs est identique à la topologie à serveur unique, sauf que plusieurs serveurs hébergent un serveur de conversation permanente et peuvent être plus importantes. La topologie à plusieurs serveurs peut inclure jusqu’à quatre ordinateurs actifs exécutant le serveur de conversation permanente (les configurations de haute disponibilité et de récupération d’urgence autorisent jusqu’à huit, mais seuls quatre peuvent être actifs et les quatre autres en veille). Chaque serveur peut prendre en charge jusqu’à 20 000 utilisateurs simultanés, pour un total de 80 000 utilisateurs simultanés connectés à un pool de serveurs de conversation permanente avec 4 serveurs. Plusieurs ordinateurs exécutant le serveur de conversation permanente doivent résider dans le même domaine services de domaine Active Directory que Skype Entreprise Server et le service de conformité.
  
La figure suivante montre tous les composants d’une topologie à plusieurs serveurs avec plusieurs ordinateurs exécutant le serveur de conversation permanente, le service de conformité facultatif et une base de données de conformité distincte.
  
**Topologie à plusieurs serveurs**

![Serveur de conversation permanente : topologie à plusieurs serveurs.](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de conversation permanente communiquent et partagent des données. Par exemple, l’historique de conversation initialement publié dans un service de conversation permanente est disponible à partir de n’importe quel service de conversation permanente dans le système. Un fichier téléchargé via un service de conversation permanente est accessible par n’importe quel service de conversation permanente. Les utilisateurs peuvent être connectés à différents serveurs frontaux du serveur de conversation permanente et peuvent communiquer entre eux. Le port par défaut du port TCP 8011 connecte un serveur à un pool de serveurs et est utilisé par les services de conversation permanente pour communiquer entre eux ou à des fins d’administration.
  
Par exemple, dans un déploiement de serveur de conversation permanente à quatre serveurs, où 80 000 utilisateurs peuvent être simultanément inscrits à la conversation permanente, la charge est répartie uniformément à 20 000 utilisateurs par serveur. Si un serveur devient indisponible, les utilisateurs connectés à ce serveur perdent leur accès au serveur de conversation permanente. Les utilisateurs déconnectés seront automatiquement transférés sur les serveurs restants jusqu’au rétablissement du serveur indisponible. 
  

