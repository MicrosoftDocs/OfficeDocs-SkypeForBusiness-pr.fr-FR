---
title: Planifier l’archivage dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9f0dcf7-66b4-4196-9e8c-b14721b1fb84
description: 'Résumé: cette rubrique vous explique comment planifier l’archivage dans Skype entreprise Server.'
ms.openlocfilehash: 4bbe6b5bd8eb9e5e56bfdea6f8a4187a6d14b231
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277600"
---
# <a name="plan-for-archiving-in-skype-for-business-server"></a>Planifier l’archivage dans Skype entreprise Server
 
**Résumé:** Pour plus d’informations sur la planification de l’archivage dans Skype entreprise Server, reportez-vous à cette rubrique.
  
Les grandes entreprises et autres organisations sont soumises à un nombre croissant de réglementations nationales et industrielles nécessitant la conservation de types spécifiques de communications. Si votre organisation dispose de ces exigences, vous pouvez utiliser l’archivage dans Skype entreprise Server pour archiver les communications par messagerie instantanée et de conférence (réunion) pour vous aider à prendre en charge certaines de vos exigences de conformité.
  
## <a name="archiving-components"></a>Composants d’archivage

Skype entreprise Server utilise les composants d’archivage suivants:
  
- **Argents d’archivage**. Les agents d’archivage (également connus sous le nom d’agents de collecte de données unifiée) sont installés et activés automatiquement sur chaque pool frontal Enterprise Edition et serveur Standard Edition. Même si les agents d’archivage sont activés automatiquement, aucun message n’est réellement capturé tant que l’archivage n’est pas activé et correctement configuré. L’archivage est désactivé par défaut.
    
- **Archivage du stockage des données**. Le stockage des données de Skype entreprise Server peut être mis en œuvre sous la forme de bases de données SQL Server Skype entreprise Server ou, si vous disposez d’un déploiement Exchange, intégré au stockage Exchange. 
    
L’archivage nécessite également le stockage de fichiers. Cependant, l’archivage utilise le même type de stockage de fichiers que les serveurs frontaux ou le serveur Standard Edition.

  
## <a name="determine-your-organizations-requirements-for-archiving"></a>Définition des besoins de votre organisation pour l’archivage

Pour implémenter l’archivage, vous devez décider comment répondre aux besoins de votre organisation en matière d’archivage en établissant les informations suivantes:
  
- **Quelle option de stockage utiliser**. Vous pouvez implémenter le stockage de l’une des deux façons ou utiliser une combinaison des deux :
    
  - **Stockage Exchange.** Si vous disposez d’un déploiement Exchange, vous pouvez intégrer l’archivage de Skype entreprise Server et Exchange de sorte que vos données archivées Skype entreprise Server et Exchange soient stockées conjointement dans Exchange. Si vous activez l’option d’intégration de Microsoft Exchange, les boîtes aux lettres d’utilisateur hébergées sur le serveur Exchange utilisent le stockage Exchange pour les données archivées, mais uniquement si celles-ci sont placées sur le blocage sur place. Par défaut, l’intégration de Microsoft Exchange n’est pas activée.
    
  - **Stockage Skype entreprise Server.** Si vous avez des utilisateurs qui ne sont pas hébergés sur Exchange ou qui n’ont pas été mis en attente dans leurs boîtes aux lettres, ou si vous ne voulez pas utiliser l’intégration de Microsoft Exchange pour tous les utilisateurs ou votre déploiement, vous pouvez déployer les bases de données d’archivage de Skype entreprise Server à l’aide de S QL Server.
    
- **Quand déployer l’archivage**. Vous pouvez déployer l’archivage dans le cadre de votre déploiement initial de Skype entreprise Server ou vous pouvez l’ajouter à un déploiement existant. Pour utiliser le stockage d’archivage de Skype entreprise Server (bases de données SQL Server), vous devez utiliser le générateur de topologie pour ajouter les bases de données à votre topologie, puis publier de nouveau la topologie. Si tous vos utilisateurs sont hébergés sur Exchange et que leurs boîtes aux lettres sont placées sur le blocage sur place, vous n’avez pas besoin de mettre à jour votre topologie, mais vous n’avez pas besoin d’activer l’intégration de Microsoft Exchange pour stocker les données archivées dans Exchange. 
    
