---
title: Gérer les catégories dans le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 'Résumé : Découvrez comment gérer les catégories de serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 7d2cb5114b876c5354b3ba47c45f700a5bd62450
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396466"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer les catégories dans le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer les catégories de serveur de conversation permanente dans Skype Entreprise Server 2015.
  
Une catégorie est une structure logique pour l’organisation des salles de conversation. Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour contrôler les utilisateurs et les groupes d’utilisateurs qui peuvent créer ou rejoindre les salles de conversation. Les catégories de salles de conversation contiennent des salles de conversation, mais pas d’autres catégories. Chaque catégorie décrit son contenu avec des métadonnées, telles que Nom et Description. La catégorie possède des propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui lui appartiennent . par exemple, si les salles de conversation autorisent les invitations ou les téléchargements de fichiers, ou contiennent l’historique des conversation. 
  
La création et la gestion des salles de conversation sont beaucoup plus faciles avec l’utilisation correcte des catégories. En tant qu’administrateur de serveur de conversation permanente, vous pouvez définir AllowedMembers et Creators pour chaque catégorie, ainsi que les paramètres et comportements de salle de conversation par défaut qui seront appliqués à toutes les salles de conversation créées dans la catégorie. Par exemple, si vous définissez allowedMembers de la catégorie sur contoso.com, vous pouvez ajouter n’importe quel groupe ou utilisateur de Contoso en tant que membre aux salles de conversation de cette catégorie. Si vous définissez les membres autorisés d’une catégorie sur Ventes, seuls les groupes et les utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membres aux salles de conversation de cette catégorie. La propriété Creators vous permet de contrôler qui peut créer des salles de conversation dans cette catégorie. Une fois la salle de conversation créée, toute personne du groupe AllowedMembers peut être désignée comme responsable des opérations de gestion en cours sur les salles (par exemple, modification de l’appartenance et approbation).
  
La définition de AllowedMembers et Créateurs pour une catégorie comporte les avantages suivants :
  
- Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie. Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.
    
- Un utilisateur qui se trouve dans la liste Créateurs peut créer des salles de conversation dans cette catégorie. Si vous souhaitez implémenter un système dans lequel un nombre restreint de membres du personnel de l’organisation peut créer des salles de conversation, ce contrôle peut être utilisé pour répondre à ces exigences. 
    
Les utilisateurs, les unités d’organisation et les groupes d’utilisateurs identifiés comme créateurs de la catégorie sont les seuls individus et groupes autorisés à créer des salles dans la catégorie. Une fois la catégorie créée, vous pouvez choisir des utilisateurs, des utilisateurs et des groupes d’utilisateurs dans la liste AllowedMembers de la catégorie en tant que responsables et membres de salle de conversation pour gérer et participer à la salle. 
  
Avant de configurer des catégories, veillez à lire les catégories de conversation permanente, les salles de conversation et les rôles d’utilisateur dans [Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).
  
Vous pouvez configurer et gérer des catégories à l’aide du Panneau de configuration ou à l’aide Windows PowerShell cmdlets.

> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
  
## <a name="configure-categories-by-using-the-control-panel"></a>Configurer des catégories à l’aide du Panneau de configuration

1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer**, sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.
    
    Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste finale.
    
4. Dans la page **Catégorie**, cliquez sur **Nouvelle** ou **Modifier**.
    
5. Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente sur lequel la catégorie doit être créée. Le service est le pool de serveurs de conversation permanente que le client de conversation permanente utilise pour identifier le pool auquel appartient la catégorie. Une catégorie ne peut appartenir qu’à un seul pool de serveurs de conversation permanente et ne peut pas être déplacée vers un autre pool ou partagée avec lui.
    
