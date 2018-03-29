---
title: Planification de l’archivage dans Skype Entreprise Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier un archivage dans Skype pour Business Server 2015.'
ms.openlocfilehash: 53895a404c2502a0d54553fda979add6031b09f6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-archiving-in-skype-for-business-server-2015"></a>Planification de l’archivage dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment planifier un archivage dans Skype pour Business Server 2015.
  
Les grandes entreprises et autres organisations sont soumises à un nombre croissant de réglementations nationales et industrielles nécessitant la conservation de types spécifiques de communications. Si votre organisation dispose de ces exigences, vous pouvez utiliser l’option d’archivage dans Skype pour Business Server 2015 d’archivage de la messagerie instantanée (IM) et les communications de la conférence (meeting) pour vous aider à prendre en charge certaines de vos exigences de conformité.
  
## <a name="archiving-components"></a>Composants d’archivage

Skype pour Business Server utilise les composants suivants de l’archivage :
  
- **Argents d’archivage**. Les agents d’archivage (également connus sous le nom d’agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et serveur Standard Edition. Même si les agents d’archivage sont activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré. L’archivage est désactivé par défaut.
    
- **Archivage du stockage des données**. Stockage de données pour Skype pour 2015 de serveur d’entreprise peut être implémenté en tant que Skype pour les bases de données de SQL Server Business Server ou, si vous disposez d’un déploiement Exchange, intégrant le stockage Exchange. 
    
L’archivage nécessite également le stockage de fichiers. Cependant, l’archivage utilise le même type de stockage de fichiers que les serveurs frontaux ou le serveur Standard Edition.
  
Pour une liste des exigences matérielles et logicielles pour l’archivage, voir [configuration matérielle et logicielle pour l’archivage dans Skype pour Business Server 2015](hardware-and-software-requirements.md).
  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Définition des besoins de votre organisation pour l’archivage

Pour implémenter l’archivage, vous devez décider comment répondre aux besoins de votre entreprise pour l’archivage par déterminer les éléments suivants :
  
- **Quelle option de stockage utiliser**. Vous pouvez implémenter le stockage de l’une des deux façons ou utiliser une combinaison des deux :
    
  - **Stockage pour Exchange.** Si vous disposez d’un déploiement Exchange, vous pouvez intégrer Skype pour Business Server et de l’archivage Exchange afin que votre Skype pour Business Server et les données Exchange archivé sont stockés et rassemblés dans Exchange. Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres hébergement sur l’utilisation d’Exchange Server Exchange de stockage pour les données archivées, mais uniquement si les boîtes aux lettres ont été mis en Place retenu. Par défaut, intégration de Microsoft Exchange n’est pas activée.
    
  - **Skype pour le stockage du serveur de l’entreprise.** Si vous avez des utilisateurs qui ne sont pas hébergées sur Exchange ou qui n’ont pas leurs boîtes aux lettres mis en Place maintenez, ou si vous ne souhaitez pas utiliser l’intégration de Microsoft Exchange pour les utilisateurs de tout ou partie de votre déploiement, vous pouvez déployer Skype pour les bases de données d’archivage de Server Business à l’aide de S QL Server.
    
- **Quand déployer l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre Skype initiale pour le déploiement du serveur de l’entreprise, ou vous pouvez l’ajouter à un déploiement existant. Pour utiliser Skype pour le stockage d’archivage Business Server (bases de données SQL Server), vous le Générateur de topologies permet d’ajouter les bases de données à votre topologie et puis publiez de nouveau la topologie. Si tous vos utilisateurs sont hébergés sur Exchange et que leurs boîtes aux lettres sur Place maintenez, vous n’avez pas à mettre à jour votre topologie, mais vous ne devez activer l’intégration de Microsoft Exchange stocker les données archivées dans Exchange. 
    
- **Quels sont les sites et les utilisateurs d’une organisation qui nécessitent l’archivage**. Vous pouvez configurer les paramètres d’archivage pour toute votre organisation et, le cas échéant, pour des sites, des pools, des utilisateurs et des groupes.
    
- **Quel contenu archiver**. Que l’archivage soit spécifié au niveau global ou pour des sites et utilisateurs spécifiques, à chacun de ces niveaux, vous devez spécifier si vous activez l’archivage pour les types de contenu suivants : 
    
  - Messages instantanés P2P
    
  - Conférences (réunions) sous forme de messages instantanés entre plusieurs participants
    
  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)
    
  - Tableaux blancs et sondages partagés durant une conférence
    
