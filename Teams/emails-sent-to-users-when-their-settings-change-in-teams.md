---
title: Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez quelles informations sont envoyées automatiquement aux utilisateurs par e-mail lorsque leurs paramètres d’audioconférence sont modifiés dans Microsoft Teams. '
ms.openlocfilehash: db9b2c2d99aad64bd9d607e5acbac99afc36d978
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754672"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams

Des courriers électroniques seront envoyés automatiquement aux utilisateurs qui lesquels [l’audioconférence est activée](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) et qui utilisent Microsoft comme fournisseur de service d’audioconférence.

Par défaut, quatre types de courriers électroniques seront envoyés à vos utilisateurs pour lesquels la fonction d’audioconférence est activée. Toutefois, si vous souhaitez imiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. La fonction d’audioconférence dans Office 365 enverra un courrier électronique à vos utilisateurs dans les cas suivants :

- **Une licence pour l’audioconférence leur est attribuée ou le fournisseur de service d’audioconférence est remplacé par Microsoft.**

     Ce courrier électronique contient l'ID de conférence, le numéro de téléphone d'accès par défaut aux réunions, le code confidentiel d’audioconférence attribué à l'utilisateur, ainsi que les instructions et le lien de l'outil de mise à jour des réunions Skype Entreprise Online existantes de l'utilisateur. Consultez la section [Attribuer des licences pour Skype Entreprise ou Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [Attribuer Microsoft comme fournisseur de service d’audioconférence](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

    > [!NOTE]
    > Si des ID de conférence dynamiques ont été activés pour votre organisation, toutes les réunions qu'un utilisateur planifie auront un ID de conférence unique. Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 

    Voici un exemple de ce courrier électronique :

     ![Vérifier la licence Skype Entreprise](media/audio-conferencing-user-enabled.png)

    Pour plus d'informations sur l'affectation de licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

- **L'ID de conférence ou le numéro de téléphone de conférence par défaut d’un utilisateur est modifié.**

    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Toutefois, il ne comporte pas le code confidentiel d’audioconférence de l'utilisateur. Reportez-vous à la section [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).

    Voici un exemple de ce courrier électronique :

     ![Les informations de conférence rendez-vous ont été modifiées.](media/audio-conferencing-info-change.png)

- **Le code confidentiel d’audioconférence d'un utilisateur est modifié.**

    Ce courrier électronique contient le code confidentiel d’audioconférence de l'organisateur, l'ID de conférence existant et le numéro d'accès par défaut pour l'utilisateur. Reportez-vous à la section [Réinitialiser le code confidentiel d'audioconférence](reset-the-audio-conferencing-pin-in-teams.md).
    
     Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel d’audioconférence a été modifiée.](media/audio-conferencing-pin-has-changed.png)
  
- **La licence d’un utilisateur est supprimée ou le fournisseur de service d’audioconférence Microsoft est remplacé par un autre fournisseur ou est défini sur Aucun.**

    Cela se produit lorsque la licence pour l’**audioconférence** d'un utilisateur est supprimée, lorsque vous remplacez le fournisseur de service d’audioconférence Microsoft d'un utilisateur par un fournisseur de service d'audioconférence tiers ou lorsque le fournisseur est défini sur **Aucun**. Ce courrier électronique contient les instructions et les informations nécessaires à l'utilisateur pour utiliser l'outil de mise à jour de réunion de Skype Entreprise Online pour supprimer les informations spécifiques à l’audioconférence, comme le numéro de téléphone de conférence par défaut ou l'ID de conférence.

    Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Voici un exemple de ce courrier électronique :

     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/audio-conferencing-turned-off.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez apporter des modifications aux courriers électroniques envoyés automatiquement à vos utilisateurs, dont l'adresse électronique et le nom d'affichage figurant dans les informations de contact *De*. Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell. Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques aux utilisateurs, le courrier électronique ne sera pas envoyé même si une licence est attribuée à l’utilisateur. Dans ce cas, l'ID de conférence, le numéro de téléphone d'accès par défaut à la conférence et, plus important, son code confidentiel d’audioconférence ne seront pas envoyés à l'utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.

Par défaut, des courriers électroniques seront envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu'ils en reçoivent pour l’audioconférence, vous pouvez utiliser Microsoft Teams ou Windows PowerShell. 

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la barre de navigation de gauche, accédez à **Réunions** > **Conference Bridges** (Ponts de conférence). 

2. En haut de la page **Conference Bridges** (Ponts de conférence), cliquez sur **Bridge Settings** (Paramètres du pont). 

3. Dans le volet **Bridge settings** (Paramètres du pont), activez ou désactivez l’option **Envoyer automatiquement un courrier électronique aux utilisateurs en cas de modification de leurs paramètres de numérotation**.

4. Cliquez sur **Enregistrer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Utiliser Windows PowerShell**

Pour des informations complémentaires, consultez la rubrique [Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Par défaut, l'envoi des courriers électroniques se fera à partir d'Office 365, mais vous pouvez modifier l'adresse électronique et le nom d'affichage à l'aide de Windows PowerShell. 

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Meilleurs moyens de gérer Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).


## <a name="related-topics"></a>Rubriques connexes

[Activer ou désactiver l'envoi de courriers électroniques lorsque les paramètres d’audioconférence sont modifiés](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
