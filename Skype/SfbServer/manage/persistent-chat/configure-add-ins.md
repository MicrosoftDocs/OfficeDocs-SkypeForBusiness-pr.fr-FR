---
title: Configurer des add-ins pour les salles de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Résumé : Découvrez comment configurer des add-ins pour les salles de conversation du serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: c23a0dd11d51bbfa1c49d8a910decda5be0ac48f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854298"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configurer des add-ins pour les salles de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment configurer des add-ins pour les salles de conversation du serveur de conversation permanente Skype Entreprise Server 2015.
  
Les add-ins sont utilisés pour étendre l’expérience dans la salle en associant des URL à des salles de conversation. Ces URL apparaissent dans le volet d’extensibilité de conversation client. Un add-in type peut inclure une URL pointant vers une application Silverlight qui intercepte lorsqu’un ticker de stock est publié dans une salle de conversation et affiche l’historique des actions dans le volet d’extensibilité. En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément pour inclure un contexte partagé, tel que « Tête de liste » ou « Sujet du jour ».
  
 Pour que les utilisateurs voient un add-in dans le client, vous devez l’ajouter à la liste des add-ins inscrits, et les responsables ou créateurs de salles de conversation doivent associer des salles au module.
  
> [!NOTE]
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>Configurer des modules pour les salles de conversation à l’aide du Panneau de configuration

Pour configurer des add-ins pour les salles de conversation à l’aide du Panneau de configuration :
  
1. À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.
    
2. Dans le menu **Démarrer,** sélectionnez Skype Entreprise Server panneau de Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.
    
    Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste finale.
    
4. Dans la page **Complément**, cliquez sur **Nouveau**.
    
5. Dans **Sélectionner un service,** sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous devez créer le add-in. Les compléments ne peuvent pas être déplacés d’un pool à un autre ou partagés parmi différents pools.
    
6. Dans **Nouveau complément**, procédez comme suit :
    
   - Dans **Nom**, spécifiez un nom pour le nouveau complément.
    
   - Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.
    
7. Cliquez sur **Valider**.
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>Configurer des add-ins à l’aide de Windows PowerShell

Vous pouvez configurer des add-ins pour les salles de conversation à l’aide des cmdlets Windows PowerShell suivantes. Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, [voir Skype Entreprise Server 2015 Management Shell](../management-shell.md).
  

|**Applet de commande**|**Description**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |Créer un nouveau add-in  <br/> |
|Set-CsPersistentChatAddin  <br/> |Configurer les paramètres d’un add-in existant  <br/> |
|Get-CsPersistentChatAddin  <br/> |Récupérer des informations sur les modules complémentaires  <br/> |
|Remove-CsPersistentChatAddin  <br/> |Supprimer un add-in  <br/> |
   
### <a name="create-a-new-add-in"></a>Créer un nouveau add-in

Vous pouvez créer un nouveau add-in à l’aide de l’cmdlet **New-CsPersistentChatAddin.**
  
Par exemple, la commande suivante crée un nouveau module (avec le nom ITPersistentChatAddin) pour le `atl-cs-001.contoso.com` pool. Le paramètre URL et la valeur de paramètre spécifient l’emplacement de la page `http://atl-cs-001.contoso.com/itchat` web du add-in :
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>Configurer les paramètres d’un add-in existant

Vous pouvez configurer les paramètres d’un add-in existant à l’aide de l’cmdlet **Set-CsPersistentChatAddIn.** Par exemple, la commande suivante modifie l’URL attribuée au module de conversation permanente ITPersistentChatAddin. Dans ce cas, l’URL est modifiée en `http://atl-cs-001.contoso.com/itchat2` :
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>Récupérer des informations sur les modules complémentaires

Vous pouvez obtenir des informations sur les modules complémentaires à l’aide de l’cmdlet **Get-CsPersistentChatAddin.** Par exemple, la commande suivante retourne des informations sur tous les modules de conversation permanente configurés pour être utilisés dans l’organisation :
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>Supprimer un add-in

Vous pouvez supprimer un add-in à l’aide de **l’cmdlet Remove-CsPersistentChatAddIn.** Par exemple, la commande suivante supprime le add-in de conversation permanente ITChatAddin trouvé sur le pool `atl-cs-001.contoso.com` :
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


