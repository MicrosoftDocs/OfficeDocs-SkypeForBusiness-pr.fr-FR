---
title: Messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'En savoir plus sur les informations est envoyé automatiquement aux utilisateurs par courrier électronique lors de la modification de leurs paramètres de conférence rendez-vous dans Microsoft Teams. '
ms.openlocfilehash: f351f7a1107c3f52ddc2c9f60b7cd79feb31388c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890061"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Messages électroniques envoyés aux utilisateurs lorsque les paramètres changent dans Microsoft Teams

Les messages électroniques seront automatiquement envoyés aux utilisateurs qui sont [activés pour la conférence Audio](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) à l’aide de Microsoft en tant que le fournisseur de services d’audioconférence.
  
Par défaut, il existe quatre types de courrier électronique qui sera envoyé à vos utilisateurs activés pour une audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. Services d’audioconférence dans Office 365 sera envoyer un message électronique à vos utilisateurs de messagerie lorsque :
  
- **Une licence de conférence Audio est attribuée à leur ou lorsque vous passez le fournisseur de services d’audioconférence à Microsoft.**
    
     Ce message électronique inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, les services d’audioconférence code confidentiel pour l’utilisateur et les instructions et lien à utiliser le Skype pour Business Online Meeting outil mises à jour qui sert à mettre à jour des réunions existantes pour le utilisateur. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft licences](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [Affecter de Microsoft en tant que le fournisseur de services d’audioconférence](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [ID de conférence Audio dynamiques dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Skype for Business Verify License](media/audio-conferencing-user-enabled.png)
  
    Vous trouverez plus d’informations sur la gestion des licences en consultant la rubrique [Skype pour les licences d’entreprise et les équipes Microsoft module complémentaire](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**
    
    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Mais ce message n’inclut pas les services d’audioconférence son code confidentiel. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](media/audio-conferencing-info-change.png)
  
- **Le code confidentiel d’un utilisateur de conférence audio est réinitialisé.**
    
    Ce message électronique contient le code confidentiel de conférence audio de l’organisateur, l’ID de conférence existante et numéro de téléphone de conférence par défaut pour l’utilisateur. Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](media/audio-conferencing-pin-has-changed.png)
  
- **Licence d’un utilisateur est supprimée ou lorsque le fournisseur de services d’audioconférence modifié à partir de Microsoft à un autre fournisseur ou aucun.**
    
    Cela se produit lorsque la licence de **Conférence Audio** est supprimée à partir d’un utilisateur ou lors de la modification d’un utilisateur, le fournisseur de services d’audioconférence de Microsoft à un fournisseur de services d’audioconférence tiers ou lors de la définition du fournisseur sur **None**. Ce message électronique contient les instructions et les informations de l’utilisateur à utiliser le Skype pour l’outil de mise à jour de réunion en ligne Business pour supprimer des informations de conférence audio spécifiques, telles que la valeur par défaut ID de conférence téléphone nombre ou une conférence.
    
    Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez modifier le message électronique qui est envoyé automatiquement aux utilisateurs, y compris l’adresse de messagerie et le nom complet qui est inclus dans les informations de contact *à partir de* . Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et affiche le nom de l’aide de Windows PowerShell. Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de conférence, par défaut le numéro de téléphone de conférence et, plus important, leur code confidentiel de conférence audio ne seront pas envoyée à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.
  
Par défaut, les messages électroniques sont envoyés à vos utilisateurs, mais si vous souhaitez empêcher leur réception de courrier électronique pour les conférences audio, vous pouvez utiliser Microsoft Teams ou Windows PowerShell. 

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide les équipes Microsoft Skype entreprise centre d’administration**

1. Dans la navigation de gauche, accédez à des **réunions** > **Ponts de conférence**. 

2. En haut de la page de **Ponts de conférence** , cliquez sur **paramètres du pont**. 

3. Dans le volet **paramètres du pont** , activez ou désactivez **Envoyer automatiquement des messages électroniques aux utilisateurs si leurs paramètres de connexion à modifient**.

4. Cliquez sur **Enregistrer**.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
**Utilisation de Windows PowerShell**
  
Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et affiche le nom de l’aide de Windows PowerShell. 

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Pour plus d’informations sur Windows PowerShell, voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  
  
## <a name="related-topics"></a>Rubriques connexes

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)
  
[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
