---
title: Planification de la topologie du serveur de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 'Résumé : cette rubrique vous permet d’en savoir plus sur les composants et les topologies serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: afcdf7ed85cca6b54652dcf5170316258a6b5551
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815722"
---
# <a name="plan-persistent-chat-server-topology"></a>Planification de la topologie du serveur de conversation permanente
 
**Résumé :** Consultez cette rubrique pour en savoir plus sur les composants et topologies serveur Chat permanent dans Skype entreprise Server 2015.
  
Le serveur Chat permanent prend en charge les configurations à un serveur et à plusieurs serveurs. Vous pouvez installer le serveur Chat permanent sur Skype entreprise Server 2015 Enterprise Edition ou Standard Edition Server. 

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
  
## <a name="persistent-chat-server-components"></a>Composants serveur de chat permanent

Le serveur de conversation permanente comprend les composants suivants :
  
- Un ou plusieurs ordinateurs exécutant un serveur Chat permanent et fournissant les services suivants :
    
  - Service Chat permanent
    
  - Service de conformité, activé si la conformité est activée
    
- Un ou plusieurs serveurs (en plus d’un en miroir) exécutent la base de données principale de SQL Server pour l’hébergement de la base de données de contenu de conversation permanente où le contenu, les salles et les catégories de salle de conversation sont stockés.
    
    > [!NOTE]
    > La base de données principale stocke les données de l’historique des conversations, y compris les informations sur les catégories et les salles de conversation permanentes qui sont créées. 
  
- Si la conformité est activée, un ou plusieurs serveurs (en plus d’un en miroir) exécutent la base de données principale de SQL Server pour l’hébergement de la base de données de compatibilité des conversations permanentes, où les événements de conformité et les contenus de discussion dans le cadre de la conformité sont stockés.
    
Pour plus d’informations sur les configurations matérielles et logicielles requises pour le serveur de chat permanent, voir [Configuration requise pour Skype entreprise server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) et configurations [matérielle et logicielle requises pour le serveur de chat permanent dans skype entreprise Server 2015](hardware-and-software-requirements.md). 
  
## <a name="persistent-chat-server-topologies"></a>Topologies serveur de chat permanent

Vous pouvez déployer le serveur de chat permanent dans les pools serveur unique ou serveur multiples, avec une topologie à pool unique ou à plusieurs pools. Le serveur Chat permanent prend en charge les topologies suivantes :
  
-  Serveur Standard Edition avec serveur de conversation permanente colocalisé sur le serveur frontal
    
-  Serveur Standard Edition avec serveur de conversation permanent sur un serveur distinct
    
-  Serveur Enterprise Edition avec un serveur de chat permanent unique sur un serveur distinct
    
-  Serveur Enterprise Edition avec plusieurs serveurs de chat permanents sur des serveurs distincts
    
Même si vous pouvez déployer le serveur Chat permanent sur un serveur Standard Edition Server, sachez que les performances et l’évolutivité seront affectées et qu’une disponibilité élevée n’est pas une option. Par conséquent, nous vous conseillons de déployer une conversation persistante sur un serveur Standard Edition Server essentiellement pour la preuve de concept et d’évaluation. 
  
