---
title: Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 'Résumé : Lisez cette rubrique pour savoir comment créer des stratégies de l’utilisateur initial pour le serveur Chat persistant dans Skype pour Business Server 2015. Les stratégies utilisateur Chat permanentes déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.'
ms.openlocfilehash: 01ed6eb048f1949c93260c554eb58d0c76c5259f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>Configuration des stratégies utilisateur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment créer des stratégies de l’utilisateur initial pour le serveur Chat persistant dans Skype pour Business Server 2015. Les stratégies utilisateur Chat permanentes déterminent si les utilisateurs sont autorisés à accéder aux salles de conversation.
  
Vous pouvez gérer des stratégies d’utilisateur de serveur de conversation permanent aux niveaux suivants : global, site ou à l’utilisateur. Initialement, vous configurez la stratégie globale pour activer les paramètres de conversation permanente pour tous les utilisateurs de votre déploiement, puis créer des stratégies utilisateur et site supplémentaires afin de déterminer si la conversation permanente est activée pour des utilisateurs ou des sites spécifiques.
  
Cette rubrique contient les sections suivantes :
  
- Configurer la stratégie globale
    
- Créer une stratégie de site
    
- Créer une stratégie utilisateur
    
- Appliquer une stratégie à un utilisateur ou un groupe d’utilisateurs
    
## <a name="configure-the-global-policy"></a>Configurer la stratégie globale

Pour configurer la stratégie globale :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans Skype pour le panneau de configuration de Business Server, cliquez sur **Conversation permanent**, puis cliquez sur **Stratégie permanente de Chat**.
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit : 
    
   - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».
    
   - Dans **Description**, fournissez des détails sur les nouveautés de la stratégie de l’utilisateur (par exemple, une stratégie globale pour _centralSiteName_).
    
   - Pour contrôler le Chat permanente pour tous les sites et les utilisateurs ne sont pas spécifiquement contrôlés par une stratégie de site ou de la stratégie de l’utilisateur, activez ou désactivez la case à cocher **Activer le Chat persistant** .
    
6. Cliquez sur **Valider**.
    
## <a name="create-a-site-policy"></a>Créer une stratégie de site

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifique au site. La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est défini. Pour créer une stratégie de site :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).
    
   - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.
    
7. Cliquez sur **Valider**.
    
## <a name="create-a-user-policy"></a>Créer une stratégie utilisateur

Vous pouvez créer des stratégies propres à l’utilisateur qui remplacent la stratégie globale et les stratégies de tout site auquel appartient l’utilisateur. Pour créer une stratégie utilisateur :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
   - Dans **Description**, fournissez des détails sur les nouveautés de la stratégie de l’utilisateur (par exemple, Chat persistant de stratégie pour un utilisateur spécifique).
    
   - Pour contrôler le Chat permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlées par une stratégie utilisateur, activez ou désactivez la case à cocher **Activer le Chat persistant** .
    
6. Cliquez sur **Valider**.
    
## <a name="apply-a-policy-to-a-user-account"></a>Appliquer une stratégie à un compte d’utilisateur

Après avoir créé les stratégies, vous pouvez les appliquer à un compte d’utilisateur, comme suit :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier un Skype pour l’utilisateur de serveur d’entreprise** sous **stratégie de Chat persistant**, sélectionnez la stratégie d’utilisateur Chat permanent que vous souhaitez appliquer.
    
    > [!NOTE]
    > La ** \<automatique\> ** les paramètres s’appliquent à la stratégie par défaut en cours. Le serveur les applique automatiquement.
  
6. Cliquez sur **Valider**.
    