- **Le contenu qui ne peut pas être archivé**. Les types de contenu suivants ne peuvent pas être archivés : 
    
  - Transfert de fichiers d’égal à égal
    
  - Audio/vidéo pour messages instantanés et conférences P2P
    
  - Partage d’application et de Bureau pour messages instantanés et conférences d’égal à égal
    
    Skype pour Business Server n’archive également les conversations de Chat persistant. Pour archiver les conversations de Chat permanente, vous devez activer et configurer le service de mise en conformité, qui est un composant qui peut être déployé avec le serveur de conversation persistant. Pour plus d’informations, consultez [planification de serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).
    
- **Quelle doit être la durée de conservation du contenu archivé**. La base de données d’archivage n’est pas conçue pour la rétention à long terme et Skype pour Business Server ne fournit pas une solution e-discovery (recherche) pour les données archivées, les données doivent être déplacés vers d’autres systèmes de stockage. Skype pour Business Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées, et qui crée des transcriptions disponible pour la recherche de données archivées. 
    
     Pour la stratégie globale et pour chaque stratégie de site et d’utilisateur que vous créez, vous pouvez spécifier quand purger les données archivées et exportées. Pour plus d’informations sur la purge des données, voir [Gérer la purge des données archivées dans Skype pour Business Server 2015](../../manage/archiving/purging-of-archived-data.md). Pour plus d’informations sur l’utilisation de la session d’outil d’exportation, voir [exporter des données archivées dans Skype pour Business Server 2015](../../manage/archiving/export-archived-data.md).
    
- **Archivage des communications internes ou externes**. Vous pouvez activer l’archivage pour les communications internes (communications entre les utilisateurs internes) et/ou les communications externes (communications incluant au moins un utilisateur externe à votre réseau interne). Vous pouvez spécifier ces options pour l’ensemble de votre organisation, ou pour des sites et pools spécifiques. Par défaut, aucune des ces options n’est activée.
    
    > [!NOTE]
    > Contrôle de l’archivage des communications internes ou externes n’est disponible pour Skype pour la stratégie d’entreprise. Pour Exchange intégré d’archivage, les communications internes et externes sont archivées ou pas archivées. 
  
- **Implémenter le mode critique**. Si l’archivage est un besoin de votre organisation, configuration mode critique bloquera les sessions de messagerie instantanée et de conférence dans le cas d’un Skype pour Échec de Business Server qui peut empêcher l’archivage. Par exemple : 
    
  - Un problème avec le Skype pour le service de stockage de serveur de l’entreprise. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs qui sont activés pour l’archivage.
    
  - Un partage de fichiers non disponible ou un problème au niveau du service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de la défaillance passent en mode restreint et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Choisir les options de configuration et de déploiement de l’archivage

L’archivage est automatiquement installé sur chaque serveur frontal lorsque vous déployez le serveur, mais l’archivage n’est pas activé jusqu'à ce que vous le configurez. La configuration de l’archivage est déterminé par la façon dont vous le déployez. Vous pouvez déployer l’archivage dans une des manières suivantes :
  
- Utilisez le stockage de Microsoft Exchange
    
- Utiliser Skype pour le stockage du serveur de l’entreprise
    
> [!NOTE]
> Si vous implémentez à la fois Skype pour bases de données d’archivage de Server Business et activez l’intégration de Microsoft Exchange, les stratégies Exchange substituent Skype pour Business Server politiques d’archivage, mais uniquement pour les utilisateurs qui sont hébergés sur Exchange et ont leurs boîtes aux lettres mis sur Maintenir en Place. Skype pour un archivage d’entreprise dépend de la stratégie Microsoft Exchange Place maintenez. 
  
Si vous déployez l’archivage pour un pool frontal ou un serveur Standard Edition Server, vous devez l’activer pour tous les autres pools de Front-End et les serveurs Standard Edition Server dans votre déploiement. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, il est possible que toutes les données de conférence ne soient pas archivées. L’archivage fonctionnera toujours pour les messages instantanés, mais il est possible que le contenu des conférences et les événements ne soient pas archivés.
  
