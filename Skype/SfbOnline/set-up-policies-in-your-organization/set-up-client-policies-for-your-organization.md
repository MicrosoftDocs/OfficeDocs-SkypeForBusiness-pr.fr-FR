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
ms.openlocfilehash: 3a7dd7a2840a4e94abe88c472e6dc5b0e1720704
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814353"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurer les stratégies client pour votre organisation

Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
  
Les paramètres de stratégie de client peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-client-policies"></a>Définir vos stratégies de client

> [!NOTE]
> Pour tous les paramètres de stratégie de client dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre **d’administration** **Skype Entreprise.** 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
    1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
        
    2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
        
    3. Si vous n’avez pas la version 3.0 ou une version supérieure, vous devez télécharger et installer les mises à jour Windows PowerShell. Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à jour Windows PowerShell vers la version 4.0. Redémarrez votre ordinateur lorsque vous y êtes invité.
        
    4. Vous devrez également installer le module Windows PowerShell teams qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. 
    
    Pour en savoir plus, consultez Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx)dans une Windows PowerShell unique.
    
- **Démarrez une session Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. Dans la **Windows PowerShell,** connectez-vous à votre Microsoft 365 ou Office 365 en exécutant :
    
    > [!NOTE]
    > Skype Entreprise Online Connector fait actuellement partie du module Teams PowerShell le plus récent.
    >
    > Si vous utilisez la dernière version publique [de Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)vous n’avez pas besoin d’installer Skype Entreprise Online Connector.

       ```powershell
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session 
       ```
Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Désactiver les émoticônes et des notifications de présence et empêcher l’enregistrement des messages instantanés

- Pour créer une stratégie pour ces paramètres, exécutez :
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  En savoir plus sur [l’cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés

- Pour créer une stratégie pour ces paramètres, exécutez :
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  En savoir plus sur [l’cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="prevent-showing-recent-contacts"></a>Bloquer l'affichage des contacts récents

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  En savoir plus sur [l’cmdlet New-CsClientPolicy.](https://technet.microsoft.com/library/mt779155.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](https://technet.microsoft.com/library/mt779152.aspx)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](https://technet.microsoft.com/library/mt779153.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](https://technet.microsoft.com/library/mt779152.aspx) pour appliquer les paramètres à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Sujets associés
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
