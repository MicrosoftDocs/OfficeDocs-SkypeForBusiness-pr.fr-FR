---
title: Activation ou désactivation de l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Skype entreprise Online
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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: bfdbe1c6c9380b12086ce667c588d8b974438ee5
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707219"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Activation ou désactivation de l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Skype entreprise Online

> [!Note]
> Si vous souhaitez activer ou désactiver l’envoi de courriers électroniques dans Microsoft Teams, voir [activer ou désactiver l’envoi de courriers électroniques en cas de modification des paramètres de conférence audio dans Microsoft teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Les utilisateurs sont automatiquement avertis par courrier lorsqu’ils sont activés pour les conférences audio. Toutefois, il peut arriver que vous souhaitiez réduire le nombre de messages électroniques envoyés aux utilisateurs de Skype entreprise. Dans ces cas, vous pouvez désactiver l’envoi de messages électroniques.
  
Si vous désactivez l’envoi de courriers électroniques, les messages électroniques de l’audioconférence ne seront envoyés à vos utilisateurs, y compris les messages électroniques pour lesquels les utilisateurs sont activés ou désactivés pour les conférences audio, lorsque leur code confidentiel est réinitialisé et lorsque l’ID de conférence et le numéro de téléphone de la Conférence par défaut changent. .
  
Voici un exemple de message électronique envoyé aux utilisateurs lorsqu’ils sont activés pour les conférences audio :
  
![Messagerie de l’audioconférence](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Plusieurs messages électroniques sont envoyés aux utilisateurs de votre organisation après leur activation pour l’audioconférence :
    
  - Lorsqu’une licence de **conférence audio** leur est affectée.
    
  - Lorsque vous réinitialisez manuellement le code confidentiel de l’audioconférence de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque la licence de **conférence audio** y est supprimée.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est passé de Microsoft à un autre fournisseur ou à **aucun**.
    
  - Lorsque Microsoft est remplacé par le fournisseur de services d’audioconférence d’un utilisateur.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activation ou désactivation de l’envoi de messages électroniques aux utilisateurs

Vous pouvez utiliser le centre d’administration Skype entreprise ou Windows PowerShell pour activer ou désactiver les messages envoyés aux utilisateurs.

 
![Icône illustrant le logo](../images/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**
    
1. Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation de gauche, cliquez sur **audioconférence**.
    
2. Dans la page des **paramètres de pont Microsoft**, activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres d’audioconférence ont été modifiés**.
    
3. Cliquez sur **Enregistrer**.
    
    > [!TIP]
    > Vous pouvez également envoyer un courrier électronique à un utilisateur avec les paramètres de l’audioconférence en accédant aux**utilisateurs**de l' **audioconférence** > , en sélectionnant l’utilisateur, puis en cliquant sur **Envoyer les informations sur la Conférence par courrier électronique**.  Dans ce cas, un message électronique est envoyé, qui inclut l’ID de conférence et le numéro de téléphone de la Conférence, mais pas le code confidentiel.  Pour plus d’informations, voir [Envoyer un courrier électronique à un utilisateur avec ses informations de conférence audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
- Pour désactiver l’envoi de courriers électroniques, exécutez la commande suivante : 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Pour obtenir de l’aide sur cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Lorsque les messages électroniques automatiques sont désactivés, vous pouvez toujours déclencher manuellement l’envoi d’un courrier électronique contenant l’ID de la Conférence et le numéro de téléphone à l’aide du centre d’administration Skype entreprise. Toutefois, le code confidentiel n’est pas inclus. Si vous souhaitez réinitialiser le code confidentiel de l’audioconférence et que l’envoi des courriers électroniques est désactivé, vous devez l’envoyer à l’utilisateur d’une autre manière.
    
- L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Vous pouvez utiliser ces applets pour gagner du temps ou automatiser cette opération.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres de conférence audio](emails-sent-to-users-when-their-settings-change.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)


