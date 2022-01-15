---
title: Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
- seo-marvel-mar2020
description: Découvrez les étapes permettant de réinitialiser l’ID de conférence d’un utilisateur dans Microsoft Teams et obtenez des liens vers les outils de mise à jour et de migration de réunion.
ms.openlocfilehash: 55dc8935d191f518ca353d4b384b36e205f5c584
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056044"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Réinitialiser l'ID de conférence d'un utilisateur dans Microsoft Teams

Un ID de conférence dynamique est inclus au bas des invitations aux réunions, ainsi que les numéros de téléphone à composer qui peuvent être utilisés par les appelants pour participer à une réunion. Lorsque l’utilisateur compose le numéro de téléphone, le attendant automatique de la réunion demande à l’appelant d’entrer cet ID de conférence afin qu’il puisse participer à la réunion.
  
> [!NOTE]
> Les ID de conférence sont générés automatiquement, ils sont entre 7 et 9 chiffres et sont définies lorsque vous activez l’audioconférence pour un utilisateur. **Les ID de conférence statiques ne sont pas pris en charge.**

## <a name="resetting-the-conference-id-for-a-user"></a>Réinitialisation de l’ID de conférence d’un utilisateur

À l’aide Microsoft Teams centre d’administration :

1. Dans le navigation à gauche, cliquez **sur Utilisateurs,** puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez **sur Modifier.**

3. Sous **Audioconférence, cliquez** sur **Réinitialiser l’ID de conférence.**

4. Dans la fenêtre **Réinitialiser l’ID de conférence,** cliquez sur **Réinitialiser.** A conference ID will be automatically created and an email sent to the user with the new conference ID. Par défaut, les courriers électroniques sont envoyés aux utilisateurs, mais cette option peut être désactivée.

> [!NOTE]
> Une fois l'ID de conférence réinitialisé, un message électronique contenant le nouvel ID de conférence est envoyé à l'utilisateur. Ce courrier électronique est envoyé à l’adresse de messagerie principale, le plus souvent, Microsoft 365 ou Office 365 boîte aux lettres. Le message électronique contient le nouvel ID de conférence, le ou les numéros de téléphone à composer par défaut et les instructions de mise à jour des réunions existantes.
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>Informations supplémentaires

- Vous pouvez envoyer toutes les informations sur les conférences à l’utilisateur dans un message électronique  qui inclut l’ID de conférence et les numéros de téléphone à composer en cliquant sur Envoyer les informations sur la conférence par courrier électronique à l’utilisateur dans la section Audioconférence.  Le code confidentiel n'est pas envoyé.

- Un ID de conférence à 7 ou 9 chiffres est créé par le service Teams service. Vous ne pouvez pas modifier sa longueur.

- Une fois l'ID de conférence réinitialisé, vous pouvez afficher le nouvel ID de conférence sous **ID de conférence**.

- Une fois qu'un nouvel ID de conférence est créé, l'ancien ID ne peut plus être utilisé par les appelants. Vous devez inviter les utilisateurs à replanifier leurs invitations à la réunion pour vous assurer que le nouvel ID de conférence sera ajouté aux invitations.

## <a name="want-to-know-more-about-windows-powershell"></a>Vous souhaitez en savoir plus sur Windows PowerShell ?

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer vos tâches Microsoft 365 Office 365 d’un seul point d’administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures méthodes pour gérer vos Microsoft 365 vos Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour plus d’informations sur Windows PowerShell, consultez la rubrique [Microsoft Teams PowerShell ](/powershell/module/teams/?view=teams-ps&preserve-view=true).

## <a name="related-topics"></a>Rubriques connexes

[Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md)
