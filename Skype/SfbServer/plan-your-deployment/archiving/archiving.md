---
title: Planifier l’archivage dans Skype pour Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier l’archivage dans Skype pour Business Server.'
ms.openlocfilehash: 164a3207153986e788a7db47b86014063e37e0e5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236115"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planifier l’archivage dans Skype pour Business Server
 
**Résumé :** Lisez cette rubrique pour savoir comment planifier l’archivage dans Skype pour Business Server.
  
Les grandes entreprises et autres organisations sont soumises à un nombre croissant de réglementations nationales et industrielles nécessitant la conservation de types spécifiques de communications. Si votre organisation dispose de ces exigences, vous pouvez utiliser l’archivage dans Skype pour Business Server d’archivage de la messagerie instantanée et les communications de conférence (réunion) pour vous aider à prendre en charge certaines de vos exigences de conformité.
  
## <a name="archiving-components"></a>Composants d’archivage

Skype pour Business Server utilise les composants d’archivage suivantes :
  
- **Argents d’archivage**. Les agents d’archivage (également connus sous le nom d’agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et serveur Standard Edition. Même si les agents d’archivage sont activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré. L’archivage est désactivé par défaut.
    
- **Archivage du stockage des données**. Stockage des données pour Skype pour Business Server peut être implémentée en tant que Skype pour les bases de données métiers serveur SQL Server, ou, si vous disposez d’un déploiement Exchange, intégrée avec le stockage Exchange. 
    
L’archivage nécessite également le stockage de fichiers. Cependant, l’archivage utilise le même type de stockage de fichiers que les serveurs frontaux ou le serveur Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Définition des besoins de votre organisation pour l’archivage

Pour implémenter l’archivage, vous devez décider comment répondre aux besoins de votre organisation pour l’archivage à déterminer les éléments suivants :
  
- **Quelle option de stockage utiliser**. Vous pouvez implémenter le stockage de l’une des deux façons ou utiliser une combinaison des deux :
    
  - **Stockage Exchange.** Si vous disposez d’un déploiement Exchange, vous pouvez intégrer Skype pour Business Server et de l’archivage Exchange afin que votre Skype pour Business Server et des données Exchange archivé sont stockés ensemble dans Exchange. Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres utilisateur hébergement sur l’utilisation d’Exchange Server stockage Exchange pour des données archivées, mais uniquement si les boîtes aux lettres ont été placées en archive permanente. Par défaut, l’intégration de Microsoft Exchange n’est pas activée.
    
  - **Skype pour le stockage de serveur d’entreprise.** Si vous avez des utilisateurs qui ne sont pas hébergés sur Exchange ou qui n’ont pas leurs boîtes aux lettres mettre en blocage sur Place, ou si vous ne souhaitez pas utiliser l’intégration de Microsoft Exchange pour un ou tous les utilisateurs dans votre déploiement, vous pouvez déployer Skype pour les bases de données d’archivage de serveur métiers à l’aide de S SQL Server.
    
- **Quand déployer l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre Skype initiale pour le déploiement de serveur d’entreprise, ou vous pouvez l’ajouter à un déploiement existant. Pour utiliser Skype pour le stockage d’archivage Business Server (bases de données SQL Server), vous utilisez le Générateur de topologie pour ajouter les bases de données à votre topologie, puis publiez la topologie à nouveau. Si tous vos utilisateurs sont hébergés sur Exchange et mettre les boîtes aux lettres en blocage sur Place, vous n’avez pas à mettre à jour votre topologie, mais il souhaitez d’activer l’intégration de Microsoft Exchange stocker les données archivées dans Exchange. 
    
- **Quels sont les sites et les utilisateurs d’une organisation qui nécessitent l’archivage**. Vous pouvez configurer les paramètres d’archivage pour votre organisation et, éventuellement, pour des sites spécifiques, les pools, les utilisateurs et groupes d’utilisateurs.
    
- **Quel contenu archiver**. Que l’archivage soit spécifié au niveau global ou pour des sites et utilisateurs spécifiques, à chacun de ces niveaux, vous devez spécifier si vous activez l’archivage pour les types de contenu suivants : 
    
  - Messages instantanés P2P
    
  - Conférences (réunions) sous forme de messages instantanés entre plusieurs participants
    
  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)
    
  - Tableaux blancs et sondages partagés durant une conférence
    
