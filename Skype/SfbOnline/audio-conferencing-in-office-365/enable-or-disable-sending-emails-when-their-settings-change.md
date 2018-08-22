---
title: Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Skype pour Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 4d52603fb0d2701cbebd58644cd002dbc94baf89
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490584"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a>Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans Skype pour Business Online

> [!Note]
> Si vous souhaitez activer ou désactiver l’envoi d’e-mails dans Microsoft Teams, voir [Activer ou désactiver l’envoi de messages électroniques lorsque les paramètres de conférence Audio changent dans les équipes Microsoft](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).

Les utilisateurs sont avertis automatiquement par courrier électronique lorsqu’ils sont activés pour une audioconférence. Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés à Skype pour les utilisateurs professionnels. Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.
  
Si vous désactivez envoi de courriers électroniques, messages électroniques de conférence Audio ne seront pas envoyées à vos utilisateurs, y compris pour les messages électroniques lorsque les utilisateurs sont activés ou désactivés pour l’audioconférence, leur code confidentiel est réinitialisé et modifications numéros de téléphone de l’ID de conférence et la conférence par défaut .
  
Voici un exemple du courrier électronique qui est envoyé aux utilisateurs lorsqu’ils sont activés pour une audioconférence :
  
![Conférence audio par courrier électronique](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Il existe plusieurs messages électroniques envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :
    
  - Lorsqu’une licence de **Conférence Audio** est attribuée.
    
  - Lorsque vous réinitialisez manuellement code confidentiel de conférence audio de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque la licence de **Conférence Audio** est supprimée à partir de celles-ci.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de services d’audioconférence d’un utilisateur est remplacé par Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver la messagerie d’être envoyés aux utilisateurs

Activation ou désactivation de l'envoi de messages électroniques aux utilisateurs d'appels entrants

 
![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, cliquez sur **conférence Audio**.
    
2. Dans la page **paramètres du pont Microsoft** , activez ou désactivez l' **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**.
    
3. Cliquez sur **Enregistrer**.
    
    > [!TIP]
    > Vous pouvez également envoyer des e-mail à un utilisateur avec les paramètres de conférence audio en accédant à la **conférence Audio** > **les utilisateurs**, sélectionnez l’utilisateur, puis cliquez sur **Envoyer les informations de conférence par courrier électronique**.  Si vous le faites, un message électronique sera envoyé qui inclut uniquement les ID de conférence et numéro de téléphone de conférence, mais pas le code confidentiel.  Pour plus d’informations, voir [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.
  
- Exécutez la procédure suivante pour désactiver l’envoi de messages électroniques : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Pour une assistance avec cette cmdlet, voir [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Lorsque les messages électroniques automatiques sont désactivées, vous pouvez manuellement déclencher l’envoi d’un message électronique avec le numéro de téléphone et les ID de conférence à l’aide de la Skype pour le centre d’administration de Business. Toutefois, si vous faites cela, le code confidentiel ne sera inclus. Si vous souhaitez réinitialiser le code confidentiel de conférence audio et l’envoi d’e-mails est désactivé, vous devrez envoyer à l’utilisateur d’une autre manière.
    
- L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Vous pouvez utiliser ces applets de commande pour gagner du temps ou d’automatiser cette action.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Remove-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Messages électroniques envoyés aux utilisateurs lorsque modifient leurs paramètres de conférence Audio](emails-sent-to-users-when-their-settings-change.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)


