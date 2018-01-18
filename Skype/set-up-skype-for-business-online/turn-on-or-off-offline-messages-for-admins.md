---
title: "Activation ou désactivation des messages hors connexion pour les administrateurs"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: Setup
description: Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell.
ms.openlocfilehash: 2210f7f0acb2609b7557afe781bbb4349d76c73f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="turn-on-or-off-offline-messages-for-admins"></a>Activation ou désactivation des messages hors connexion pour les administrateurs

Vous pouvez envoyer les Skype pour entreprise IMs à vos contacts, même s’ils ne sont pas signés. Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé de les atteindre. Vous n’êtes pas obligé d’attendre que quelqu'un est en ligne avant de les envoyer un message. 
  
Pour les messages hors connexion, il est important de savoir que :
  
- les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;
    
- Les messages en mode hors connexion seront envoyées à la boîte aux lettres de l’utilisateur et l’utilisateur sera averti de leur connexion à Skype pour les entreprises.
    
- Si état du destinataire du message est **Ne pas déranger** ou **projetées**, qu’ils recevront un message non envoyé à partir Skype du destinataire pour client d’entreprise.
    
Pour plus d’informations, consultez [utilisation de messagerie hors connexion dans Skype pour les entreprises](http://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).
  
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
  
1. À partir du **Menu Démarrer**de > **de Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="turning-on-or-off-offline-im"></a>Activation ou désactivation de la messagerie instantanée hors connexion

> [!NOTE]
> Les Messages en mode hors connexion sont **uniquement** disponibles dans la dernière version de la Skype clic pour client d’entreprise et ne sont pas disponibles lorsqu’un Skype clic plus ancien pour les entreprises est utilisé ou un fichier *.msi a été utilisé pour installer le Skype pour client d’entreprise.
  
Pour activer ou désactiver les Messages en mode hors connexion envoyer des Messages en mode hors connexion pour les utilisateurs de votre organisation, la valeur _EnableIMAutoArchiving_ `True` ou `False`. Par défaut, il est défini `True`.
  
Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Pour activer ou désactiver l’envoi des Messages en mode hors connexion en mode hors connexion des Messages pour un utilisateur, la valeur _EnableIMAutoArchiving_ `True` ou `False`. Par défaut, il est défini `True`. Vous pouvez utiliser une stratégie existante ou en créer une comme dans l’exemple ci-dessous.
  
> 
  ```
  New-CsClientPolicy -Identity OfflineIM
  ```

> 
  ```
  Set-CsClientPolicy -Identity OfflineIM -EnableIMAutoArchiving $False
  ```

> 
  ```
  Grant -CsClientPolicy -Identity "Tony Smith" - PolicyName OfflineIM
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utiliser Windows PowerShell pour les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)

[Permettent d’ajouter des contacts de Skype Skype pour les utilisateurs professionnels](let-skype-for-business-users-add-skype-contacts.md)
