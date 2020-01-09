---
title: Gestion des catégories sur un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Résumé : Découvrez comment gérer les catégories serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: f0c85c2246c85c93f96e6c13cef0a5d4360213cb
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991999"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestion des catégories sur un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer les catégories de serveurs de chat permanent dans Skype entreprise Server 2015.
  
Une catégorie est une structure logique permettant d’organiser des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès (ACL) pour contrôler les utilisateurs et groupes d’utilisateurs qui peuvent créer des salles de conversation ou y participer. Les catégories de salle de conversation contiennent des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que nom et description. La catégorie dispose de propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui en dépendent. par exemple, si les salles de conversation autorisent les invitations ou les téléchargements de fichiers ou contiennent l’historique de vos conversations. 
  
La création et la gestion des salles de conversation est beaucoup plus facile en cas d’utilisation pertinente des catégories. En tant qu’administrateur du serveur de conversation permanente, vous pouvez définir AllowedMembers et Creators pour chaque catégorie, et définir aussi les paramètres de la salle de conversation et les comportements qui s’appliqueront à toutes les salles de conversation créées dans cette catégorie. Par exemple, si vous définissez le AllowedMembers de la catégorie sur contoso.com, vous pouvez ajouter un groupe ou un utilisateur de contoso en tant que membre aux salles de conversation de cette catégorie. Si vous définissez Membres autorisés d’une catégorie sur Ventes, seuls les groupes et utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membre des salles de conversation de cette catégorie. La propriété Creators vous permet de contrôler qui peut créer des salles de conversation dans la catégorie. Une fois la salle de conversation créée, toute personne membre du groupe AllowedMembers peut être désignée en tant que Gestionnaire pour les opérations de gestion courantes des salles (par exemple, modifications des membres et approbation).
  
La définition de AllowedMembers et Créateurs pour une catégorie comporte les avantages suivants :
  
- Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie. Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.
    
- Un utilisateur qui se trouve dans la liste Créateurs peut créer des salles de conversation dans cette catégorie. Si vous voulez mettre en place un système qui limite le nombre de personnes de votre organisation ayant la possibilité de créer des salles de conversation, ce contrôle peut être utilisé. 
    
Les utilisateurs, unités d’organisation et groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent définir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste AllowedMembers de la catégorie comme responsables et membres de salle de conversation pour gérer et participer à la salle. 
  
Avant de configurer des catégories, assurez-vous de lire [les catégories, les salles de conversation et les rôles d’utilisateur persistants dans Skype entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
Vous pouvez configurer et gérer les catégories en utilisant le Panneau de configuration ou les applets de commande Windows PowerShell.

> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurer des catégories via le Panneau de configuration

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Dans la liste déroulante des déploiements de pools de serveurs de chat permanent, sélectionnez le pool approprié.
    
4. Dans la page **Catégorie**, cliquez sur **Créer** ou **Modifier**.
    
5. Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de chat permanent sur lequel la catégorie doit être créée. Le service est le pool de serveurs de chat permanent utilisé par le client de chat permanent pour identifier le regroupement auquel appartient la catégorie. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de chat permanent et ne peut pas être déplacée vers un autre pool ou partagé avec elle.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
   - Dans **Description**, indiquez une description détaillée de la catégorie de salle (par exemple, « catégorie de salle pour Contoso »).
    
   - Pour déterminer si les invitations peuvent être activées pour des salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **activer les invitations** . Si cette option est sélectionnée, les salles de cette catégorie peuvent avoir des invitations activées ou désactivées ; Si cette option est désactivée, les salles de cette catégorie ne peuvent pas avoir d’invitations. Si une salle est dotée d’invitations à l’ajout d’un nouveau membre, ce dernier reçoit une notification de la nouvelle salle dans le client de chat permanent.
    
   - Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si elle est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
   - Pour contrôler l’historique des conversations, cochez ou décochez la case **activer l’historique des conversations** . Si cette option est sélectionnée, les conversations de la salle deviennent permanentes ; dans le cas contraire, les messages ne sont pas conservés. Si la conformité est activée, les discussions sur place seront enregistrées en conformité, mais les utilisateurs ne seront pas en mesure d’accéder à d’anciens messages. Cette option peut être utilisée pour les salles destinées à des réunions ad hoc en temps réel, qui n’ont pas besoin de l’historique des discussions pour être persistants.
    
7. Dans **Modifier la catégorie**, procédez comme suit :
    
   - Dans **appartenance**, dans la section **membres autorisés** , ajoutez ou supprimez des utilisateurs et d’autres principaux services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres de salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
   - Dans **appartenance (membership**), dans la section **membres refusés** , ajoutez ou supprimez des utilisateurs et d’autres entités Active Directory associées aux membres refusés à partir de la salle.
    
   - Dans **appartenance**, dans la section **créateurs** , ajoutez ou supprimez des utilisateurs et d’autres entités Active Directory associées à des créateurs pour la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
8. Cliquez sur **Valider**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurer des catégories via Windows PowerShell

Vous pouvez configurer des catégories en utilisant les applets de commande Windows PowerShell :
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Créer une catégorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurer des paramètres pour une catégorie existante  <br/> |
|Get-CsPersistentChatCategory  <br/> |Récupérer des informations sur les catégories  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Supprimer une catégorie  <br/> |
   
Vous pouvez configurer les paramètres suivants des catégories :
  
- EnableFileUpload. Permet le chargement de fichiers dans les salles de conversation de la catégorie.
    
- EnableInvitations. Active les invitations pour la catégorie. Les utilisateurs figurant dans la liste AllowedMembers reçoivent automatiquement une invitation à rejoindre une nouvelle salle de conversation au moment où cette salle est créée.
    
- ChatHistory. Active ou désactive la fonction d’historique de la conversation.
    
- Creators. Liste les utilisateurs autorisés à créer des salles de conversation au sein de la catégorie.
    
- AllowedMembers. Spécifie les utilisateurs autorisés à accéder aux salles de conversation dans la catégorie.
    
- DeniedMembers. Liste les utilisateurs qui ne sont pas autorisés à accéder aux salles de conversation de la catégorie.
    
Pour des informations complètes sur la syntaxe des applets de commande, notamment tous les paramètres, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Créer une catégorie

Vous pouvez créer une nouvelle catégorie en utilisant l’applet de commande **New-CsPersistentChatCategory**. Par exemple, la commande suivante crée une nouvelle catégorie nommée HelpDesk dans le pool atl-cs-001.contoso.com. Dans cet exemple, le chargement de fichiers est autorisé :
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurer une catégorie existante

Vous pouvez configurer une catégorie existante en utilisant l’applet de commande **Set-CsPersistentCategory**.
  
Par exemple, la commande suivante spécifie que User1 est un AllowedMember et un créateur, alors que Utilisateur2 ne peut pas accéder aux salles de la catégorie :
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obtenir des informations sur les catégories

Vous pouvez obtenir des informations sur les catégories en utilisant l’applet de commande **Get-CsPersistentChatCategory**. Par exemple, la commande suivante retourne des informations pour toutes les catégories de conversation permanente de l’organisation :
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Supprimer une catégorie

Vous pouvez supprimer une catégorie en utilisant l’applet de commande **Remove-CsPersistentChatCategory**. Avant de supprimer une catégorie, vous devez soit supprimer toutes les salles de conversation qui en dépendent, soit déplacer les salles de conversation vers une nouvelle catégorie. Par exemple, la commande suivante supprime la catégorie ayant l’identité « atl-cs-001.contoso.com\helpdesk » :
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
