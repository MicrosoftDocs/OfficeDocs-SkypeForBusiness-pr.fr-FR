---
title: Déployer un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Résumé: cette rubrique vous explique comment déployer Skype entreprise Server 2015 permanent Chat Server.'
ms.openlocfilehash: 06cc51ccbbab193e749c2f919102d7d38fde3f56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273895"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Déployer un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Pour plus d’informations sur le déploiement de Skype entreprise Server 2015, voir le serveur de chat permanent.
  
Pour déployer le serveur de chat permanent, vous devez: 
  
- Utiliser le générateur de topologie pour définir, importer et publier ultérieurement votre topologie et les composants que vous voulez déployer
    
- Préparer votre environnement pour le déploiement de composants serveur Chat permanent
    
- Installer et configurer les composants serveur de chat permanent pour votre déploiement
    
Avant de déployer le serveur Chat permanent, il est conseillé de lire [plan pour le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Les rubriques de planification décrivent la configuration logicielle et matérielle requise, les topologies possibles et les scénarios de colocalisation. 
  
> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 

## <a name="deployment-checklist"></a>Liste de contrôle du déploiement

Vous pouvez déployer un serveur Chat permanent après le déploiement de votre topologie initiale, y compris au moins une liste frontale Skype entreprise Server ou un serveur Skype entreprise Standard Edition. La liste de vérification de déploiement décrit la procédure de déploiement de chat permanent et fournit des liens pour en savoir plus.
  
**Processus de déploiement d’un serveur de chat permanent**

|**Task**|**Étapes**|**Rôles et appartenance aux groupes nécessaires**|**Rubriques associées**|
|:-----|:-----|:-----|:-----|
|**Installer le matériel et les logiciels prérequis** <br/> | Sur le matériel conforme à la configuration système requise, installez ce qui suit : <br/>  Sur les serveurs front-end serveur Chat permanent: <br/>  Un système d’exploitation conforme à la configuration système requise <br/>  Configuration logicielle requise pour les ordinateurs exécutant Skype entreprise Server <br/>  Sur le serveur qui héberge la base de données serveur Chat permanent: <br/>  Une version de SQL Server prise en charge <br/>  Si la conformité du serveur Chat permanent est requise: <br/>  Serveur SQL Server sur le serveur qui héberge la base de données de compatibilité de serveur Chat permanent <br/> |Un utilisateur membre du groupe Administrateurs local.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Configuration logicielle et matérielle requise pour le serveur de conversation permanente dans Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Créer la topologie interne appropriée pour prendre en charge le serveur de chat permanent (et éventuellement la conformité avec la conversation permanente)** <br/> | Exécutez le générateur de topologie pour ajouter un pool de serveurs de chat permanent à votre topologie: <br/>  Ajouter des composants serveur de chat permanent à la topologie <br/>  Créer une base de données SQL Server pour le magasin serveur Chat permanent (et un serveur SQL de sauvegarde pour la récupération d’urgence) <br/>  Définition d’une nouvelle banque de fichiers Skype entreprise ou utilisation d’un magasin de fichiers Skype entreprise existant pour les fichiers du serveur de chat permanent <br/>  Associez le pool Skype entreprise Server qui peut acheminer les demandes vers ce pool de serveurs de chat permanent. <br/>  Si la conformité de conversation permanente est requise : <br/>  Ajouter un magasin de conformité des conversations permanentes <br/>  Cliquez sur la case à cocher de la définition de pool de serveurs de conversation permanente pour activer la conformité <br/>  Publiez la topologie. <br/>  Si vous installez le serveur Chat permanent sur l’édition standard, le nom de domaine complet (FQDN) du pool de serveurs de chat permanent doit correspondre au serveur Standard Edition Server, et les bases de données SQL Server sont colocalisées sur l’instance SQL Server Express sur le standard. Serveur édition <br/> |Pour définir une topologie, un compte membre du groupe Utilisateurs local  <br/> Pour publier la topologie, un compte membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins et l’utilisateur doit également disposer des autorisations de contrôle total (lecture/écriture/modification) sur le stockage de fichiers Skype entreprise pour les fichiers de chat permanent Ce générateur de topologie peut configurer les DACL requis).  <br/> |[Création et publication d’une topologie dans Skype Entreprise Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Ajouter un serveur de chat permanent à votre topologie 2015 Skype entreprise Server](add-persistent-chat-server.md) <br/> |
|**Déployer un serveur de conversation permanente** <br/> | Exécutez le programme d’installation de Skype entreprise Server sur tous les ordinateurs exécutant la fonction de chat permanent du serveur. La configuration du serveur de chat permanent est intégrée à l’Assistant Déploiement de Skype entreprise Server, qui fournit les instructions suivantes: <br/>  Déployer le magasin de gestion local <br/>  Installer les services de chat permanent <br/>  Demander et affecter des certificats <br/>  Exécuter et démarrer les services <br/> |Un utilisateur membre du groupe Administrateurs local.  <br/> |[Déployer un Serveur de Conversation Permanente dans Skype Entreprise Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Créer un administrateur de conversation permanente** <br/> |Ajoutez des utilisateurs au groupe de sécurité CsPersistentChatAdministrator.  <br/> |Un utilisateur membre des administrateurs de domaines.  <br/> |[Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configuration du serveur de conversation permanente** <br/> | Configurez les utilisateurs : <br/>  La stratégie doit être activée pour permettre à l’utilisateur d’accéder au serveur de chat permanent. Par défaut, la stratégie est désactivée pour tous les utilisateurs et peut être définie au niveau de l’étendue globale/Site/Pool/Utilisateur. <br/>  Configurer les paramètres <br/> |L’utilisateur doit être membre du groupe CsPersistentChatAdministrator. Pour changer de stratégie, l’utilisateur doit au moins faire partie du groupe CsUserAdministrator.  <br/> |[Gérer un serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

