---
title: "Activation ou désactivation des messages hors connexion pour les administrateurs"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 8967a77f-caa2-4680-aa22-8faa32c716e4
description: "Learn how to send Skype for Business instant messages even when your contacts aren't signed in using PowerShell."
---

# Activation ou désactivation des messages hors connexion pour les administrateurs

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Vous pouvez envoyer Skype entreprise des messages à vos contacts même si elles ne sont pas connectés. Cette fonctionnalité permet à vos contacts de savoir que vous avez essayé de communiquer avec elles. Vous n'êtes pas obligé de patienter jusqu'à ce qu'une personne est en ligne avant de les envoyer un message.
  
Pour les messages hors connexion, il est important de savoir que :
  
- les messages hors connexion ne seront archivés dans la boîte aux lettres de l'utilisateur ;
    
- Messages en mode hors connexion seront envoyés aux boîtes aux lettres de l'utilisateur et l'utilisateur sera averti lorsqu'ils se connectent à Skype entreprise.
    
- Si le statut du destinataire du message est défini sur **Ne pas déranger** ou **en présentation**, ils recevront un message manqué envoyé à partir Skype du destinataire entreprise.
    
Pour plus d'informations, voir [Utilisation de la messagerie hors ligne dans Skype Entreprise](https://support.office.com/article/ffdc6a43-71a1-40ee-bfcc-640d21324a3d).
  
## Pour commencer

### 

 **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
  
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### 

 **Démarrez une session Windows PowerShell**
  
1. Dans le **menu Démarrer**, recherchez **Windows PowerShell**.
    
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

Pour plus d'informations sur le démarrage de Windows PowerShell, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou[Connexion à Skype Entreprise Online à l'aide de Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
## Activation ou désactivation de la messagerie instantanée hors connexion

> [!NOTE]
> Les Messages en mode hors connexion sont **uniquement** disponibles dans la dernière version de la démarrer en un clic Skype entreprise et ne sont pas disponibles lorsqu'une ancienne Skype démarrer en un clic pour les entreprises est utilisé ou un fichier *.msi a été utilisé pour installer le Skype entreprise.
  
Pour activer ou désactiver l'envoi des Messages en mode hors connexion Messages en mode hors connexion pour les utilisateurs de votre organisation, définissez  _EnableIMAutoArchiving_ sur `True` ou `False`. Par défaut, il est défini sur  `True`.
  
Pour éteindre, utilisez la cmdlet **Set-CsClientPolicy** et exécutez :
  
```
Set-CsClientPolicy -Identity Global -EnableIMAutoArchiving $False
```

Pour activer ou désactiver l'envoi des Messages en mode hors connexion Messages en mode hors connexion pour un utilisateur, définissez  _EnableIMAutoArchiving_ sur `True` ou `False`. Par défaut, il est défini sur  `True`. Vous pouvez utiliser une stratégie existante ou créer sur comme dans l'exemple ci-dessous.
  
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

## Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

