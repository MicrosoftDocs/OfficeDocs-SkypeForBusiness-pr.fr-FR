---
title: Activer ou désactiver l’envoi de messages électroniques lors de la modifient de leurs paramètres
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: 9db213285a24ad0a67d305a84f275f21ce741013
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio

Les utilisateurs sont automatiquement avertis par e-mail lorsqu’ils sont activés pour les conférences Audio. Il peut arriver, cependant, lorsque vous souhaitez réduire le nombre de messages électroniques qui sont envoyés à Skype pour des utilisateurs professionnels et Teams de Microsoft. Dans ce cas, vous pouvez désactiver l’envoi de courrier électronique.
  
Si vous désactivez l’envoi de courriers électroniques, les e-mails de conférence Audio ne seront pas envoyées à vos utilisateurs, y compris les e-mails pour lorsque les utilisateurs sont activés ou désactivés pour la conférence audio, lorsque leur code PIN est réinitialisé, et lors de modifications de numéro de téléphone de l’ID de conférence et la conférence par défaut .
  
Voici un exemple du courriel envoyé aux utilisateurs lorsqu’ils sont activés pour les conférences Audio :
  
![Audio conférence par courrier électronique](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>Quand les messages électroniques sont-ils envoyés à vos utilisateurs ?

- Il existe plusieurs messages électroniques qui sont envoyés aux utilisateurs de votre organisation une fois qu’ils sont activés pour les conférences audio :
    
  - Lorsqu’une licence **Audioconférence** est attribuée.
    
  - Lorsque vous effectuez manuellement la conférence code PIN de l’utilisateur.
    
  - Lorsque vous réinitialisez manuellement l'ID de conférence de l'utilisateur.
    
  - Lorsque la licence **d’Audioconférence** est supprimée à partir de ceux-ci.
    
  - Lorsque le fournisseur de conférence audio d’un utilisateur est modifié à partir de Microsoft vers un autre fournisseur ou **Aucun**.
    
  - Lorsque le fournisseur de conférence audio d’un utilisateur est modifié à Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Activer ou désactiver l’envoi pour les utilisateurs de courrier

Vous pouvez utiliser Microsoft Teams, le Skype pour le centre d’administration Business ou Windows PowerShell pour activer ou désactiver des e-mails envoyés aux utilisateurs.

**À l’aide de Skype les équipes Microsoft pour Business Admin Center**
1. Dans la navigation de gauche, accédez à des **réunions** > **Les ponts de conférence**. 

2. En haut de la page de **Ponts de conférence** , cliquez sur **Paramètres du pont**. 

3. Dans le volet **paramètres du pont** , activer ou désactiver **automatiquement envoyer des e-mails aux utilisateurs si leurs paramètres de connexion à modifient**.

4. Cliquez sur **Appliquer**.
  
Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.
    
1. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, cliquez sur **audioconférence**.
    
2. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**.
    
3. Cliquez sur **Enregistrer**.
    
    > [!TIP]
    > Vous pouvez également envoyer des e-mail à un utilisateur avec les paramètres de conférence audio en accédant à **l’audioconférence** > **les utilisateurs**, la sélection de l’utilisateur et en cliquant sur **Envoyer par courrier électronique, les informations de conférence**.  Si vous le faites, un e-mail sera envoyé qui inclut uniquement les ID de conférence et numéro de téléphone de conférence, mais pas le code PIN.  Pour plus d’informations, reportez-vous à la section [Envoyer un courrier électronique à un utilisateur avec les informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.
  
- Exécutez la commande suivante pour désactiver l’envoi de messages électroniques : 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Pour obtenir de l’aide avec cette applet de commande, consultez [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>Informations supplémentaires

- Lorsque les courriels automatiques sont désactivées, vous pouvez manuellement déclencher l’envoi d’un e-mail avec le numéro de téléphone et les ID de conférence utilisant le Skype pour le centre d’administration de Business. Toutefois, si vous le faites, le code confidentiel ne sera inclus. Si vous voulez réinitialiser la code PIN de conférence audio et l’envoi d’e-mails est désactivé, vous devrez envoyer à l’utilisateur d’une autre manière.
    
- L'envoi de courrier électronique à vos utilisateurs peut être désactivé à l'aide du Centre d'administration Skype Entreprise ou de Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Ces applets de commande vous permet de gagner du temps ou d’automatiser cette action.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Supprimer-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[E-mails envoyés aux utilisateurs lors de la modifient de leurs paramètres d’audioconférence](emails-sent-to-users-when-their-settings-change.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)


