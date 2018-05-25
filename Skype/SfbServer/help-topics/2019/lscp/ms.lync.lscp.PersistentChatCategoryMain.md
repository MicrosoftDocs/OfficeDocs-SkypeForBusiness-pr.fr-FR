---
title: Catégorie de conversation permanente – Page principale
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: Vous pouvez utiliser la section catégorie de la page de conversation permanente pour configurer des catégories. Catégorie de salle de conversation permanente est une structure logique pour organiser des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.
ms.openlocfilehash: 52c58cb17f4d5bec9fbfb61188ac67d5d57978c3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="persistent-chat-category-main-page"></a>Catégorie de conversation permanente – Page principale
 
Vous pouvez utiliser la section **Catégorie** de la page **Conversation permanente** pour configurer des catégories. Catégorie de salle de conversation permanente est une structure logique pour organiser des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.
  
Catégories de salle de conversation peuvent contenir des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que _nom_ et _Description_. En outre, la catégorie possède les propriétés qui peuvent être définies pour contrôler le comportement de la salle de conversation appartenant, par exemple, si les salles de conversation autoriser les _Invitations_ ou _Téléchargement de fichiers_ou contenir _L’historique des conversations_.
  
Pour créer une nouvelle catégorie, voir [Gérer les catégories dans Persistent Chat Server dans Skype pour Business Server 2015](../../manage/persistent-chat/categories.md). Si vous êtes un administrateur de conversation permanente, vous pouvez créer des catégories à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Catégorie**, vous pouvez effectuer les tâches suivantes :
  
- Création ou modification d’une catégorie
    
- Déplacement d’une salle de conversation d’une catégorie vers une autre
    
- Suppression d’une catégorie ou d’une salle de conversation
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a>Pour configurer des catégories pour les salles de conversation permanente

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration. .
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.
    
4. Dans la page **Catégorie**, cliquez sur **Créer** ou **Modifier**.
    
5. Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente sur lequel la catégorie doit être créé. Le service est le serveur de conversation permanente pool que la conversation permanente (client) utilise pour identifier la catégorie du pool auquel appartient. Une catégorie peut appartenir qu’un seul pool de serveurs de conversation permanente et ne peut pas être déplacée vers un autre ou partagée avec un autre pool.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
1. Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
2. Dans **Description**, indiquez une description détaillée de la catégorie de salle (par exemple, « catégorie de salle pour Contoso »).
    
3. Pour contrôler si les invitations peuvent être activées pour les salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **Activer les invitations** . Si sélectionné, les salles de cette catégorie peuvent ont des invitations on ou off ; Si désactivée, les salles de cette catégorie ne sont pas autorisés à avoir des invitations. Si une salle a invitations sur lorsqu’un nouveau membre est ajouté à un espace, il obtient une notification de la nouvelle salle de client de conversation permanente.
    
4. Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si elle est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
5. Pour contrôler l’historique des conversations, activez ou désactivez la case à cocher **Activer l’historique des conversations** . Si sélectionné, conversations salle devient permanentes ; dans le cas contraire, les messages de conversation ne sont pas conservées. Si la conformité est activée, conversations salle seront enregistrées dans la conformité, mais les utilisateurs ne pourront pas accéder aux anciens messages. Cette option peut être utilisée pour les salles désignés pour la collaboration en temps réel, ad hoc qui n’ont pas besoin de l’historique des conversations d’être conservée.
    
7. Dans **Modifier la catégorie**, procédez comme suit :
    
  - Dans **l’appartenance**, dans la section **membres autorisés** , ajouter ou supprimer des utilisateurs et autres entités de Services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation et ainsi de suite) sont autorisées à ajouter en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
  - Dans **l’appartenance**, dans la section **membres refusés** , ajouter ou supprimer des utilisateurs et autres principaux Active Directory associées aux membres refusées à partir de la salle.
    
  - Dans **l’appartenance**, dans la section **créateurs** , ajouter ou supprimer des utilisateurs et autres principaux Active Directory associé aux créateurs de la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
8. Cliquez sur **Valider**.
    
### 

Pour plus d’informations sur le serveur de conversation permanente des fonctionnalités, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer Persistent Chat Server dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanente dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

