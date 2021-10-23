---
title: Messages électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Découvrez quelles informations sont envoyées automatiquement aux utilisateurs par courrier électronique en cas de modification de leurs paramètres de conférence Microsoft Teams. '
ms.openlocfilehash: ad61f7886d5a71fb8753b887ebfd6cd90f4f6a82
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536475"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams

Les messages électroniques seront automatiquement envoyés aux utilisateurs activés pour l’audioconférence en utilisant Microsoft comme fournisseur de services d’audioconférence. [](set-up-audio-conferencing-in-teams.md)

Par défaut, quatre types de messages électroniques sont envoyés aux utilisateurs activés pour l’audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. L’audioconférence dans Microsoft 365 ou Office 365 permet d’envoyer un courrier électronique à vos utilisateurs dans les cas ci-après :

- **Une licence d’audioconférence leur est affectée ou lorsque vous changez le fournisseur de services d’audioconférence en Microsoft.**

     Ce message électronique inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, le code confidentiel de l’audioconférence pour l’utilisateur, ainsi que les instructions et le lien de l’outil de mise à jour des réunions en ligne Skype Entreprise pour l’utilisateur. Consultez [Affecter Microsoft Teams licences de modules add-on ou](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) Affecter Microsoft comme fournisseur de services [d’audioconférence.](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)

    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) 

    Voici un exemple de ce courrier électronique :

     ![Skype Entreprise Vérifier la licence.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Pour en savoir plus sur les licences, voir [Microsoft Teams de modules add-on.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**

    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Toutefois, cet e-mail n’inclut pas le code confidentiel de l’utilisateur pour l’audioconférence. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).

    Voici un exemple de ce courrier électronique :

     ![Les informations de la conférence rendez-vous ont été modifiées.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Réinitialisation du code confidentiel de conférence audio d’un utilisateur.**

    Ce courrier électronique contient le code confidentiel de l’audioconférence de l’organisateur, l’ID de conférence existant et le numéro de téléphone par défaut de l’utilisateur. Consultez [réinitialiser le code confidentiel de l’audioconférence.](reset-the-audio-conferencing-pin-in-teams.md)
    
     Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **La licence d’un utilisateur est supprimée ou lorsque le fournisseur de services d’audioconférence passe de Microsoft à un autre fournisseur ou à Aucun.**

    Cela se produit lorsque la licence Audioconférence est supprimée d’un utilisateur ou lorsque vous attribuez au fournisseur de services d’audioconférence la définition **sur Aucun.** 

    Consultez [Attribuer ou supprimer des licences pour Microsoft 365 entreprise.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    Voici un exemple de ce courrier électronique :

     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez apporter des modifications aux messages électroniques envoyés automatiquement aux utilisateurs. Par défaut, l’expéditeur des courriers électroniques est de Microsoft 365 ou Office 365, mais vous pouvez modifier le nom d’affichage à l’aide de Windows PowerShell. Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de conférence, le numéro de téléphone de conférence par défaut et, plus important, le code confidentiel de conférence audio ne sont pas envoyés à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.

Par défaut, des courriers électroniques sont envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu’ils en reçoivent pour l’audioconférence, vous pouvez utiliser Microsoft Teams ou Windows PowerShell. 

 **Utiliser le centre d’administration Microsoft Teams**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page Ponts **de** conférence, cliquez sur **Paramètres du pont.** 

3. Dans le **volet Paramètres du** pont, activez ou désactivez automatiquement l’envoi de courriers électroniques aux utilisateurs en cas de modification de **leurs paramètres de connexion.**

4. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

Vous pouvez également utiliser le module Microsoft Teams PowerShell et exécuter :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

Pour plus [d’informations, Microsoft Teams la référence PowerShell.](/powershell/module/teams/?view=teams-ps)

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Par défaut, l’expéditeur des courriers électroniques est de Microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell. 

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Rubriques connexes

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
