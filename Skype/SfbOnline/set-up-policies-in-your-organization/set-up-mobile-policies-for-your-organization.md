---
title: Configurer les stratégies mobiles pour votre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui leur permet d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
ms.openlocfilehash: e29a02bddcb9ace29ebd059f8cbc42c5a85c3f12
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240066"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurer les stratégies mobiles pour votre organisation

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui leur permet d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
  
Les paramètres de stratégie mobile peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-mobile-policies"></a>Définir vos stratégies mobiles

> [!NOTE]
> Pour tous les paramètres de stratégie mobile dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous ne pouvez pas utiliser le Centre **d’administration** **Skype Entreprise'** 
  
### <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

> [!NOTE]
> Skype Entreprise Online Connector fait actuellement partie du dernier module PowerShell Teams. Si vous utilisez la version publique la plus récente de PowerShell Teams, vous n’avez pas besoin d’installer Skype Entreprise Online Connector.
1. Installez le [Teams module PowerShell.](/microsoftteams/teams-powershell-install)
    
2. Ouvrez une invite Windows PowerShell commande et exécutez les commandes suivantes : 

   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   Pour plus d’informations sur le démarrage d’Windows PowerShell, consultez Connecter pour tous les [services Microsoft 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) ou Office 365 dans une seule fenêtre Windows PowerShell ou configurer votre ordinateur pour une Windows PowerShell. [](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
   
### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) pour appliquer le paramètre à vos utilisateurs.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Empêcher un utilisateur d'utiliser l'application Skype Entreprise

- Pour créer une stratégie pour ces paramètres, exécutez :
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) pour appliquer le paramètre à vos utilisateurs.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](/powershell/module/skype/New-CsMobilityPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](/powershell/module/skype/Grant-CsMobilityPolicy)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](/powershell/module/skype/Set-CsMobilityPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](/powershell/module/skype/Grant-CsMobilityPolicy) pour appliquer le paramètre à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Six raisons d’utiliser des Windows PowerShell pour gérer des Microsoft 365 ou des Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Sujets associés
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
