---
title: Afficher, modifier et réinitialiser un ID de conférence affecté à un utilisateur de Skype pour Business Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment attribuer un ID de conférence à un utilisateur de Skype pour Business en ligne et les paramètres d’ID de conférence doivent être. '
ms.openlocfilehash: 7996cc91bd9461f733f82da3eb01eeac7109604a
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883414"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur les ID de conférence affectés aux utilisateurs dans Microsoft Teams, consulter [Afficher et réinitialiser un ID de conférence affecté à un utilisateur dans Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Un ID de conférence est automatiquement attribué à un utilisateur Skype Entreprise lorsque l'utilisateur configure les services d’audioconférence dans Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence affecté est envoyé dans l’invitation à la réunion lorsque la réunion est planifiée. Chaque réunion planifie un utilisateur sera se voit attribuer un ID de conférence unique.

Bien qu’un ID de conférence est automatiquement créé et affecté à un utilisateur, il peut arriver lorsqu’un utilisateur ne souhaite pas utiliser cette et vous voulez lui attribuer un certain nombre, ou lorsque les utilisateurs ne vous souvenez pas ou ont perdu leur ID de conférence. Vous pouvez utiliser le centre d’administration **Skype Entreprise** et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.

Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l’ID de conférence

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.

3. Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.

4. Dans la page Action, affichez la section **ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un message électronique qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par courrier électronique** une fois que vous sélectionnez l’utilisateur dans la page **utilisateurs** .

**Utilisation de Windows PowerShell**

Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur. Pour ce faire, exécutez :

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l’ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.

![SFB-logo-30x30.png](../images/sfb-logo-30x30.png) **à l’aide de la Skype entreprise centre d’administration**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.

3. Dans la **Skype pour le centre d’administration Business**> **audioconférence** > **les utilisateurs**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.

4. Dans le **Réinitialiser l’ID de conférence ?** fenêtre, cliquez sur **Oui**. A conference ID will be automatically created and an email sent to the user with the new conference ID.

**Utilisation de Windows PowerShell**

Vous pouvez réinitialiser l’ID de conférence d'un utilisateur à l’aide de Windows PowerShell. Pour ce faire, exécutez :

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois un nouvel ID de conférence est créé ou une est réinitialisée, l’ancien ID de conférence ne peut être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser le Skype pour l’outil de Migration de réunion Business pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter l’outil, voir : [Outil de mise à jour de réunion pour Skype pour les entreprises et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype pour Business Online, outil de Migration de réunion (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et [Skype pour Business Online, outil de Migration de réunion (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- L’ID de conférence doit respecter la longueur en chiffres définie sur le pont de conférence audio. Vous ne pouvez pas utiliser des caractères alphabétiques ou spéciaux conférence ID ; Seuls les nombres peuvent être utilisées.

- L’ID de conférence pour tous vos utilisateurs de conférence audio sera 7 chiffres par défaut et le nombre de chiffres ne peut pas être modifié.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

