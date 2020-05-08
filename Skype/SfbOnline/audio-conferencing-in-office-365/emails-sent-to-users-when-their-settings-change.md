---
title: Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'En savoir plus sur les informations envoyées automatiquement aux utilisateurs par courrier électronique en cas de modification de leurs paramètres de conférence rendez-vous dans Skype entreprise online. '
ms.openlocfilehash: e2f58bfe582b7adc6672c06bec0e90571ff9a96a
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164273"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Courriers électroniques envoyés aux utilisateurs en cas de modification de leurs paramètres dans Skype entreprise Online

> [!Note]
> Si vous recherchez des informations de messagerie automatique dans Microsoft Teams, voir [messages électroniques envoyés aux utilisateurs lorsque leurs paramètres changent dans Microsoft teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

Des courriers électroniques seront automatiquement envoyés aux utilisateurs qui sont [activés pour les conférences audio](set-up-audio-conferencing.md) en utilisant Microsoft comme fournisseur de services d’audioconférence.
  
Par défaut, il existe quatre types de messages électroniques qui seront envoyés aux utilisateurs qui sont activés pour les conférences audio. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. L’audioconférence dans Microsoft 365 ou Office 365 envoie un message électronique aux messages électroniques de vos utilisateurs dans les cas suivants :
  
- **Une licence d’audioconférence lui est affectée ou lorsque vous modifiez le fournisseur de services d’audioconférence pour Microsoft.**
    
     Cet e-mail contient l’ID de conférence, le numéro de téléphone de la Conférence par défaut pour les réunions, le code confidentiel d’audioconférence pour l’utilisateur, ainsi que les instructions et le lien pour utiliser l’outil de mise à jour des réunions de Skype entreprise Online qui est utilisé pour mettre à jour les réunions existantes pour l’utilisateur. Consultez la rubrique [affectation de licences Skype entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [affectation de Microsoft en tant que fournisseur](assign-microsoft-as-the-audio-conferencing-provider.md)de services d’audioconférence.
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer les [ID dynamiques de l’audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Pour plus d'informations sur l'affectation de licences Skype Entreprise, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**
    
    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Mais ce message ne comprend pas le code confidentiel de l’audioconférence de l’utilisateur. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer les [ID dynamiques de l’audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](../images/audio-conferencing-info-change.png)
  
- **Le code confidentiel de conférence audio d’un utilisateur est réinitialisé.**
    
    Ce courrier électronique contient le code confidentiel d’audioconférence de l’organisateur, l’ID de conférence actuel et le numéro de téléphone de la Conférence par défaut de l’utilisateur. Voir [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer les [ID dynamiques de l’audioconférence dans votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](../images/audio-conferencing-pin-has-changed.png)
  
- **La licence d’un utilisateur est supprimée ou le fournisseur de services d’audioconférence passe de Microsoft à un autre fournisseur ou à aucun.**
    
    Cette situation se produit lorsque la licence de **conférence audio** est supprimée d’un utilisateur ou lorsque vous définissez un fournisseur de services d’audioconférence tiers pour un utilisateur ou un fournisseur de services d’audioconférence tiers ou lorsque vous définissez le fournisseur sur **aucun**. Ce courrier électronique contient les instructions et les informations nécessaires à l’utilisateur pour utiliser l’outil de mise à jour des réunions de Skype entreprise Online afin de supprimer les informations spécifiques aux services d’audioconférence, comme le numéro de téléphone de la Conférence par défaut ou l’ID de conférence.
    
    Voir [affecter ou supprimer des licences pour les applications Microsoft 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez modifier le message électronique qui est envoyé automatiquement aux utilisateurs, notamment l’adresse de courrier et le nom d’affichage qui est inclus dans les informations *de contact de* . Par défaut, l’expéditeur des messages électroniques provient de Microsoft 365 ou d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de l’applet [de passe Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Pour modifier l’adresse de messagerie qui envoie le message électronique aux utilisateurs, vous devez :
  
- entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- Définissez le paramètre _SendEmailOverride_ sur _true_.
    
Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, comme l’adresse électronique d’envoi du courrier électronique et le nom d’affichage pour le message électronique, en exécutant :
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si vous souhaitez modifier les informations de l’adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les messages électroniques provenant de l’adresse personnalisée de l’expéditeur spécifiée. Si vous décidez de remplacer les informations *de* contact, vous devez vérifier que les courriers électroniques sont correctement envoyés aux utilisateurs. Pour cela, vous pouvez le faire en test avec un seul utilisateur au sein de votre organisation.
  
Vous pouvez utiliser l’applet de cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d’autres paramètres de votre organisation, notamment la messagerie électronique.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans le cas présent, l’ID de conférence, le numéro de téléphone de l’audioconférence par défaut et, plus important encore, le code confidentiel de l’audioconférence ne sera pas envoyé à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.
  
Par défaut, les courriers électroniques seront envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu’ils en reçoivent pour les conférences audio, vous pouvez utiliser le centre d’administration Skype entreprise ou Windows PowerShell. 
 
![Icône illustrant le logo](../images/sfb-logo-30x30.png)Skype entreprise**dans le centre d’administration Skype entreprise**  
    
1. Dans le **Centre d’administration de Skype entreprise**, dans le volet de navigation gauche, accédez à**paramètres du pont Microsoft** **Conferencing** > .
    
2. Dans la page **paramètres du pont Microsoft** , activez ou désactivez **Envoyer automatiquement les messages électroniques aux utilisateurs en cas de modification de leurs paramètres de conférence audio**. 
    
3. Cliquez sur **Enregistrer**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
1. Pour désactiver l'envoi de courrier électronique à tous vos utilisateurs, exécutez la commande suivante :
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Vous pouvez utiliser l’applet de cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) pour gérer d’autres paramètres de votre organisation, notamment la messagerie électronique.
  
## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Pour plus d'informations sur l'activation et la désactivation automatiques de l'envoi de courriers électroniques à vos utilisateurs, reportez-vous à la rubrique [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Parfois, les utilisateurs perdent leurs informations audio et vous devez être en mesure de leur envoyer des informations audio. Pour cela, vous pouvez utiliser le centre d’administration Skype entreprise et cliquer sur **Envoyer les informations sur la Conférence par courrier électronique** sous les propriétés de l’audioconférence pour un utilisateur. Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md). Toutefois, ces informations n’incluent pas le code confidentiel de l’audioconférence.
    
    Voici un exemple du courrier électronique qui sera envoyé aux utilisateurs :
    
     ![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Par défaut, l’expéditeur des messages électroniques provient de Microsoft 365 ou d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de l’applet [de passe Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Windows PowerShell vous permet de gérer Microsoft 365 ou Office 365 à l’aide d’un point d’administration unique qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Raisons pour lesquelles vous avez besoin d’utiliser Microsoft 365 ou Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell dispose de nombreux avantages de la vitesse, de la simplicité et de la productivité par le biais du centre d’administration Microsoft 365, par exemple, lorsque vous apportez des modifications à un grand nombre d’utilisateurs à la fois. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Voir aussi

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
