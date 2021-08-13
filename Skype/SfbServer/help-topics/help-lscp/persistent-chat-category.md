---
title: Catégorie de conversation permanente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Vous pouvez utiliser la section Catégorie de la page Conversation permanente pour configurer des catégories. Une catégorie de salle de conversation permanente est une structure logique d’organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et groupes d’utilisateurs autorisés à créer ou rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes subdivisions au sein de leurs organisations.
ms.openlocfilehash: 009cc7ef5cd35b7637f687043a0a5c5ddd24fa2f228c95a8bb4660b4c9140b47
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299820"
---
# <a name="persistent-chat-category"></a>Catégorie de conversation permanente
 
Vous pouvez utiliser la section **Catégorie** de la page **Conversation** permanente pour configurer des catégories. Une catégorie de salle de conversation permanente est une structure logique d’organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et groupes d’utilisateurs autorisés à créer ou rejoindre les salles de conversation. Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes subdivisions au sein de leurs organisations.
  
Les catégories de salles de conversation peuvent contenir des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que _nom_ et _description._ En outre, la catégorie possède des propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui lui appartiennent, par exemple si les salles de conversation autorisent les _invitations_ ou les _téléchargements_ de fichiers, ou contiennent l’historique de _conversation._
  
Pour créer une catégorie, voir [Manage categories in Persistent Chat Server in Skype Entreprise Server 2015](../../manage/persistent-chat/categories.md). Si vous êtes administrateur de conversation permanente, vous pouvez créer des catégories à l’aide du panneau de Windows PowerShell cmdlets.
  
## <a name="tasks-that-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes dans la page **Catégorie** :
  
- Créer ou modifier une nouvelle catégorie
    
- Déplacer une salle de conversation d’une catégorie vers une autre
    
- Supprimer une salle de conversation ou une catégorie
    
## <a name="to-configure-categories-for-chat-rooms"></a>Pour configurer les catégories des salles de conversation

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste finale.
    
4. Dans la page **Catégorie**, cliquez sur **Nouvelle** ou **Modifier**.
    
5. Dans **Sélectionner un service,** sélectionnez le service correspondant au pool de serveurs de conversation permanente sur lequel la catégorie doit être créée. Le service est le pool de serveurs de conversation permanente que la conversation permanente (client) utilise pour identifier le pool auquel appartient la catégorie. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de conversation permanente et ne peut pas être déplacée vers un autre pool ou partagée avec un autre pool.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
7. Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
8. Dans **Description**, fournissez une description détaillée de la catégorie de salle (exemple : catégorie de salle pour Contoso).
    
9. Pour contrôler si les invitations peuvent être activées pour les salles de conversation appartenant à cette catégorie, activez ou activez la case à cocher Activer les **invitations.** S’il est sélectionné, les salles de cette catégorie peuvent avoir des invitations en cours ou non ; si elles sont effacées, les salles de cette catégorie ne sont pas autorisées à recevoir des invitations. Si une salle a des invitations, lorsqu’un nouveau membre est ajouté à une salle, il reçoit une notification de la nouvelle salle dans son client de conversation permanente.
    
10. Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si la case à cocher est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
     > [!IMPORTANT]
     > Ce paramètre est appliqué sur le serveur car les applications personnalisées ou les clients group chat précédents qui utilisent Office Communications Server 2007 R2 Group Chat Server ou Lync Server 2010, Group Chat peuvent publier des fichiers dans une salle. Le client Lync 2013 n’a pas de fonctionnalité de téléchargement/téléchargement de fichiers. Par conséquent, si vous avez un déploiement Lync 2013 pur ou un client Lync 2013, il n’est pas possible de publier des fichiers dans une salle de conversation du serveur de conversation permanente. 
  
11. Pour contrôler l’historique des conversation, activez ou videz la case à cocher **Activer l’historique des** conversation. Si la case à cocher est activée, les conversations des salles deviennent permanentes ; sinon, les messages des conversations ne sont pas conservés. Si la conformité est activée, les conversations des salles sont enregistrées à des fins de conformité mais les utilisateurs ne peuvent pas accéder aux anciens messages. Cette option peut être utilisée pour les salles désignées pour des collaborations ad hoc en temps réel qui n’ont pas besoin d’être persistantes dans l’historique des conversation.
    
12. Dans **Modifier la catégorie**, procédez comme suit :
    
    - Dans l’appartenance, dans la **section** Membres autorisés, ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
    - Dans **l’appartenance**, dans la **section** Membres refusés, ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés à des membres refusés de la salle.
    
    - Dans **l’appartenance,** dans la section **Créateurs,** ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés aux créateurs de la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
13. Cliquez sur **Valider**.
    
## <a name="see-also"></a>Voir aussi

Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de conversation permanente, voir [Plan for Persistent Chat Server in Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), Deploy Persistent Chat Server in Skype Entreprise Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [Manage Persistent Chat Server in Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).
  