- **Quels sont les sites et les utilisateurs d’une organisation qui nécessitent l’archivage**. Vous pouvez configurer les paramètres d’archivage pour l’ensemble de votre organisation et, si vous le souhaitez, pour des sites, des groupes, des utilisateurs et des groupes d’utilisateurs spécifiques.
    
- **Quel contenu archiver**. Que l’archivage soit spécifié au niveau global ou pour des sites et utilisateurs spécifiques, à chacun de ces niveaux, vous devez spécifier si vous activez l’archivage pour les types de contenu suivants : 
    
  - Messages instantanés P2P
    
  - Conférences (réunions) sous forme de messages instantanés entre plusieurs participants
    
  - Contenu de conférence, dont le contenu téléchargé (par exemple, documents) et le contenu lié à l’événement (par exemple, joindre, quitter la réunion, téléchargement de partage et modifications en termes de visibilité)
    
  - Tableaux blancs et sondages partagés durant une conférence
    
- **Le contenu qui ne peut pas être archivé**. Les types de contenu suivants ne peuvent pas être archivés : 
    
  - Transfert de fichiers d’égal à égal
    
  - Audio/vidéo pour messages instantanés et conférences P2P
    
  - Partage d’application et de Bureau pour messages instantanés et conférences d’égal à égal
    
    Skype entreprise Server ne permet pas non plus d’archiver des conversations persistantes. Pour archiver des conversations permanentes, vous devez activer et configurer le service de conformité, qui est un composant qui peut être déployé avec le serveur de chat permanent. Pour plus d’informations, reportez-vous à la section [planification du serveur de conversation permanente dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

    > [!NOTE] 
    > La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
    
- **Quelle doit être la durée de conservation du contenu archivé**. La base de données d’archivage n’est pas destinée à la conservation longue durée, et Skype entreprise Server ne fournit pas de solution de découverte électronique pour les données archivées, de sorte que les données doivent être déplacées vers un autre stockage. Skype entreprise Server fournit un outil d’exportation de session que vous pouvez utiliser pour exporter des données archivées et qui crée des transcriptions sur les données archivées. 
    
     Pour la stratégie globale, et pour chaque site et stratégie d’utilisateur que vous créez, vous pouvez spécifier le moment où effacer les données archivées et exportées. Pour plus d’informations sur la suppression de données, reportez-vous à la section [gestion de la suppression de données archivées dans Skype entreprise Server](../../manage/archiving/purging-of-archived-data.md). Pour plus d’informations sur l’utilisation de l’outil d’exportation de session, voir [exporter des données archivées dans Skype entreprise Server](../../manage/archiving/export-archived-data.md).
    
- **Archivage des communications internes ou externes**. Vous pouvez activer l’archivage pour les communications internes (communications entre les utilisateurs internes) et/ou les communications externes (communications incluant au moins un utilisateur externe à votre réseau interne). Vous pouvez spécifier ces options pour l’ensemble de votre organisation, ou pour des sites et pools spécifiques. Par défaut, aucune des ces options n’est activée.
    
    > [!NOTE]
    > Le contrôle de l’archivage pour les communications internes ou externes n’est disponible que pour la stratégie Skype entreprise. Dans le cas d’un archivage intégré à Exchange, les communications internes et externes sont soit archivées, soit non archivées. 
  
- **Implémenter le mode critique**. Si l’archivage est requis pour votre organisation, la configuration du mode critique bloquera les sessions de messagerie instantanée et de conférence en cas de panne du serveur Skype entreprise qui empêcherait l’archivage. Par exemple : 
    
  - Un problème avec le service de stockage Skype entreprise Server. Dans le cas présent, la messagerie instantanée est bloquée pour les utilisateurs autorisés à archiver.
    
  - Un partage de fichiers non disponible ou un problème au niveau du service de stockage. Dans ce cas, toutes les conférences actives hébergées dans le pool au moment de la défaillance passent en mode restreint et l’activation de nouvelles conférences est suspendue.
    
    La récupération des sessions de messagerie instantanée et de conférence s’effectue automatiquement après la correction des défaillances.
    
## <a name="choose-archiving-deployment-and-configuration-options"></a>Choisir les options de configuration et de déploiement de l’archivage

L’archivage est automatiquement installé sur chaque serveur frontal lors du déploiement du serveur, mais la mise à jour n’est pas activée tant que vous ne l’avez pas configuré. La configuration de l’archivage dépend du mode de déploiement. Vous pouvez déployer l’archivage de l’une des façons suivantes:
  
- Utiliser le stockage Microsoft Exchange
    
- Utiliser le stockage Skype entreprise Server
    
> [!NOTE]
> Si vous implémentez les bases de données d’archivage Skype entreprise Server et activez l’intégration de Microsoft Exchange, les stratégies Exchange remplacent les stratégies d’archivage de Skype entreprise Server, mais uniquement pour les utilisateurs hébergés sur Exchange et ayant reçu leur boîte aux lettres. Blocage sur place. L’archivage Skype entreprise dépend de la stratégie de conservation inaltérable de Microsoft Exchange. 
  
Si vous déployez l’archivage pour une liste frontale ou un serveur Standard Edition Server, vous devez l’activer pour tous les autres pools front-end et serveurs Standard Edition de votre déploiement. Si l’archivage n’est pas activé sur le pool sur lequel la conversation ou la réunion est hébergée, il est possible que toutes les données de conférence ne soient pas archivées. L’archivage fonctionnera toujours pour les messages instantanés, mais il est possible que le contenu des conférences et les événements ne soient pas archivés.
  
> [!NOTE]
> Pour permettre la délégation de tâches administratives tout en préservant les exigences de sécurité de votre organisation, Skype entreprise Server utilise le contrôle de contrôle d’accès basé sur les rôles (RBAC). Dans ce cadre, le privilège administratif est accordé en affectant les utilisateurs à des rôles d’administration prédéfinis. Pour configurer les stratégies et configurations d’archivage Skype entreprise, l’utilisateur doit être affecté au rôle CsArchivingAdministrator (à moins que la configuration ne soit réalisée directement sur le serveur où l’archivage est déployé, au lieu d’un autre ordinateur). ). Pour obtenir la liste des droits d’utilisateur, des autorisations et des rôles requis pour le déploiement d’archivage, voir [déployer l’archivage pour Skype entreprise Server](../../deploy/deploy-archiving/deploy-archiving.md). 
  
