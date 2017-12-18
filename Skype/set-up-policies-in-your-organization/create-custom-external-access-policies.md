---
title: "Créer des stratégies d'accès externe personnalisé"
ms.author: tonysmit
author: tonysmit
ms.date: 11/10/2017
ms.audience: ITPro
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
description: "Skype entreprise Online vous permet de créer des stratégies supplémentaires accès externe. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies prédéfinies accès externe qui peuvent couvrir la plupart des scénarios. Il s'agit des :"
---

# Créer des stratégies d'accès externe personnalisé

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Skype entreprise Online vous permet de créer des stratégies supplémentaires accès externe. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies prédéfinies accès externe qui peuvent couvrir la plupart des scénarios. Il s'agit des :
  
- N° fédéré ou grand public de Skype Access ( _Tag:NoFederationAndPIC_ )
    
- Accès fédéré uniquement ( _Tag:FederationOnly_ )
    
- Fédéré et consommateur accéder aux ( _FederationAndPICDefault_)
    
Vous permettent pas de stratégies externes personnalisées pour créer d'autres stratégies qui ne sont pas couverts par les paramètres ci-dessus. Lorsque la stratégie a été créée, vous devez être amené à définir tous les paramètres requis et n'a pas pu les modifier ultérieurement. Création de nouvelles stratégies personnalisées permettent aux fonctionnalités de contrôle tel qu'access grand public de Skype ou une stratégie de désactivation public cloud audio/vidéo, qui est un élément qui n'a pas été recouverte de paramètres prédéfinis. Les stratégies d'accès externe personnalisé suivent la même syntaxe en tant que stratégies client, mobilité et conférences. Vous trouverez plus d'informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Pour ce faire, l'utilisateur doit utiliser une version prise en charge de 2016 Click-to-Run Skype entreprise App prenant en charge. La version minimale suivante de Skype entreprise 2016-clic client est requise :
  
|**Type**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|First Release pour Canal actuel  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Canal actuel  <br/> |6/12/2016  <br/> |16.0.7571.2072  <br/> | Version 1611 (build 7571.2072) <br/> |
|Canal différé  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications d'entreprise Windows ou Mac pourront toujours transférer des fichiers. 
  
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
    
## Créer une stratégie d'accès externe personnalisée pour un utilisateur

Pour ce faire, exécutez :
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
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
  

