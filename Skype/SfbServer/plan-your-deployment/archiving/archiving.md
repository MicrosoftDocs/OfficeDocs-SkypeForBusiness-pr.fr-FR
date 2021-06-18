---
title: Planifier l’archivage dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Résumé : Lisez cette rubrique pour découvrir comment planifier l’archivage dans Skype Entreprise Server.'
ms.openlocfilehash: b868555b0a79b1abdfd96e50cf88d6db9cdae2ae
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810144"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planifier l’archivage dans Skype Entreprise Server
 
**Résumé :** Lisez cette rubrique pour découvrir comment planifier l’archivage dans Skype Entreprise Server.
  
Les grandes entreprises et d’autres organisations sont soumises à un nombre croissant de réglementations gouvernementales et industrielles nécessitant la conservation de types spécifiques de communications. Si votre organisation a de telles exigences, vous pouvez utiliser l’archivage dans Skype Entreprise Server pour archiver les communications de messagerie instantanée et de conférence (réunion) afin de prendre en charge certaines de vos exigences de conformité.
  
## <a name="archiving-components"></a>Composants d’archivage

Skype Entreprise Server utilise les composants d’archivage suivants :
  
- **Argents d’archivage**. Les agents d’archivage (également appelés agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et serveur Standard Edition Server. Bien que les agents d’archivage soient activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré. Par défaut, l’archivage est désactivé.
    
- **Stockage des données d’archivage**. Le stockage de données pour Skype Entreprise Server peut être implémenté en tant que base de données Skype Entreprise Server SQL Server ou, si vous avez un déploiement Exchange, intégré au stockage Exchange. 
    
L’archivage nécessite également un stockage de fichiers, mais l’archivage utilise le même stockage de fichiers que les serveurs frontux ou standard.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Déterminer les besoins de votre organisation en matière d’archivage

Pour implémenter l’archivage, vous devez déterminer comment répondre aux exigences de votre organisation en matière d’archivage en déterminant ce qui suit :
  
- **Option de stockage à utiliser.** Vous pouvez implémenter le stockage de deux manières ou utiliser une combinaison des deux :
    
  - **Stockage Exchange.** Si vous avez un déploiement Exchange, vous pouvez intégrer Skype Entreprise Server et l’archivage Exchange afin que vos données archivées Skype Entreprise Server et Exchange soient stockées ensemble dans Exchange. Si vous activez l’option d’intégration Microsoft Exchange, les boîtes aux lettres d’utilisateurs Exchange Server utilisent le stockage Exchange pour les données archivées, mais uniquement si les boîtes aux lettres ont été mises en conservation In-Place. Par défaut, l’intégration de Microsoft Exchange n’est pas activée.
    
  - **Stockage Skype Entreprise Server.** Si vous avez des utilisateurs qui ne sont pas sur Exchange ou dont la boîte aux lettres n’a pas été mise en attente In-Place ou si vous ne souhaitez pas utiliser l’intégration de Microsoft Exchange pour un ou tous les utilisateurs de votre déploiement, vous pouvez déployer des bases de données d’archivage Skype Entreprise Server à l’aide de SQL Server.
    
- **Quand déployer l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre déploiement initial de Skype Entreprise Server ou l’ajouter à un déploiement existant. Pour utiliser le stockage d’archivage Skype Entreprise Server (bases de données SQL Server), utilisez le Générateur de topologie pour ajouter les bases de données à votre topologie, puis publiez à nouveau la topologie. Si tous vos utilisateurs sont do domicile sur Exchange et que leurs boîtes aux lettres sont mises en archive In-Place, vous n’avez pas besoin de mettre à jour votre topologie, mais seulement d’activer l’intégration de Microsoft Exchange pour stocker les données archivées dans Exchange. 
    
- **Quels sites et utilisateurs de l’organisation nécessitent l’archivage**. Vous pouvez configurer les paramètres d’archivage pour l’ensemble de votre organisation et, éventuellement, pour des sites, pools, utilisateurs et groupes d’utilisateurs spécifiques.
    
- **Quel contenu doit être archivé**. Que vous spécifiant l’archivage au niveau global ou pour des sites et des utilisateurs spécifiques, à chacun de ces niveaux, vous spécifiez s’il faut activer les types de contenu suivants : 
    
  - Messages instantanés d’égal à égal
    
  - Conférences (réunions), qui sont des messages instantanés à plusieurs
    
  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)
    
  - Tableaux blancs et sondages partagés au cours d’une conférence
    
