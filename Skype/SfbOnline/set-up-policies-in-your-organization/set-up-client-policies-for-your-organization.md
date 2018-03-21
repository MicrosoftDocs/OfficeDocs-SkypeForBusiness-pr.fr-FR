---
title: "Définir des stratégies de client pour votre organisation"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: "Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs."
ms.openlocfilehash: 82fa2c828af9aed01652870ea5d3db02ca8248c3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="set-up-client-policies-for-your-organization"></a>Définir des stratégies de client pour votre organisation

Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
  
Les paramètres de stratégie de client peuvent être configurés au moment de la que création d’une stratégie, ou vous pouvez utiliser l’applet de commande **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-client-policies"></a>Définir vos stratégies de client

> [!NOTE]
> Pour tous les paramètres de la stratégie client dans Skype pour professionnels en ligne, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype pour le centre d’administration commerciale**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
    
2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
    
3. Si vous n'utilisez pas la version 3.0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4.0, consultez [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). Redémarrez votre ordinateur lorsque vous y êtes invité.
    
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
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Désactiver les notifications de présence et les émoticônes et empêcher l’enregistrement de IMs

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
    
> 
  ```
  New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) pour appliquer les paramètres de vos utilisateurs.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
    
> 
  ```
  New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) pour appliquer les paramètres de vos utilisateurs.
  
### <a name="prevent-showing-recent-contacts"></a>Bloquer l'affichage des contacts récents

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
> 
  ```
  New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [New-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779155.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour Amos marbre, exécutez :
> 
  ```
  Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779153.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande [Grant-CsClientPolicy](https://technet.microsoft.com/en-us/library/mt779152.aspx) pour appliquer les paramètres de vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Définir des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)
