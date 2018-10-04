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
description: Vous pouvez utiliser la page Stratégie de conversation permanente du groupe Conversation permanente pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si un utilisateur est activé pour le serveur de conversation permanente par stratégie, l’environnement de serveur de conversation permanente s’affiche dans le client.
ms.openlocfilehash: 670c372c5dc3997d0d2c15622a9780e52c03508c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372727"
---
# <a name="persistent-chat-policy-main-page"></a>Stratégie de conversation permanente – Page principale
 
Vous pouvez utiliser la page **Stratégie de conversation permanente** du groupe **Conversation permanente** pour gérer les stratégies au niveau utilisateur, site, pool ou global, y compris pour configurer la stratégie globale par défaut et créer une ou plusieurs autres stratégies utilisateur et de site pour votre déploiement. Si un utilisateur est activé pour le serveur de conversation permanente par stratégie, l’environnement de serveur de conversation permanente s’affiche dans le client.
  
> [!NOTE]
> Dans la topologie, les stratégies de site Persistent Chat Server s’appliquent globalement, par pool de l’utilisateur ou par site de l’utilisateur ou par utilisateur. 
  
La stratégie globale est créée automatiquement lorsque vous déployez le serveur de conversation permanente, et il peut être configuré, mais pas supprimé. Étant donné que la stratégie globale s’applique à tous les utilisateurs, il ne doit être définie par l’utilisateur.
  
Vous pouvez créer et configurer plusieurs stratégies de site et d’utilisateur qui, avec la stratégie globale, permettent aux utilisateurs pour le serveur de conversation permanente. Les stratégies de Persistent Chat Server pool et site remplacent la stratégie globale de serveur de conversation permanente, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur remplacent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est affectée.
  
> [!NOTE]
> Pour configurer et utiliser le serveur de conversation permanente, vous devez tout d’abord utiliser le Générateur de topologie pour ajouter la prise en charge des serveurs de conversation permanente à la topologie et puis publiez la topologie. Pour plus d’informations, voir [Ajouter des serveurs de conversation permanente à votre Skype pour topologie Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md). 
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Stratégie de conversation permanente**, vous pouvez effectuer les tâches suivantes : autorisation et gestion de la stratégie de serveur de conversation permanente.
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>Pour configurer la stratégie globale pour la conversation permanente

1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans Skype pour Business Server le panneau de configuration, cliquez sur **Conversation permanente**, puis cliquez sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Globale** dans la liste des stratégies, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier la stratégie de conversation permanente - Globale**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nouveau nom pour la stratégie globale si vous ne souhaitez pas utiliser le nom par défaut « Global ».
    
   - Dans **Description**, fournissez les informations décrivant la stratégie utilisateur (par exemple, stratégie globale pour _Nom_site_central_).
    
   - Pour contrôler la conversation permanente pour tous les sites et les utilisateurs ne sont pas spécifiquement contrôlés via une stratégie de site ou d’une stratégie utilisateur, activez ou désactivez la case à cocher **Activer la conversation permanente** .
    
6. Cliquez sur **Valider**.
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>Pour créer une stratégie de conversation permanente pour un site

Pour chaque site que vous avez déployé, vous pouvez créer une stratégie de conversation permanente spécifiques au site.
  
La configuration de la stratégie de site remplace la stratégie globale, uniquement pour le site pour lequel elle est définie.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie de site**.
    
5. Dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit s’appliquer.
    
6. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie de site (par exemple, « Redmond »).
    
   - Dans **Description**, entrez des informations décrivant la stratégie de site (par exemple, « Stratégie de salle de conversation pour Redmond »).
    
   - Pour contrôler la conversation permanente pour tous les sites qui ne sont pas contrôlés spécifiquement par le biais d’une stratégie de site, activez ou désactivez la case à cocher **Activer la conversation permanente**.
    
7. Cliquez sur **Valider**.
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>Pour créer une stratégie utilisateur pour la conversation permanente

Dans Skype pour le panneau de configuration serveur Business, vous définissez des stratégies d’utilisateur qui peuvent être affectés aux utilisateurs dans **utilisateurs**.
  
La stratégie utilisateur remplace les stratégies globales et de site, mais uniquement pour les utilisateurs spécifiques auxquels la stratégie utilisateur est affectée.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Stratégie de conversation permanente**.
    
4. Cliquez sur **Créer**, puis sur **Stratégie utilisateur**.
    
5. Dans **Nouvelle stratégie de conversation permanente**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle stratégie utilisateur.
    
   - Dans **Description**, fournissez les informations décrivant la stratégie utilisateur (par exemple, stratégie de conversation permanente pour utilisateur spécifique).
    
   - Pour contrôler la conversation permanente pour tous les utilisateurs qui ne sont pas spécifiquement contrôlés via une stratégie utilisateur, activez ou désactivez la case à cocher **Activer la conversation permanente** .
    
6. Cliquez sur **Valider**.
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Pour appliquer une stratégie utilisateur de conversation permanente à un compte d’utilisateur

Si un utilisateur a été activé pour Skype pour les entreprises, vous pouvez appliquer les stratégies appropriées à des utilisateurs spécifiques pour activer ou désactiver pour le serveur de conversation permanente.
  
Utilisez la procédure de cette rubrique pour appliquer une stratégie utilisateur de conversation permanente précédemment créée à un ou plusieurs comptes d’utilisateurs ou groupes d’utilisateurs.
  
1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur à configurer.
    
4. Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.
    
5. Dans **Modifier l’utilisateur Lync Server** sous **stratégie de conversation permanente**, sélectionnez la stratégie d’utilisateur de conversation permanente que vous souhaitez appliquer.
    
    > [!NOTE]
    > Le ** \<automatique\> ** paramètres s’appliquent à la stratégie par défaut en cours. Le serveur les applique automatiquement.
  
6. Cliquez sur **Valider**.
    

