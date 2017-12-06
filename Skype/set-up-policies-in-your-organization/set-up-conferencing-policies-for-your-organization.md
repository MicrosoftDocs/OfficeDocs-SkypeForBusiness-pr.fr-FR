---
title: "Configurer des stratégies de conférence pour votre organisation"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
description: "La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer."
---

# Configurer des stratégies de conférence pour votre organisation

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](9957722b-b542-49ad-8ec8-5569df7fb08b.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/9957722b-b542-49ad-8ec8-5569df7fb08b). 
  
La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.
  
Il est important de conserver le contrôle des paramètres de conférence et les conférences. Dans certains cas, il peut y avoir des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés peut participer aux réunions et enregistrer des diapositives ou documents distribuées pendant les réunions. Par ailleurs, il peut être minimes questions juridiques. Par exemple, par défaut, les participants à la réunion sont autorisés à effectuer des annotations sur le contenu partagé ; Toutefois, ces annotations ne sont pas enregistrées lors de l'archivage de la réunion. Si votre organisation est nécessaire pour garder une trace de toutes les communications électroniques, vous souhaiterez peut-être désactiver les annotations.
  
Conférences sont gérées dans Skype Entreprise Online, en utilisant des stratégies de conférence. Stratégies de conférence déterminent les fonctionnalités pouvant être utilisées dans une conférence, y compris tous les éléments à partir d'ou non la conférence peut inclure IP audio et vidéo pour le nombre maximal de personnes qui peuvent participer à une réunion. Stratégies de conférence peuvent être configurées à la portée globale ou à l'étendue par utilisateur. Cela fournit des administrateurs avec une grande flexibilité lorsqu'il s'agit de décider des capacités seront disponibles pour les utilisateurs.
  
Paramètres de stratégie peuvent être configurés au moment de la que création d'une stratégie, ou vous pouvez utiliser l'applet de commande **Set-CsConferencingPolicy** pour modifier les paramètres d'une stratégie existante.
  
## Définir vos stratégies de conférence

> [!NOTE]
> Pour tous les paramètres de stratégie de conférence dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype centre d'administration entreprise**. 
  
### Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
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
    
### Bloquer les transferts de fichiers et le partage de bureau pendant les réunions

- Pour créer une nouvelle stratégie de ces paramètres, exécutez :
    
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```

    En savoir plus sur l'applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Pour accorder à la nouvelle stratégie que vous avez créé à tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```

    En savoir plus sur l'applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer la paramètres pour vos utilisateurs.
  
### Bloquer l'enregistrement des conférences et empêcher les participants à la réunion anonyme

- Pour créer une nouvelle stratégie de ces paramètres, exécutez :
    
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```

    En savoir plus sur l'applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Pour autoriser la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :
    
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```

    En savoir plus sur l'applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer la paramètres pour vos utilisateurs.
  
### Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions

- Pour créer une nouvelle stratégie de ces paramètres, exécutez :
    
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```

    En savoir plus sur l'applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx).
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

    En savoir plus sur l'applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer la paramètres pour vos utilisateurs.
  
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
  

