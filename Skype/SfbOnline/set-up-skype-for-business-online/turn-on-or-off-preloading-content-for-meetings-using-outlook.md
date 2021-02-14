---
title: Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 079d0642158aa6d28b3c92a63e77afa0a0024d94
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814583"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook

Les utilisateurs peuvent précharger du contenu, des fichiers ou des pièces jointes joints à une invitation à une réunion Outlook pour participer à une réunion Skype Entreprise Online, mais vous pouvez activer ou désactiver cette fonction. Elle est désactivée par défaut pour toutes les organisations qui utilisent Skype Entreprise Online. Découvrez comment [Préchargement des pièces jointes pour une réunion Skype Entreprise](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Actuellement, aucune cmdlets n’est disponible dans Skype Entreprise Online pour définir ou afficher les valeurs en ligne pour _MaxContentStorageMB_ et _MaxUploadFileMB._ Elles ne sont disponibles que pour les déploiements locaux. Il est important de savoir que le contenu ne sera pas téléchargé dans une réunion si le contenu joint dépasse la limite  _MaxUploadFileSizeMB_ ou si la limite _maxContentStorageMB_ est atteinte.
  
## <a name="to-get-you-started"></a>Pour commencer

### 

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à jour Windows PowerShell vers la version 4.0. Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, consultez Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx)dans une Windows PowerShell unique.
  
### 

 **Démarrez une session Windows PowerShell**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Dans la **Windows PowerShell,** connectez-vous à votre Microsoft 365 ou Office 365 en exécutant :
    
> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.
>
> Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
  
```PowerShell
Import-Module -Name MicrosoftTeams
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="turning-it-on-or-off"></a>Activation ou désactivation des applications intégrées

La possibilité de précharger du contenu joint à une invitation à une réunion Outlook pour les réunions Skype Entreprise Online est désactivée par défaut, mais vous devrez peut-être empêcher les utilisateurs de votre organisation de précharger du contenu dans leurs réunions.
  
> [!IMPORTANT]
> Ce paramètre peut uniquement être désactivé pour l’ensemble de votre organisation. vous ne pouvez pas l’activer ou le désactiver pour un seul utilisateur. 
  
 **Pour le désactiver, ouvrez Windows PowerShell et procédez comme suit :**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Si vous voulez le réactiver, ouvrez Windows PowerShell et procédez comme suit :**
  
```PowerShell
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi
[Configurer Skype entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 
