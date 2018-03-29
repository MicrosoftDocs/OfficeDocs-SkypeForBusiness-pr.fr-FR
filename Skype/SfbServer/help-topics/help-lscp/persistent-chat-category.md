---
title: Catégorie de conversation permanente
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: Vous pouvez utiliser la section catégorie de la page Chat persistant pour configurer des catégories. Une catégorie de salle de conversation permanent est une structure logique pour organiser les salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.
ms.openlocfilehash: 24be7e342e5c87d355d577a05a7039872c0b2602
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-category"></a>Catégorie de conversation permanente
 
Vous pouvez utiliser la section **Catégorie** de la page **Conversation permanente** pour configurer des catégories. Une catégorie de salle de conversation permanent est une structure logique pour organiser les salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.
  
Catégories de salles de Chat peuvent contenir des salles de chat, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que le _nom_ et la _Description_. En outre, la catégorie possède des propriétés qui peuvent être définies pour contrôler le comportement de la salle de conversation lui appartenant, par exemple, si les salles de conversation permettent _des Invitations_ ou des _Téléchargements de fichiers_, ou contenir un _Historique de conversation_.
  
Pour créer une nouvelle catégorie, voir [Gérer les catégories dans le serveur Chat persistant dans Skype pour Business Server 2015](../../manage/persistent-chat/categories.md). Si vous êtes un administrateur de Chat persistantes, vous pouvez créer des catégories en utilisant le panneau de configuration ou les applets de commande Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Catégorie**, vous pouvez effectuer les tâches suivantes :
  
- Création ou modification d’une catégorie
    
- Déplacement d’une salle de conversation d’une catégorie vers une autre
    
- Suppression d’une catégorie ou d’une salle de conversation
    
## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration de Business Server ou ouvrir une fenêtre de navigateur et puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Pour plusieurs déploiements de pool persistant Chat Server, sélectionnez le pool approprié dans la liste déroulante.
    
4. Dans la page **Catégorie**, cliquez sur **Créer** ou **Modifier**.
    
5. Dans la zone **Sélectionnez un Service**, sélectionnez le service correspondant au pool persistant Chat Server sur lequel la catégorie doit être créé. Le service est le serveur Chat persistant pool par le Chat persistant (client) pour identifier la catégorie du pool auquel appartient. Une catégorie peut appartenir à un seul pool de serveur de Chat persistant et ne peut pas être déplacée vers un autre ou partagée avec un autre pool.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
1. Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
2. Dans **Description**, indiquez une description détaillée de la catégorie de salle (par exemple, « catégorie de salle pour Contoso »).
    
3. Pour contrôler des invitations peuvent être activées pour les salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **Activer les invitations** . Si sélectionné, les salles de cette catégorie peuvent avoir des invitations on ou off ; Si désactivée, les locaux de cette catégorie ne sont pas autorisés pour que les invitations. Si une pièce a des invitations sur, lorsqu’un nouveau membre est ajouté à un espace, il obtient une notification de la nouvelle pièce dans leur client Chat persistant.
    
4. Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si elle est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
    > [!IMPORTANT]
    > Ce paramètre est appliqué sur le serveur, car les applications personnalisées ou des clients de conversation de groupe précédents qui utilisent le serveur Office Communications Server 2007 R2 groupe Chat ou Lync Server 2010, groupe de conversation peuvent publier des fichiers à un espace. Le client Lync 2013 ne dispose pas de fonctionnalité de téléchargement de fichier, donc si vous avez un déploiement de Lync 2013 pur ou un client de Lync 2013, il n’est pas possible de publier des fichiers dans une salle de conversation permanent serveur de conversation. 
  
5. Pour contrôler l’historique de conversation, activez ou désactivez la case à cocher **Activer l’historique de conversation** . Si sélectionné, les conversations de salle devient permanentes ; dans le cas contraire, les messages de conversation ne sont pas conservées. Si la conformité est activée, salle salles de conversation seront enregistrées dans le respect de la réglementation, mais les utilisateurs ne seront pas en mesure d’accéder à des messages plus anciens. Cette option peut être utilisée pour les salles de désigné pour la collaboration en temps réel, ad hoc qui ne nécessaire pas l’historique de la conversation pour être rendues persistantes.
    
7. Dans **Modifier la catégorie**, procédez comme suit :
    
  - Dans **l’appartenance**, dans la section **membres d’autorisés** , ajouter ou supprimer des utilisateurs et des autres entités de Services de domaine Active Directory (utilisateurs, groupes de distribution, les unités d’organisation, etc.) qui sont autorisées à être ajoutés comme membres de salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
  - **Appartenance**, dans la section **membres de refusé** , ajouter ou supprimer des utilisateurs et des autres entités de sécurité Active Directory associées aux membres refusées à partir de la salle de.
    
  - **Appartenance**, dans la section **créateurs** , ajouter ou supprimer des utilisateurs et autres entités de Active Directory associées aux créateurs pour la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
8. Cliquez sur **Valider**.
    
### 

Pour plus d’informations sur les fonctionnalités de serveur de conversation persistant de, voir [planification serveur Chat persistant dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer le serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [Gérer permanent Chat Server dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

