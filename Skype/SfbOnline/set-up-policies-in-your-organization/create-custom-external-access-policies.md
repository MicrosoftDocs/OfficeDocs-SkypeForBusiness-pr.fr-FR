---
title: "Créer des stratégies d’accès externe personnalisée"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: "Skype pour entreprise en ligne vous permet de vous permet de créer des stratégies d’accès externes supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies prédéfinies accès externe qui peuvent couvrir la plupart des scénarios."
ms.openlocfilehash: 7a5e347f3f9629f603544ad9ab06e11d4b649868
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="create-custom-external-access-policies"></a>Créer des stratégies d’accès externe personnalisée

Skype pour entreprise en ligne vous permet de vous permet de créer des stratégies d’accès externes supplémentaires. Contrairement aux stratégies de client ou de conférence, où vous pouvez avoir plusieurs combinaisons, il existe trois stratégies prédéfinies accès externe qui peuvent couvrir la plupart des scénarios. Il s’agit :
  
- Non fédéré ou consommateur de Skype Access (_Balise : NoFederationAndPIC_ )
    
- Accès fédéré uniquement (_Balise : FederationOnly_ )
    
- Fédéré et consommateurs accédez (_FederationAndPICDefault_)
    
Stratégies externes personnalisées vous permettent de créer d’autres stratégies qui ne sont pas couverts par les paramètres ci-dessus. Lors de la création de la stratégie, vous est demandé de définir tous les paramètres requis et n’a pas pu les modifier ultérieurement. Création de nouvelles stratégies personnalisées permettent aux fonctionnalités de contrôle de l’accès client Skype ou une stratégie de désactivation public cloud audio/vidéo, qui est un élément qui n’a pas été recouverte de paramètres prédéfinis. Stratégies d’accès externe personnalisées suivent la même syntaxe que les stratégies de client, de mobilité et de conférence. Vous trouverez plus d’informations sur ces paramètres [ici](https://technet.microsoft.com/en-us/library/mt228132.aspx).
  
Pour ce faire, l’utilisateur doit utiliser une version prise en charge de 2016 Skype clic pour l’application d’entreprise qui prend en charge. La version minimale suivante de Skype pour client d’entreprise 2016-clic est nécessaire :
  
|**Type de**|**Date de publication**|**Version**|**Build**|
|:-----|:-----|:-----|:-----|
|Première version pour canal d’en cours  <br/> |17/11/2016  <br/> |16.0.7571.2006  <br/> |Version 1611 (Build 7571.2006)  <br/> |
|Canal de cours  <br/> |12/6/2016  <br/> |16.0.7571.2072  <br/> |Version 1611 (Build 7571.2072)  <br/> |
|Canal différée  <br/> |2/22/2017  <br/> |16.0.7369.2118  <br/> |Version 1609 (Build 7369.2118)  <br/> |
   
> [!CAUTION]
> Les utilisateurs qui utilisent des versions antérieures de Skype pour les applications métier Windows ou Mac sera toujours en mesure de transférer des fichiers. 
  
## <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
    
    > [!NOTE]
    > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [connexion à Skype pour entreprise en ligne à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a>Créer une stratégie d’accès externe personnalisée pour un utilisateur

Pour ce faire, exécutez la commande :
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True 
-EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Définir des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)
