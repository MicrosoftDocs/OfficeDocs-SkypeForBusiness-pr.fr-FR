---
title: Activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres d’audioconférence dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 9deb04e418d00171375aec34ca873a89c8a31cdf
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011728"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres d’audioconférence dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Si vous voulez activer ou désactiver l’envoi de courriers électroniques dans Microsoft Teams, voir Activer ou désactiver l’envoi de courriers électroniques en cas de modification des [paramètres d’audioconférence dans Microsoft Teams.](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams)

Les utilisateurs sont avertis automatiquement par courrier électronique lorsqu’ils sont activés pour l’audioconférence. Toutefois, il peut être possible que vous vouliez réduire le nombre de courriers électroniques envoyés à Skype Entreprise utilisateurs. Dans ce cas, vous pouvez désactiver l’envoi de courriers électroniques.
  
Si vous désactivez l’envoi de courriers électroniques, les messages audioconférences ne seront pas envoyés à vos utilisateurs, y compris les courriers électroniques concernant les moments où les utilisateurs sont activés ou désactivés pour l’audioconférence, lorsque leur code confidentiel est réinitialisé, et lorsque l’ID de conférence et le numéro de téléphone de conférence par défaut changent.
  
Voici un exemple du courrier électronique envoyé aux utilisateurs lorsqu’ils sont activés pour l’audioconférence :
  
![Messagerie audioconférence.](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Après avoir activé l’audioconférence, plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation :
    
  - **Lorsqu’une licence d’audioconférence** leur est affectée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel de l’utilisateur pour l’audioconférence.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque la **licence d’audioconférence** leur est retirée.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur passe de Microsoft à un autre fournisseur ou à **Aucun.**
    
  - Lorsque Microsoft est le fournisseur de services d’audioconférence.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver l’envoi de courriers électroniques aux utilisateurs

Vous pouvez utiliser le Centre Skype Entreprise d’administration ou Windows PowerShell pour activer ou désactiver le courrier électronique envoyé aux utilisateurs.

 
![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **Utilisation du Skype Entreprise d’administration**
    
1. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, cliquez sur **Audioconférence.**
    
2. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.
    
3. Cliquez sur **Enregistrer**.
    
    > [!TIP]
    > Vous pouvez également envoyer un courrier électronique à un utilisateur avec les paramètres de conférence audio en sélectionnant Utilisateurs de l’audioconférence, en sélectionnant l’utilisateur et en cliquant sur Envoyer les informations sur la conférence  >  par **courrier électronique.**  Dans ce cas, un message électronique incluant uniquement l’ID de conférence et le numéro de téléphone de la conférence sera envoyé, mais pas le code confidentiel.  Pour [plus d’informations,](send-an-email-to-a-user-with-their-dial-in-information.md) voir Envoyer un courrier électronique à un utilisateur avec ses informations d’audioconférence.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
- Pour désactiver l’envoi de courriers électroniques, exécutez l’une des exécuter comme suit : 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Pour obtenir de l’aide sur cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings)
    
## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Lorsque les messages automatiques sont désactivés, vous pouvez toujours déclencher l’envoi d’un courrier électronique avec l’ID de conférence et le numéro de téléphone à l’aide du Centre Skype Entreprise’administration. Toutefois, si vous le faites, le code confidentiel n’est pas inclus. Si vous voulez réinitialiser le code confidentiel de l’audioconférence et que l’envoi de courriers électroniques est désactivé, vous devrez l’envoyer à l’utilisateur par un autre moyen.
    
- L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Vous pouvez utiliser ces cmdlets pour gagner du temps ou automatiser ce processus.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d'administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell distante, qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du Centre de téléchargement Microsoft à l’aide du téléchargement et de l’installation du [module Teams PowerShell](https://go.microsoft.com/fwlink/?LinkId=294688)(.). /set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>Voir aussi

[Messages électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