> [!NOTE]
> Si vous utilisez l’intégration de Microsoft Exchange, la configuration des stratégies Exchange exige des droits et des autorisations d’administrateur appropriés. Pour plus d’informations, consultez la documentation sur Exchange. 
  
### <a name="microsoft-exchange-storage"></a>Stockage Microsoft Exchange

 Si vous choisissez l’intégration de Microsoft Exchange, vous utilisez les stratégies et configurations Exchange pour contrôler l’archivage de Skype entreprise Server. Vous pouvez configurer l’option intégration de Microsoft Exchange au niveau global, au niveau du site et au niveau du pool. Si votre déploiement inclut plusieurs forêts, vous devez synchroniser les paramètres entre Skype entreprise Server et Exchange. Vous devez déterminer si :
  
- vous devez archiver la messagerie instantanée, les conférences ou les deux ;
    
- S’il est nécessaire de mettre en œuvre le mode critique qui bloque les sessions de messagerie instantanée et de conférence en cas de panne du serveur Skype entreprise 
    
- Choix de l’option d’intégration de Microsoft Exchange à utiliser Exchange pour le stockage des données archivées
    
Pour plus d’informations sur la configuration des stratégies de blocage et des paramètres Exchange pour la prise en charge de l’archivage, voir la documentation du produit Exchange.
  
### <a name="skype-for-business-server-storage"></a>Stockage Skype Entreprise Server

Si vous choisissez le stockage Skype entreprise Server, vous utilisez les stratégies et configurations d’archivage de Skype entreprise Server pour contrôler l’activation et l’implémentation de l’archivage. Le stockage de Skype entreprise Server utilise des bases de données SQL Server; vous devrez donc ajouter les bases de données SQL Server appropriées à votre topologie, puis configurer vos stratégies d’archivage. 
  
### <a name="add-storage-databases-to-your-topology"></a>Ajouter des bases de données à votre topologie

Lorsque vous ajoutez des bases de données de stockage SQL Server à votre topologie, vous pouvez choisir de collocateer les bases de données d’archivage avec l’une des options suivantes:
  
- Base de données de surveillance
    
- Base de données principale d’un pool frontal Enterprise Edition
    
