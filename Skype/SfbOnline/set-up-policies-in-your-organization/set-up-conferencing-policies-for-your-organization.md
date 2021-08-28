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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: "La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer."
ms.openlocfilehash: 6c940a7d06d05f9584ee3ac1c2e88b78b6275ada
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58597388"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Configurer les stratégies de conférence pour votre organisation

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.
  
Il est important de garder le contrôle sur les conférences et les paramètres de conférence. Dans certains cas, il peut y avoir des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés, peuvent participer aux réunions et enregistrer les diapositives ou les distribuer pendant ces réunions. De plus, il peut y avoir des problèmes juridiques occasionnels. Par exemple, par défaut, les participants à la réunion sont autorisés à ajouter des annotations sur le contenu partagé. toutefois, ces annotations ne sont pas enregistrées lorsque la réunion est archivée. Si votre organisation est tenue de conserver un enregistrement de toutes les communications électroniques, vous pouvez désactiver les annotations. 
  
Dans Skype Entreprise Online, les conférences sont gérées à l’aide de stratégies de conférence. Les stratégies de conférence déterminent les fonctionnalités et fonctions pouvant être utilisées lors d'une conférence, y compris la possibilité, pour la conférence, d'inclure de l'audio et de la vidéo IP à destination du nombre maximum de personnes pouvant participer à une réunion. Les stratégies de conférence peuvent être configurées à l'échelle globale ou individuelle. Les administrateurs bénéficient ainsi d'une très grande souplesse en ce qui concerne les fonctions qu'ils souhaitent mettre à la disposition des utilisateurs.
  
Les paramètres de stratégie peuvent être configurés lors de la création d’une stratégie, ou vous pouvez utiliser l’cmdlet **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-conferencing-policies"></a>Définir vos stratégies de conférence

> [!NOTE]
> Pour tous les paramètres de stratégie de conférence dans Skype Entreprise Online, vous devez utiliser Windows PowerShell et vous ne pouvez pas utiliser le Skype Entreprise **d’administration.**  

### <a name="start-windows-powershell"></a>Démarrer Windows PowerShell

 > [!Note]
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
      
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquer les transferts de fichiers et le partage de bureau pendant les réunions

- Pour créer une stratégie pour ces paramètres, exécutez :
   
   ```powershell
   New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
   ```
   En savoir plus [sur l’cmdlet New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
   
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
  Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquer l’enregistrement des conférences et empêcher les participants anonymes à la réunion

- Pour créer une stratégie pour ces paramètres, exécutez : 
   
   ```powershell
   New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
   ```
   En savoir plus [sur l’cmdlet New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à Amos Marble, exécutez :
   
   ```powershell
    Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
   ```
   En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet [Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions

- Pour créer une stratégie pour ces paramètres, exécutez :  
   
   ```powershell
   New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
   ```
   En savoir plus [sur l’cmdlet New-CsConferencingPolicy.](/powershell/module/skype/New-CsConferencingPolicy)
    
- Pour accorder la nouvelle stratégie que vous avez créée à tous les utilisateurs de votre organisation, exécutez :
    
 
   ```powershell
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
   ```

En savoir plus sur [l’cmdlet Grant-CsConferencingPolicy.](/powershell/module/skype/Grant-CsConferencingPolicy)
    
Si vous avez déjà créé une stratégie, vous pouvez utiliser l’cmdlet [Set-CsConferencingPolicy](/powershell/module/skype/Set-CsConferencingPolicy) pour apporter des modifications à la stratégie existante, puis utiliser l’cmdlet[Grant-CsConferencingPolicy](/powershell/module/skype/Grant-CsConferencingPolicy) pour appliquer les paramètres à vos utilisateurs.
  
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

[Configurer les stratégies client pour votre organisation](set-up-client-policies-for-your-organization.md)

  
