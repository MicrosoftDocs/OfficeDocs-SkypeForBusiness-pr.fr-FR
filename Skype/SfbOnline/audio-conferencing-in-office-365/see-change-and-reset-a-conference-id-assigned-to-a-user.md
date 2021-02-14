---
title: Consulter, modifier et réinitialiser un ID de conférence attribué à un utilisateur dans Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: 'Découvrez comment affecter un ID de conférence à un utilisateur dans Skype Entreprise Online et ce que doivent être les paramètres d’ID de conférence. '
ms.openlocfilehash: a8f0e64ef30e1e503a1e3b78c9823f5d115df837
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46643604"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur les ID de conférence utilisateur dans Microsoft Teams, consultez et réinitialisez un ID de conférence attribué à un [utilisateur dans Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Un ID de conférence est automatiquement attribué à un utilisateur Skype Entreprise lorsqu’il est configurer pour l’audioconférence dans Microsoft 365 ou Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence attribué est envoyé dans l’invitation à la réunion lorsque la réunion est programmée. Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique.

Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID. You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.

An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN. For more information about resetting a conference organizer's PIN, [go here](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l’ID de conférence

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Allez au Centre d'> **dans Skype Entreprise.**

3. Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.

4. Dans la page Action, affichez la section **ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message  électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur Envoyer les informations sur la conférence par courrier électronique après avoir sélectionné l’utilisateur dans la **page** Utilisateurs.

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

You can use Windows PowerShell to view the conference ID for a user. To do so, run:

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Pour en savoir plus sur l’cmdlet, voir [Get-CsOnlineDialInConferencingUser.](https://go.microsoft.com/fwlink/?LinkId=617693 )


### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l’ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.

![Icône affichant le logo Skype Entreprise](../images/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Allez au Centre d'> **dans Skype Entreprise.**

3. Dans le **Centre d’administration Skype** Entreprise Utilisateurs de l’audioconférence, dans le volet Action sous ID de >    >  conférence, cliquez sur  **Réinitialiser.**

4. Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

Vous pouvez réinitialiser l’ID de conférence d'un utilisateur à l’aide de Windows PowerShell. Pour ce faire, exécutez :

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois qu’un nouvel ID de conférence est créé ou réinitialisé, l’ancien ID de conférence ne peut pas être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser l’outil de migration de réunions Skype Entreprise pour mettre à jour leurs réunions existantes. Pour découvrir comment télécharger, installer et exécuter l’outil, consultez : Outil de mise à jour des réunions pour Skype Entreprise et [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype Entreprise Online, Outil de migration de réunions [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et Skype Entreprise Online, Outil de migration de réunions [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)

- Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio. Vous ne pouvez pas utiliser de caractères alphabéétiques ou spéciaux dans les ID de conférence. seuls des nombres peuvent être utilisés.

- L’ID de conférence de tous vos utilisateurs d’audioconférence aura neuf chiffres par défaut et le nombre de chiffres ne peut pas être modifié.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online depuis un seul point d’administration, ce qui simplifie votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Pourquoi utiliser Microsoft 365 ou PowerShell Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation du Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d’utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Sujets associés

[Essayer ou acheter l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

