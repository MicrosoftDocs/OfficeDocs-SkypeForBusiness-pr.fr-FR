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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Découvrez comment affecter un ID de conférence à un utilisateur dans Skype Entreprise Online et ce que doivent être les paramètres d’ID de conférence. '
ms.openlocfilehash: a400536050ea22d4f841e3b401e30c3c14729093
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728003"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Pour plus d’informations sur les ID de conférence utilisateur dans Microsoft Teams, consultez l’affichage et réinitialisez un ID de conférence attribué à un utilisateur [dans Microsoft Teams.](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams)

Un ID de conférence est automatiquement attribué à un utilisateur de Skype Entreprise lorsqu’il est prêt pour l’audioconférence dans Microsoft 365 ou Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence attribué est envoyé dans l’invitation à la réunion lorsque la réunion est programmée. Chaque réunion qu’un utilisateur planifiera se voit attribuer un ID de conférence unique.

Bien qu’un ID de conférence soit automatiquement créé et attribué à un utilisateur, il peut arrive qu’un utilisateur ne souhaite pas l’utiliser et que vous le définissez sur un nombre donné, ou que vos utilisateurs ne peuvent pas se souvenir de leur ID de conférence ou qu’ils l’ont perdu. Vous pouvez utiliser le centre d’administration **Skype Entreprise** et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.

Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l’ID de conférence

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **Utilisation du Skype Entreprise d’administration**

Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.

4. Dans la page Action, affichez la section **ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message  électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur Envoyer les informations sur la conférence par courrier électronique après avoir sélectionné l’utilisateur dans la **page** Utilisateurs.

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur. Pour ce faire, exécutez :

  ```powershell
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

Pour en savoir plus sur l’cmdlet, voir [Get-CsOnlineDialInConferencingUser.](/powershell/module/skype/Get-CsOnlineDialInConferencingUser)


### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l’ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.

![Icône représentant le logo Skype Entreprise’affichage.](../images/sfb-logo-30x30.png) **Utilisation du Skype Entreprise d’administration**

1. Connectez-vous avec votre compte scolaire ou scolaire.

2. Dans le centre d’administration, > **Skype Entreprise.**

3. Dans le **Skype Entreprise d’administration** Utilisateurs de l’audioconférence, dans le volet Action sous >    >   **ID** de conférence, cliquez sur **Réinitialiser.**

4. Dans la fenêtre **Réinitialiser l’ID de conférence** ? cliquez sur **Oui.** A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Reportez-vous à la rubrique **Envoyer un message électronique à un utilisateur avec leurs informations de conférence Audio**.**

Vous pouvez réinitialiser l’ID de conférence d'un utilisateur à l’aide de Windows PowerShell. Pour ce faire, exécutez :

  ```PowerShell
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble" -ResetConferenceID
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois qu’un nouvel ID de conférence est créé ou réinitialisé, l’ancien ID de conférence ne peut pas être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser l’outil Skype Entreprise migration de réunions pour mettre à jour leurs réunions existantes. Pour découvrir comment télécharger, installer et exécuter l’outil, voir : Outil de mise à jour des réunions pour Skype Entreprise et [Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype Entreprise Online, Outil de migration de réunions [(64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et Skype Entreprise Online, outil de migration de réunion [(32 bits).](https://www.microsoft.com/download/details.aspx?id=54079)

- Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).

- L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio. Vous ne pouvez pas utiliser de caractères alphabéétiques ou spéciaux dans les ID de conférence. seuls des nombres peuvent être utilisés.

- L’ID de conférence de tous vos utilisateurs d’audioconférence aura neuf chiffres par défaut et le nombre de chiffres ne peut pas être modifié.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 et Skype Entreprise Online à l’aide d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Raisons pour lesquelles vous devez Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- Windows PowerShell présente de nombreux avantages en matière de vitesse, de simplicité et de productivité par rapport à l’utilisation de la Centre d’administration Microsoft 365 uniquement, par exemple lorsque vous modifiez des paramètres pour de nombreux utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

## <a name="related-topics"></a>Sujets associés

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
