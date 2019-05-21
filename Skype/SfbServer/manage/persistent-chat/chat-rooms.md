---
title: Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Résumé: Découvrez comment gérer des salles de conversation serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 91e8a2888a7c83e30f80160d8c2c1fbc2af542fc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279346"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé:** Découvrez comment gérer des salles de conversation serveur de chat permanent dans Skype entreprise Server 2015.
  
La création et la gestion des salles de conversation est beaucoup plus facile en cas d’utilisation pertinente des catégories. Une catégorie définit qui peut créer des salles de conversation ou y participer. Avant de tenter de gérer des salles de conversation, veillez à lire les [catégories de discussion, les salles de conversation et les rôles d’utilisateur persistants dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) et à [gérer les catégories dans le serveur Chat permanent dans skype entreprise Server 2015](categories.md).
  
> [!NOTE]
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique [voyage de Skype entreprise à Microsoft teams](/microsoftteams/journey-skypeforbusiness-teams). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 

Vous pouvez configurer et gérer des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, ou à l’aide du client Skype entreprise si vous êtes membre de la salle de conversation. Cette rubrique explique comment gérer les salles de conversation en utilisant l’interface de ligne de commande Windows PowerShell. Si vous voulez gérer des salles de conversation à l’aide du client Skype entreprise, voir l’aide du client. 
  
Les salles de conversation peuvent être l’un des deux types suivants: normal et Auditorium. Une salle de conversation normale permet à tous les membres de publier et de lire des messages. Un auditorium est un type de salle de conversation où seuls les présentateurs peuvent publier, mais où tout le monde peut lire.
  
Les rôles utilisateur déterminent qui peut accéder aux salles de conversation et les gérer, comme suit :
  
- Les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.
    
- Les présentateurs sont autorisés à publier dans les salles de type Auditorium.
    
- Les administrateurs peuvent supprimer un contenu précédant (par exemple, du contenu publié avant une certaine date) d’une salle de conversation afin de conserver une taille de base de données raisonnable. Ils peuvent aussi supprimer ou remplacer des messages qu’ils considèrent inappropriés pour une salle de conversation spécifique.
    
- Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.
    
- Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés de la salle de conversation, notamment en désactivant des salles. Les responsables ne peuvent pas, toutefois, supprimer une salle ou modifier la catégorie d’une salle. 
    
- Seuls les administrateurs peuvent supprimer une salle de conversation une fois qu’elle a été créée.
    
Vous pouvez configurer et gérer des salles de conversation en utilisant les applets de commande Windows PowerShell :
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |Créer une salle de conversation  <br/> |
|Set-CsPersistentChatRoom  <br/> |Configurer des paramètres pour une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle  <br/> |
|Get-CsPersistentChatRoom  <br/> |Extraire des informations sur les salles  <br/> |
|Clear-CsPersistentChatRoom  <br/> |Effacer une salle et les messages d’une salle  <br/> |
|Remove-CsPersistentChatRoom  <br/> |Supprimer une salle  <br/> |
|Remove-CsPersistentChatMessage  <br/> |Supprimer les messages d’une salle  <br/> |
   
Utilisez l’applet de commande **New-CsPersistentChatRoom** pour créer des salles de conversation et utilisez l’applet de commande **Set-CsPersistentChatRoom** pour configurer une salle de conversation existante, notamment pour ajouter des utilisateurs à la salle de conversation. Vous pouvez configurer les paramètres suivants pour les salles de conversation :
  
- Disabled. Vous permet de désactiver ou d’activer une salle de conversation. 
    
- Invitations. Permet d’activer ou de désactiver des invitations aux salles de conversation, qui sont utilisées pour avertir les utilisateurs qu’ils ont été ajoutés en tant que membres de salle de conversation. Le paramétrage par défaut des invitations est inherit, ce qui a amené la salle de conversation à adopter le paramètre d’invitation configuré dans la catégorie à laquelle elle appartient. La configuration du paramètre des invitations sur false au niveau de la salle de conversation permet de remplacer le paramétrage de la catégorie. 
    
- Privacy. Permet de spécifier si une salle de conversation est ouverte, fermée ou secrète. Les salles de type Ouvert peuvent faire l’objet d’une recherche et d’un accès de la part de tout le monde. Les salles de type Fermé peuvent faire l’objet d’une recherche de la part de tous, mais peuvent faire l’objet d’un accès uniquement de la part des membres. Les salles de type Secret peuvent faire l’objet d’une recherche et d’un accès uniquement de la part des membres de la salle. Par défaut, chaque nouvelle salle est initialement configurée comme fermée.
    
- Type. Vous permet de spécifier si une salle de conversation est une salle normale qui accepte les messages publiés par n’importe quel membre ou une salle d’auditorium qui accepte les messages publiés uniquement par un présentateur.
    
- Addin. Permet d’associer un complément précédemment configuré avec une salle de conversation, ce qui permet aux membres de voir le contenu d’URL tout en participant.
    
