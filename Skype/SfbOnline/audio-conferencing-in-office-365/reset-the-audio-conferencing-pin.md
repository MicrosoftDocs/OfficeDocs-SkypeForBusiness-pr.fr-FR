---
title: Réinitialiser le code confidentiel de l’audioconférence dans Skype entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
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
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et la manière de les réinitialiser dans Skype entreprise online. '
ms.openlocfilehash: 21e2742653e72919df0647c0539fdb335585cc84
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164693"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Réinitialiser le code confidentiel de l’audioconférence dans Skype entreprise Online

> [!Note]
> Pour plus d’informations sur la réinitialisation des codes confidentiels des audioconférences dans Microsoft Teams, consultez la rubrique [Réinitialiser le code confidentiel des audioconférences dans Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

A PIN is a code made up of numbers that is created for each Skype for Business user who is enabled for audio conferencing. Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone. If they use the Skype for Business app to start the meeting, a PIN isn't required. If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.
  
Meetings can be started when an authenticated user joins using the Skype for Business app or when the organizer joins with his or her PIN over the phone. When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts. If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.
  
## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

1. Connectez-vous à l’aide de votre compte professionnel ou scolaire.
    
2. Accédez au centre d’administration > **Skype entreprise**, puis, dans le volet de navigation de gauche, cliquez sur **audioconférence**.
    
3. Cliquez sur **utilisateurs**, sélectionnez l’utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.
    
4. Dans le volet action, sous **code confidentiel**, cliquez sur **Réinitialiser**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Réinitialisation par un utilisateur de son propre code confidentiel

A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page. This page can be accessed in one of three ways:

* Dans un navigateur, allez à [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Dans Skype Entreprise, cliquez sur la flèche **Afficher le Menu** en face de **Options**, puis cliquez sur **Outils** > **Paramètres de connexion aux conférences**.
* Dans Skype Entreprise, cliquez sur **Options**, cliquez sur **Transfert d’appel** dans le menu de gauche, puis, dans la section **Paramètres supplémentaires d’appel**, cliquez sur **Modifier les paramètres en ligne**. 

## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset. After the PIN is reset by an administrator, the PIN will be listed as *********** in the **Skype for Business admin center** and in the results when they use Get-CsCsOnlineDialInConfencingUser in Windows PowerShell.
    
- Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Par défaut, les appelants anonymes ne permettent pas de démarrer une réunion.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, il est envoyé par défaut des messages électroniques qui incluent des informations de conférence et leur code confidentiel. L’utilisateur doit posséder une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code secret est envoyé à l’utilisateur dans un message électronique à l’adresse SMTP principale (alias) qui est définie pour l’utilisateur.
    
- When you set up audio conferencing, you set the digits that are required for the PINs in your organization. PINs can be from 4 to 12 digits - the default is 5. If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing. See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Par défaut, l’adresse électronique est définie sur l’adresse SMTP principale de Microsoft 365 ou Office 365. Vous pouvez envoyer un courrier électronique à une adresse non Microsoft 365 ou non-Office 365, telle qu’une adresse de messagerie Hotmail ou MSN. Vous pouvez remplacer l’adresse électronique par défaut à l’aide de Windows PowerShell. Cette fonctionnalité est utile si les utilisateurs ne disposent pas de boîte aux lettres Exchange dans Microsoft 365 ou Office 365.
    
- To override the default user address where the email is sent, the tenant admin can use the following cmdlet: Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". The SendEmail parameter is required to override the email address of the user.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Vous pouvez définir le code confidentiel pour Amos Marbel en exécutant :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell consiste à gérer les utilisateurs et à identifier les utilisateurs autorisés ou interdits. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité qui consiste à utiliser le centre d’administration Microsoft 365, par exemple, lorsque vous modifiez les paramètres de nombreux utilisateurs en même temps. Découvrez les avantages suivants dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Voir aussi

[Réinitialiser l’ID de conférence d’un utilisateur](reset-a-conference-id-for-a-user.md)
