---
title: "Transfert de fichiers bloc point à point"
ms.author: tonysmit
author: tonysmit
ms.date: 11/9/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
description: "Dans Skype entreprise Online, vous devez possibilité de contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cette option permet d'ou transferts pour les utilisateurs ou non qu'ils sont transfert de fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d'une autre organisation de blocs de fichiers. Suivre les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations fédérées ou partenaires."
---

# Transfert de fichiers bloc point à point

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](9adf9859-de5b-461e-92ea-b6ce4dd2f7c1.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/9adf9859-de5b-461e-92ea-b6ce4dd2f7c1). 
  
Dans Skype entreprise Online, vous devez possibilité de contrôler les transferts de fichiers de point à point (P2P) dans le cadre des paramètres de stratégie de conférence existants. Toutefois, cette option permet d'ou transferts pour les utilisateurs ou non qu'ils sont transfert de fichiers à un utilisateur qui se trouve dans la même organisation ou à un utilisateur fédéré à partir d'une autre organisation de blocs de fichiers. Suivre les étapes ci-dessous, vous pouvez bloquer les transferts de fichiers P2P avec des organisations fédérées ou partenaires.
  
Un scénario très courant est lorsque vous souhaitez permettre aux utilisateurs internes de transfert de fichier utiliser P2P mais transfert de fichiers bloc avec les partenaires fédérés. Dans ce scénario, vous devez faire :
  
- Attribuer une stratégie de conférence avec P2P transfert de fichiers activé ( _EnableP2PFileTransfer_ défini sur _True_) aux utilisateurs de votre organisation.
    
- Créer la stratégie de communication utilisateur externe aglobal pour bloquer les transferts de fichier externes P2P (défini _EnableP2PFileTransfer_ à _False_) et les affecter à un utilisateur de votre organisation.
    
Vous trouverez plus d'informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Si un utilisateur fédéré à l'extérieur de votre organisation tente d'envoyer un fichier à un utilisateur dans lequel la stratégie a été appliquée, ils recevront une erreur **Échec de transfert**. Et si un utilisateur tente d'envoyer un fichier, celui-ci reçoit une erreur de **transfert de fichiers est désactivé**.
  
Pour ce faire, l'utilisateur doit être à l'aide une version prise en charge d'un Skype Click-to-Run 2016 Business application prenant en charge. La version minimale suivante de Skype entreprise 2016-clic client est requise :
  
|**Type**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release pour Canal actuel  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Canal actuel  <br/> |6/12/2016  <br/> |16.0.7571.2072  <br/> | Version 1611 (build 7571.2072) <br/> |
|Canal différé  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications d'entreprise Windows ou Mac sont toujours en mesure de transférer des fichiers. 
  
## Vérifier et démarrer Windows PowerShell

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
    
## Désactiver le transfert de fichiers P2P pour votre organisation

Par défaut,  _EnableP2PFileTransfer_ est activé sur stratégie globale de l'organisation. Lorsqu'il a été créé, vos utilisateurs ont été affectés à la stratégie _BposSAllModality_.
  
> Pour autoriser les transferts P2P pour à l'intérieur de votre organisation mais bloquer les transferts de fichiers externes à une autre organisation, il vous suffit de modifier à un niveau global. Pour ce faire, exécutez :
    
  ```
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## Désactiver le transfert de fichiers P2P pour un utilisateur

- Vous pouvez appliquer cette à un utilisateur en créant une nouvelle stratégie et octroyer à cet utilisateur. Pour ce faire, exécutez :
    
> 
  ```
  New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
  ```

> 
  ```
  Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
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
  

