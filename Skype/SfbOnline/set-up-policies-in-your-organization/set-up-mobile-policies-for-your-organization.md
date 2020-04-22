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
description: Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype entreprise Online à l’aide de l’application Skype entreprise sur les appareils mobiles, par exemple une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone professionnel plutôt que leur numéro de téléphone mobile. Les stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lors de la création ou de la réception d’appels.
ms.openlocfilehash: ac8f94cb7203b3b0ee4698969db0b76cb1e31a49
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776259"
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurer les stratégies mobiles pour votre organisation

Vous pouvez configurer la manière dont vos utilisateurs se connectent à Skype entreprise Online à l’aide de l’application Skype entreprise sur les appareils mobiles, par exemple une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels téléphoniques sur leur téléphone mobile en utilisant leur numéro de téléphone professionnel plutôt que leur numéro de téléphone mobile. Les stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lors de la création ou de la réception d’appels.
  
Vous pouvez configurer les paramètres de stratégie mobile lors de la création d’une stratégie ou utiliser l’applet de connexion **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-mobile-policies"></a>Définir vos stratégies mobiles

> [!NOTE]
> Pour tous les paramètres de stratégie mobile dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
    1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
        
    2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
        
    3. Si vous n’avez pas la version 3,0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.
        
    4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. Dans la fenêtre **Windows PowerShell** , connectez-vous à Microsoft 365 ou Office 365 en exécutant :
        
        > [!NOTE]
        > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
   ```
   En savoir plus sur l’applet de [nouvelle cmdlet New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
   ```
   En savoir plus sur l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Empêcher un utilisateur d'utiliser l'application Skype Entreprise

- Pour créer une stratégie pour ces paramètres, exécutez :
  ```PowerShell
  New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
  ```
  En savoir plus sur l’applet de [nouvelle cmdlet New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :  
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
   ```
   En savoir plus sur l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
   ```
   En savoir plus sur l’applet de [nouvelle cmdlet New-CsMobilityPolicy](https://technet.microsoft.com/library/mt779150.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
   ```

  En savoir plus sur l’applet de passe [Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsMobilityPolicy](https://technet.microsoft.com/library/mt779147.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsMobilityPolicy](https://technet.microsoft.com/library/mt779149.aspx) pour appliquer le paramètre à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Voir aussi
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Configuration des stratégies de conférence au sein de votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 
