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
description: 'Résumé : Lisez cette rubrique pour savoir comment déployer Skype pour Business Server 2015 persistant Chat Server.'
ms.openlocfilehash: c2dedae876c61f84d672f8cf457e1b6c4baeff43
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Déployer un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment déployer Skype pour Business Server 2015 persistant Chat Server.
  
Pour déployer le serveur Chat persistant, vous : 
  
- Générateur de topologies permet de définir, ou importer et ensuite publier votre topologie et les composants que vous souhaitez déployer
    
- Préparez votre environnement pour le déploiement des composants de serveur de conversation persistant
    
- Installer et configurer les composants serveur de Chat persistant pour votre déploiement.
    
Avant de déployer persistant Chat Server, vous devez lire le [Plan pour serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Les rubriques de planification décrivent la configuration logicielle et matérielle requise, les topologies possibles et les scénarios de colocalisation. 
  
## <a name="deployment-checklist"></a>Liste de contrôle du déploiement

Vous pouvez déployer le serveur de Chat persistant après avoir déployé votre topologie initiale, y compris au moins un Skype pour le pool d’entreprise serveur frontal ou un Skype pour entreprise Standard Edition Server. La liste de vérification de déploiement décrit les étapes de base nécessaires pour déployer le serveur de Chat persistant et fournit des liens pour plus de détails.
  
**Processus de déploiement de serveur de conversation permanent**

|**Tâche**|**Étapes**|**Appartenances aux groupes et les rôles requis**|**Rubriques connexes**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> | Sur le matériel conforme à la configuration système requise, installez ce qui suit : <br/>  Sur les connexions de Chat Server Front-End Servers : <br/>  Un système d’exploitation conforme à la configuration système requise <br/>  Configuration logicielle requise pour les ordinateurs exécutant Skype pour Business Server <br/>  Sur le serveur qui hébergera la base de données du serveur de conversation persistant : <br/>  Une version de SQL Server prise en charge <br/>  Si la conformité du serveur de conversation permanent est nécessaire : <br/>  SQL Server sur le serveur qui hébergera la base de données de conformité permanente Chat Server <br/> |Un utilisateur membre du groupe Administrateurs local.  <br/> |[Configuration serveur requise pour Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Besoins environnementaux dans Skype pour Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Matérielle et logicielle requise pour le serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Création de la topologie interne appropriée pour prendre en charge le serveur de Chat persistant (et éventuellement, Chat permanente de la conformité)** <br/> | Exécuter le Générateur de topologies pour ajouter un pool de serveurs de Chat permanente à votre topologie : <br/>  Ajouter des composants de serveur de conversation persistant à la topologie <br/>  Créer une base de données SQL Server pour le magasin persistant Chat Server (et une sauvegarde de SQL Server pour la reprise après sinistre) <br/>  Définir un nouveau Skype activité magasin de fichiers ou utiliser un Skype existant activité magasin de fichiers pour les fichiers de serveur de conversation persistant <br/>  Associer le Skype pour le pool de serveur d’entreprise qui peut acheminer des requêtes vers ce pool persistant Chat Server <br/>  Si la conformité de conversation permanente est requise : <br/>  Ajouter banque de conformité de conversation permanente <br/>  Cliquez sur la case persistant Chat Server Définition pool d’activation de la conformité <br/>  Publiez la topologie. <br/>  Si vous installez le serveur de conversation permanent sur Édition Standard, le nom de domaine complet (FQDN) du pool persistant Chat Server doit correspondre au serveur Standard Edition et les bases de données SQL Server sont colocalisés sur l’instance de SQL Server Express sur la norme Édition server <br/> |Pour définir une topologie, un compte membre du groupe Utilisateurs local  <br/> Pour publier la topologie, un compte qui est membre du groupe Admins du domaine et de groupe RTCUniversalServerAdmins et de l’utilisateur doit également avoir les autorisations de contrôle total (en lecture/écriture/modification) sur le Skype activité magasin de fichiers pour les fichiers de serveur de conversation persistant (c’est le cas Générateur de topologies peut configurer les listes DACL requises).  <br/> |[Créez et publiez la nouvelle topologie dans Skype pour Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Ajouter serveur de Chat permanente à votre Skype pour la topologie de Business Server 2015](add-persistent-chat-server.md) <br/> |
|**Déployer le serveur de conversation permanent** <br/> | Exécutez le Skype pour le programme d’installation du serveur de l’entreprise sur tous les ordinateurs exécutant le serveur de Chat persistant. Le programme d’installation du serveur de Chat persistant est intégré dans le Skype pour l’Assistant de déploiement de serveur d’entreprise qui fournit des instructions : <br/>  Déployer le magasin de gestion local <br/>  Installer les services de conversation permanent <br/>  Demander et affecter des certificats <br/>  Exécuter et démarrer les services <br/> |Un utilisateur membre du groupe Administrateurs local.  <br/> |[Déployer le serveur de conversation permanents dans Skype pour Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Créer un administrateur de Chat persistant** <br/> |Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.  <br/> |Un utilisateur membre des administrateurs de domaines.  <br/> |[Créer un administrateur de Chat persistant dans Skype pour Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurer le serveur de conversation permanent** <br/> | Configurez les utilisateurs : <br/>  Utilisateur doit être activé par la stratégie d’accéder aux serveur de Chat persistant. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur. <br/>  Configurer les paramètres <br/> |L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.  <br/> |[Gérer le serveur de conversation permanents dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