- **Le contenu qui ne peut pas être archivé**. Les types de contenu suivants ne peuvent pas être archivés : 
    
  - Transfert de fichiers d’égal à égal
    
  - Audio/vidéo pour messages instantanés et conférences P2P
    
  - Partage d’application et de Bureau pour messages instantanés et conférences d’égal à égal
    
    Skype pour Business Server n’archive également les conversations de conversation permanente. Pour archiver les conversations de conversation permanente, vous devez activer et configurer le service de conformité, qui est un composant qui peut être déployé avec le serveur de conversation permanente. Pour plus d’informations, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
    
- **Quelle doit être la durée de conservation du contenu archivé**. La base de données d’archivage n’est pas conçue pour la rétention à long terme et Skype pour Business Server ne fournit pas une solution d’e-discovery (recherche) pour les données archivées, afin que les données doivent être déplacés vers d’autres systèmes de stockage. Skype pour Business Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées, et qui crée des transcriptions de recherche des données archivées. 
    
     Pour la stratégie globale et pour chaque stratégie de site et d’utilisateur que vous créez, vous pouvez spécifier à quel moment vider les données archivées et exportées. Pour plus d’informations sur le vidage des données, voir [Gérer la purge des données archivées dans Skype pour Business Server](../../manage/archiving/purging-of-archived-data.md). Pour plus d’informations sur l’utilisation de la session d’exportation outil, voir [exporter des données archivées dans Skype pour Business Server](../../manage/archiving/export-archived-data.md).
    
- **Archivage des communications internes ou externes**. Vous pouvez activer l’archivage pour les communications internes (communications entre les utilisateurs internes) et/ou les communications externes (communications incluant au moins un utilisateur externe à votre réseau interne). Vous pouvez spécifier ces options pour l’ensemble de votre organisation, ou pour des sites et pools spécifiques. Par défaut, aucune des ces options n’est activée.
    
    > [!NOTE]
    > Contrôler l’archivage des communications internes ou externes n’est disponible pour Skype pour la stratégie d’entreprise. Pour Exchange intégré d’archivage, les communications internes et externes sont archivées ou pas archivées. 
  
- **Implémenter le mode critique**. Si l’archivage est une condition requise pour votre organisation, configuration du mode critique bloquer les sessions de messagerie instantanée et la conférence en cas d’un Skype pour Échec Business Server qui empêche l’archivage. Par exemple : 
    
  - Un problème avec le Skype pour le service de stockage Business Server. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs qui sont activés pour l’archivage.
    
  - Un partage de fichiers non disponible ou un problème au niveau du service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de la défaillance passent en mode restreint et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Choisir les options de configuration et de déploiement de l’archivage

L’archivage est automatiquement installé sur chaque serveur frontal lorsque vous déployez le serveur, mais l’archivage n’est pas activé jusqu'à ce que vous configurez. Comment configurer l’archivage est déterminé par la façon de déployer. Vous pouvez déployer l’archivage dans une des manières suivantes :
  
- Utiliser le stockage de Microsoft Exchange
    
- Utiliser Skype pour le stockage de serveur d’entreprise
    
> [!NOTE]
> Si vous implémentez les deux Skype pour les bases de données d’archivage de serveur Business et activez l’intégration de Microsoft Exchange, les stratégies Exchange remplacent Skype pour Business Server, les stratégies d’archivage, mais uniquement pour les utilisateurs qui sont hébergés sur Exchange et à leurs boîtes aux lettres a été mis en Archive permanente. Skype pour l’archivage entreprise dépend de la stratégie de blocage sur Place dans Microsoft Exchange. 
  
Si vous déployez l’archivage pour un pool frontal ou serveur Standard Edition Server, vous devez l’activer pour tous les autres pools frontaux et les serveurs Standard Edition Server dans votre déploiement. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, il est possible que toutes les données de conférence ne soient pas archivées. L’archivage fonctionnera toujours pour les messages instantanés, mais il est possible que le contenu des conférences et les événements ne soient pas archivés.
  
