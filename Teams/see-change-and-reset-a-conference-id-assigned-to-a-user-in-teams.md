---
title: Afficher, modifier et réinitialiser l’ID de conférence d’un utilisateur
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: Découvrez comment attribuer un ID de conférence à un utilisateur dans Microsoft Teams et quels sont les paramètres des ID de conférence.
ms.openlocfilehash: 9ff068a8485f77531ba034ebeaab3e27e1ed42ef
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642115"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Afficher et réinitialiser un ID de conférence attribué à un utilisateur dans Microsoft Teams

Un ID de conférence est automatiquement attribué à un utilisateur Microsoft Teams lorsqu’il est configuré pour l’audioconférence dans Microsoft 365 ou Office 365 et utilise Microsoft comme fournisseur d’audioconférence. L’ID de conférence affecté est envoyé dans l’invitation à la réunion lorsque la réunion est planifiée. Chaque réunion planifiée par un utilisateur se voit attribuer un ID de conférence unique.
  
Bien qu’un ID de conférence soit automatiquement créé et affecté à un utilisateur, il peut arriver qu’un utilisateur ne souhaite pas utiliser celui-ci et que vous le définissiez sur un certain nombre, ou lorsque vos utilisateurs ne se souviennent pas ou ont perdu leur ID de conférence. Vous pouvez utiliser le Centre d’administration Microsoft Teams ou Windows PowerShell pour afficher, modifier et réinitialiser son ID de conférence.
  
Un e-mail contenant l’ID de conférence et les numéros de téléphone de conférence audio sera envoyé à l’utilisateur par défaut, ou si vous réinitialisez l’ID de conférence, un autre e e-mail sera envoyé et inclura l’ID de conférence sans code confidentiel. Pour plus d’informations sur la [réinitialisation du code confidentiel d’un organisateur de conférence, consultez Réinitialiser un ID de conférence pour un utilisateur dans Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) .

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Afficher et réinitialiser les ID de conférence

### <a name="to-view-the-conference-id"></a>Pour afficher l’ID de conférence

#### <a name="view-the-conference-id-using-the-microsoft-teams-admin-center"></a>Afficher l’ID de conférence à l’aide du Centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, regardez sous **ID de conférence**.

    > [!TIP]
    > Vous pouvez envoyer toutes les informations de conférence à l’utilisateur dans un e-mail qui inclut l’ID de conférence et les numéros de téléphone audio en cliquant sur **Envoyer les informations de conférence dans le lien de messagerie** .
  
#### <a name="view-the-conference-id-using-windows-powershell"></a>Afficher l’ID de conférence à l’aide de Windows PowerShell

Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

### <a name="to-reset-the-conference-id"></a>Pour réinitialiser l’ID de conférence

Vous pouvez réinitialiser un ID de conférence pour un utilisateur, en cas d'oubli par exemple.
  
#### <a name="reset-the-conference-id-using-the-microsoft-teams-admin-center"></a>Réinitialiser l’ID de conférence à l’aide du Centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. En haut de la page, cliquez sur **Modifier**.

3. Sous **Audioconférence**, cliquez sur **Réinitialiser l’ID de conférence**.

4. Dans la fenêtre **Réinitialiser l’ID de conférence** , cliquez sur **Réinitialiser**. A conference ID will be automatically created and an email sent to the user with the new conference ID.
  
#### <a name="reset-the-conference-id-using-windows-powershell"></a>Réinitialiser l’ID de conférence à l’aide de Windows PowerShell

Pour plus d’informations, consultez la [référence Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) .

## <a name="what-else-should-you-know"></a>Informations supplémentaires

> [!IMPORTANT]
> Une fois qu’un nouvel ID de conférence a été créé ou réinitialisé, l’ancien ID de conférence ne peut pas être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.

- L’ID de conférence doit respecter la longueur en chiffres définie sur le pont d’audioconférence. Vous ne pouvez pas utiliser de caractères alphabétiques ou spéciaux dans les ID de conférence ; seuls les nombres peuvent être utilisés.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Rubriques connexes

[Essayer ou acheter l’audioconférence dans Microsoft 365 pour Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
