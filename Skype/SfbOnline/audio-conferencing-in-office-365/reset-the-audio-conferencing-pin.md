---
title: Réinitialiser le code confidentiel de conférence Audio
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez ce que vous devez savoir sur les codes confidentiels et comment les réinitialiser. '
ms.openlocfilehash: 956c8e1ec7a83832c9aa2605845bc7fd42a047f7
ms.sourcegitcommit: 9d816453083c26fd24f8a1cdc0f53f3d218c43b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2018
---
# <a name="reset-the-audio-conferencing-pin"></a>Réinitialiser le code confidentiel de conférence Audio

Un code confidentiel est un code constitué de numéros sont créées pour chaque Skype pour professionnels et Microsoft Teams utilisateur qui est activé pour l’audioconférence. Codes confidentiels de conférence audio sont utilisés par les organisateurs de réunion pour identifier qu’ils sont l’organisateur de la réunion et de démarrer une réunion par téléphone. S’ils utilisent le Skype pour l’application Microsoft Teams ou de l’entreprise pour démarrer la réunion, un code confidentiel n’est pas obligatoire. Si les utilisateurs oublient leur code confidentiel et qu’ils ne peut pas trouver dans le courrier électronique qui a été envoyé lorsqu’ils ont été activés pour l’audioconférence, un administrateur peut réinitialiser leur code confidentiel, ou ils peuvent réinitialiser leur propre code confidentiel.
  
Réunions peuvent être démarrées lorsqu’un utilisateur authentifié est ajouté à l’aide d’un Skype pour l’application Microsoft Teams ou de l’entreprise ou lorsque l’organisateur de jointures avec son code confidentiel par téléphone. Si la réunion nécessite un code confidentiel pour commencer, par défaut, tous les utilisateurs qui rejoignent la réunion par téléphone avant le début de la réunion seront mis en attente jusqu'à ce que la réunion commence. Si l'organisateur d'une réunion n'impose pas de code confidentiel pour commencer la réunion par téléphone, un appelant qui tente de participer n'est pas invité à indiquer un code confidentiel.
  
## <a name="reset-a-users-pin"></a>Réinitialiser le code confidentiel d’un utilisateur

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Dans la navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. **Conférence Audio**, cliquez sur **Réinitialiser le code confidentiel**.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png)  **à l’aide de la Skype entreprise centre d’administration**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Accéder au **Centre d’administration Office 365** > **Skype pour les entreprises**, dans la navigation de gauche, cliquez sur **conférence Audio**.
    
3. Cliquez sur **utilisateurs**, sélectionnez l’utilisateur que vous souhaitez réinitialiser le code confidentiel pour.
    
4. Dans le volet Actions, sous **code confidentiel**, cliquez sur **Réinitialiser**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Ont un utilisateur à réinitialiser son propre code confidentiel

![les équipes-logo-30x30.png](../images/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Demandez à l’utilisateur d’accéder à [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).
2. Cliquez sur **Réinitialiser le code confidentiel**. 

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png)  **à l’aide de la Skype entreprise centre d’administration**

Un utilisateur peut réinitialiser un code confidentiel à l’aide de l’option **Réinitialiser le code confidentiel** dans la page **conférence rendez-vous** . Cette page est accessible dans une des trois manières :

* Dans un navigateur, accédez à [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).
* Dans Skype pour les entreprises, cliquez sur la flèche **Afficher le Menu** en regard de **Options**, puis cliquez sur **Outils** > **Paramètres de conférence rendez-vous**.
* Dans Skype pour les entreprises, cliquez sur **Options**, cliquez sur **Transfert d’appel** dans le menu de gauche, puis, dans la section **Paramètres supplémentaires d’appel** , cliquez sur **Modifier les paramètres en ligne**. 

## <a name="what-else-should-you-know-about-pins"></a>Que devez-vous savoir d'autre sur les codes confidentiels ?

- Pour des raisons de sécurité, le code confidentiel n'est affiché qu'une fois à l'administrateur lors de la réinitialisation du code confidentiel. Une fois que le code confidentiel est réinitialisé par un administrateur, le code confidentiel est répertorié comme *** dans le **Skype entreprise centre d’administration** et dans les résultats lorsqu’ils utilisent Get-CsCsOnlineDialInConfencingUser dans Windows PowerShell.
    
- Envoyer automatiquement des messages électroniques aux utilisateurs est activée par défaut, et les utilisateurs reçoivent un message électronique avec leur code confidentiel lorsqu’elles sont activées pour les services d’audioconférence ou lorsque le code confidentiel est réinitialisé. Mais si vous avez désactivé automatiquement l’envoi d’e-mails, un message électronique de réinitialisation du code confidentiel ne seront pas envoyé à un utilisateur et vous devez envoyer manuellement les informations de code confidentiel à l’utilisateur.
    
- Lorsqu'une réunion commence, tous les utilisateurs qui se trouvent dans la salle d'attente participent automatiquement à l'événement. Par exemple, si deux participants tentent de participer à une réunion avant qu'elle ait commencé, ils sont placés dans la salle d'attente et entendent de la musique pour patienter. Lorsque l'organisateur saisit son code confidentiel sur le clavier du téléphone, il commence la réunion, ce qui permet aux utilisateurs jusqu'alors en salle d'attente d'y participer.
    
- Le paramètre par défaut n’autorise ne pas une réunion doit être démarré par les appelants anonymes.
    
- Lorsque vous activez un utilisateur pour l’audioconférence, par défaut, ils sont envoyés les messages électroniques qui incluent des informations de conférence et de leur code confidentiel. L’utilisateur doit avoir une boîte aux lettres Office 365, étant donné que lorsqu’un code confidentiel est réinitialisé, un nouveau code confidentiel sera envoyé à l’utilisateur dans le message électronique à leur adresse SMTP principale (alias) est définie pour l’utilisateur.
    
- Lorsque vous configurez les services d’audioconférence, vous définissez les chiffres qui sont requis pour les codes confidentiels dans votre organisation. Les codes confidentiels peuvent contenir de 4 à 12 chiffres, la valeur par défaut étant 5. Si vous modifiez le paramètre de longueur de code confidentiel, le paramètre est appliqué uniquement sur les codes confidentiels nouvellement créés et n’est pas appliqué au paramètre code confidentiel pour les utilisateurs existants qui sont activées pour l’audioconférence. Voir [définir la longueur de l’axe des réunions de conférence Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).
    
- Le courrier électronique par défaut est fixé à l’adresse SMTP principale d’Office 365 de l’utilisateur. Vous pouvez envoyer un message électronique à une adresse non Office 365 tels que Hotmail ou MSN. Vous pouvez substituer l’adresse de messagerie par défaut à l’aide de Windows PowerShell. Cela est utile si les utilisateurs ne disposent pas d'une boîte aux lettres Exchange dans Office 365.
    
- Pour remplacer l’adresse d’utilisateur par défaut où le courrier électronique est envoyé, l’administrateur du client peut utiliser l’applet de commande suivante : Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress « u@hotmail.com ». Le paramètre SendEmail est requise pour substituer l’adresse de messagerie de l’utilisateur.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Pour gagner du temps ou automatiser ce processus, vous pouvez utiliser l'applet de commande [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Vous pouvez définir le code confidentiel pour Amos Marbel en exécutant :
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous modifiez les paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md)
