---
title: Messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans Skype pour Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'En savoir plus sur les informations est envoyé automatiquement aux utilisateurs par courrier électronique lorsque leurs paramètres de conférence rendez-vous modifier dans Skype pour Business Online. '
ms.openlocfilehash: f3b4a530e204524dcf183ac671124c6d6ff8df03
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32230903"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans Skype pour Business Online

> [!Note]
> Si vous recherchez des informations de courrier électronique automatique dans Microsoft Teams, consultez [les messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans les équipes Microsoft](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

Les messages électroniques seront automatiquement envoyés aux utilisateurs qui sont [activés pour la conférence Audio](set-up-audio-conferencing.md) à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence.
  
Par défaut, il existe quatre types de courrier électronique qui sera envoyé à vos utilisateurs activés pour une audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. Services d’audioconférence dans Office 365 sera envoyer un message électronique à vos utilisateurs de messagerie lorsque :
  
- **Une licence de conférence Audio est attribuée à leur ou lorsque vous passez le fournisseur de services d’audioconférence à Microsoft.**
    
     Ce message électronique inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, les services d’audioconférence code confidentiel pour l’utilisateur et les instructions et lien à utiliser le Skype pour Business Online Meeting outil mises à jour qui sert à mettre à jour des réunions existantes pour le utilisateur. Voir [Assigner de Skype pour les licences d’entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [Affecter de Microsoft en tant que le fournisseur de services d’audioconférence](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [ID de conférence Audio dynamiques dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Pour plus d'informations sur l'affectation de licences Skype Entreprise, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**
    
    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Mais ce message n’inclut pas les services d’audioconférence son code confidentiel. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [ID de conférence Audio dynamiques dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](../images/audio-conferencing-info-change.png)
  
- **Le code confidentiel d’un utilisateur de conférence audio est réinitialisé.**
    
    Ce message électronique contient le code confidentiel de conférence audio de l’organisateur, l’ID de conférence existante et numéro de téléphone de conférence par défaut pour l’utilisateur. Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [ID de conférence Audio dynamiques dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](../images/audio-conferencing-pin-has-changed.png)
  
- **Licence d’un utilisateur est supprimée ou lorsque le fournisseur de services d’audioconférence modifié à partir de Microsoft à un autre fournisseur ou aucun.**
    
    Cela se produit lorsque la licence de **Conférence Audio** est supprimée à partir d’un utilisateur ou lors de la modification d’un utilisateur, le fournisseur de services d’audioconférence de Microsoft à un fournisseur de services d’audioconférence tiers ou lors de la définition du fournisseur sur **None**. Ce message électronique contient les instructions et les informations de l’utilisateur à utiliser le Skype pour l’outil de mise à jour de réunion en ligne Business pour supprimer des informations de conférence audio spécifiques, telles que la valeur par défaut ID de conférence téléphone nombre ou une conférence.
    
    Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez modifier le message électronique qui est envoyé automatiquement aux utilisateurs, y compris l’adresse de messagerie et le nom complet qui est inclus dans les informations de contact *à partir de* . Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell et l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :
  
- entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- Définissez le paramètre _SendEmailOverride_ sur _True_.
    
Vous pouvez modifier le message électronique envoyé aux utilisateurs, telles que l’adresse de messagerie, le courrier électronique est envoyé à partir d’et le nom complet pour le courrier électronique, en exécutant :
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si vous souhaitez modifier les informations d’adresse de messagerie, vous devez vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les messages électroniques qui proviennent de personnalisé d’adresse spécifié. Si vous décidez de remplacer les informations *de* contact, vous devez vérifier que les messages électroniques sont correctement envoyés aux utilisateurs. Pour cela, ce test avec un seul utilisateur dans votre organisation.
  
Vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer les autres paramètres pour votre organisation, y compris le courrier électronique.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de conférence, par défaut le numéro de téléphone de conférence et, plus important, leur code confidentiel de conférence audio ne seront pas envoyée à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.
  
Par défaut, les messages électroniques sont envoyés à vos utilisateurs, mais si vous souhaitez empêcher leur réception de courrier électronique pour les conférences audio, vous pouvez utiliser la Skype pour le centre d’administration Business ou Windows PowerShell. 
 
![SFB-logo-30x30.png](../images/sfb-logo-30x30.png)  **à l’aide de la Skype entreprise centre d’administration**
    
1. Dans la **Skype entreprise centre d’administration**, dans la navigation de gauche, accédez à la **conférence Audio** > **paramètres de pont de Microsoft**.
    
2. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si modifient leurs paramètres de conférence audio**. 
    
3. Cliquez sur **Enregistrer**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
1. Pour désactiver l'envoi de courrier électronique à tous vos utilisateurs, exécutez la commande suivante :
    
   ```
   Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
   ```

Vous pouvez utiliser l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer les autres paramètres pour votre organisation, y compris le courrier électronique.
  
## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Pour plus d'informations sur l'activation et la désactivation automatiques de l'envoi de courriers électroniques à vos utilisateurs, reportez-vous à la rubrique [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Parfois, les utilisateurs perdent leurs informations audio et vous devez être en mesure de les envoyer toutes leurs informations audio leur. Vous pouvez procéder à l’aide de la Skype entreprise centre d’administration et cliquez sur **Envoyer les informations de conférence par courrier électronique** sous les propriétés de services d’audioconférence pour un utilisateur. Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md). Toutefois, ces informations n’inclut pas le code confidentiel de conférence audio.
    
    Voici un exemple du courrier électronique qui sera envoyé aux utilisateurs :
    
     ![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell et l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell présente de nombreux avantages dans vitesse, la simplicité et la productivité sur qu’à l’aide du centre d’administration Office 365, tels que lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Voir aussi

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
