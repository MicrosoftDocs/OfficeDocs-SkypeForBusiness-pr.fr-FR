---
title: Gérer les salles de conversation dans le serveur de conversation permanente Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Résumé : Découvrez comment gérer les salles de conversation du serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: 63566d897901be32b7d0f33ea099bac202e61515
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830848"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gérer les salles de conversation dans le serveur de conversation permanente Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment gérer les salles de conversation du serveur de conversation permanente Skype Entreprise Server 2015.
  
La création et la gestion des salles de conversation sont beaucoup plus faciles avec l’utilisation correcte des catégories. Une catégorie définit qui peut créer ou rejoindre les salles de conversation. Avant d’essayer de gérer les salles de conversation, veillez à lire les catégories de conversation permanente, les salles de conversation et les rôles d’utilisateur dans [Skype Entreprise Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) et gérer les catégories dans le serveur de conversation permanente dans [Skype Entreprise Server 2015.](categories.md)
  
> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 

Vous pouvez configurer et gérer des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell ou à l’aide du client Skype Entreprise si vous êtes membre de la salle de conversation. Cette rubrique décrit comment gérer les salles de conversation à l’aide de l Windows PowerShell interface de ligne de commande. Si vous souhaitez gérer des salles de conversation à l’aide Skype Entreprise client, consultez l’aide du client. 
  
Les salles de conversation peuvent être de deux types : Normal et Auditorium. Une salle de conversation normale permet à tous les membres de publier et de lire des messages. Un auditorium est un type de salle de conversation dans laquelle seuls les présentateurs peuvent publier, mais où tout le monde peut lire.
  
Qui pouvez accéder aux salles de conversation et les gérer dépend des rôles d’utilisateur suivants :
  
- Les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.
    
- Les présentateurs sont autorisés à publier dans les salles auditorium.
    
- Les administrateurs peuvent supprimer du contenu précédant, par exemple du contenu publié avant une certaine date, d’une salle de conversation afin que la base de données ne devienne pas ingérable de part sa taille. Les administrateurs peuvent également supprimer ou remplacer des messages qui sont considérés inappropriés pour une salle de conversation particulière.
    
- Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.
    
- Les responsables de salles de conversation peuvent apporter des modifications à toutes les propriétés de la salle de conversation, y compris la désactivation des salles. Toutefois, les responsables ne peuvent pas supprimer une salle ou modifier la catégorie d’une salle. 
    
- Seuls les administrateurs peuvent supprimer une salle de conversation après sa création.
    
Vous pouvez configurer et gérer des salles de conversation à l’aide des cmdlets Windows PowerShell suivantes :
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Créer une salle de conversation  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurer les paramètres d’une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle  <br/> |
|Get-CsPersistentChatRoom  <br/> |Récupérer des informations sur les salles  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Effacer une salle ou des messages d’une salle  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Supprimer une salle  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Supprimer des messages d’une salle  <br/> |
   
Vous utilisez l’cmdlet **New-CsPersistentChatRoom** pour créer des salles de conversation et l’cmdlet **Set-CsPersistentChatRoom** pour configurer une salle de conversation existante, y compris l’ajout d’utilisateurs à la salle de conversation. Vous pouvez configurer les paramètres suivants pour les salles de conversation :
  
- Désactivé. Permet de désactiver ou d’activer une salle de conversation. 
    
- Invitations. Permet d’activer ou de désactiver les invitations aux salles de conversation, qui sont utilisées pour informer les utilisateurs lorsqu’ils ont été ajoutés en tant que membres de la salle de conversation. Le paramètre par défaut pour les invitations dans hériter, ce qui a provoqué l’adoption par la salle de conversation du paramètre d’invitation configuré sur la catégorie à laquelle elle appartient. La configuration du paramètre d’invitations sur False au niveau de la salle de conversation permet de faire en place le paramètre de catégorie. 
    
- Confidentialité. Permet de spécifier si une salle de conversation est ouverte, fermée ou secrète. Les salles ouvertes peuvent être recherchés et accessibles par tout le monde. Les salles fermées peuvent être recherchés par n’importe qui, mais sont accessibles uniquement par les membres. Les salles secrètes ne sont accessibles qu’aux membres de la salle. Par défaut, chaque nouvelle salle est initialement configurée comme fermée.
    
- Type. Permet de spécifier si une salle de conversation est une salle normale, qui accepte les messages publiés par un membre, ou une salle auditorium, qui accepte les messages publiés uniquement par un présentateur.
    
- Addin. Permet d’associer un add-in précédemment configuré à une salle de conversation, ce qui permet aux membres d’afficher le contenu de l’URL tout en participant.
    
Outre les paramètres ci-dessus, l’cmdlet **Set-CsPersistentChatRoom** vous permet d’affecter des utilisateurs à la salle de conversation comme suit :
  