- **Quel contenu ne peut pas être archivé**. Les types de contenu suivants ne peuvent pas être archivés : 
    
  - Transferts de fichiers d’égal à égal
    
  - Audio/vidéo pour messages instantanés et conférences d’égal à égal
    
  - Partage de bureau et d’application pour les messages instantanés et les conférences D’égal à égal
    
    Skype Entreprise Server n’archive pas non plus les conversations de conversation permanente. Pour archiver des conversations de conversation permanente, vous devez activer et configurer le service de conformité, qui est un composant qui peut être déployé avec le serveur de conversation permanente. Pour plus d’informations, voir [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015. 
    
- Durée de rétention des documents **archivés.** La base de données d’archivage n’est pas destinée à une rétention à long terme, et Skype Entreprise Server ne fournit pas de solution de découverte électronique (recherche) pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage. Skype Entreprise Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées et qui crée des transcriptions utilisables dans une recherche des données archivées. 
    
     Pour la stratégie globale et pour chaque stratégie de site et d’utilisateur que vous créez, vous pouvez spécifier quand vider les données archivées et exportées. Pour plus d’informations sur la purge des données, voir [Manage purging of archived data in Skype for Business Server](../../manage/archiving/purging-of-archived-data.md). Pour plus d’informations sur l’utilisation de l’outil d’exportation de session, voir Exporter les données [archivées dans Skype Entreprise Server.](../../manage/archiving/export-archived-data.md)
    
- **S’il faut archiver les communications internes ou externes.** Vous pouvez activer l’archivage pour les communications internes (communications entre utilisateurs internes), les communications externes (communications qui incluent au moins un utilisateur en dehors de votre réseau interne) ou les deux. Vous pouvez spécifier ces options pour l’ensemble de votre organisation ou pour des sites et pools spécifiques. Par défaut, aucune option n’est activée.
    
    > [!NOTE]
    > Le contrôle de l’archivage des communications internes ou externes est disponible uniquement pour la stratégie Skype Entreprise. Pour l’archivage intégré à Exchange, les communications internes et externes sont archivées ou non. 
  
- **S’il faut implémenter le mode critique**. Si l’archivage est une condition requise pour votre organisation, la configuration du mode critique bloque les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server qui empêcherait l’archivage. Par exemple : 
    
  - Problème avec le service de stockage Skype Entreprise Server. Dans ce cas, la messagerie instantanée est bloquée pour les utilisateurs activés pour l’archivage.
    
  - Partage de fichiers indisponible ou problème avec le service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de l’échec basculent en mode restreint et les nouvelles conférences ne peuvent pas être activées.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Choisir les options de configuration et de déploiement de l’archivage

L’archivage est automatiquement installé sur chaque serveur frontal lorsque vous déployez le serveur, mais l’archivage n’est pas activé tant que vous ne l’avez pas configuré. La façon dont vous configurez l’archivage est déterminée par la façon dont vous le déployez. Vous pouvez déployer l’archivage de l’une des manières suivantes :
  
- Utiliser le stockage Microsoft Exchange
    
- Utiliser le stockage Skype Entreprise Server
    
> [!NOTE]
> Si vous implémentez les deux bases de données d’archivage Skype Entreprise Server et activez l’intégration de Microsoft Exchange, les stratégies Exchange remplacent les stratégies d’archivage Skype Entreprise Server, mais uniquement pour les utilisateurs qui sont homed on Exchange et dont les boîtes aux lettres ont été mises en In-Place Hold. L’archivage Skype Entreprise dépend de la stratégie de In-Place microsoft Exchange. 
  
Si vous déployez l’archivage pour un pool frontal ou un serveur Standard Edition Server, vous devez l’activer pour tous les autres pools frontux et serveurs Standard Edition Server dans votre déploiement. Si l’archivage n’est pas activé sur le pool où une conversation ou une réunion est hébergée, il se peut que toutes les données de conférence ne soient pas archivées. L’archivage fonctionne toujours pour les messages instantanés, mais il se peut que le contenu et les événements de conférence ne soient pas archivés.
  
> [!NOTE]
> Pour activer la délégation de tâches administratives tout en maintenant les normes de sécurité de votre organisation, Skype Entreprise Server utilise le contrôle d’accès basé sur les rôles (RBAC). Avec le contrôle d’accès en fonction du rôle, le privilège d’administration est accordé en attribuant des rôles d’administration prédéfincés aux utilisateurs. Pour configurer les stratégies et configurations d’archivage de Skype Entreprise, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (sauf si la configuration est effectuée directement sur le serveur où l’archivage est déployé, et non à distance à partir d’un autre ordinateur). Pour obtenir la liste des droits d’utilisateur, des autorisations et des rôles requis pour le déploiement de l’archivage, voir [Déployer l’archivage pour Skype Entreprise Server.](../../deploy/deploy-archiving/deploy-archiving.md) 
  
> [!NOTE]
> Si vous utilisez l’intégration Microsoft Exchange, la configuration des stratégies Exchange nécessite des droits et autorisations d’administrateur appropriés. Pour plus d’informations, voir la documentation Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Stockage Microsoft Exchange

 Si vous choisissez l’intégration de Microsoft Exchange, vous utilisez les stratégies et configurations Exchange pour contrôler l’archivage de Skype Entreprise Server. Vous pouvez configurer l’option d’intégration Microsoft Exchange au niveau global, au niveau du site et au niveau du pool. Si votre déploiement comprend plusieurs forêts, vous devez synchroniser les paramètres entre Skype Entreprise Server et Exchange. Vous devez déterminer :
  
- S’il faut archiver la messagerie instantanée, les conférences ou les deux
    
- S’il faut implémenter le mode critique, qui bloque les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server 
    
- Sélection de l’option d’intégration Microsoft Exchange pour utiliser Exchange pour le stockage des données archivées
    
Pour plus d’informations sur la configuration des stratégies et des paramètres de la In-Place Exchange pour prendre en charge l’archivage, consultez la documentation du produit Exchange.
  
### <a name="skype-for-business-server-storage"></a>Stockage Skype Entreprise Server

Si vous choisissez le stockage Skype Entreprise Server, vous utilisez des configurations et des stratégies d’archivage Skype Entreprise Server pour contrôler la façon dont l’archivage est activé et implémenté. Le stockage Skype Entreprise Server utilise des bases de données SQL Server, vous devrez donc ajouter les bases de données SQL Server appropriées à votre topologie, puis configurer vos stratégies d’archivage. 
  
### <a name="add-storage-databases-to-your-topology"></a>Ajouter des bases de données de stockage à votre topologie

Lorsque vous ajoutez SQL Server bases de données de stockage à votre topologie, vous pouvez choisir de coutérer les bases de données d’archivage avec l’une des opérations suivantes :
  
- Base de données de surveillance
    
- Base de données principale d’un pool frontal Enterprise Edition
    
> [!NOTE]
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Toutefois, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale. 
  
Si vous coloquez la base de données d’archivage avec la base de données de surveillance, la base de données principale ou ces deux bases de données, vous pouvez utiliser une seule instance SQL pour une ou l’ensemble des bases de données, ou vous pouvez utiliser une instance de SQL distincte pour chaque base de données, avec la limitation suivante : Chaque instance de SQL ne peut contenir qu’une seule base de données principale, une seule base de données de surveillance et une seule base de données d’archivage.
  
Pour plus d’informations sur la cocation de tous les rôles serveur et bases de données, voir [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md). Pour plus d’informations sur la mise à jour de votre topologie pour inclure des bases de données de stockage, voir Créer et publier une nouvelle [topologie dans Skype Entreprise Server.](../../deploy/install/create-and-publish-new-topology.md)
  
### <a name="determine-archiving-options-and-user-policies"></a>Déterminer les options d’archivage et les stratégies utilisateur

Vous devez déterminer :
  
- Activer ou désactiver l’archivage pour les communications internes et externes
    
- S’il faut archiver la messagerie instantanée, les conférences ou les deux
    
- S’il faut implémenter le mode critique, qui bloque les sessions de messagerie instantanée et de conférence en cas de défaillance de Skype Entreprise Server 
    
- Activer ou non des stratégies pour des utilisateurs et des groupes spécifiques
    
Les options d’archivage de Skype Entreprise Server peuvent être spécifiées aux niveaux suivants. 
  
- **Option de niveau global**. Il s’agit de la configuration d’archivage par défaut qui s’applique à l’ensemble de votre déploiement. Il est créé lorsque vous déployez Skype Entreprise Server et, par défaut, désactive l’archivage pour les communications internes et externes. Vous ne pouvez pas supprimer cette option. Si vous choisissez l’option de suppression, l’option globale est réinitialisée aux paramètres par défaut.
    
- **Options au niveau du site.** Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une option d’archivage au niveau du site pour le site. Vous pouvez supprimer n’importe quelle option d’archivage au niveau du site que vous créez. Une option d’archivage au niveau du site remplace l’option globale, mais uniquement pour le site spécifié dans l’option. 
    
    Par exemple, si vous activez l’archivage pour les communications internes et externes dans votre configuration globale et que vous créez une configuration de site dans laquelle vous désactivez l’archivage pour les communications externes, seules les communications internes seront archivées pour ce site. Par exemple, si vous activez l’archivage uniquement pour la messagerie instantanée dans votre configuration globale et que vous créez une configuration de site dans laquelle vous activez l’archivage pour la messagerie instantanée et les conférences, la conférence ne sera archivée que pour le site, et non pour le reste de votre organisation.
    
- **Options au niveau du pool.** Vous pouvez spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour chaque pool. Une configuration d’archivage au niveau du pool existe uniquement si vous la créez. Vous pouvez modifier et supprimer toute configuration d’archivage au niveau du pool. Une configuration d’archivage au niveau du pool remplace la configuration globale et toute configuration d’archivage de site que vous avez peut-être créée. 
    
    Par exemple, supposons que vous activez l’archivage pour la messagerie instantanée uniquement dans votre configuration globale, que vous créez une configuration au niveau du site dans laquelle vous activez l’archivage pour la messagerie instantanée et les conférences, puis créez une configuration au niveau du pool dans laquelle vous activez l’archivage uniquement pour la messagerie instantanée. Les communications sont archivées à la fois pour la messagerie instantanée et les conférences pour tous les utilisateurs du site, à l’exception des utilisateurs qui sont situés dans le pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, l’archivage est activé uniquement pour la messagerie instantanée.
    
- **Stratégies d’archivage utilisateur.** Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, configurant et appliquant une stratégie d’archivage au niveau de l’utilisateur pour les utilisateurs et les groupes d’utilisateurs spécifiés. Vous pouvez supprimer toute stratégie d’archivage au niveau de l’utilisateur que vous créez et modifier les utilisateurs et groupes d’utilisateurs auquel la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau de l’utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et les groupes d’utilisateurs auxquels la stratégie est appliquée. 
    
    Par exemple, supposons que vous désactiviez l’archivage pour les communications internes et externes dans votre configuration globale, créez une stratégie au niveau du site dans laquelle vous activez l’archivage pour les communications internes et externes, puis créez une stratégie au niveau de l’utilisateur dans laquelle vous désactivez l’archivage pour les communications externes. Les communications seront archivées pour les communications externes et internes pour tous les utilisateurs du site à l’exception des utilisateurs auxquels vous appliquez la stratégie de niveau utilisateur; pour ces utilisateurs, seules les communications internes seront archivées.
    
Pour plus d’informations sur la configuration des configurations d’archivage initiales lorsque vous déployez l’archivage, voir [Deploy archiving for Skype for Business Server](../../deploy/deploy-archiving/deploy-archiving.md). Pour plus d’informations sur la gestion de l’archivage après le déploiement, voir [Manage archiving in Skype for Business Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Outils de configuration de l’archivage

 Vous contrôlez la plupart des options d’archivage à l’aide du Panneau de contrôle Skype Entreprise Server. Toutefois, il existe quelques options disponibles uniquement à l’aide de Skype Entreprise Server Management Shell. Ces options incluent l’archivage des messages en double et l’exportation des données archivées. Pour plus d’informations sur l’utilisation du Panneau de contrôle Skype Entreprise Server et de Skype Entreprise Server Management Shell pour gérer les stratégies d’archivage, voir Gérer l’archivage dans [Skype Entreprise Server.](../../manage/archiving/archiving.md)
  
## <a name="access-archived-data"></a>Accéder aux données archivées

L’accès aux données archivées dépend de l’endroit où elles sont stockées : 
  
- **Stockage Microsoft Exchange**. Si vous choisissez l’option d’intégration Exchange, Skype Entreprise Server dépose le contenu d’archivage dans la banque d’informations Exchange pour tous les utilisateurs qui sont stockés sur Exchange et dont les boîtes aux lettres ont été mises en In-Place. Les données archivées sont stockées dans le dossier Éléments récupérables des boîtes aux lettres utilisateur, qui est généralement invisible pour les utilisateurs et ne peut être recherché que par les utilisateurs ayant un rôle de gestion de découverte **Exchange.** Exchange active la recherche et la découverte fédérées, ainsi que SharePoint, s’il est déployé. Pour plus d’informations sur le stockage, la rétention et la découverte de données stockées dans Exchange, voir la documentation Exchange et SharePoint.
    
- **Stockage d’archivage Skype** Entreprise Server. Si vous définissez des bases de données d’archivage Skype Entreprise Server, Skype Entreprise Server dépose le contenu d’archivage dans les bases de données d’archivage Skype Entreprise Server pour les utilisateurs qui n’ont pas été placés sur Exchange et dont les boîtes aux lettres n’ont pas été mises en archive In-Place. Ces données ne sont pas utilisables dans une recherche, mais elles peuvent être exportées vers des formats utilisables dans une recherche à l’aide d’autres outils. Pour plus d’informations sur l’exportation des données stockées dans les bases de données d’archivage, voir Exporter les données [archivées dans Skype Entreprise Server.](../../manage/archiving/export-archived-data.md)
    
## <a name="for-more-information"></a>Pour plus d'informations

Pour plus d’informations sur l’archivage, consultez les rubriques suivantes :
  
- [Déployer l’archivage pour Skype Entreprise Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gérer l’archivage dans Skype Entreprise Server](../../manage/archiving/archiving.md)
    
Pour plus d’informations sur la façon dont Skype Entreprise Server et Exchange fonctionnent ensemble, voir [Plan to integrate Skype for Business and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