Outre les paramètres ci-dessus, l’applet de passe **Set-CsPersistentChatRoom** vous permet d’affecter les utilisateurs à la salle de conversation comme suit:
  
- Members. Configure les membres de la salle de conversation. Vous pouvez ajouter ou supprimer des membres individuellement ou par groupe en utilisant une seule applet de commande en spécifiant l’adresse SIP des utilisateurs. Pour permettre aux utilisateurs d’être ajoutés par lot, des unités d’organisation ou des groupes de distribution Active Directory peuvent aussi être spécifiés.
    
- Managers. Permet d’affecter des responsables à la salle de conversation. Les responsables ont les autorisations pour définir l’appartenance à une salle de conversation ainsi que d’autres paramètres.
    
- Presenters. Permet d’affecter des présentateurs à une salle de conversation Auditorium. 
    
  Pour des informations sur la syntaxe, notamment tous les paramètres, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).
  
## <a name="create-a-new-room"></a>Créer une salle

Vous pouvez créer une nouvelle salle en utilisant l’applet de commande **New-CsPersistentChatRoom**. Par exemple, la commande suivante crée une nouvelle salle de conversation nommée ITChatRoom dans le pool atl-cs-001.contoso.com. Dans cet exemple, la salle de conversation est ajoutée à la catégorie IT :
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**Remarque:** PersistentChatPoolFqdn n’est pas nécessaire si l’une des conditions suivantes est vraie: 
  
- Il n’y a qu’un seul pool de serveurs de chat permanent.
    
- Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.
    
- Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.
    
## <a name="configure-an-existing-room"></a>Configurer une salle existante

Vous pouvez configurer une salle existante à l’aide de l’applet de passe **Set-CsPersistentChatRoom** . Par exemple, la commande suivante affecte User1 en tant que membre et présentateur, et Utilisateur2 en tant que responsable, dans la salle d’Auditorium testCat:
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 L’exemple suivant ajoute tous les utilisateurs de l’unité d’organisation NorthAmericaUsers dans Active Directory à la salle de conversation NorthAmerica :
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

L’exemple suivant ajoute tous les membres du groupe de distribution Finance à la même salle de conversation :
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>Désactiver ou activer une salle de conversation

Si le sujet d’une salle de conversation permanente n’est plus pertinent, vous pouvez rendre la salle de conversation non disponible pour les utilisateurs en la désactivant. Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle. Une fois qu’une salle de conversation est désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.
  
Si l’historique de la salle de conversation persiste, le contenu est conservé lorsque la salle de conversation est désactivée. Cependant, le contenu ne s’affichera pas dans les recherches tant que la salle de conversation demeurera désactivée. Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle. Pour plus d’informations sur la configuration de l’historique des salles de conversation, voir [gérer les catégories dans le serveur Chat permanent dans Skype entreprise server 2015](categories.md). 
  
Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés. En tant qu’administrateur, vous pouvez activer une salle qui a été désactivée, et vous n’avez pas besoin de recréer manuellement les paramètres.
  
Vous pouvez désactiver une salle à l’aide de l’applet de passe **Set-CsPersistentChatRoom** et définir le paramètre disabled sur true:
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

Pour activer une salle de conversation, définissez le paramètre Disabled sur False :
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>Obtenir des informations sur les salles

Pour obtenir des informations sur les salles configurées à utiliser au sein de votre organisation, vous pouvez utiliser l’applet de commande **Get-CsPersistentChatRoom**.
  
La commande suivante renvoie des informations relatives à toutes les salles de configuration configurées pour une utilisation dans votre organisation :
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>Supprimer tout le contenu d’une salle

Vous pouvez supprimer un contenu d’une salle en utilisant l’applet de commande **Clear-CsPersistentChatRoom**. Par exemple, la commande suivante supprime tout le contenu de la salle de conversation permanente ITChatRoom qui a été ajouté à la salle jusqu’au 1er mars 2015 inclus :
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>Supprimer un message d’une salle

Vous pouvez supprimer un ou plusieurs messages dans la base de données de conversation permanente et, le cas échéant, remplacer le message par un message par défaut ou un message fourni par l’administrateur, en utilisant l’applet de commande **Remove-CsPersistentChatMessage**. Par exemple, la commande suivante supprime tous les messages de la salle de conversation ITChatRoom qui étaient publiés par l’utilisateur kenmyer@contoso.com :
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

L’exemple suivant remplace tous les messages supprimés par une note indiquant que le message n’est plus disponible :
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>Supprimer une salle

Vous pouvez supprimer une salle en utilisant l’applet de commande **Remove-CsPersistentChatRoom**.
  
Par exemple, la commande suivante supprime la salle de conversation RedmondChatRoom :
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>Déplacer une salle de conversation d’une catégorie vers une autre

Si le responsable de la salle de conversation a des privilèges **Creator** dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.
  
La modification d’une catégorie de salle de conversation est très rare et exige de la prudence. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACL) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et qu’il n’est plus un membre autorisé dans la nouvelle catégorie, l’appartenance de la salle sera modifiée et l’utilisateur sera supprimé de la salle.
  

