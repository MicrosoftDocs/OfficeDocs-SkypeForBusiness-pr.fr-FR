---
title: Configurer les stratégies de conférence pour votre organisation
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9957722b-b542-49ad-8ec8-5569df7fb08b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer."
ms.openlocfilehash: c5db13adef479bdb3a8702a2782e2ccce19195d6
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861198"
---
# <a name="set-up-conferencing-policies-for-your-organization"></a>Configurer les stratégies de conférence pour votre organisation

La fonctionnalité Conférence est une partie importante de Skype Entreprise Online : elle permet à des groupes d'utilisateurs de se retrouver en ligne pour visionner des diapositives et des vidéos, partager des applications, échanger des fichiers, communiquer et collaborer.
  
Il est important que vous permet de contrôler les conférences et leurs paramètres. Dans certains cas, peuvent poser des problèmes de sécurité : par défaut, tout le monde, y compris les utilisateurs non authentifiés permettre participer aux réunions et enregistrer des diapositives ou documents distribués durant ces dernières. En outre, il peut y avoir des implications juridiques. Par exemple, par défaut, les participants à la réunion sont autorisés à annoter le contenu partagé ; Toutefois, ces annotations ne sont pas enregistrées lors de la réunion est archivée. Si votre organisation est obligée de conserver un enregistrement de toutes les communications électroniques, vous souhaitez désactiver les annotations. 
  
Dans Skype pour Business Online, les conférences sont gérées à l’aide de stratégies de conférence. Stratégies de conférence déterminent les fonctionnalités qui peuvent être utilisées dans une conférence, y compris tout ou non la conférence peut inclure IP audio et vidéo pour le nombre maximal de personnes qui peuvent participer à une réunion. Stratégies de conférence peuvent être configurées au niveau global ou au niveau de l’étendue par utilisateur. Les administrateurs disposent ainsi d’une flexibilité considérable quand il s’agit de déterminer quelles possibilités seront disponibles pour les utilisateurs.
  
Paramètres de stratégie peuvent être configurées au niveau de la création d’une stratégie, ou vous pouvez utiliser l’applet de commande **Set-CsConferencingPolicy** pour modifier les paramètres d’une stratégie existante.
  
## <a name="set-your-conferencing-policies"></a>Définir vos stratégies de conférence

> [!NOTE]
> Pour tous les paramètres de stratégie de conférence dans Skype pour Business Online, vous devez utiliser Windows PowerShell et vous **ne pouvez pas utiliser** le **Skype entreprise centre d’administration**. 
  
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

  Si vous souhaitez plus d’informations sur le démarrage de Windows PowerShell, voir [se connecter à tous les services Office 365 dans une seule fenêtre Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Connecting to Skype pour Business Online à l’aide de Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="block-file-transfers-and-desktop-sharing-during-meetings"></a>Bloquer les transferts de fichiers et le partage de bureau pendant les réunions

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :
> 
  ```
  New-CsConferencingPolicy -Identity DesktopConferencingPolicy -EnableAppDesktopSharing None  $true -EnableFileTransfer $false
  ```
  Voir plus d’informations sur l’applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créée pour tous les utilisateurs de votre organisation, exécutez :
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName DesktopConferencingPolicy
  ```
  Voir plus d’informations sur l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
  Si vous avez déjà créé une stratégie, vous pourrez utiliser l’applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utilisez l’applet de commande[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-recording-of-conferences-and-prevent-anonymous-meeting-participants"></a>Bloquer l’enregistrement des conférences et empêcher des participants à la réunion anonyme

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez : 
> 
  ```
  New-CsConferencingPolicy -Identity ConferencingPolicy -AllowAnonymousParticipantsInMeetings  $false -AllowConferenceRecording $false
  ```
Voir plus d’informations sur l’applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Pour autoriser la nouvelle stratégie que vous avez créé à Amos marbre, exécutez :
> 
  ```
   Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName ConferencingPolicy
  ```
Voir plus d’informations sur l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
Si vous avez déjà créé une stratégie, vous pourrez utiliser l’applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utilisez l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
### <a name="block-anonymous-participants-from-recording-meetings-and-external-users-from-saving-meeting-content"></a>Empêcher les participants anonymes d'enregistrer les réunions et les utilisateurs externes d'enregistrer le contenu des réunions

- Pour créer une nouvelle stratégie pour ces paramètres, exécutez :  
> 
  ```
  New-CsConferencingPolicy -Identity BlockedConferencingPolicy  -AllowExternalUsersToRecordMeeting  $false -AllowExternalUsersToSaveContent $false 
  ```
Voir plus d’informations sur l’applet de commande [New-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779148.aspx) .
    
- Pour accorder à la nouvelle stratégie que vous avez créée pour tous les utilisateurs de votre organisation, exécutez :
    
> 
  ```
  Grant-CsConferencingPolicy -Identity "amos.marble@contoso.com" -PolicyName BlockedConferencingPolicy
  ```

Voir plus d’informations sur l’applet de commande [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) .
    
Si vous avez déjà créé une stratégie, vous pourrez utiliser l’applet de commande [Set-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779157.aspx) pour apporter des modifications à la stratégie existante, puis utilisez l’applet de commande[Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/mt779156.aspx) pour appliquer les paramètres à vos utilisateurs.
  
## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
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

  
 