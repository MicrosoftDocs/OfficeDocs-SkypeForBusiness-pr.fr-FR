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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
ms.openlocfilehash: e5fe976e3adb566c469d2c58a5d2b6a976776ac3
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619250"
---
# <a name="set-up-client-policies-for-your-organization"></a>Configurer les stratégies client pour votre organisation

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Les stratégies de client permettent d'identifier les fonctionnalités de Skype Entreprise Online mises à la disposition des utilisateurs. Par exemple, vous pouvez octroyer à certains utilisateurs le droit de transférer des fichiers tout en refusant ce droit à d'autres utilisateurs.
  
Les paramètres de stratégie de client peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsClientPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-client-policies"></a>Définir vos stratégies de client

> [!NOTE]
> Pour tous les paramètres de stratégie client dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous ne pouvez pas utiliser le Centre **Skype Entreprise d’administration.**  
  
### <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
1. Installez le [module Teams PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
 
### <a name="disable-emoticons-and-presence-notifications-and-prevent-saving-of-ims"></a>Désactiver les émoticônes et des notifications de présence et empêcher l’enregistrement des messages instantanés

- Pour créer une stratégie pour ces paramètres, exécutez :
    
 
   ```powershell
   New-CsClientPolicy -Identity ClientPolicy -DisableEmoticons $true -DisablePresenceNote -$true -DisableSavingIM $true
   ```

  En savoir plus sur [l’cmdlet New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="enable-urls-or-hyperlinks-to-be-clickable-in-ims"></a>Activer l'interactivité des URL ou des liens hypertextes dans les messages instantanés

- Pour créer une stratégie pour ces paramètres, exécutez :
    
 
   ```powershell
   New-CsClientPolicy -Identity URLClientPolicy -EnableURL $true
   ```

  En savoir plus sur [l’cmdlet New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName URLClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="prevent-showing-recent-contacts"></a>Bloquer l'affichage des contacts récents

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsClientPolicy -Identity ContactsClientPolicy -ShowRecentContacts $false 
   ```

  En savoir plus sur [l’cmdlet New-CsClientPolicy.](/powershell/module/skype/New-CsClientPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
   
   ```powershell
   Grant-CsClientPolicy -identity "amos.marble@contoso.com" -PolicyName ContactsClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsClientPolicy.](/powershell/module/skype/Grant-CsClientPolicy)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsClientPolicy](/powershell/module/skype/Set-CsClientPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsClientPolicy](/powershell/module/skype/Grant-CsClientPolicy) pour appliquer les paramètres à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
