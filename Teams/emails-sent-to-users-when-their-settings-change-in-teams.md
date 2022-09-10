---
title: Messages électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés
ms.author: heidip
author: MicrosoftHeidi
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
description: 'Découvrez les informations qui sont envoyées automatiquement aux utilisateurs par e-mail lorsque leurs paramètres de conférence rendez-vous changent dans Microsoft Teams. '
ms.openlocfilehash: b2ebb07562300a02058f3bfeaad103347299ba0c
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642135"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams

Les e-mails sont automatiquement envoyés aux utilisateurs [qui sont activés pour l’audioconférence](set-up-audio-conferencing-in-teams.md) à l’aide de Microsoft en tant que fournisseur d’audioconférence.

Par défaut, quatre types de courrier électronique sont envoyés à vos utilisateurs qui sont activés pour l’audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. L’audioconférence dans Microsoft 365 ou Office 365 envoie un e-mail à l’adresse e-mail de vos utilisateurs lorsque :

- **Une licence d’audioconférence leur est attribuée ou lorsque vous modifiez le fournisseur d’audioconférence en Microsoft.**

     Cet e-mail inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, le code confidentiel de l’audioconférence pour l’utilisateur, ainsi que les instructions et le lien permettant d’utiliser l’outil de mise à jour des réunions Teams utilisé pour mettre à jour les réunions existantes pour l’utilisateur. Voir [Attribuer des licences de module complémentaire Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Pour plus d’informations, consultez l’article [Afficher et réinitialiser un ID de conférence attribué à un utilisateur dans Microsoft Teams](see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams.md) .

    Voici un exemple de ce courrier électronique :

     ![Teams Verify License.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Pour en savoir plus sur les licences, consultez les [licences des modules complémentaires Microsoft Teams](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**

    Cet e-mail contient l’ID de conférence, le numéro de téléphone de conférence par défaut, ainsi que les instructions et le lien permettant d’utiliser l’outil de mise à jour des réunions Teams utilisé pour mettre à jour les réunions existantes pour l’utilisateur. Toutefois, cet e-mail n’inclut pas le code confidentiel d’audioconférence de l’utilisateur. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).

    Voici un exemple de ce courrier électronique :

     ![Les informations de la conférence rendez-vous ont été modifiées.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **Le code confidentiel de l’audioconférence d’un utilisateur est réinitialisé.**

    Cet e-mail contient le code confidentiel d’audioconférence de l’organisateur, l’ID de conférence existant et le numéro de téléphone de conférence par défaut de l’utilisateur. Voir [Réinitialiser le code confidentiel de l’audioconférence](reset-the-audio-conferencing-pin-in-teams.md).

     Voici un exemple de ce courrier électronique :

     ![Le code confidentiel de la conférence rendez-vous a été modifié.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **La licence d’un utilisateur est supprimée ou lorsque le fournisseur d’audioconférence passe de Microsoft à un autre fournisseur ou à Aucun.**

    Cela se produit lorsque la licence **d’audioconférence** est supprimée d’un utilisateur ou lorsque vous définissez le fournisseur d’audioconférence sur **Aucun**.

    Consultez [Attribuer ou supprimer des licences pour Microsoft 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Voici un exemple de ce courrier électronique :

     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez apporter des modifications à l’e-mail qui est automatiquement envoyé aux utilisateurs. Par défaut, l’expéditeur des e-mails sera microsoft 365 ou Office 365, mais vous pouvez modifier le nom complet à l’aide de Windows PowerShell. Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de conférence, le numéro de téléphone de conférence par défaut et, plus important encore, son code confidentiel d’audioconférence ne seront pas envoyés à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.

Par défaut, les e-mails sont envoyés à vos utilisateurs, mais si vous souhaitez les empêcher de recevoir des e-mails pour l’audioconférence, vous pouvez utiliser Microsoft Teams ou Windows PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence).

2. En haut de la page **Ponts de conférence** , cliquez sur **Paramètres du pont**.

3. Dans le volet **Paramètres du pont** , activez ou désactivez **l’envoi automatique d’e-mails aux utilisateurs si leurs paramètres de connexion changent**.

4. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Utilisation de Windows PowerShell

Vous pouvez également utiliser le module Microsoft Teams PowerShell et exécuter :

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Vous pouvez également utiliser Windows PowerShell et exécuter :[](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings)

Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Par défaut, l’expéditeur des e-mails sera microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse e-mail et le nom complet à l’aide de Windows PowerShell.

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Rubriques connexes

[Activer ou désactiver l’envoi de messages électroniques en cas de modification des paramètres d’audioconférence](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
