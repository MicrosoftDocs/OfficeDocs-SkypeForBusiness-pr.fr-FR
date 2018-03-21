---
title: "E-mails envoyés aux utilisateurs lors de la modifient de leurs paramètres"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: ccc95e8cee5f4db1729423bc7a1bccecf87ac121
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>E-mails envoyés aux utilisateurs lors de la modifient de leurs paramètres

E-mails seront automatiquement envoyées aux utilisateurs qui sont [activés pour la conférence Audio](set-up-audio-conferencing.md) à l’aide de Microsoft en tant que le fournisseur de conférence audio.
  
Par défaut, il existe quatre types de courrier électronique qui sera envoyé aux utilisateurs qui sont activés pour l’audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. Conférence audio dans Office 365 enverra un courriel à vos utilisateurs de messagerie lorsque :
  
- **Une licence de conférence Audio est affectée ou lorsque vous modifiez le fournisseur de conférence audio à Microsoft.**
    
     Ce message électronique inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, la conférence audio de code PIN pour l’utilisateur et les instructions et lien à utiliser le Skype pour entreprise en ligne réunion mise à jour outil qui sert à mettre à jour des réunions existantes pour le utilisateur. Consultez [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [Affecter de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [codes dynamiques d’audioconférence de votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Skype for Business Verify License](../images/audio-conferencing-user-enabled.png)
  
    Vous trouverez plus d’informations sur Skype pour les licences d’entreprise voir [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**
    
    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Mais cet e-mail n’inclut pas de conférence code PIN de l’utilisateur. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [codes dynamiques d’audioconférence de votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](../images/audio-conferencing-info-change.png)
  
- **La conférence audio code PIN d’un utilisateur est réinitialisée.**
    
    Cet e-mail contient conférence téléphonique l’organisateur de la PIN, ID de conférence existante et numéro de téléphone de conférence par défaut pour l’utilisateur. Reportez-vous à la rubrique [Réinitialiser le code confidentiel conférence Audio pour un utilisateur](reset-the-audio-conferencing-pin-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez définir des [codes dynamiques d’audioconférence de votre organisation](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](../images/audio-conferencing-pin-has-changed.png)
  
- **Licence d’un utilisateur est supprimée ou lorsque le fournisseur de conférence audio remplace Microsoft autre fournisseur ou aucun.**
    
    Cela se produit lorsque la licence de **Conférence Audio** est supprimée d’un utilisateur ou lors de la modification d’un utilisateur, le fournisseur de conférence audio de Microsoft pour un fournisseur de conférence audio de tiers ou lors de la définition du fournisseur sur **Aucun**. Cet e-mail contient des instructions et des informations pour l’utilisateur d’utiliser le Skype pour l’outil de mise à jour de réunion en ligne Professionnel pour supprimer des informations spécifiques de conférence audio, comme le code par défaut conférence téléphonique numéro ou une conférence.
    
    Voir [attribuer ou supprimer des licences pour Office 365 pour professionnels](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc) ou [affecter un tiers que le fournisseur de conférence audio](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez apporter des modifications à l’e-mail est automatiquement envoyé aux utilisateurs, y compris l’adresse de messagerie et le nom complet est inclus dans les informations de contact *à partir de* . Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell et l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :
  
- entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- Définissez le paramètre _SendEmailOverride_ sur _True_.
    
Vous pouvez apporter des modifications à l’e-mail envoyé aux utilisateurs, telles que l’adresse e-mail que le courrier électronique est envoyé à partir d’et le nom complet de l’e-mail, en exécutant :
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si vous souhaitez modifier les informations d’adresse de messagerie, vous avez besoin pour vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les e-mails provenant de personnalisé spécifié à partir de l’adresse. Si vous décidez de remplacer les informations *de* contact, vous devez vérifier que les messages électroniques sont correctement envoyés aux utilisateurs. Pour cela, vous pouvez ce test avec un utilisateur de votre organisation.
  
Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de la conférence, par défaut le numéro de téléphone de conférence et, plus important encore, leur code PIN de conférence audio ne seront pas envoyée à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.
  
Par défaut, e-mail sera envoyé à vos utilisateurs, mais si vous voulez les empêcher la réception de courrier électronique pour les conférences audio, vous pouvez utiliser le Skype pour le centre d’administration Business ou Windows PowerShell. 
  
 Le Centre d'administration Skype Entreprise ou Windows PowerShell permet d'activer ou de désactiver l'envoi de courrier électronique aux utilisateurs.
  
1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
2. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.
    
3. Dans le **Skype pour le centre d’administration commerciale**, dans la navigation de gauche, accédez à **audioconférence** > **paramètres de pont de Microsoft**.
    
4. Dans la page **paramètres du pont Microsoft** , activez ou désactivez la **Envoyer automatiquement des e-mails aux utilisateurs si leurs paramètres de conférence audio changent**. 
    
5. Cliquez sur **Enregistrer**. 
    
 Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.
  
1. Pour désactiver l'envoi de courrier électronique à tous vos utilisateurs, exécutez la commande suivante :
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Si vous souhaitez modifier les informations de l'adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre entreprise autorisent les messages électroniques provenant de l'adresse électronique personnalisée.
  
## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Pour plus d'informations sur l'activation et la désactivation automatiques de l'envoi de courriers électroniques à vos utilisateurs, reportez-vous à la rubrique [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Parfois, les utilisateurs perdent leurs informations audio et vous devez être en mesure de les envoyer toutes leurs informations audio pour les. Vous pouvez effectuer cette opération en cliquant sur **Envoyer par courrier électronique, les informations de conférence** sous les propriétés de téléconférence audio pour un utilisateur utilisant le Skype pour le centre d’administration de Business. Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md). Toutefois, ces informations n’incluent pas la code PIN de conférence audio.
    
    Voici un exemple du courrier électronique qui sera envoyé aux utilisateurs :
    
     ![Courrier électronique de conférence rendez-vous](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Par défaut, l’expéditeur des e-mails sera d’Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom complet à l’aide de Windows PowerShell et l’applet de commande [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :
    
  - [Six raisons d'utiliser Windows PowerShell pour gérer Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell offre de nombreux avantages de vitesse, de simplicité et de productivité, plutôt seulement le centre d’administration d’Office 365, par exemple lorsque vous devez apporter des modifications de paramètre pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Rubriques connexes

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)

