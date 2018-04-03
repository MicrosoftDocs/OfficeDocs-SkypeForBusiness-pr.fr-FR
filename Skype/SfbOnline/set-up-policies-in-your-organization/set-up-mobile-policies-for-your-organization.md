---
title: Configurer les stratégies mobiles pour votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: beea47b2-7b9a-4b28-92d0-af65d80cd00f
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
description: Vous pouvez définir comment les utilisateurs se connectent à Skype pour entreprise en ligne à l’aide de la Skype pour application métier sur des périphériques mobiles, comme une fonctionnalité qui permet aux utilisateurs d’effectuer et de recevoir des appels sur leur téléphone mobile à l’aide de leur numéro de téléphone de travail au lieu de leur nu téléphone mobile bre. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
ms.openlocfilehash: f3fa8b2974406827494ea8ceb759b23d01817825
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-mobile-policies-for-your-organization"></a>Configurer les stratégies mobiles pour votre organisation

Vous pouvez définir comment les utilisateurs se connectent à Skype pour entreprise en ligne à l’aide de la Skype pour application métier sur des périphériques mobiles, comme une fonctionnalité qui permet aux utilisateurs d’effectuer et de recevoir des appels sur leur téléphone mobile à l’aide de leur numéro de téléphone de travail au lieu de leur nu téléphone mobile bre. Des stratégies de mobilité peuvent également être utilisées pour exiger des connexions Wi-Fi lorsque les utilisateurs passent ou reçoivent des appels.
  
Paramètres de stratégie mobile peuvent être configurés au moment de la que création d’une stratégie, ou vous pouvez utiliser l’applet de commande **Set-CsMobilityPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-mobile-policies"></a>Définir vos stratégies mobiles

> [!NOTE]
> Pour tous les paramètres de stratégie mobile dans Skype pour professionnels en ligne, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype pour le centre d’administration commerciale**. 
  
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

### <a name="require-a-wifi-connection-for-video-for-a-user"></a>Exiger d'un utilisateur une connexion Wi-Fi pour les vidéos

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
> 
  ```
  New-CsMobilityPolicy -Identity MobilityPolicy -RequireWIFIForIPVideo $true
  ```
  Reportez-vous à la section plus d’informations sur l’applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
> 
  ```
  Grant-CsMobilityPolicy -Identity"amos.marble@contoso.com" -PolicyName MobilityPolicy
  ```
  Reportez-vous à la section plus d’informations sur l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramétrage à vos utilisateurs.
  
### <a name="prevent-a-user-from-using-the-skype-for-business-app"></a>Empêcher un utilisateur d'utiliser l'application Skype Entreprise

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
```
New-CsMobilityPolicy -Identity NoAppClientPolicy -EnableMobility $false 
```
  Reportez-vous à la section plus d’informations sur l’applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour Amos marbre, exécutez :  
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com"-PolicyName NoAppClientPolicy
  ```
  Reportez-vous à la section plus d’informations sur l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramétrage à vos utilisateurs.
  
### <a name="prevent-a-user-from-making-voice-over-ip-calls-using-a-mobile-device"></a>Empêcher un utilisateur de passer des appels de voix sur IP au moyen d'un appareil mobile

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
> 
  ```
  New-CsMobilityPolicy -Identity VoIPClientPolicy -EnableIPAudioVideo  $false
  ```
  Reportez-vous à la section plus d’informations sur l’applet de commande [New-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779150.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créé pour tous les utilisateurs de votre organisation, exécutez :
> 
  ```
  Grant-CsMobilityPolicy -Identity "amos.marble@contoso.com" -PolicyName VoIPClientPolicy
  ```

  Reportez-vous à la section plus d’informations sur l’applet de commande [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de commande [Set-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779147.aspx) pour apporter des modifications à la stratégie existante et ensuite utiliser l’applet de commande[Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/mt779149.aspx) pour appliquer le paramétrage à vos utilisateurs.
  
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

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

[Définir des stratégies de conférence dans votre organisation](set-up-conferencing-policies-for-your-organization.md)

  
 