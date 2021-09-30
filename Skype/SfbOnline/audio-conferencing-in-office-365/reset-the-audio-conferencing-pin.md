---
title: Réinitialiser le code confidentiel de l’audioconférence Skype Entreprise Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez ce que vous devez savoir sur les piNs et comment les réinitialiser dans Skype Entreprise Online. '
ms.openlocfilehash: c3e33655a5d92dbc24522611a1551c4240c4c228
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011928"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Réinitialiser le code confidentiel de l’audioconférence Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Pour plus d’informations sur la réinitialisation des codes confidentiels des audioconférences dans Microsoft Teams, consultez la rubrique [Réinitialiser le code confidentiel des audioconférences dans Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un code confidentiel est un code composé de nombres qui est créé pour Skype Entreprise utilisateur activé pour l’audioconférence. Les conférences audioconférences sont utilisées par les organisateurs de la réunion pour identifier qu’ils en sont l’organisateur et les autoriser à démarrer une réunion par téléphone. S’il utilise l’Skype Entreprise pour démarrer la réunion, le code confidentiel n’est pas nécessaire. Si un utilisateur oublie son code confidentiel et qu’il ne le retrouve pas dans le courrier électronique qui lui a été envoyé pour l’audioconférence, un administrateur peut réinitialiser son code confidentiel ou réinitialiser son code confidentiel.
  
Les réunions peuvent être démarrées lorsqu’un utilisateur authentifié rejoint la réunion à l’aide de l’application Skype Entreprise ou lorsque l’organisateur participe avec son code confidentiel sur le téléphone. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.
  
## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

1. Connectez-vous avec votre compte scolaire ou scolaire.
    
2. Dans le panneau de navigation de gauche du > **Skype Entreprise,** cliquez sur **Audioconférence.**
    
3. Cliquez sur **Utilisateurs,** puis sélectionnez l’utilisateur pour qui vous voulez réinitialiser le code confidentiel.
    
4. Dans le volet Action, sous Code **confidentiel,** cliquez sur **Réinitialiser.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Réinitialisation par un utilisateur de son propre code confidentiel

Un utilisateur peut réinitialiser un code confidentiel à l’aide de l’option **Réinitialiser le code confidentiel** dans la page **Connexion aux conférences**. Cette page est accessible d’une des trois manières suivantes :

* Dans un navigateur, allez à [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Dans Skype Entreprise, cliquez sur la flèche **Afficher le Menu** en face de **Options**, puis cliquez sur **Outils** > **Paramètres de connexion aux conférences**.
* Dans Skype Entreprise, cliquez sur **Options**, cliquez sur **Transfert d’appel** dans le menu de gauche, puis, dans la section **Paramètres supplémentaires d’appel**, cliquez sur **Modifier les paramètres en ligne**. 

## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Une fois le code confidentiel réinitialisé par un administrateur, il s’intitialise ********* dans le Centre d’administration **Skype Entreprise** et dans les résultats lorsqu’il utilise Get-CsCsOnlineDialInConfencingUser dans Windows PowerShell.
    
- L’envoi automatique de courriers électroniques aux utilisateurs est activé par défaut et les utilisateurs reçoivent un courrier électronique avec leur code confidentiel lorsqu’ils sont activés pour l’audioconférence ou lorsque le code confidentiel est réinitialisé. Toutefois, si vous avez désactivé l’envoi automatique de courriers électroniques, un message de réinitialisation du code confidentiel ne sera pas envoyé à l’utilisateur et vous de aurez à envoyer manuellement les informations de code confidentiel à l’utilisateur.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.
    
- Lorsque vous activez l’audioconférence pour un utilisateur, celui-ci est envoyé par défaut par courrier électronique qui inclut les informations sur la conférence et son code confidentiel. L’utilisateur doit avoir une boîte aux lettres Microsoft 365 ou Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel est envoyé à l’utilisateur par courrier électronique à son adresse SMTP principale (alias) définie pour l’utilisateur.
    
- Lorsque vous définissez l’audioconférence, vous définissez les chiffres requis pour les codex pin de votre organisation. Les codes confidentiels peuvent comporter de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, celui-ci s’applique uniquement aux nouveaux code confidentiels générés et ne s’applique pas au paramètre de code confidentiel pour les utilisateurs déjà activés pour l’audioconférence. Consultez [la longueur du code confidentiel pour les réunions d’audioconférence.](Set-the-PIN-length-for-Audio-Conferencing-meetings.md)
    
- Par défaut, l’e-mail est Microsoft 365 ou Office 365 adresse SMTP principale de l’utilisateur. Vous pouvez envoyer un courrier électronique à une adresse de courrier non Microsoft 365 ou non Office 365, telle qu’une adresse de messagerie Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Ceci est utile si les utilisateurs n’ont pas de boîte aux lettres Exchange messagerie dans Microsoft 365 ou Office 365.
    
- Pour remplacer l’adresse utilisateur par défaut dans laquelle le courrier électronique est envoyé, l’administrateur du client peut utiliser l’cmdlet suivante : Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress « u@hotmail.com ». Le paramètre SendEmail est requis pour remplacer l’adresse de courrier de l’utilisateur.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Vous pouvez définir le code confidentiel pour Amos Marbel en exécutant :
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d'administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell distante, qui se connecte à Skype Entreprise Online. Ce module, pris en charge uniquement sur les ordinateurs 64 bits, peut être téléchargé à partir du Centre de téléchargement Microsoft à l’aide du téléchargement et de l’installation du [module Teams PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md)
  
## <a name="related-topics"></a>Voir aussi

[Réinitialiser l’ID de conférence d’un utilisateur](reset-a-conference-id-for-a-user.md)
