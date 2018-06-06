---
title: Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: 'See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. '
ms.openlocfilehash: 7a572689575a708707aeca3eb963d5eb7d864594
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568270"
---
# <a name="turn-on-or-off-allowing-content-to-be-preloaded-for-meetings-using-outlook"></a>Activation ou désactivation de l'autorisation de préchargement de contenu pour les réunions à l'aide d'Outlook

Les utilisateurs peuvent précharger contenu, des fichiers ou des pièces jointes qui sont liées à une invitation de réunion Outlook à un Skype pour une réunion en ligne Business, mais vous pouvez activer ou désactiver. Il est activé par défaut pour toutes les organisations qui utilisent Skype pour Business Online. Découvrez comment [Préchargement des pièces jointes pour une réunion Skype Entreprise](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> Actuellement, aucune des applets de commande ne sont disponibles dans Skype pour Business en ligne pour le paramètre ou l’affichage de valeurs en ligne pour _MaxContentStorageMB_ et _MaxUploadFileMB_. Elles ne sont disponibles que pour les déploiements locaux. Il est important de savoir que le contenu ne seront pas téléchargé à une réunion si le contenu joint dépasse le _MaxUploadFileSizeMB_ ou si la limite _MaxContentStorageMB_ est atteinte.
  
## <a name="to-get-you-started"></a>Pour commencer

### 

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
### 

 **Démarrez une session Windows PowerShell**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
$credential = Get-Credential
$session = New-CsOnlineSession -Credential $credential
Import-PSSession $session
```

Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="turning-it-on-or-off"></a>Activation ou désactivation des applications intégrées

Pouvoir précharger contenu attaché à une invitation de réunion Outlook à Skype pour les réunions en ligne Business est activée par défaut, mais vous devrez peut-être empêcher les utilisateurs de votre organisation de précharger le contenu de leurs réunions.
  
> [!IMPORTANT]
> Ce paramètre uniquement peut être activé ou désactivé pour l’ensemble de votre organisation ; Vous ne pouvez pas activer ou désactiver pour un seul utilisateur. 
  
 **Pour le désactiver, ouvrez Windows PowerShell et procédez comme suit :**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Si vous voulez le réactiver, ouvrez Windows PowerShell et procédez comme suit :**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)

  
 