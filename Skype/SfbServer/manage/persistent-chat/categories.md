---
title: Gestion des catégories sur un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Résumé : Découvrez comment gérer les catégories de serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: a0d70ec0266fc85d94c44c11ba15e42eea0be44b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219736"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestion des catégories sur un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer les catégories de serveurs de conversation permanente dans Skype pour Business Server 2015.
  
Une catégorie est une structure logique pour organiser des salles de conversation. Une catégorie définit un ensemble de listes de contrôle d’accès (ACL) pour contrôler les utilisateurs et les groupes d’utilisateurs qui peuvent créer ou joindre les salles de conversation par défaut. Catégories de salle de conversation contiennent des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que nom et Description. La catégorie a des propriétés qui peuvent être définies pour contrôler le comportement de la salle de conversation appartenant à par exemple, si les salles de conversation autoriser les Invitations ou téléchargement de fichiers ou contenir l’historique des conversations. 
  
La création et la gestion des salles de conversation est beaucoup plus facile en cas d’utilisation pertinente des catégories. En tant qu’administrateur du serveur de conversation permanente, vous pouvez définir AllowedMembers et Creators pour chaque catégorie, et définir aussi les paramètres de la salle de conversation et les comportements qui s’appliqueront à toutes les salles de conversation créées dans cette catégorie. Par exemple, si vous définissez AllowedMembers de la catégorie à contoso.com, vous pouvez ajouter n’importe quel utilisateur ou groupe chez Contoso en tant que membre des salles de conversation dans cette catégorie. Si vous définissez Membres autorisés d’une catégorie sur Ventes, seuls les groupes et utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membre des salles de conversation de cette catégorie. La propriété Creators vous permet de contrôler qui peut créer des salles de conversation dans la catégorie. Une fois la salle de conversation créée, toute personne membre du groupe AllowedMembers peut être désignée en tant que Gestionnaire pour les opérations de gestion courantes des salles (par exemple, modifications des membres et approbation).
  
La définition de AllowedMembers et Créateurs pour une catégorie comporte les avantages suivants :
  
- Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie. Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.
    
- Un utilisateur qui se trouve dans la liste Créateurs peut créer des salles de conversation dans cette catégorie. Si vous voulez mettre en place un système qui limite le nombre de personnes de votre organisation ayant la possibilité de créer des salles de conversation, ce contrôle peut être utilisé. 
    
Les utilisateurs, unités d’organisation et groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, ils peuvent définir les utilisateurs, les unités d’organisation et les groupes d’utilisateurs à partir de la liste AllowedMembers de la catégorie comme responsables et membres de salle de conversation pour gérer et participer à la salle. 
  
Avant de configurer des catégories, veillez à lire les [catégories de conversation permanente, les salles de conversation et les rôles d’utilisateur dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
Vous pouvez configurer et gérer les catégories en utilisant le Panneau de configuration ou les applets de commande Windows PowerShell.

> [!NOTE]
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurer des catégories via le Panneau de configuration

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.
    
4. Dans la page **Catégorie**, cliquez sur **Créer** ou **Modifier**.
    
5. Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente sur lequel la catégorie doit être créé. Le service est le serveur de conversation permanente pool que le client de conversation permanente utilise pour identifier la catégorie du pool auquel appartient. Une catégorie peut appartenir qu’un seul pool de serveurs de conversation permanente et ne peuvent pas être déplacée vers ou partagée avec un autre pool.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
   - Dans **Description**, indiquez une description détaillée de la catégorie de salle (par exemple, « catégorie de salle pour Contoso »).
    
   - Pour contrôler si les invitations peuvent être activées pour les salles de conversation qui appartiennent à cette catégorie, activez ou désactivez la case à cocher **Activer les invitations** . Si sélectionné, les salles de cette catégorie peuvent ont des invitations on ou off ; Si désactivée, les salles de cette catégorie ne sont pas autorisés à avoir des invitations. Si une salle a invitations sur lorsqu’un nouveau membre est ajouté à un espace, il obtient une notification de la nouvelle salle de client de conversation permanente.
    
   - Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si elle est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
   - Pour contrôler l’historique des conversations, activez ou désactivez la case à cocher **Activer l’historique des conversations** . Si sélectionné, conversations salle devient permanentes ; dans le cas contraire, les messages de conversation ne sont pas conservées. Si la conformité est activée, conversations salle seront enregistrées dans la conformité, mais les utilisateurs ne pourront pas accéder aux anciens messages. Cette option peut être utilisée pour les salles désignés pour la collaboration en temps réel, ad hoc qui n’ont pas besoin de l’historique des conversations d’être conservée.
    
7. Dans **Modifier la catégorie**, procédez comme suit :
    
   - Dans **l’appartenance**, dans la section **membres autorisés** , ajouter ou supprimer des utilisateurs et autres entités de Services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation et ainsi de suite) sont autorisées à ajouter en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (sauf si la salle est masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
   - Dans **l’appartenance**, dans la section **membres refusés** , ajouter ou supprimer des utilisateurs et autres principaux Active Directory associées aux membres refusées à partir de la salle.
    
   - Dans **l’appartenance**, dans la section **créateurs** , ajouter ou supprimer des utilisateurs et autres principaux Active Directory associé aux créateurs de la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
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
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurer une catégorie existante

Vous pouvez configurer une catégorie existante en utilisant l’applet de commande **Set-CsPersistentCategory**.
  
Par exemple, la commande suivante spécifie qu’user1 est un AllowedMember et un créateur, alors qu’user2 est refusé dans les salles de la catégorie :
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obtenir des informations sur les catégories

Vous pouvez obtenir des informations sur les catégories en utilisant l’applet de commande **Get-CsPersistentChatCategory**. Par exemple, la commande suivante retourne des informations pour toutes les catégories de conversation permanente de l’organisation :
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Supprimer une catégorie

Vous pouvez supprimer une catégorie en utilisant l’applet de commande **Remove-CsPersistentChatCategory**. Avant de supprimer une catégorie, vous devez soit supprimer toutes les salles de conversation qui en dépendent, soit déplacer les salles de conversation vers une nouvelle catégorie. Par exemple, la commande suivante supprime la catégorie ayant l’identité « atl-cs-001.contoso.com\helpdesk » :
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
