---
title: Configurer les stratégies client pour votre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 0326b19f-4fd1-4b74-8791-df4c09a964b9
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
description: Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
ms.openlocfilehash: 43b51b800b3107410c64bd2605b5a6a7622fe65a
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776289"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurer les stratégies client pour votre organisation

Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
  
Vous pouvez configurer les paramètres de stratégie de client lors de la création d’une stratégie ou utiliser l’applet de connexion **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-client-policies"></a>Définir vos stratégies de client

> [!NOTE]
> Pour tous les paramètres de stratégie de client dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
    1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
        
    2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
        
    3. Si vous n’avez pas la version 3,0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.
        
    4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
    1. Depuis le **Menu Démarrer** > **Windows PowerShell**.
        
    2. Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :
    
        > [!NOTE]
        > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

       ```powershell
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```
Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Désactiver les émoticônes et des notifications de présence et empêcher l’enregistrement des messages instantanés

- Pour créer une stratégie pour ces paramètres, exécutez :
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  En savoir plus sur l’applet de [nouvelle cmdlet New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  En savoir plus sur l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés

- Pour créer une stratégie pour ces paramètres, exécutez :
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  En savoir plus sur l’applet de [nouvelle cmdlet New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  En savoir plus sur l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="prevent-showing-recent-contacts"></a>Bloquer l'affichage des contacts récents

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  En savoir plus sur l’applet de [nouvelle cmdlet New-CsClientPolicy](https://technet.microsoft.com/library/mt779155.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  En savoir plus sur l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez les avantages suivants dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configuration des stratégies de conférence au sein de votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