> [!NOTE]
> Pour activer la délégation des tâches administratives tout en conservant les normes de sécurité de votre organisation, Skype pour Business Server utilise le contrôle d’accès basé sur un rôle (RBAC). Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis. Pour configurer Skype pour les configurations et les stratégies d’archivage d’entreprise, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (sauf si la configuration est effectuée directement sur le serveur où l’archivage est déployé, au lieu d’à distance à partir d’un autre ordinateur ). Pour obtenir la liste des droits d’utilisateur, autorisations et les rôles requis pour l’archivage de déploiement, voir [déployer l’archivage pour Skype pour Business Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si vous utilisez l’intégration de Microsoft Exchange, la configuration de stratégies Exchange nécessite des autorisations et droits d’administration appropriés. Pour plus d’informations, voir la documentation Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Stockage de Microsoft Exchange

 Si vous choisissez l’intégration de Microsoft Exchange, vous utilisez les configurations et les stratégies Exchange pour contrôler l’archivage de Skype pour Business Server. Vous pouvez configurer l’option d’intégration de Microsoft Exchange au niveau global, au niveau du site et au niveau du pool. Si votre déploiement comprend plusieurs forêts, vous devez synchroniser les paramètres entre Skype pour Business Server et Exchange. Vous devez déterminer si :
  
- vous devez archiver la messagerie instantanée, les conférences ou les deux ;
    
- S’il faut implémenter le mode critique, qui bloque les sessions par messagerie instantanée et de conférence en cas d’un Skype de défaillance du serveur d’entreprise 
    
- Sélection de l’option d’intégration de Microsoft Exchange à utiliser Exchange pour le stockage des données archivées
    
Pour plus d’informations sur la façon de configurer les paramètres pour prendre en charge l’archivage et les stratégies de blocage sur Place Exchange, voir la documentation du produit Exchange.
  
### <a name="skype-for-business-server-storage"></a>Stockage Skype Entreprise Server

Si vous choisissez Skype pour le stockage des Business Server, vous utilisez Skype pour les configurations et les stratégies d’archivage Business Server pour contrôler l’archivage est activé et implémenté. Skype pour le stockage des Business Server utilise des bases de données SQL Server, vous devez ajouter les bases de données SQL Server appropriés à votre topologie, puis configurez vos stratégies d’archivage. 
  
### <a name="add-storage-databases-to-your-topology"></a>Ajouter des bases de données à votre topologie

Lorsque vous ajoutez des bases de données SQL Server à votre topologie, vous pouvez choisir de colocaliser les bases de données d’archivage avec l’une des options suivantes :
  
- Base de données de surveillance
    
- Base de données principale d’un pool frontal Enterprise Edition
    
> [!NOTE]
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Cependant, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale. 
  
Si vous colocalisez la base de données d’archivage avec la base de données de surveillance, base de données principale ou les deux de ces bases de données, vous pouvez utiliser une seule instance SQL pour tout ou partie des bases de données, ou vous pouvez utiliser une instance SQL distincte pour chaque base de données, avec les éléments suivants limitation : instance SQL chaque peut contenir uniquement une seule base de données principale, base de données de surveillance unique et base de données d’archivage unique.
  
Pour plus d’informations sur la colocalisation de tous les rôles de serveur et les bases de données, voir [Les concepts de topologie pour Skype pour Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Pour plus d’informations sur la mise à jour de votre topologie pour inclure des bases de données de stockage, consultez la rubrique [créer et publier la nouvelle topologie dans Skype pour Business Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Déterminer les options d’archivage et les stratégies utilisateur

Vous devez déterminer si vous devez :
  
- Activer ou désactiver l’archivage pour les communications internes et externes
    
- Archiver la messagerie instantanée et/ou les conférences
    
- S’il faut implémenter le mode critique, qui bloque les sessions par messagerie instantanée et de conférence en cas d’un Skype de défaillance du serveur d’entreprise 
    
- Activer des stratégies pour des utilisateurs et des groupes spécifiques
    
Skype pour les options d’archivage de serveur Business peut être spécifié aux niveaux suivants. 
  
- **Option de niveau globale**. Ceci est la valeur par défaut de configuration de l’archivage et s’applique à tout votre déploiement. Il est créé lorsque vous déployez Skype pour Business Server et, par défaut, désactive l’archivage des communications internes et externes. Vous ne pouvez pas supprimer cette option. Si vous choisissez l’option Supprimer, l’option globale est réinitialiser les paramètres par défaut.
    
- **Options de niveau Site**. Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une option d’archivage au niveau du site. Vous pouvez supprimer toute option d’archivage au niveau du site que vous créez. Une option d’archivage au niveau du site remplace l’option globale, mais seulement pour le site spécifié dans l’option. 
    
    Par exemple, si vous activez l’archivage des communications internes et externes dans votre configuration globale et si vous créez une configuration de site dans laquelle vous désactivez l’archivage des communications externes, seules les communications internes sont archivées pour ce site. Autre exemple, si vous activez l’archivage de la messagerie instantanée uniquement dans votre configuration globale et si vous créez une configuration de site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences, ces dernières ne sont archivées que pour le site et non pour le reste de votre organisation.
    
- **Options de niveau pool**. Vous pouvez spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour un pool particulier. Une configuration d’archivage au niveau du pool n’existe que si vous la créez. Vous pouvez modifier et supprimer une configuration d’archivage au niveau du pool. Une configuration d’archivage au niveau du pool remplace la configuration globale et les configurations d’archivage de site que vous avez créées. 
    
    Par exemple, si vous activez uniquement l’archivage de la messagerie instantanée dans votre configuration globale, créez une configuration au niveau du site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences pour le site, puis créez une configuration au niveau du pool dans laquelle vous activez uniquement l’archivage de la messagerie instantanée. Les communications relatives à la messagerie instantanée et aux conférences sont archivées pour tous les utilisateurs du site à l’exception des utilisateurs hébergés au sein du pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, seul l’archivage de la messagerie instantanée est activé.
    
- **Stratégies d’archivage utilisateur**. Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, en configurant et en appliquant une stratégie d’archivage au niveau de l’utilisateur pour les utilisateurs et groupes d’utilisateurs spécifiés. Vous pouvez supprimer les stratégies d’archivage au niveau de l’utilisateur que vous avez créées. En outre, vous pouvez modifier les utilisateurs et groupes d’utilisateurs auxquels la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau de l’utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et groupes d’utilisateurs auxquels la stratégie est appliquée.. 
    
    Par exemple, si vous désactivez l’archivage des communications internes et externes dans votre stratégie globale, créez une stratégie au niveau du site dans laquelle vous activez l’archivage des communications internes et externes, puis créez une stratégie au niveau de l’utilisateur dans laquelle vous désactivez l’archivage des communications externes. Dans ce cas, les communications internes et externes sont archivées pour tous les utilisateurs du site, sauf pour les utilisateurs auxquels vous appliquez la stratégie au niveau de l’utilisateur, où seules les communications internes sont archivées.
    
Pour plus d’informations sur la configuration des configurations d’archivage initiales lorsque vous déployez l’archivage, voir [déployer l’archivage pour Skype pour Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Pour plus d’informations sur la gestion de l’archivage après le déploiement, voir [gérer l’archivage dans Skype pour Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Outils de configuration l’archivage

 Vous contrôlez la plupart des options d’archivage à l’aide de la Skype pour le panneau de configuration serveur Business. Toutefois, il existe quelques options disponibles uniquement à l’aide de la Skype pour Business Server Management Shell. Ces options incluent d’archivage des messages en double et l’exportation des données archivées. Pour plus d’informations sur l’utilisation de la Skype pour le panneau de configuration serveur Business et le Skype pour Business Server Management Shell pour gérer les stratégies d’archivage, voir [gérer l’archivage dans Skype pour Business Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Accès aux données archivées

L’accès aux données archivées dépend de l’emplacement où les données sont stockées : 
  
- **Stockage de Microsoft Exchange**. Si vous choisissez l’option d’intégration Exchange, Skype pour Business Server dépôts le contenu d’archivage dans la banque d’informations Exchange pour tous les utilisateurs hébergés sur Exchange et qui ont eu à leurs boîtes aux lettres mettre en blocage sur Place. Données archivées sont stockées dans le dossier éléments récupérables de boîtes aux lettres utilisateur, qui est généralement invisible aux utilisateurs et peut uniquement être exploré par les utilisateurs avec un rôle de **Gestion de la découverte** d’Exchange. Exchange permet de découverte, ainsi que de SharePoint et recherche fédérée s’il est déployé. Pour plus d’informations sur le stockage, de rétention et découverte des données stockées dans Exchange, consultez la documentation Exchange et SharePoint.
    
- **Skype pour le stockage d’archivage Business Server**. Si vous configurez Skype pour les bases de données d’archivage de serveur Business, Skype pour les dépôts Business Server d’archivage ne pas de contenu dans le Skype pour les bases de données d’archivage de serveur Business pour tous les utilisateurs hébergés sur Exchange et qui n’ont pas leurs boîtes aux lettres mettre en blocage sur Place. This data is not searchable, but it can be exported to formats that are searchable using other tools. Pour plus d’informations sur l’exportation des données stockées dans des bases de données d’archivage, voir [exporter des données archivées dans Skype pour Business Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur l’archivage, consultez les rubriques suivantes :
  
- [Déployer l’archivage pour Skype pour Business Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gérer l’archivage dans Skype pour Business Server](../../manage/archiving/archiving.md)
    
Pour plus d’informations sur la façon Skype pour Business Server et Exchange fonctionnent ensemble, voir [planifier l’intégration Skype pour les entreprises et Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