> [!NOTE]
> Le serveur qui héberge la base de données d’archivage peut également héberger d’autres bases de données. Cependant, quand vous envisagez de colocaliser la base de données d’archivage avec d’autres bases de données, sachez que si vous archivez les messages d’un certain nombre d’utilisateurs, les besoins en espace disque de la base de données d’archivage peuvent devenir très importants. C’est la raison pour laquelle nous vous déconseillons de colocaliser la base de données d’archivage avec la base de données principale. 
  
Si vous collocate la base de données d’archivage avec la base de données de surveillance, la base de données principale, ou les deux, vous pouvez utiliser une instance SQL unique pour tout ou partie des bases de données, ou vous pouvez utiliser une instance SQL distincte pour chaque base de données, comme suit: limitation: chaque instance SQL ne peut contenir qu’une seule base de données principale, une seule base de données de surveillance et une seule base de données d’archivage.
  
Pour plus d’informations sur la colocalisation de tous les rôles de serveur et bases de données, voir notions de base de la [topologie pour Skype entreprise Server](../../plan-your-deployment/topology-basics/topology-basics.md). Pour plus d’informations sur la mise à jour de votre topologie de façon à inclure des bases de données de stockage, reportez-vous à la rubrique [créer et publier une nouvelle topologie dans Skype entreprise Server](../../deploy/install/create-and-publish-new-topology.md).
  
### <a name="determine-archiving-options-and-user-policies"></a>Déterminer les options d’archivage et les stratégies utilisateur

Vous devez déterminer si vous devez :
  
- Activer ou désactiver l’archivage pour les communications internes et externes
    
- Archiver la messagerie instantanée et/ou les conférences
    
- S’il est nécessaire de mettre en œuvre le mode critique qui bloque les sessions de messagerie instantanée et de conférence en cas de panne du serveur Skype entreprise 
    
- Activer des stratégies pour des utilisateurs et des groupes spécifiques
    
Les options d’archivage de Skype entreprise Server peuvent être spécifiées aux niveaux suivants. 
  
- **Option niveau global**. Il s’agit de la configuration de l’archivage par défaut qui s’applique à votre déploiement complet. Elle est créée lors du déploiement de Skype entreprise Server et, par défaut, désactive l’archivage pour les communications internes et externes. Vous ne pouvez pas supprimer cette option. Si vous choisissez l’option Supprimer, l’option global est rétablir les paramètres par défaut.
    
- **Options de niveau Site**. Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs sites spécifiques en créant et en configurant une option d’archivage au niveau du site. Vous pouvez supprimer toute option d’archivage au niveau du site que vous créez. Une option d’archivage au niveau du site remplace l’option globale, mais seulement pour le site spécifié dans l’option. 
    
    Par exemple, si vous activez l’archivage des communications internes et externes dans votre configuration globale et si vous créez une configuration de site dans laquelle vous désactivez l’archivage des communications externes, seules les communications internes sont archivées pour ce site. Autre exemple, si vous activez l’archivage de la messagerie instantanée uniquement dans votre configuration globale et si vous créez une configuration de site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences, ces dernières ne sont archivées que pour le site et non pour le reste de votre organisation.
    
- **Options de niveau pool**. Vous pouvez spécifier des paramètres d’archivage pour un ou plusieurs pools spécifiques en créant et en configurant une configuration au niveau du pool pour un pool particulier. Une configuration d’archivage au niveau du pool n’existe que si vous la créez. Vous pouvez modifier et supprimer une configuration d’archivage au niveau du pool. Une configuration d’archivage au niveau du pool remplace la configuration globale et les configurations d’archivage de site que vous avez créées. 
    
    Par exemple, si vous activez uniquement l’archivage de la messagerie instantanée dans votre configuration globale, créez une configuration au niveau du site dans laquelle vous activez l’archivage de la messagerie instantanée et des conférences pour le site, puis créez une configuration au niveau du pool dans laquelle vous activez uniquement l’archivage de la messagerie instantanée. Les communications relatives à la messagerie instantanée et aux conférences sont archivées pour tous les utilisateurs du site à l’exception des utilisateurs hébergés au sein du pool spécifié dans la configuration au niveau du pool. Pour tous les autres utilisateurs de votre organisation, seul l’archivage de la messagerie instantanée est activé.
    
