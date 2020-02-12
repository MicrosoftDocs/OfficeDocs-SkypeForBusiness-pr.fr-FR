---
title: Configurer les stratégies de conférence pour votre organisation
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
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
description: "La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer."
ms.openlocfilehash: aba41b8c1e527157c9ff8d58a2a7a78bfebb0a82
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887893"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Configurer les stratégies de conférence pour votre organisation

La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.
  
Il est important de garder le contrôle sur les conférences et les paramètres de conférence. Dans certains cas, il peut y avoir des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés, peut participer aux réunions et enregistrer les diapositives ou documents distribuées lors de ces réunions. Par ailleurs, il peut y avoir des problèmes légaux occasionnels. Par exemple, les participants à la réunion peuvent par défaut faire des annotations sur le contenu partagé. Toutefois, ces annotations ne sont pas enregistrées lors de l’archivage de la réunion. Si votre organisation est tenue de conserver une trace de toutes les communications électroniques, il peut être préférable de désactiver les annotations. 
  
Dans Skype entreprise Online, les conférences sont gérées à l’aide de stratégies de conférence. Les stratégies de conférence déterminent les fonctionnalités qui peuvent être utilisées dans une conférence, y compris le nombre de fois que la Conférence peut inclure les appels audio et vidéo IP vers le nombre maximal de personnes qui peuvent participer à une réunion. Les stratégies de conférence peuvent être configurées au niveau de l’étendue globale ou par utilisateur. Cela fournit aux administrateurs une souplesse énorme pour décider quelles fonctionnalités seront mises à la disposition des utilisateurs.
  
Vous pouvez configurer les paramètres de stratégie lors de la création d’une stratégie ou utiliser l’applet de connexion **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-conferencing-policies"></a>Définir vos stratégies de conférence

> [!NOTE]
> Pour tous les paramètres de stratégie de conférence dans Skype entreprise Online, vous devez utiliser Windows PowerShell et **ne pouvez pas utiliser** le **Centre d’administration Skype entreprise**. 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
    1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
        
    2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
        
    3. Si vous n’avez pas la version 3,0 ou une version ultérieure, vous devez télécharger et installer les mises à jour de Windows PowerShell. Pour télécharger et mettre à jour Windows PowerShell vers la version 4,0, voir [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Redémarrez votre ordinateur lorsque vous y êtes invité.
        
    4. Vous devrez également installer le module Windows PowerShell pour Skype Entreprise Online qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé sur le centre de téléchargement de Microsoft à la page [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688). Redémarrez votre ordinateur si vous y êtes invité.
    
    Pour en savoir plus, voir [Se connecter à tous les services Office 365 dans une fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Démarrez une session Windows PowerShell**
    
    1. From the **Start Menu** > **Windows PowerShell**.
        
    2. Dans la fenêtre **Windows PowerShell**, connectez-vous à votre organisation Office 365 en exécutant :
        
        > [!NOTE]
        > Vous devez seulement exécuter la commande **Import-Module** la première fois que vous utilisez le module Windows PowerShell pour Skype Entreprise Online.

       ```PowerShell      
        Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   Pour plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurer votre ordinateur pour Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquer les transferts de fichiers et le partage de bureau pendant les réunions

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   En savoir plus sur l’applet de [nouvelle cmdlet New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .
    
- Pour permettre à tous les utilisateurs de votre organisation d’avoir la nouvelle stratégie créée, exécutez :
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   En savoir plus sur l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquer l’enregistrement des conférences et les participants aux réunions anonymes

- Pour créer une stratégie pour ces paramètres, exécutez : 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   En savoir plus sur l’applet de [nouvelle cmdlet New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   En savoir plus sur l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions

- Pour créer une stratégie pour ces paramètres, exécutez :  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   En savoir plus sur l’applet de [nouvelle cmdlet New-CsConferencingPolicy](https://technet.microsoft.com/library/mt779148.aspx) .
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

En savoir plus sur l’applet de passe [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) .
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’applet de demande [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour modifier la stratégie existante, puis utiliser l’applet de passe[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Six raisons d’utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes
[Créer des stratégies d'accès externe personnalisées](create-custom-external-access-policies.md)

[Bloquer les transferts de fichiers de point à point](block-point-to-point-file-transfers.md)

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

  
 
