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
ms.openlocfilehash: f5b420b9a5f288a0c733d3dfdc7ebc45fb323f32
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814753"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Configurer les stratégies de conférence pour votre organisation

La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.
  
Il est important de garder le contrôle sur les conférences et les paramètres de conférence. Dans certains cas, il peut y avoir des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés, peuvent participer aux réunions et enregistrer les diapositives ou les distribuer pendant ces réunions. De plus, il peut y avoir des problèmes juridiques occasionnels. Par exemple, par défaut, les participants à la réunion sont autorisés à ajouter des annotations sur le contenu partagé. toutefois, ces annotations ne sont pas enregistrées lorsque la réunion est archivée. Si votre organisation est tenue de conserver un enregistrement de toutes les communications électroniques, vous pouvez désactiver les annotations. 
  
Dans Skype Entreprise Online, les conférences sont gérées à l’aide de stratégies de conférence. Les stratégies de conférence déterminent les fonctionnalités et fonctionnalités qui peuvent être utilisées pendant une conférence, y compris la possibilité pour la conférence d’inclure ou non l’audio et la vidéo IP au nombre maximal de personnes qui peuvent participer à une réunion. Les stratégies de conférence peuvent être configurées à l’échelle globale ou par utilisateur. Cela permet aux administrateurs d’avoir une très grande flexibilité en ce qui concerne la décision des fonctionnalités à mettre à la disposition des utilisateurs.
  
Les paramètres de stratégie peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-conferencing-policies"></a>Définir vos stratégies de conférence

> [!NOTE]
> Pour tous les paramètres de stratégie de conférence dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et le Centre **d’administration** **Skype Entreprise.** 
  
### <a name="verify-and-start-windows-powershell"></a>Vérifier et démarrer Windows PowerShell

- **Vérifiez que vous exécutez la version 3.0 ou une version ultérieure de Windows PowerShell**
    
    1. Pour vérifier que vous exécutez la version 3.0 ou une version ultérieure : **Menu Démarrer** > **Windows PowerShell**.
        
    2. Consultez la version en entrant  _Get-Host_ dans la fenêtre **Windows PowerShell**.
        
    3. Si vous n’avez pas la version 3.0 ou une version supérieure, vous devez télécharger et installer les mises à jour Windows PowerShell. Voir [Windows Management Framework 4.0 pour](https://go.microsoft.com/fwlink/?LinkId=716845) télécharger et mettre à jour Windows PowerShell vers la version 4.0. Redémarrez votre ordinateur lorsque vous y êtes invité.
        
    4. Vous devrez également installer le module Windows PowerShell pour Teams qui vous permet de créer une session Windows PowerShell distante qui se connecte à Skype Entreprise Online.
    
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
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquer les transferts de fichiers et le partage de bureau pendant les réunions

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   En savoir plus sur [l’cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquer l’enregistrement des conférences et empêcher les participants anonymes à la réunion

- Pour créer une stratégie pour ces paramètres, exécutez : 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   En savoir plus [sur l’cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions

- Pour créer une stratégie pour ces paramètres, exécutez :  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   En savoir plus sur [l’cmdlet New-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779148.aspx)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](https://technet.microsoft.com/library/mt779156.aspx)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](https://technet.microsoft.com/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsConferencingPolicy](https://technet.microsoft.com/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
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

  
 
