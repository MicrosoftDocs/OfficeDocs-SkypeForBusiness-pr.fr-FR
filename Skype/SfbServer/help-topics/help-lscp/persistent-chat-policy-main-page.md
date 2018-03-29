---
title: Stratégie de conversation permanente – Page principale
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: Vous pouvez utiliser la page de stratégie permanente de Chat du groupe de conversation permanent pour gérer les stratégies à un niveau global, pool, site ou utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’un ou plusieurs utilisateurs et sites des stratégies supplémentaires pour votre déploiement. Si un utilisateur est activé pour le serveur de conversation permanent par la stratégie, l’environnement du serveur de conversation permanent s’affiche dans leur client.
ms.openlocfilehash: 14d600c558a7a72887aa7ff3e349857115e8a792
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-policy-main-page"></a>Stratégie de conversation permanente – Page principale
 
Vous pouvez utiliser la page **Stratégie de conversation permanente** du groupe **Conversation permanente** pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si un utilisateur est activé pour le serveur de conversation permanent par la stratégie, l’environnement du serveur de conversation permanent s’affiche dans leur client.
  
> [!NOTE]
> Dans la topologie, les stratégies de site de serveur de Chat persistant s’appliquent globalement, par pool de l’utilisateur, ou par le site de l’utilisateur ou par l’utilisateur. 
  
La stratégie globale est créée automatiquement lorsque vous déployez des persistant Chat Server, et il peut être configuré, mais pas supprimé. Étant donné que la stratégie globale s’applique à tous les utilisateurs, il ne doit être défini par l’utilisateur.
  
Vous pouvez créer et configurer plusieurs stratégies de site et d’utilisateur qui, avec la stratégie globale, permettent aux utilisateurs de serveur de conversation persistant. Les stratégies permanentes Chat Server pool et site substituent la stratégie persistante Chat Server globale, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur remplacent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est affectée.
  
> [!NOTE]
> Pour configurer et utiliser le serveur de conversation permanent, vous devez d’abord utiliser le Générateur de topologies pour ajouter la prise en charge du serveur de conversation persistant à la topologie et puis publiez la topologie. Pour plus d’informations, consultez [Ajouter serveur Chat persistant à votre Skype pour la topologie de Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Stratégie de conversation permanente**, vous pouvez effectuer les tâches suivantes : autorisation et gestion de la stratégie de serveur de conversation permanente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Pour configurer la stratégie globale de Chat persistant

1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans Skype pour le panneau de configuration de Business Server, cliquez sur **Conversation permanent**, puis cliquez sur **Stratégie permanente de Chat**.
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
  - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».
    
  - Dans **Description**, fournissez des détails sur les nouveautés de la stratégie de l’utilisateur (par exemple, une stratégie globale pour _centralSiteName_).
    
  - Pour contrôler le Chat permanente pour tous les sites et les utilisateurs ne sont pas spécifiquement contrôlés par une stratégie de site ou de la stratégie de l’utilisateur, activez ou désactivez la case à cocher **Activer le Chat persistant** .
    
6. Cliquez sur **Valider**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Pour créer une stratégie pour un site de Chat persistant

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de Chat persistant spécifiques au site.
  
La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
  - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).
    
  - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).
    
  - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.
    
7. Cliquez sur **Valider**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Pour créer une stratégie d’utilisateur de Chat persistant

Dans le panneau de commande du serveur Business Skype, vous définissez des stratégies d’utilisateur qui peuvent être affectés aux utilisateurs dans **utilisateurs**.
  
La stratégie utilisateur remplace les stratégies globales et de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
  - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
  - Dans **Description**, fournissez des détails sur les nouveautés de la stratégie de l’utilisateur (par exemple, Chat persistant de stratégie pour un utilisateur spécifique).
    
  - Pour contrôler le Chat permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlées par une stratégie utilisateur, activez ou désactivez la case à cocher **Activer le Chat persistant** .
    
6. Cliquez sur **Valider**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Pour appliquer une stratégie d’utilisateur Chat permanente à un compte d’utilisateur

Si un utilisateur a été activé pour Skype pour les entreprises, vous pouvez appliquer les stratégies appropriées à des utilisateurs spécifiques pour les activer ou les désactiver pour serveur de Chat persistant.
  
Pour appliquer une stratégie d’utilisateur Chat persistant créée précédemment pour un ou plusieurs comptes d’utilisateurs ou des groupes d’utilisateurs, utilisez la procédure dans cette rubrique.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. **Modifier l’utilisateur Lync Server** sous **stratégie de Chat persistant**, sélectionnez la stratégie d’utilisateur Chat permanent que vous souhaitez appliquer.
    
    > [!NOTE]
    > La ** \<automatique\> ** les paramètres s’appliquent à la stratégie par défaut en cours. Le serveur les applique automatiquement.
  
6. Cliquez sur **Valider**.
    