Skype entreprise Server 2015 prend en charge un large éventail de scénarios de colocalisation qui vous permettent de gagner en souplesse en exécutant plusieurs composants sur un serveur (si vous disposez d’une petite organisation) ou pour exécuter des composants individuels sur des serveurs différents ( Si votre organisation exige une évolutivité et des performances optimales. Vous devez considérer les facteurs d’extensibilité avant de décider si vous allez colocaliser des composants. Les scénarios de coorganisation diffèrent pour les serveurs Skype entreprise Server 2015 Enterprise Edition et Standard Edition. 
  
Les sections suivantes décrivent les topologies plus en détail, notamment les scénarios de colocalisation et les options des serveurs de base de données principale. Pour plus d’informations sur la colocalisation de tous les rôles de serveur et bases de données, voir notions de base de la [topologie pour Skype entreprise server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>Serveur Standard Edition avec serveur de conversation permanente colocalisé sur le serveur frontal

Avec Standard Edition, vous pouvez colocaliser la conversation permanente sur le serveur frontal. Il s’agit de la configuration la plus simple et la plus basique. Vous devez vous assurer que le serveur frontal actuel dispose d’une capacité suffisante en termes de ressources physiques : processeur, mémoire, espace disque, etc.
  
De plus, vous pouvez collocate du serveur principal de chat permanent et de la base de données de conformité des discussions persistantes (si elle est activée) sur le serveur principal SQL Server Express local. Vous pouvez également choisir d’utiliser un serveur SQL Server distinct avec une instance dédiée. 
  
> [!IMPORTANT]
> Vous ne pouvez pas ajouter de serveurs supplémentaires à un pool de serveurs de chat permanent si le premier serveur de chat permanent est colocalisé avec un serveur frontal Standard Edition. Nous vous recommandons d’installer le premier serveur en tant qu’instance autonome pour pouvoir ajouter d’autres serveurs ultérieurement si nécessaire. 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Serveur Standard Edition avec serveur de conversation permanente installé sur un serveur distinct

Avec Standard Edition, vous pouvez installer le serveur de conversation permanente en tant qu’instance autonome et ajouter d’autres serveurs ultérieurement si besoin.   
  
Vous pouvez collocate du serveur principal serveur Chat permanent et de la base de données de conformité des conversations Permanentles (si activée) sur le serveur principal SQL Server Express local. Vous pouvez également choisir d’utiliser un serveur SQL Server distinct avec une instance dédiée. 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>Serveur Enterprise Edition avec un seul serveur de conversation permanente

Avec Enterprise Edition, vous devez installer le serveur de conversation permanente sur un ordinateur distinct. Ainsi, vous ne pouvez pas colocaliser le serveur de conversation permanente sur le serveur frontal Enterprise Edition. Ce déploiement nécessite un serveur distinct qui exécute le serveur Chat permanent et le service de conformité (s’il est activé).
  
Toutefois, vous pouvez collocate la base de données SQL Server pour le serveur de chat permanent sur la base de données principale d’un pool frontal Enterprise Edition.
  
> [!NOTE]
> Si vous prévoyez d'utiliser des groupes de disponibilité AlwaysOn SQL pour la récupération d’urgence de haute disponibilité, notez que cette fonctionnalité n'est pas prise en charge pour les bases de donnés de serveur de conversation permanente. 
  
Si vous collocate la base de données de chat permanent avec la base de données principale, vous pouvez utiliser une instance unique de SQL Server pour tout ou partie des bases de données, ou vous pouvez utiliser une instance distincte de SQL Server pour chaque base de données.
  
> [!IMPORTANT]
> Le serveur qui héberge la base de données de chat permanent peut héberger d’autres bases de données. Toutefois, si vous envisagez de collocating la base de données de chat persistante avec d’autres bases de données, n’ayez pas besoin d’augmenter la taille de la base de données de chat persistante. C’est pourquoi nous vous déconseillons de collocating la base de données de chat persistante avec la base de données principale. 
  
La figure suivante montre tous les composants d’une topologie pour un serveur de chat permanent unique avec conformité activée (facultatif).
  
**Topologie à serveur unique**

![Serveur de conversation permanente - Topologie à serveur unique](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>Serveur Enterprise Edition avec plusieurs serveurs de conversation permanente

Avec Enterprise Edition, vous pouvez déployer une topologie multiserveur pour une plus grande capacité et fiabilité. Une topologie multiserveur est la même que celle de la topologie sur un serveur, à l’exception de l’hébergement de plusieurs serveurs et de la possibilité d’augmenter leur taille. La topologie multiserveur peut inclure jusqu’à quatre ordinateurs actifs exécutant chat permanent (les configurations de haute disponibilité et de récupération d’urgence peuvent prendre jusqu’à 8, mais seules quatre peuvent être actives et les quatre autres en veille). Chaque serveur peut prendre en charge autant d’utilisateurs simultanés qu' 20 000, soit un total d' 80 000 utilisateurs simultanés connectés à un pool de serveurs de chat permanent doté de 4 serveurs. Plusieurs ordinateurs exécutant un serveur Chat permanent doivent résider dans le même domaine de services de domaine Active Directory que Skype entreprise Server et le service de conformité.
  
La figure suivante montre tous les composants d’une topologie multiserveur avec plusieurs ordinateurs exécutant une conversation permanente serveur, le service de conformité facultatif et une base de données de conformité séparée.
  
**Topologie à plusieurs serveurs**

![Serveur de conversation permanente - Topologie à plusieurs serveurs](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
Les topologies à plusieurs serveurs permettent de regrouper les fonctionnalités des serveurs. Dans un pool de serveurs, les services de chat permanent communiquent et partagent des données. Par exemple, l’historique des discussions publié à l’origine dans un service de chat permanent est disponible à partir de n’importe quel service de chat permanent du système. Un service de chat permanent peut accéder à un fichier téléchargé par le biais d’un service de chat permanent. Les utilisateurs peuvent se connecter à différents serveurs front-end serveur de chat permanent et peuvent communiquer entre eux. Le port TCP 8011 par défaut connecte un serveur à un pool de serveurs et est utilisé par les services de chat permanent pour communiquer entre eux ou à des fins d’administration.
  
Par exemple, dans le cas d’un déploiement de serveur de chat permanent sur quatre serveurs, où les utilisateurs de 80 000 peuvent être connectés simultanément à une conversation permanente, le chargement est distribué de façon égale auprès des utilisateurs 20 000 par serveur. Si un serveur devient indisponible, les utilisateurs qui se connectent à ce serveur perdront leur accès au serveur Chat permanent. Ces utilisateurs déconnectés sont alors automatiquement transférés vers les serveurs restants jusqu’à ce que le serveur indisponible soit restauré. 
  

