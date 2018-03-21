---
title: "Réinitialiser le code confidentiel conférence Audio pour un utilisateur"
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Find out what you should know about PINs and how to reset them for your users. '
ms.openlocfilehash: 1deacb0a00ccef585e220752ea94c678d1d5a4d3
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="reset-the-audio-conferencing-pin-for-a-user"></a>Réinitialiser le code confidentiel conférence Audio pour un utilisateur

Un code PIN est un code composé de nombres qui est créé pour chaque Skype pour l’utilisateur professionnel et Teams de Microsoft qui est activé pour la conférence audio. Broches de conférence audio sont utilisés par les organisateurs de la réunion pour identifier leur organisateur de la réunion et de démarrer une réunion par téléphone. S’ils utilisent le Skype pour application métier ou Teams de Microsoft pour démarrer la réunion, un code confidentiel n’est pas obligatoire. Si les utilisateurs oublient leur code PIN, et ils ne peuvent pas le trouver dans l’e-mail envoyé lorsqu’ils ont été activés pour la conférence audio, un administrateur doit réinitialiser son code PIN. Un utilisateur ne peut pas réinitialiser son code confidentiel.
  
Réunions peuvent démarrer lorsqu’un utilisateur authentifié de jointures utilisant un Skype pour application métier ou Teams de Microsoft, ou lorsque l’organisateur de jointures avec son code confidentiel par téléphone. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.
  
## <a name="reset-a-conference-organizers-pin"></a>Réinitialisation du code confidentiel d'un organisateur de conférence

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accédez au **Centre d’administration Office 365** > **Skype pour les entreprises**et de la navigation de gauche, cliquez sur **audioconférence**.
    
3. Cliquez sur **utilisateurs**, sélectionnez l’utilisateur que vous souhaitez réinitialiser le code PIN pour.
    
4. Dans le volet Actions, sous le **code confidentiel**, cliquez sur **Réinitialiser**.
    
## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Une fois que le code confidentiel est réinitialisé par un administrateur, le code PIN sera répertorié comme *** dans le **Skype pour le centre d’administration métier** et dans les résultats lorsqu’ils utilisent Get-CsCsOnlineDialInConfencingUser dans Windows PowerShell.
    
- Envoyer automatiquement des e-mails aux utilisateurs est activé par défaut, et les utilisateurs recevront un message électronique avec leur code PIN lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un e-mail de réinitialisation du code PIN ne seront pas envoyé à un utilisateur et vous devrez envoyer manuellement les informations de code PIN pour l’utilisateur.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Le paramètre par défaut pour ne pas autoriser une réunion doit être démarré par des appelants anonymes.
    
- Lorsque vous activez un utilisateur pour la conférence audio, par défaut, ils sont envoyés les e-mails qui contiennent des informations de conférence et de leur code PIN. L’utilisateur doit avoir une boîte aux lettres Office 365, étant donné que lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel sera envoyé à l’utilisateur par courrier électronique à leur adresse SMTP principale (alias) qui est défini pour l’utilisateur.
    
- Lorsque vous configurez la conférence audio, vous définissez les chiffres qui sont requis pour les broches dans votre organisation. Les codes confidentiels peuvent contenir de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur de broche, le paramètre est appliqué uniquement sur les broches vient d’être générés et n’est pas appliqué au paramètre de code PIN pour les utilisateurs qui sont activés pour les conférences audio. Voir la [définition de la longueur de la broche pour les réunions de la conférence de l’Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Le courrier électronique par défaut est fixé à l’adresse SMTP principale d’Office 365 de l’utilisateur. Vous pouvez envoyer un e-mail à une adresse non - Office 365, tels que Hotmail ou MSN. Vous pouvez remplacer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.
    
- Pour substituer l’adresse d’utilisateur par défaut dans lequel le message est envoyé, l’administration des clients peut utiliser l’applet de commande suivante : Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress « u@hotmail.com ». Le paramètre SendEmail est requise pour substituer l’adresse de messagerie de l’utilisateur.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Vous pouvez définir le code confidentiel pour Amos Marbel en exécutant :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité sur uniquement en utilisant le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md)
