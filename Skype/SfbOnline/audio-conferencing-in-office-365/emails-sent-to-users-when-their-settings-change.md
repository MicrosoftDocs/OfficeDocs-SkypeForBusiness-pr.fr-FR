---
title: Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres changent dans Skype Entreprise Online
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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez quelles informations sont envoyées automatiquement aux utilisateurs par courrier électronique en cas de modification de leurs paramètres de conférences Skype Entreprise Online. '
ms.openlocfilehash: b33fc6176d4103125432ebe0896ccab34e8fe269
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728033"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres changent dans Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Si vous recherchez des informations de messagerie automatique dans Microsoft Teams, voir Courriers électroniques envoyés aux utilisateurs lorsque leurs paramètres changent [dans Microsoft Teams.](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams)

Les messages électroniques seront automatiquement envoyés aux utilisateurs activés pour l’audioconférence en utilisant Microsoft comme fournisseur de services d’audioconférence. [](set-up-audio-conferencing.md)
  
Par défaut, quatre types de messages électroniques sont envoyés aux utilisateurs activés pour l’audioconférence. Toutefois, si vous voulez limiter le nombre de messages électroniques envoyés aux utilisateurs, vous pouvez désactiver cette option. L’audioconférence dans Microsoft 365 ou Office 365 permet d’envoyer un courrier électronique à vos utilisateurs dans les cas ci-après :
  
- **Une licence d’audioconférence leur est affectée ou lorsque vous changez le fournisseur de services d’audioconférence en Microsoft.**
    
     Ce message électronique inclut l’ID de conférence, le numéro de téléphone de conférence par défaut pour les réunions, le code confidentiel de l’audioconférence pour l’utilisateur, ainsi que les instructions et le lien de l’outil de mise à jour des réunions en ligne Skype Entreprise pour l’utilisateur. Consultez [Attribuer Skype Entreprise licences d’accès](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [Affecter Microsoft comme fournisseur de services d’audioconférence.](assign-microsoft-as-the-audio-conferencing-provider.md)
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation.](./reset-a-conference-id-for-a-user.md) 
  
    Voici un exemple de ce courrier électronique :
    
     ![Skype Entreprise Vérifier la licence.](../images/audio-conferencing-user-enabled.png)
  
    Pour plus d'informations sur l'affectation de licences Skype Entreprise, reportez-vous à la rubrique [Licences de module complémentaire Skype Entreprise](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **L'ID de conférence ou le numéro de téléphone par défaut d'une conférence pour un utilisateur change.**
    
    Ce courrier électronique contient l'ID de conférence, le numéro d'accès à la conférence par défaut, ainsi que les instructions et le lien de l'outil de mise à jour de réunion de Skype Entreprise Online pour mettre à jour les réunions existantes de l'utilisateur. Toutefois, cet e-mail n’inclut pas le code confidentiel de l’utilisateur pour l’audioconférence. Reportez-vous à la rubrique [Réinitialiser l'ID de conférence d'un utilisateur](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation.](./reset-a-conference-id-for-a-user.md) 
  
    Voici un exemple de ce courrier électronique :
    
     ![Les informations de la conférence rendez-vous ont été modifiées.](../images/audio-conferencing-info-change.png)
  
- **Réinitialisation du code confidentiel de conférence audio d’un utilisateur.**
    
    Ce courrier électronique contient le code confidentiel de l’audioconférence de l’organisateur, l’ID de conférence existant et le numéro de téléphone par défaut de l’utilisateur. Consultez [réinitialiser le code confidentiel de l’audioconférence.](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > Si votre organisation a été activée pour les ID de conférence dynamiques, toutes les réunions d'un utilisateur planifiées auront un ID de conférence unique. Vous pouvez configurer des [ID dynamiques d’audioconférence dans votre organisation.](./reset-a-conference-id-for-a-user.md) 
  
    Voici un exemple de ce courrier électronique :
    
     ![Le code confidentiel de la conférence rendez-vous a été modifié.](../images/audio-conferencing-pin-has-changed.png)
  
- **La licence d’un utilisateur est supprimée ou lorsque le fournisseur de services d’audioconférence passe de Microsoft à un autre fournisseur ou à Aucun.**
    
    Cela se produit lorsque la licence **d’audioconférence** est supprimée d’un utilisateur, lorsque vous changez le fournisseur de services d’audioconférence d’un utilisateur de Microsoft en fournisseur de services d’audioconférence tiers ou lorsque le fournisseur est « Aucun **».** Ce courrier électronique contient les instructions et les informations permettant à l’utilisateur d’utiliser l’outil de mise à jour de réunion en ligne Skype Entreprise pour supprimer les informations spécifiques à l’audioconférence, telles que le numéro de téléphone de conférence par défaut ou l’ID de conférence.
    
    Voir [Attribuer ou supprimer des licences pour Applications Microsoft 365 pour les PME.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)
    
    Voici un exemple de ce courrier électronique :
    
     ![La fonctionnalité Conférence rendez-vous est désactivée.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Modifier les courriers électroniques qui leur sont envoyés

Vous pouvez apporter des modifications aux courriers électroniques envoyés automatiquement aux utilisateurs, dont l’adresse de messagerie et le nom d’affichage inclus dans les informations de *contact.* Par défaut, l’expéditeur des courriers électroniques est de Microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de la cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10)) Pour apporter des modifications à l’adresse de messagerie qui envoie le courrier électronique aux utilisateurs, vous devez :
  
- entrer l'adresse électronique dans le paramètre À _SendEmailFromAddress_;
    
- entrer le nom d'affichage associé à l'adresse électronique dans le paramètre  _SendEmailFromDisplayName_.
    
- Définissez _le paramètre SendEmailOverride_ sur _True._
    
Vous pouvez apporter des modifications aux courriers électroniques envoyés aux utilisateurs, comme l’adresse électronique d’envoi et le nom d’affichage de l’e-mail, en exécutant :
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si vous voulez modifier les informations de l’adresse électronique, vous devez vous assurer que les stratégies de courrier électronique entrant de votre environnement autorisent les courriers électroniques provenant de l’adresse personnalisée de l’adresse spécifiée. Si vous décidez de remplacer les informations de *contact* de, vous devez vérifier que les courriers électroniques sont envoyés correctement aux utilisateurs. Vous pouvez le faire en testant cela avec un utilisateur de votre organisation.
  
Vous pouvez utiliser l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) pour gérer d’autres paramètres de votre organisation, y compris le courrier électronique.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>Comment procéder si vous ne souhaitez pas leur envoyer de courriers électroniques ?

