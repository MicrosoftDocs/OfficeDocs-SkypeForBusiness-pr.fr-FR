---
title: Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Résumé : Découvrez comment configurer des compléments pour les salles de conversation Persistent Chat Server Skype pour Business Server 2015.'
ms.openlocfilehash: b43340f44b7ce41a1d77768f10a96bff651afc3f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219729"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer des compléments pour les salles de conversation Persistent Chat Server Skype pour Business Server 2015.
  
Les compléments servent à étendre l’expérience dans la salle en associant des URL à des salles de conversation. Ces URL apparaissent dans le volet d’extensibilité de conversation client. Un complément typique peut contenir une URL pointant vers une application Silverlight qui intercepte lorsqu’un téléscripteur est publié dans une salle de conversation et affiche l’historique des actions dans le volet de l’extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».
  
 Avant que les utilisateurs puissent voir un complément dans le client, vous devez ajouter le complément à la liste des compléments enregistrés, et les responsables ou créateurs de salles de conversation doivent associer des salles au complément.
  
> [!NOTE]
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurer des compléments pour les salles de conversation en utilisant le Panneau de configuration

Pour configurer compléments pour les salles de conversation en utilisant le Panneau de configuration :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.
    
    Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.
    
4. Dans la page **Complément**, cliquez sur **Créer**.
    
5. Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous avez besoin pour créer le complément. Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.
    
6. Dans **Nouveau complément**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour le nouveau complément.
    
   - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurer des compléments via Windows PowerShell

Vous pouvez configurer des compléments pour les salles de conversation en utilisant les applets de commande Windows PowerShell suivantes. Pour plus d’informations sur la syntaxe, notamment tous les paramètres disponibles, consultez [Skype for Business Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Créer un complément  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurer des paramètres pour un complément existant  <br/> |
|Get-CsPersistentChatAddin  <br/> |Récupérer des informations sur les compléments  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Supprimer un complément  <br/> |
   
### <a name="create-a-new-add-in"></a>Créer un complément

Vous pouvez créer un complément à l’aide de l’applet de commande **New-CsPersistentChatAddin** .
  
Par exemple, la commande suivante crée un nouveau complément (avec le nom ITPersistentChatAddin) pour le pool atl-cs-001.contoso.com. Le paramètre URL et la valeur du paramètre http://atl-cs-001.contoso.com/itchat spécifiez l’emplacement de la page de la macro complémentaire :
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurer des paramètres pour un complément existant

Vous pouvez configurer les paramètres d’un complément existant en utilisant l’applet de commande **Set-CsPersistentChatAddIn**. Par exemple, la commande suivante modifie l’URL affecté au complément Conversation permanente ITPersistentChatAddin. Dans ce cas, l’URL est remplacée parhttp://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Récupérer des informations sur les compléments

Vous pouvez obtenir des informations sur les compléments en utilisant l’applet de commande **Get-CsPersistentChatAddin**. Par exemple, la commande suivante retourne des informations sur tous les compléments Conversation permanente à utiliser dans l’organisation :
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Supprimer un complément

Vous pouvez supprimer un complément à l’aide de l’applet de commande **Remove-CsPersistentChatAddIn** . Par exemple, la commande suivante supprime le complément Conversation permanente ITChatAddin trouvé dans le pool atl-cs-001.contoso.com :
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


