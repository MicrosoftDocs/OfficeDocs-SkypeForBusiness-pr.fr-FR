---
title: Déployer un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer Skype pour Business 2015 Persistent Chat Server.'
ms.openlocfilehash: b7b0e2731056eb1dd0584f0ba20d553d49ea2f83
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20975997"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Déployer un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment déployer Skype pour Business 2015 Persistent Chat Server.
  
Pour déployer des serveurs de conversation permanente, vous : 
  
- Utilisez le Générateur de topologie pour définir, ou importer et publiez votre topologie et les composants que vous souhaitez déployer
    
- Préparer votre environnement pour le déploiement des composants du serveur de conversation permanente
    
- Installer et configurer des composants de serveur de conversation permanente pour votre déploiement
    
Avant de déployer le serveur de conversation permanente, lisez [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Les rubriques de planification décrivent la configuration logicielle et matérielle requise, les topologies possibles et les scénarios de colocalisation. 
  
> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 

## <a name="deployment-checklist"></a>Liste de contrôle du déploiement

Vous pouvez déployer des serveurs de conversation permanente après avoir déployé votre topologie initiale, y compris au moins un Skype pour Business Server un pool frontal ou un Skype pour Business Standard Edition Server. La liste de contrôle de déploiement décrit les étapes de base nécessaires pour déployer des serveurs de conversation permanente et fournit des liens pour plus d’informations.
  
**Processus de déploiement de serveur de conversation permanente**

|**Tâche**|**Étapes**|**Rôles et appartenance aux groupes nécessaires**|**Rubriques associées**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> | Sur le matériel conforme à la configuration système requise, installez ce qui suit : <br/>  Sur la Persistent Chat serveurs frontaux : <br/>  Un système d’exploitation conforme à la configuration système requise <br/>  Éléments logiciels requis pour les ordinateurs exécutant Skype pour Business Server <br/>  Sur le serveur qui hébergera la base de données du serveur de conversation permanente : <br/>  Une version de SQL Server prise en charge <br/>  Si la conformité Persistent Chat Server est requise : <br/>  SQL Server sur le serveur qui hébergera la base de données de conformité Persistent Chat Server <br/> |Un utilisateur membre du groupe Administrateurs local.  <br/> |[Configuration serveur requise pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Conditions préalables d’environnement pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge des serveurs de conversation permanente (et éventuellement, conformité de conversation permanente)** <br/> | Exécutez le Générateur de topologie pour ajouter un pool de serveurs de conversation permanente à votre topologie : <br/>  Ajouter des composants de serveur de conversation permanente à la topologie <br/>  Créer une base de données SQL Server pour le magasin du serveur de conversation permanente (et une sauvegarde SQL Server pour la récupération d’urgence) <br/>  Définir un nouveau Skype pour le magasin de fichiers Business ou utilisez un Skype existant pour le magasin de fichiers d’entreprise pour les fichiers du serveur de conversation permanente <br/>  Associer le Skype pour pool Business Server qui permet d’acheminer les demandes vers ce pool de serveurs de conversation permanente <br/>  Si la conformité de conversation permanente est requise : <br/>  Ajouter le magasin de conformité de conversation permanente <br/>  Cliquez sur la case à cocher Persistent Chat Server pool définition pour activer la conformité <br/>  Publiez la topologie. <br/>  Si vous installez le serveur de conversation permanente sur Standard Edition, le nom de domaine complet (FQDN) du pool de serveurs de conversation permanente doit correspondre au serveur Standard Edition et les bases de données SQL Server sont colocalisés sur l’instance SQL Server Express sur la norme Serveur Édition <br/> |Pour définir une topologie, un compte membre du groupe Utilisateurs local  <br/> Pour publier la topologie, un compte qui est membre du groupe Admins du domaine et groupe RTCUniversalServerAdmins et l’utilisateur doit également avoir des autorisations Contrôle total (lecture/écriture/modifier) sur le Skype pour le magasin de fichiers Business pour les fichiers du serveur de conversation permanente (c’est le cas le Générateur de topologie peuvent configurer les DACL requis).  <br/> |[Création et publication d’une topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Ajouter des serveurs de conversation permanente à votre Skype pour Business Server 2015 topologie](add-persistent-chat-server.md) <br/> |
|**Déployer un serveur de conversation permanente** <br/> | Exécutez le Skype pour le programme d’installation de Business Server sur tous les ordinateurs exécutant le serveur de conversation permanente. La configuration du serveur de conversation permanente est intégrée à la Skype pour l’Assistant de déploiement de serveur d’entreprise qui fournit les instructions suivantes : <br/>  Déployer le magasin de gestion local <br/>  Installer les services de conversation permanente <br/>  Demander et affecter des certificats <br/>  Exécuter et démarrer les services <br/> |Un utilisateur membre du groupe Administrateurs local.  <br/> |[Déployer un serveur de conversation permanente dans Skype Entreprise Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Créer un administrateur de conversation permanente** <br/> |Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.  <br/> |Un utilisateur membre des administrateurs de domaines.  <br/> |[Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configuration du serveur de conversation permanente** <br/> | Configurez les utilisateurs : <br/>  Utilisateur doit être activé par stratégie pour accéder aux serveurs de conversation permanente. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur. <br/>  Configurer les paramètres <br/> |L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.  <br/> |[Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