Lorsque vous désactivez l'envoi de courriers électroniques, le courrier électronique ne sera pas envoyé même si l'utilisateur dispose d'une licence. Dans ce cas, l’ID de conférence, le numéro de téléphone de conférence par défaut et, plus important, le code confidentiel de conférence audio ne sont pas envoyés à l’utilisateur. En pareil cas, vous devez en informer l'utilisateur en lui envoyant un courrier électronique distinct ou en l'appelant.
  
Par défaut, des courriers électroniques sont envoyés à vos utilisateurs, mais si vous ne souhaitez pas qu’ils en reçoivent pour l’audioconférence, vous pouvez utiliser le Centre d’administration Skype Entreprise ou Windows PowerShell. 
 
![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png)  **Utilisation du Skype Entreprise d’administration**
    
1. Dans le **Skype Entreprise d’administration,** dans le panneau de navigation de gauche, allez aux paramètres du pont Microsoft d’audioconférence.   >  
    
2. Dans la page **des paramètres** du pont Microsoft, sélectionnez ou sélectionnez Envoyer automatiquement des courriers électroniques aux utilisateurs en cas de modification de **leurs paramètres d’audioconférence.** 
    
3. Cliquez sur **Enregistrer**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**
  
1. Pour désactiver l'envoi de courrier électronique à tous vos utilisateurs, exécutez la commande suivante :
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

Vous pouvez utiliser l’cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) pour gérer d’autres paramètres de votre organisation, y compris le courrier électronique.
  
## <a name="what-else-should-you-know-about-this-email"></a>Que devez-vous savoir d'autre sur les courriers électroniques ?

- Pour plus d'informations sur l'activation et la désactivation automatiques de l'envoi de courriers électroniques à vos utilisateurs, reportez-vous à la rubrique [Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- Parfois, les utilisateurs perdent leurs informations audio et vous devez être en mesure de leur envoyer toutes leurs informations audio. Pour ce faire, utilisez le Centre d’administration  Skype Entreprise et cliquez sur Envoyer les informations sur la conférence par courrier électronique sous les propriétés de conférence audio d’un utilisateur. Reportez-vous à la rubrique [Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md). Cependant, ces informations n’incluent pas le code confidentiel de l’audioconférence.
    
    Voici un exemple du courrier électronique qui sera envoyé aux utilisateurs :
    
     ![Courrier électronique de conférences téléphoniques.](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Par défaut, l’expéditeur des courriers électroniques est de Microsoft 365 ou Office 365, mais vous pouvez modifier l’adresse de messagerie et le nom d’affichage à l’aide de Windows PowerShell et de la cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))
    
- Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :
    
  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes : 
    
  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > Le module Windows PowerShell pour Skype Entreprise Online permet de créer une session Windows PowerShell à distance qui se connecte à Skype Entreprise Online. Ce module est pris en charge uniquement sur les systèmes 64 bits. Il peut être téléchargé à partir du Centre de téléchargement Microsoft accessible à l'emplacement suivant : [Module Windows PowerShell pour Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Sujets associés

[Activer ou désactiver l'envoi de messages électroniques lorsque modifient les paramètres de conférence Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