- Membres. Configure l’appartenance à la salle de conversation. Vous pouvez ajouter ou supprimer un ou plusieurs membres à l’aide d’une seule cmdlet en spécifiant l’adresse SIP des utilisateurs. Pour autoriser l’ajout en bloc d’utilisateurs, vous pouvez également spécifier des unités d’organisation ou des groupes de distribution Active Directory.
    
- Responsables. Permet d’affecter des responsables à la salle de conversation. Les responsables ont les autorisations pour définir l’appartenance à une salle de conversation avec d’autres paramètres.
    
- Présentateurs. Permet d’affecter des présentateurs à une salle de conversation auditorium. 
    
  Pour plus d’informations sur la syntaxe, y compris tous les paramètres, [voir Skype Entreprise Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Créer une salle

Vous pouvez créer une salle à l’aide de l’cmdlet **New-CsPersistentChatRoom.** Par exemple, la commande suivante crée une salle de conversation nommée ITChatRoom sur le pool atl-cs-001.contoso.com. Dans cet exemple, la salle de conversation est ajoutée à la catégorie IT :
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Remarque :** PersistentChatPoolFqdn n’est pas nécessaire si l’une des valeurs suivantes est vraie : 
  
- Il n’existe qu’un seul pool de serveurs de conversation permanente.
    
- Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.
    
- Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.
    
## <a name="configure-an-existing-room"></a>Configurer une salle existante

Vous pouvez configurer une salle existante à l’aide de l’cmdlet **Set-CsPersistentChatRoom.** Par exemple, la commande suivante affecte user1 en tant que membre et présentateur, et user2 en tant que responsable, de la salle auditorium testCat :
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 L’exemple suivant ajoute tous les utilisateurs de l’ou NorthAmericaUsers dans Active Directory à la salle de conversation NorthAmerica :
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

L’exemple suivant ajoute tous les membres du groupe de distribution Finance à la même salle de conversation :
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Désactiver ou activer une salle

Si la rubrique d’une salle de conversation permanente n’est plus pertinente, vous pouvez rendre la salle de conversation inaccessible aux utilisateurs en la désactivant. Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle. Une fois une salle de conversation désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.
  
Si l’historique de la salle de conversation persiste, le contenu est conservé lorsque la salle de conversation est désactivée. Toutefois, le contenu n’apparaîtra pas dans les recherches tant que la salle de conversation demeurera dans son état de désactivation. Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle. Pour plus d’informations sur la configuration de l’historique des salles de conversation, voir [Manage categories in Persistent Chat Server in Skype Entreprise Server 2015](categories.md). 
  
Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés. En tant qu’administrateur, vous pouvez activer une salle qui a été désactivée et vous n’avez pas besoin de créer manuellement les paramètres.
  
Vous pouvez désactiver une salle à l’aide de l’cmdlet **Set-CsPersistentChatRoom** et définir le paramètre Disabled sur True :
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Pour activer une salle de conversation, définissez le paramètre Disabled sur False :
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obtenir des informations sur les salles

Pour obtenir des informations sur les salles configurées pour être utilisés dans votre organisation, vous pouvez utiliser l’cmdlet **Get-CsPersistentChatRoom.**
  
La commande suivante retourne des informations sur toutes les salles de conversation configurées pour être utilisés dans l’organisation :
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Supprimer tout le contenu d’une salle

Vous pouvez supprimer du contenu d’une salle à l’aide de l’cmdlet **Clear-CsPersistentChatRoom.** Par exemple, la commande suivante supprime tout le contenu de la salle de conversation permanente ITChatRoom qui a été ajoutée à la salle le ou avant le 1er mars 2015 :
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Supprimer un message d’une salle

Vous pouvez supprimer un ou plusieurs messages dans la base de données de conversation permanente et éventuellement remplacer le message par un message par défaut ou par un message fourni par l’administrateur, à l’aide de l';cmdlet **Remove-CsPersistentChatMessage.** Par exemple, la commande suivante supprime tous les messages de la salle de conversation ITChatRoom qui ont été publiés par l’utilisateur kenmyer@contoso.com :
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

L’exemple suivant remplace tous les messages supprimés par la note que le message n’est plus disponible :
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Supprimer une salle

Vous pouvez supprimer une salle à l’aide de l’cmdlet **Remove-CsPersistentChatRoom.**
  
Par exemple, la commande suivante supprime la salle de conversation RedmondChatRoom :
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Déplacer une salle d’une catégorie vers une autre

Si un responsable de salle de conversation **dispose** de privilèges Créateur dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.
  
La modification d’une catégorie de salle de conversation doit être effectuée rarement et avec précaution. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACLs) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et n’est plus un membre autorisé dans la nouvelle catégorie, l’appartenance à la salle sera modifiée et l’utilisateur sera supprimé de la salle.
  

