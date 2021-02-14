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
description: Vous pouvez configurer la façon dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui permet aux utilisateurs d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile. Des stratégies de mobilité peuvent également être utilisées pour exiger Wi-Fi connexions lorsque vous recevez ou recevez des appels.
ms.openlocfilehash: 5094a536a636300ea70a7d358e24ee5c0f511379
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814743"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurer les stratégies mobiles pour votre organisation

Vous pouvez configurer la façon dont vos utilisateurs se connectent à Skype Entreprise Online à l’aide de l’application Skype Entreprise sur les appareils mobiles, comme une fonctionnalité qui permet aux utilisateurs d’effectuer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone à la place de leur numéro de téléphone mobile. Des stratégies de mobilité peuvent également être utilisées pour exiger Wi-Fi connexions lorsque vous recevez ou recevez des appels.
  
Les paramètres de stratégie mobile peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-mobile-policies"></a>Définir vos stratégies mobiles

> [!NOTE]
> Pour tous les paramètres de stratégie mobile dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre **d’administration** **Skype Entreprise.** 
  
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

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Pour plus d’informations sur le démarrage d’Windows PowerShell, voir Se connecter à tous les [services Microsoft 365 ou Office 365](https://technet.microsoft.com/library/dn568015.aspx) dans une seule fenêtre Windows PowerShell ou Configurer votre ordinateur pour une [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Empêcher un utilisateur d'utiliser l'application Skype Entreprise

- Pour créer une stratégie pour ces paramètres, exécutez :
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   En savoir plus sur [l’cmdlet New-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779150.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  En savoir plus sur [l’cmdlet Grant-CsMobilityPolicy.](https://technet.microsoft.com/library/mt779149.aspx)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
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

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configurer des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