> [!NOTE]
> Pour activer la délégation des tâches administratives, tout en conservant des normes de sécurité de votre organisation, Skype pour Business Server utilise le contrôle d’accès basé sur les rôles (RBAC). Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis. Pour configurer Skype pour les configurations et les stratégies d’archivage d’entreprise, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (sauf si la configuration est effectuée directement sur le serveur où l’archivage est déployé, et non à distance à partir d’un autre ordinateur ). Pour obtenir la liste des droits d’utilisateur, autorisations et rôles requis pour l’archivage de déploiement, reportez-vous à la section [déployer l’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si vous utilisez l’intégration de Microsoft Exchange, la configuration de stratégies Exchange nécessite des autorisations et des droits d’administration appropriés. Pour plus d’informations, consultez la documentation d’Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Stockage de Microsoft Exchange

 Si vous choisissez d’intégration de Microsoft Exchange, vous utilisez les configurations et les stratégies Exchange pour contrôler l’archivage de Skype pour Business Server. Vous pouvez configurer l’option d’intégration de Microsoft Exchange au niveau global, au niveau du site et au niveau du pool. Si votre déploiement inclut plusieurs forêts, vous devez synchroniser les paramètres entre Skype pour Business Server et Exchange. Vous devez déterminer si :
  
- vous devez archiver la messagerie instantanée, les conférences ou les deux ;
    
- Si vous souhaitez implémenter le mode critique, ce qui bloque les sessions de messagerie instantanée et de conférence dans le cas d’un Skype de défaillance du serveur de l’entreprise 
    
- Sélection de l’option d’intégration de Microsoft Exchange pour utiliser Exchange pour le stockage des données archivées
    
Pour plus d’informations sur la configuration Exchange contenir de Place les stratégies et les paramètres pour prendre en charge de l’archivage, consultez la documentation du produit Exchange.
  
### <a name="skype-for-business-server-storage"></a>Stockage Skype Entreprise Server

Si vous choisissez Skype pour le stockage du serveur de l’entreprise, Skype pour les configurations et les stratégies d’archivage Business Server vous permet de contrôler comment l’archivage est activé et mis en œuvre. Skype pour le stockage de Business Server utilise les bases de données SQL Server, vous devez ajouter les bases de données SQL Server appropriés à votre topologie, puis configurer les stratégies d’archivage. 
  
### <a name="add-storage-databases-to-your-topology"></a>Ajouter des bases de données à votre topologie

Lors de l’ajout de bases de données SQL Server à votre topologie, vous pouvez choisir colocaliser des bases de données d’archivage avec une des opérations suivantes :
  
- Base de données de surveillance
    
- Base de données principale d’un pool frontal Enterprise Edition
    
> [!NOTE]
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Cependant, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale. 
  
Si vous colocaliser la base de données d’archivage avec la base de données de surveillance, de la base de données back-end ou les deux de ces bases de données, vous pouvez utiliser une seule instance SQL pour tout ou partie des bases de données, ou vous pouvez utiliser une instance distincte de SQL pour chaque base de données, avec les éléments suivants limitation : instance de chaque SQL peut contenir uniquement une seule base de données back-end unique analyse de base de données et une base de données d’archivage unique.
  
Pour plus d’informations sur la colocalisation de tous les rôles de serveur et les bases de données, consultez [Notions fondamentales de la topologie pour Skype pour Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md). Pour plus d’informations sur la mise à jour de votre topologie, afin d’inclure des bases de données de stockage, reportez-vous à la section [créer et publier la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Déterminer les options d’archivage et les stratégies utilisateur

Vous devez déterminer si vous devez :
  
- Activer ou désactiver l’archivage pour les communications internes et externes
    
- Archiver la messagerie instantanée et/ou les conférences
    
- Si vous souhaitez implémenter le mode critique, ce qui bloque les sessions de messagerie instantanée et de conférence dans le cas d’un Skype de défaillance du serveur de l’entreprise 
    
- Activer des stratégies pour des utilisateurs et des groupes spécifiques
    
Skype pour les options d’archivage de serveur Business peut être spécifié aux niveaux suivants. 
  
- **Option de niveau globale**. Cette configuration d’archivage par défaut et s’applique à tout votre déploiement. Il est créé lorsque vous déployez Skype pour Business Server et, par défaut, désactive l’archivage des communications internes et externes. Vous ne pouvez pas supprimer cette option. Si vous choisissez l’option Supprimer, l’option globale est réinitialisée les paramètres par défaut.
    
- **Options de niveau Site**. Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une option d’archivage au niveau du site. Vous pouvez supprimer toute option d’archivage au niveau du site que vous créez. Une option d’archivage au niveau du site remplace l’option globale, mais seulement pour le site spécifié dans l’option. 
    
    Par exemple, si vous activez l’archivage des communications internes et externes dans votre configuration globale et si vous créez une configuration de site dans laquelle vous désactivez l’archivage des communications externes, seules les communications internes sont archivées pour ce site. Autre exemple, si vous activez l’archivage de la messagerie instantanée uniquement dans votre configuration globale et si vous créez une configuration de site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences, ces dernières ne sont archivées que pour le site et non pour le reste de votre organisation.
    
- **Options de niveau pool**. Vous pouvez spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour un pool particulier. Une configuration d’archivage au niveau du pool n’existe que si vous la créez. Vous pouvez modifier et supprimer une configuration d’archivage au niveau du pool. Une configuration d’archivage au niveau du pool remplace la configuration globale et les configurations d’archivage de site que vous avez créées. 
    
    Par exemple, si vous activez uniquement l’archivage de la messagerie instantanée dans votre configuration globale, créez une configuration au niveau du site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences pour le site, puis créez une configuration au niveau du pool dans laquelle vous activez uniquement l’archivage de la messagerie instantanée. Les communications relatives à la messagerie instantanée et aux conférences sont archivées pour tous les utilisateurs du site à l’exception des utilisateurs hébergés au sein du pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, seul l’archivage de la messagerie instantanée est activé.
    
- **Stratégies d’archivage utilisateur**. Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, en configurant et en appliquant une stratégie d’archivage au niveau de l’utilisateur pour les utilisateurs et groupes d’utilisateurs spécifiés. Vous pouvez supprimer les stratégies d’archivage au niveau de l’utilisateur que vous avez créées. En outre, vous pouvez modifier les utilisateurs et groupes d’utilisateurs auxquels la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau de l’utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et groupes d’utilisateurs auxquels la stratégie est appliquée.. 
    
    Par exemple, si vous désactivez l’archivage des communications internes et externes dans votre stratégie globale, créez une stratégie au niveau du site dans laquelle vous activez l’archivage des communications internes et externes, puis créez une stratégie au niveau de l’utilisateur dans laquelle vous désactivez l’archivage des communications externes. Dans ce cas, les communications internes et externes sont archivées pour tous les utilisateurs du site, sauf pour les utilisateurs auxquels vous appliquez la stratégie au niveau de l’utilisateur, où seules les communications internes sont archivées.
    
Pour plus d’informations sur le paramétrage des configurations d’archivage initiales lorsque vous déployez d’archivage, consultez [déploiement d’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md). Pour plus d’informations sur la gestion de l’archivage après le déploiement, consultez [gérer l’archivage dans Skype pour Business Server 2015](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Outils de configuration l’archivage

 Vous contrôlez la plupart des options d’archivage pour le panneau de configuration de Business Server à l’aide de la Skype. Toutefois, il existe quelques options disponibles uniquement en utilisant le Skype pour Business Server Management Shell. Ces options incluent d’archivage des messages en double et l’exportation des données archivées. Pour plus d’informations sur l’utilisation de la Skype pour panneau de Business Server et le Skype pour Business Server Management Shell pour gérer les stratégies d’archivage, reportez-vous à la section [gérer l’archivage dans Skype pour Business Server 2015](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Accès aux données archivées

L’accès aux données archivées dépend de l’emplacement où les données sont stockées : 
  
- **Stockage de Microsoft Exchange**. Si vous choisissez l’option d’intégration Exchange, Skype pour Business Server dépôts du contenu d’archivage dans la banque Exchange pour tous les utilisateurs qui sont hébergés sur Exchange et qui ont eu à leurs boîtes aux lettres mis en Place maintenez. Les données archivées sont stockées dans le dossier d’éléments récupérables de boîtes aux lettres utilisateur, qui est généralement invisible aux yeux des utilisateurs et peut uniquement être explorée par les utilisateurs ayant un rôle Exchange, **Gestion de découverte** . Exchange active fédérées de recherche et de découverte, ainsi que de SharePoint, si elle est déployée. Pour plus d’informations sur le stockage, la rétention et la recherche des données stockées dans Exchange, voir la documentation Exchange et SharePoint.
    
- **Skype pour le stockage d’archivage du serveur de l’entreprise**. Si vous configurez Skype pour bases de données d’archivage de Server Business, Skype pour les dépôts Business Server d’archivage ne pas de contenu dans le Skype pour bases de données d’archivage de Server entreprise pour tous les utilisateurs hébergés sur Exchange et qui n’ont pas leurs boîtes aux lettres mis en Place maintenez. Ces données peuvent faire l’objet de recherches, mais peuvent également être exportées vers des formats autorisant les recherches à l’aide d’autres outils. Pour plus d’informations sur l’exportation des données stockées dans les bases de données d’archivage, voir [exporter des données archivées dans Skype pour Business Server 2015](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur l’archivage, consultez les rubriques suivantes :
  
- [Déployer l’archivage pour Skype pour Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gérer l’archivage dans Skype pour Business Server 2015](../../manage/archiving/archiving.md)
    
Pour plus d’informations sur la façon de Skype pour Business Server et Exchange collaborent, reportez-vous à la section [planifier l’intégration de Skype pour les entreprises et Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

