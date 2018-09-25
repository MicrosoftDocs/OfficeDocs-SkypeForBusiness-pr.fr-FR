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
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016164"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres sont modifiés dans Microsoft Teams

Des courriers électroniques seront envoyés automatiquement aux utilisateurs qui lesquels [l’audioconférence est activée](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) et qui utilisent Microsoft comme fournisseur de service d’audioconférence.
  
Par défaut, il existe quatre types de courrier électronique qui sera envoyé à vos utilisateurs activés pour une audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. Services d’audioconférence dans Office 365 sera envoyer un message électronique à vos utilisateurs de messagerie lorsque :
  
- **Une licence pour l’audioconférence leur est attribuée ou le fournisseur de service d’audioconférence est remplacé par Microsoft.**
    
     Ce message électronique inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, les services d’audioconférence code confidentiel pour l’utilisateur et les instructions et lien à utiliser le Skype pour Business Online Meeting outil mises à jour qui sert à mettre à jour des réunions existantes pour le utilisateur. Voir [Assigner de Skype pour les professionnels et les équipes Microsoft licences](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [Affecter de Microsoft en tant que le fournisseur de services d’audioconférence](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [ID de conférence Audio dynamiques dans votre organisation](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Vérifier la licence Skype Entreprise](media/audio-conferencing-user-enabled.png)
  
    Pour plus d'informations sur l'affectation de licences, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
- **L'ID de conférence ou le numéro de téléphone de conférence par défaut d’un utilisateur est modifié.**
    
    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Mais ce message n’inclut pas les services d’audioconférence son code confidentiel. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de conférence rendez-vous ont été modifiées.](media/audio-conferencing-info-change.png)
  
- **Le code confidentiel d’audioconférence d'un utilisateur est modifié.**
    
    Ce message électronique contient le code confidentiel de conférence audio de l’organisateur, l’ID de conférence existante et numéro de téléphone de conférence par défaut pour l’utilisateur. Consultez la rubrique [Réinitialiser le code confidentiel de conférence Audio](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel d’audioconférence a été modifiée.](media/audio-conferencing-pin-has-changed.png)
  
- **La licence d’un utilisateur est supprimée ou le fournisseur de service d’audioconférence Microsoft est remplacé par un autre fournisseur ou est défini sur Aucun.**
    
    Cela se produit lorsque la licence de **Conférence Audio** est supprimée à partir d’un utilisateur ou lors de la modification d’un utilisateur, le fournisseur de services d’audioconférence de Microsoft à un fournisseur de services d’audioconférence tiers ou lors de la définition du fournisseur sur **None**. Ce message électronique contient les instructions et les informations de l’utilisateur à utiliser le Skype pour l’outil de mise à jour de réunion en ligne Business pour supprimer des informations de conférence audio spécifiques, telles que la valeur par défaut ID de conférence téléphone nombre ou une conférence.
    
    Consultez la rubrique [Attribuer ou supprimer des licences pour Office 365 pour les entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez modifier le message électronique qui est envoyé automatiquement aux utilisateurs, y compris l’adresse de messagerie et le nom complet qui est inclus dans les informations de contact *à partir de* . Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et affiche le nom de l’aide de Windows PowerShell. Voir la [référence PowerShell d’équipes Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) pour plus d’informations.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de conférence, par défaut le numéro de téléphone de conférence et, plus important, leur code confidentiel de conférence audio ne seront pas envoyée à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.
  
Par défaut, des courriers électroniques seront envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu'ils en reçoivent pour l’audioconférence, vous pouvez utiliser Microsoft Teams ou Windows PowerShell. 

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Utiliser le Centre d’Administration de Microsoft Teams et de Skype Entreprise :**

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
