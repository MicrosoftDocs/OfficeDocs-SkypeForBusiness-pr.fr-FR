---
title: Réinitialiser le code confidentiel d’audioconférence dans Skype Entreprise Online
mms.author: tonysmit
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et comment les réinitialiser dans Skype Entreprise Online. '
ms.openlocfilehash: 57431b51607f963f6dbd6da688e9bf7bd2758b53
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854294"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a>Réinitialiser le code confidentiel d’audioconférence dans Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur la réinitialisation des codes confidentiels des audioconférences dans Microsoft Teams, consultez la rubrique [Réinitialiser le code confidentiel des audioconférences dans Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).

Un code confidentiel est un code numérique créé pour chaque utilisateur Skype Entreprise pour qui l’audioconférence est activée. Un code confidentiel d’audioconférence permet à l’organisateur d’une réunion de s’identifier en tant que tel et de démarrer une réunion téléphonique. S’il utilise l’application Skype Entreprise pour démarrer la réunion, le code confidentiel n’est pas obligatoire. Si un utilisateur oublie son code confidentiel et qu’il ne le retrouve pas dans le courrier électronique qui lui a été envoyé lors de l’activation de la fonctionnalité d’audioconférence, un administrateur peut réinitialiser son code confidentiel, ou il peut réinitialiser son propre code confidentiel.
  
Les réunions peuvent commencer lorsqu’un utilisateur authentifié rejoint une réunion avec l’application Skype Entreprise ou lorsque l’organisateur rejoint la réunion en saisissant son code confidentiel par téléphone. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.
  
## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Allez dans le **Centre d’administration Office 365** > **Skype Entreprise**, et dans la navigation de gauche, cliquez sur **Audioconférences**.
    
3. Cliquez sur **Utilisateurs**, sélectionnez l’utilisateur pour lequel vous souhaitez réinitialiser le code confidentiel.
    
4. Dans le volet Actions, sous **Code confidentiel**, cliquez sur **Réinitialiser**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Réinitialisation par un utilisateur de son propre code confidentiel

Un utilisateur peut réinitialiser un code confidentiel à l’aide de l’option **Réinitialiser le code confidentiel** dans la page **Connexion aux conférences**. Cette page est accessible d’une des trois manières suivantes :

* Dans un navigateur, allez à [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Dans Skype Entreprise, cliquez sur la flèche **Afficher le Menu** en face de **Options**, puis cliquez sur **Outils** > **Paramètres de connexion aux conférences**.
* Dans Skype Entreprise, cliquez sur **Options**, cliquez sur **Transfert d’appel** dans le menu de gauche, puis, dans la section **Paramètres supplémentaires d’appel**, cliquez sur **Modifier les paramètres en ligne**. 

## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Une fois réinitialisé par un administrateur, le code confidentiel s’affiche sous la forme *********** dans le Centre d’administration Skype Entreprise et dans les résultats de **Get-CsCsOnlineDialInConfencingUser** dans Windows PowerShell.
    
- L’envoi automatique de courrier électronique aux utilisateurs est activé par défaut, et les utilisateurs recevront un courrier électronique avec leur code confidentiel lorsqu'ils seront activés pour les audioconférences ou lorsque le code confidentiel sera réinitialisé. Si vous avez désactivé l’envoi automatique de courriers électroniques, aucun message de réinitialisation du code confidentiel ne sera envoyé à l’utilisateur, ce qui vous obligera à réinitialiser manuellement le code confidentiel.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Par défaut, les appelants anonymes ne peuvent pas commencer une réunion.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, par défaut, un message électronique lui est envoyé incluant les informations de conférence et son code confidentiel. L’utilisateur doit posséder une boîte aux lettres Office 365, car lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel est envoyé à l’utilisateur dans un courrier électronique à l’adresse SMTP principale (alias) qui lui est associée.
    
- Lorsque vous configurez les audioconférences, vous définissez les codes confidentiels numériques de votre entreprise. Les codes confidentiels peuvent contenir de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur du code confidentiel, celui-ci s’applique uniquement aux nouveaux codes confidentiels générés et ne s’applique pas au paramètre de code confidentiel des utilisateurs déjà activés pour les audioconférences. Reportez-vous à la rubrique [Définir la longueur du code confidentiel pour les réunions en audioconférence](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Le courrier électronique par défaut est l’adresse SMTP principale Office 365 de l’utilisateur. Vous pouvez envoyer un message électronique à une adresse non Office 365 telle que Hotmail ou MSN. Vous pouvez changer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.
    
- Pour remplacer l’adresse par défaut de l’utilisateur à laquelle le courrier électronique est envoyé, l’administrateur du client peut utiliser le cmdlet suivant : Set-CsOnlineDialInConferencingUser -amos.marble -ResetLeaderPIN -SendEmail -SendEmailToAddress "u@hotmail.com". Le paramètre SendEmail est obligatoire pour le changement de l’adresse électronique de l’utilisateur.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Vous pouvez définir le code confidentiel pour Amos Marbel en exécutant :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à la seule utilisation du centre d’administration Office 365, par exemple lorsque vous faites des modifications de paramètres pour beaucoup d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md)