6. Dans **Nouvelle catégorie**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.
    
   - Dans **Description**, fournissez une description détaillée de la catégorie de salle (exemple : catégorie de salle pour Contoso).
    
   - Pour contrôler si les invitations peuvent être activées pour les salles de conversation appartenant à cette catégorie, activez ou videz la case à cocher Activer **les invitations** . S’il est sélectionné, les salles de cette catégorie peuvent avoir des invitations en cours ou non ; si elles sont effacées, les salles de cette catégorie ne sont pas autorisées à recevoir des invitations. Si une salle a des invitations, lorsqu’un nouveau membre est ajouté à une salle, il reçoit une notification de la nouvelle salle dans son client de conversation permanente.
    
   - Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si la case à cocher est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.
    
   - Pour contrôler l’historique des conversation, activez ou videz la case à cocher **Activer l’historique des** conversation. Si la case à cocher est activée, les conversations des salles deviennent permanentes ; sinon, les messages des conversations ne sont pas conservés. Si la conformité est activée, les conversations des salles sont enregistrées à des fins de conformité mais les utilisateurs ne peuvent pas accéder aux anciens messages. Cette option peut être utilisée pour les salles désignées pour des collaborations ad hoc en temps réel qui n’ont pas besoin d’être persistantes dans l’historique des conversation.
    
7. Dans **Modifier la catégorie**, procédez comme suit :
    
   - Dans l’appartenance **, dans** **la section Membres** autorisés, ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) qui sont autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie. Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).
    
   - Dans **l’appartenance**, dans **la section Membres** refusés, ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés à des membres refusés de la salle.
    
   - Dans **Appartenance**, dans la section **Créateurs** , ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés aux créateurs de la catégorie. Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.
    
8. Cliquez sur **Valider**.
    
## <a name="configure-categories-by-using-windows-powershell"></a>Configurer des catégories à l’aide Windows PowerShell

Vous pouvez configurer des catégories à l’aide des cmdlets Windows PowerShell suivantes :
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |Créer une catégorie  <br/> |
|Set-CsPersistentChatCategory  <br/> |Configurer les paramètres d’une catégorie existante  <br/> |
|Get-CsPersistentChatCategory  <br/> |Récupérer des informations sur les catégories  <br/> |
|Remove-CsPersistentChatCategory  <br/> |Supprimer une catégorie  <br/> |
   
Vous pouvez configurer les paramètres suivants pour les catégories :
  
- EnableFileUpload. Autorise les téléchargements de fichiers dans les salles de conversation de la catégorie.
    
- EnableInvitations. Active les invitations pour la catégorie. Les utilisateurs de la liste AllowedMembers reçoivent automatiquement une invitation à rejoindre une nouvelle salle de conversation au moment de sa création.
    
- ChatHistory. Active ou désactive la fonctionnalité d’historique des conversation.
    
- Créateurs. Spécifie les utilisateurs autorisés à créer des salles de conversation dans la catégorie.
    
- AllowedMembers. Spécifie les utilisateurs autorisés à accéder aux salles de conversation de la catégorie.
    
- DeniedMembers. Liste les utilisateurs qui ne sont pas autorisés à accéder aux salles de conversation de la catégorie.
    
Pour plus d’informations sur la syntaxe de cmdlet, y compris tous les paramètres, voir [Skype Entreprise Server 2015 Management Shell](../management-shell.md).
  
### <a name="create-a-new-category"></a>Créer une catégorie

Vous pouvez créer une catégorie à l’aide de l’cmdlet **New-CsPersistentChatCategory** . Par exemple, la commande suivante crée une catégorie nommée HelpDesk sur le pool atl-cs-001.contoso.com. Dans cet exemple, le chargement de fichiers est activé :
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>Configurer une catégorie existante

Vous pouvez configurer une catégorie existante à l’aide de l’cmdlet **Set-CsPersistentCategory** .
  
Par exemple, la commande suivante spécifie que user1 est un AllowedMember et un Creator, tandis que l’utilisateur 2 ne peut pas accéder aux salles de la catégorie :
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>Obtenir des informations sur les catégories

Vous pouvez obtenir des informations sur les catégories à l’aide de l’cmdlet **Get-CsPersistentChatCategory** . Par exemple, la commande suivante retourne des informations pour toutes les catégories de conversation permanente de l’organisation :
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>Supprimer une catégorie

Vous pouvez supprimer une catégorie à l’aide de l’cmdlet **Remove-CsPersistentChatCategory** . Avant de supprimer une catégorie, vous devez d’abord supprimer toutes les salles de conversation sous cette catégorie ou déplacer les salles de conversation vers une nouvelle catégorie. Par exemple, la commande suivante supprime la catégorie dont l’identité est « atl-cs-001.contoso.com\helpdesk » :
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
