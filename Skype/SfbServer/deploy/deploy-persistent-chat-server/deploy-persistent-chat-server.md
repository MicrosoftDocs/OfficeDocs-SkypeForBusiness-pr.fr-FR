---
title: Déploiement d’un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Résumé : Lisez cette rubrique pour découvrir comment déployer le serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830474"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Déploiement d’un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment déployer le serveur de conversation permanente Skype Entreprise Server 2015.
  
Pour déployer un serveur de conversation permanente, vous devez : 
  
- Utiliser le Générateur de topologies pour définir ou importer, puis publier votre topologie et les composants que vous souhaitez déployer
    
- Préparer votre environnement pour le déploiement des composants du serveur de conversation permanente
    
- Installer et configurer les composants du serveur de conversation permanente pour votre déploiement
    
Avant de déployer le serveur de conversation permanente, vous devez lire [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Les rubriques de planification décrivent les configurations matérielles et logicielles requises, les topologies possibles et les scénarios de c collocation. 
  
> [!NOTE] 
> La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015. 

## <a name="deployment-checklist"></a>Liste de vérification du déploiement

Vous pouvez déployer un serveur de conversation permanente après avoir déployé votre topologie initiale, y compris au moins un pool frontal Skype Entreprise Server ou un serveur Skype Entreprise Standard Edition Server. La liste de vérification du déploiement décrit les étapes de base requises pour déployer le serveur de conversation permanente et fournit des liens pour plus d’informations.
  
**Processus de déploiement du serveur de conversation permanente**

|**Tâche**|**Étapes**|**Rôles et appartenance aux groupes nécessaires**|**Rubriques connexes**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> | Sur le matériel conforme à la configuration système requise, installez ce qui suit : <br/>  Sur les serveurs frontux du serveur de conversation permanente : <br/>  Un système d’exploitation conforme à la configuration système requise <br/>  Conditions préalables logicielles pour les ordinateurs exécutant Skype Entreprise Server <br/>  Sur le serveur qui hébergera la base de données du serveur de conversation permanente : <br/>  Une version prise en charge de SQL Server <br/>  Si la conformité du serveur de conversation permanente est requise : <br/>  SQL Server sur le serveur qui hébergera la base de données de conformité du serveur de conversation permanente <br/> |Un utilisateur membre du groupe Administrateurs local  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Exigences environnementales pour Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Configuration matérielle et logicielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge le serveur de conversation permanente (et éventuellement la conformité de conversation permanente)** <br/> | Exécutez le Générateur de topologie pour ajouter un pool de serveurs de conversation permanente à votre topologie : <br/>  Ajouter des composants de serveur de conversation permanente à la topologie <br/>  Créer une base SQL Server de données pour le magasin de serveurs de conversation permanente (et une base de données de SQL Server pour la récupération d’urgence) <br/>  Définir un nouveau magasin de fichiers Skype Entreprise ou utiliser un magasin de fichiers Skype Entreprise existant pour les fichiers du serveur de conversation permanente <br/>  Associer le pool Skype Entreprise Server qui peut router les demandes vers ce pool de serveurs de conversation permanente <br/>  Si la conformité de conversation permanente est requise : <br/>  Ajouter un magasin de conformité de conversation permanente <br/>  Cochez la case définition du pool de serveurs de conversation permanente pour activer la conformité <br/>  Publiez la topologie. <br/>  Si vous installez le serveur de conversation permanente sur Standard Edition, le nom de domaine complet (FQDN) du pool de serveurs de conversation permanente doit correspondre au serveur Standard Edition Server et les bases de données SQL Server sont coclaquées sur l’instance SQL Server Express sur le serveur Standard Edition <br/> |Pour définir une topologie, un compte membre du groupe Utilisateurs local  <br/> Pour publier la topologie, un compte membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins, et l’utilisateur doit également avoir des autorisations de contrôle total (lecture/écriture/modification) sur le magasin de fichiers Skype Entreprise pour les fichiers du serveur de conversation permanente (afin que le Générateur de topologie puisse configurer les DAC requises).  <br/> |[Création et publication d’une topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Ajouter un serveur de conversation permanente à votre topologie Skype Entreprise Server 2015](add-persistent-chat-server.md) <br/> |
|**Déployer un serveur de conversation permanente** <br/> | Exécutez le programme d’installation de Skype Entreprise Server sur tous les ordinateurs exécutant le serveur de conversation permanente. La configuration du serveur de conversation permanente est intégrée à l’Assistant Déploiement de Skype Entreprise Server qui fournit les instructions suivantes : <br/>  Déployer le magasin de gestion local <br/>  Installer les services de conversation permanente <br/>  Demander et assigner des certificats <br/>  Exécuter et démarrer les services <br/> |Un utilisateur membre du groupe Administrateurs local  <br/> |[Déploiement d’un serveur de conversation permanente dans Skype Entreprise Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Créer un administrateur de conversation permanente** <br/> |Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.  <br/> |Un utilisateur membre des administrateurs de domaines.  <br/> |[Créer un administrateur de conversation permanente dans Skype Entreprise Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configuration du serveur de conversation permanente** <br/> | Configurez les utilisateurs : <br/>  L’utilisateur doit être activé par une stratégie pour accéder au serveur de conversation permanente. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur. <br/>  Configurer les paramètres <br/> |L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.  <br/> |[Gérer le serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