- **Stratégies d’archivage utilisateur**. Vous pouvez activer ou désactiver l’archivage pour un ou plusieurs utilisateurs et groupes d’utilisateurs spécifiques en créant, en configurant et en appliquant une stratégie d’archivage au niveau de l’utilisateur pour les utilisateurs et groupes d’utilisateurs spécifiés. Vous pouvez supprimer les stratégies d’archivage au niveau de l’utilisateur que vous avez créées. En outre, vous pouvez modifier les utilisateurs et groupes d’utilisateurs auxquels la stratégie d’archivage s’applique. Une stratégie d’archivage au niveau de l’utilisateur remplace la stratégie globale et les stratégies de site, mais uniquement pour les utilisateurs et groupes d’utilisateurs auxquels la stratégie est appliquée.. 
    
    Par exemple, si vous désactivez l’archivage des communications internes et externes dans votre stratégie globale, créez une stratégie au niveau du site dans laquelle vous activez l’archivage des communications internes et externes, puis créez une stratégie au niveau de l’utilisateur dans laquelle vous désactivez l’archivage des communications externes. Dans ce cas, les communications internes et externes sont archivées pour tous les utilisateurs du site, sauf pour les utilisateurs auxquels vous appliquez la stratégie au niveau de l’utilisateur, où seules les communications internes sont archivées.
    
Pour plus d’informations sur la configuration d’un archivage initial lors du déploiement de l’archivage, voir [déployer l’archivage pour Skype entreprise Server](../../deploy/deploy-archiving/deploy-archiving.md). Pour plus d’informations sur la gestion de l’archivage après le déploiement, voir [gérer l’archivage dans Skype entreprise Server](../../manage/archiving/archiving.md). 
  
## <a name="archiving-configuration-tools"></a>Outils de configuration l’archivage

 Vous pouvez contrôler la plupart des options d’archivage à l’aide du panneau de configuration Skype entreprise Server. Toutefois, certaines options sont disponibles uniquement à l’aide de Skype entreprise Server Management Shell. Ces options incluent d’archivage des messages en double et l’exportation des données archivées. Pour plus d’informations sur l’utilisation du panneau de configuration Skype entreprise Server et de Skype entreprise Server Management Shell pour gérer les stratégies d’archivage, voir [gérer l’archivage dans Skype entreprise Server](../../manage/archiving/archiving.md).
  
## <a name="access-archived-data"></a>Accès aux données archivées

L’accès aux données archivées dépend de l’emplacement où les données sont stockées : 
  
- **Stockage Microsoft Exchange**. Si vous choisissez l’option intégration Exchange, Skype entreprise Server effectue le dépôt du contenu d’archivage dans la banque Exchange pour tous les utilisateurs qui sont hébergés sur Exchange et qui ont eu accès à leurs boîtes aux lettres en conservation inaltérable. Les données archivées sont stockées dans le dossier éléments récupérables de la boîte aux lettres utilisateur, qui est généralement invisible pour les utilisateurs et ne peut être recherchée que par les utilisateurs disposant d’un rôle de gestion de la **découverte** Exchange. Exchange autorise la recherche et la découverte fédéré, ainsi que SharePoint, s’il est déployé. Pour plus d’informations sur le stockage, la rétention et la découverte des données stockées dans Exchange, voir la documentation Exchange et SharePoint.
    
- **Stockage d’archivage de Skype entreprise Server**. Si vous configurez les bases de données d’archivage de Skype entreprise Server, le contenu de l’archivage Skype entreprise Server est déposé dans les bases de données d’archivage de Skype entreprise Server pour les utilisateurs qui ne sont pas à domicile sur Exchange et qui n’ont pas été mis en attente sur place. This data is not searchable, but it can be exported to formats that are searchable using other tools. Pour plus d’informations sur l’exportation de données stockées dans les bases de données d’archivage, voir [exporter des données archivées dans Skype entreprise Server](../../manage/archiving/export-archived-data.md).
    
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur l’archivage, consultez les rubriques suivantes :
  
- [Déploiement de l’archivage pour Skype entreprise Server](../../deploy/deploy-archiving/deploy-archiving.md)
    
- [Gestion de l’archivage dans Skype entreprise Server](../../manage/archiving/archiving.md)
    
Pour plus d’informations sur la façon dont Skype entreprise Server et Exchange collaborent, reportez-vous à la section [planifier l’intégration de Skype entreprise et Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  

