---
title: Catégorie de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: Vous pouvez utiliser la section Catégorie de la page Conversation permanente pour configurer des catégories. Une catégorie de salles de conversation permanente est une structure logique d’organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.
ms.openlocfilehash: de0a638da6de622b9646347c4eaa733deecdd2ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822547"
---
# <a name="persistent-chat-category"></a>Catégorie de conversation permanente
 
Vous pouvez utiliser la section **Catégorie** de la page **Conversation permanente** pour configurer des catégories. Une catégorie de salles de conversation permanente est une structure logique d’organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et des groupes d’utilisateurs autorisés à créer ou à rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes sous-divisions au sein de leur organisation.
  
Les catégories de salle de conversation pourront contenir des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que _nom_ et _Description_. De plus, la catégorie dispose de propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui en dépendent, par exemple si les salles de conversation autorisent les _invitations_ ou les _téléchargements de fichiers_, ou qui contiennent _l’historique_de vos conversations.
  
Pour créer une catégorie, reportez-vous à la rubrique [gérer les catégories dans le serveur Chat permanent de Skype entreprise server 2015](../../manage/persistent-chat/categories.md). Si vous êtes un administrateur de chat permanent, vous pouvez créer des catégories à l’aide du panneau de configuration ou des applets de commande Windows PowerShell.
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Catégorie**, vous pouvez effectuer les tâches suivantes :
  
- Création ou modification d’une catégorie
    
- Déplacement d’une salle de conversation d’une catégorie vers une autre
    
- Suppression d’une catégorie ou d’une salle de conversation
    
## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

1. À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Dans la liste déroulante des déploiements de pools de serveurs de chat permanent, sélectionnez le pool approprié.
    
4. Dans la page **Catégorie**, cliquez sur **Créer** ou **Modifier**.
    
5. Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de chat permanent sur lequel la catégorie doit être créée. Le service est le pool de serveurs de chat permanent que le client de chat permanent utilise pour identifier le regroupement auquel la catégorie appartient. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de chat permanent et ne peut pas être déplacée vers une autre liste ou partagée avec un autre.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
7. Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
8. Dans **Description**, indiquez une description détaillée de la catégorie de salle (par exemple, « catégorie de salle pour Contoso »).
    
9. Pour déterminer si les invitations peuvent être activées pour des salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **activer les invitations** . Si cette option est sélectionnée, les salles de cette catégorie peuvent avoir des invitations activées ou désactivées ; Si cette option est désactivée, les salles de cette catégorie ne peuvent pas avoir d’invitations. Si une salle est dotée d’invitations à l’ajout d’un nouveau membre, ce dernier reçoit une notification de la nouvelle salle dans le client de chat permanent.
    
10. Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si elle est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
     > [!IMPORTANT]
     > Ce paramètre est appliqué sur le serveur, car des applications personnalisées ou des clients de discussion de groupe précédents qui utilisent Office Communications Server 2007 R2 Server Chat Server ou Lync Server 2010, une discussion de groupe peut publier des fichiers dans une salle. Le client Lync 2013 ne disposant pas de la fonctionnalité de chargement et de téléchargement de fichiers, donc si vous avez un simple déploiement Lync 2013 ou un client Lync 2013, il est impossible de publier des fichiers dans une salle de conversation serveur Chat permanent. 
  
11. Pour contrôler l’historique des conversations, cochez ou décochez la case **activer l’historique des conversations** . Si cette option est sélectionnée, les conversations de la salle deviennent permanentes ; dans le cas contraire, les messages ne sont pas conservés. Si la conformité est activée, les discussions sur place seront enregistrées en conformité, mais les utilisateurs ne seront pas en mesure d’accéder à d’anciens messages. Cette option peut être utilisée pour les salles destinées à des réunions ad hoc en temps réel, qui n’ont pas besoin de l’historique des discussions pour être persistants.
    
12. Dans **Modifier la catégorie**, procédez comme suit :
    
    - Dans **appartenance**, dans la section **membres autorisés** , ajoutez ou supprimez des utilisateurs et d’autres principaux services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres de salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
    - Dans **appartenance (membership**), dans la section **membres refusés** , ajoutez ou supprimez des utilisateurs et d’autres entités Active Directory associées aux membres refusés à partir de la salle.
    
    - Dans **appartenance**, dans la section **créateurs** , ajoutez ou supprimez des utilisateurs et d’autres entités Active Directory associées à des créateurs pour la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
13. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de chat permanent, voir [planifier le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer le serveur de conversation permanente dans skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanent dans Skype entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

