---
title: "Configurer des stratégies mobiles pour votre organisation"
ms.author: tonysmit
author: tonysmit
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
description: "Vous pouvez configurer la façon dont vos utilisateurs se connecteront à Skype entreprise Online à l'aide de la Skype entreprise App sur les appareils mobiles, par exemple une fonctionnalité qui permet aux utilisateurs d'émission et réception d'appels téléphoniques sur leur téléphone mobile à l'aide de son numéro de téléphone professionnel au lieu de leur nu téléphone mobile bre. Mobilité stratégies peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque effectuer ou de recevoir des appels."
---

# Configurer des stratégies mobiles pour votre organisation

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](beea47b2-7b9a-4b28-92d0-af65d80cd00f.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/beea47b2-7b9a-4b28-92d0-af65d80cd00f). 
  
Vous pouvez configurer la façon dont vos utilisateurs se connecteront à Skype entreprise Online à l'aide de la Skype entreprise App sur les appareils mobiles, par exemple une fonctionnalité qui permet aux utilisateurs d'émission et réception d'appels téléphoniques sur leur téléphone mobile à l'aide de son numéro de téléphone professionnel au lieu de leur nu téléphone mobile bre. Mobilité stratégies peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque effectuer ou de recevoir des appels.
  
Paramètres de stratégie mobile peuvent être configurés au moment de la que création d'une stratégie, ou vous pouvez utiliser l'applet de commande **Set-CsMobilityPolicy** pour modifier les paramètres d'une stratégie existante.
  
## Définir vos stratégies mobiles

> [!NOTE]
> Pour tous les paramètres de stratégie mobile dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype centre d'administration entreprise**. 
  
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
    
### Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos

- Pour créer une nouvelle stratégie de ces paramètres, exécutez :
    
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```

    En savoir plus sur l'applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```

    En savoir plus sur l'applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
### Empêcher un utilisateur d'utiliser l'application Skype Entreprise

- Pour créer une nouvelle stratégie de ces paramètres, exécutez :
    
> 
  ```
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```

    En savoir plus sur l'applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Pour autoriser la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :
    
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```

    En savoir plus sur l'applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
### Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile

- Pour créer une nouvelle stratégie de ces paramètres, exécutez :
    
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```

    En savoir plus sur l'applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx).
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

    En savoir plus sur l'applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx).
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l'applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l'applet de commande[Grant CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
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
  

