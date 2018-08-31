---
title: Afficher, modifier et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Découvrez comment attribuer un ID de conférence à un utilisateur de Skype Entreprise Online et les paramètres nécessaires des ID de conférence. '
ms.openlocfilehash: 472f3b007a584979e029aade593c7b6c93ea1565
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252307"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-skype-for-business-online"></a>Afficher et réinitialiser un ID de conférence affecté à un utilisateur de Skype Entreprise Online

> [!Note]
> Pour plus d’informations sur les ID de conférence affectés aux utilisateurs dans Microsoft Teams, consulter [Afficher et réinitialiser un ID de conférence affecté à un utilisateur dans Microsoft Teams](/MicrosoftTeams/see-change-and-reset-a-conference-id-assigned-to-a-user-in-teams).

Un ID de conférence est automatiquement attribué à un utilisateur Skype Entreprise lorsque l'utilisateur configure les services d’audioconférence dans Office 365 et utilise Microsoft comme fournisseur de services d’audioconférence. L’ID de conférence affecté est envoyé dans l’invitation à la réunion lors de sa planification. Chaque réunion qu'un utilisateur planifie se verra affecter un ID de conférence unique.

Bien qu’un ID de conférence soit automatiquement créé et affecté à un utilisateur, il peut y avoir des cas où un utilisateur ne souhaite pas l'utiliser et où vous voudrez le définir à un certain nombre, ou dans lesquels vos utilisateurs ne pourront pas se souvenir ou auront perdu leur ID de conférence. Vous pouvez utiliser le centre d’administration **Skype Entreprise** et Windows PowerShell pour afficher, modifier et réinitialiser leurs ID de conférence.

Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour plus d’informations sur la réinitialisation du code confidentiel de l’organisateur d’une conférence, [Cliquez ici](reset-a-conference-id-for-a-user.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l’ID de conférence

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d'administration Skype Entreprise**

Vous pouvez afficher leurs ID de conférence et les envoyer aux utilisateurs.

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.

3. Dans le **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, sélectionnez l’utilisateur qui a besoin d'un ID de conférence.

4. Dans la page Action, affichez la section **ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un email comprennant l'ID de conférence et les numéros de téléphone audio en cliquant sur le lien **Envoyer les informations de conférence par email** une fois l’utilisateur sélectionné sur la page **Utilisateurs**.

**Utilisation de Windows PowerShell**

Vous pouvez utiliser Windows PowerShell pour afficher l’ID de conférence pour un utilisateur. Pour cela, exécutez :

  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.


### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l'ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Utilisation du centre d'administration Skype Entreprise**

1. Connectez-vous à Office 365 à l'aide de votre compte professionnel ou scolaire.

2. Sélectionnez **Centre d'administration Office 365** > **Skype Entreprise**.

3. Dans la page **centre d'administration Skype Entreprise**> **Audioconférence** > **Utilisateurs**, dans le volet Actions, sous **ID de conférence**, cliquez sur **Réinitialiser**.

4. Dans la fenêtre **Réinitialiser l’ID de conférence ?**, cliquez sur **Oui**. Un ID de conférence sera créé automatiquement et un email sera envoyé à l'utilisateur avec le nouvel ID de conférence.

**Utilisation de Windows PowerShell**

Vous pouvez réinitialiser l’ID de conférence d'un utilisateur à l’aide de Windows PowerShell. Pour cela, exécutez :

  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>Informations supplémentaires

   > [!IMPORTANT]
   >  Une fois qu'un nouvel ID de conférence est créé ou qu'un ID de conférence est réinitialisé, l'ancien ID de conférence ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations. Les utilisateurs peuvent utiliser l'Outil de migration de réunions de Skype Entreprise pour mettre à jour leurs réunions existantes. Pour savoir comment télécharger, installer et exécuter l'outil, voir : [Outil de migration de réunions de Skype Entreprise et Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype Entreprise Online, Outil de migration de réunions (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)et [Skype Entreprise Online, Outil de migration de réunions (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

- Pour en savoir plus sur l'applet de commande, reportez-vous à la rubrique [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).

- L'ID de conférence doit respecter le nombre de chiffres défini sur le pont de conférence audio. Les ID de conférence ne doivent comporter que des chiffres, jamais de caractères alphabétiques ou spéciaux.

- L'ID de conférence comporte sept chiffres par défaut pour tous les utilisateurs de l'audioconférence . Il n'est pas possible de modifier le nombre de chiffres.


## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Comment utiliser Windows PowerShell pour gérer cette fonction ?

- Windows PowerShell permet de gérer les utilisateurs et ce qu'ils sont autorisés ou non à faire. Avec Windows PowerShell, vous pouvez gérer Office 365 et Skype Entreprise Online à l'aide d'un point d'administration central qui peut simplifier votre travail quotidien, lorsque vous devez effectuer plusieurs tâches. Pour prendre en main Windows PowerShell, consultez ces rubriques :

  - [Présentation de Windows PowerShell et Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](https://go.microsoft.com/fwlink/?LinkId=525041)

- Windows PowerShell offre de nombreux avantages en matière de rapidité, de simplicité et de productivité par rapport à l'utilisation du centre d'administration Office 365 uniquement, par exemple lorsque vous modifiez des paramètres pour un grand nombre d'utilisateurs en même temps. Découvrez ces avantages dans les rubriques suivantes :

  - [Meilleures méthodes de gestion d'Office 365 avec Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

  - [Utilisation de Windows PowerShell pour gérer Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Utilisation de Windows PowerShell pour effectuer les tâches de gestion courantes de Skype Entreprise Online](https://go.microsoft.com/fwlink/?LinkId=525038)

## <a name="related-topics"></a>Rubriques connexes

[Tester ou acheter l'audioconférence dans Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

