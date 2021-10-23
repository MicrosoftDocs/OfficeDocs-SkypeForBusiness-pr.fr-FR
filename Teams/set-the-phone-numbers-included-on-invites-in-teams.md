---
title: Définir les numéros de téléphone inclus dans les invitations
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Pour créer un numéro de téléphone par défaut, les appelants pourront rejoindre une Microsoft Teams réunion.
ms.openlocfilehash: bef8575e1e799c63159bec5cbfb06c80f4af6c83
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536745"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Définir les numéros de téléphone inclus sur les invitations dans Microsoft Teams.

L’audioconférence dans Microsoft 365 et Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams et d’autoriser les utilisateurs à s’y rendre par téléphone.
  
Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.
  
> [!NOTE]
> Il peut y avoir au maximum une ligne simple et une ligne de téléphone gratuite dont les numéros apparaissent sur l’invitation à la réunion pour un organisateur de réunion, mais il existe également un lien situé en bas de chaque invitation à une réunion qui ouvre la liste complète de tous les numéros de téléphone qui peuvent être utilisés pour participer à une réunion.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Affectation initiale des numéros de téléphone inclus dans les invitations aux réunions pour les nouveaux utilisateurs

Les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs activés pour l’audioconférence sont définis par le numéro de téléphone gratuit de conférence par défaut et les paramètres d’utilisateur du numéro de téléphone gratuit de conférence par défaut. Chaque paramètre spécifie le numéro gratuit et gratuit qui sera inclus dans l’invitation à la réunion d’un utilisateur donné. Comme indiqué ci-dessus, chaque invitation à une réunion contient un numéro gratuit, un numéro gratuit facultatif et un lien qui ouvre la liste complète de tous les numéros de téléphone à composer pour participer à une réunion donnée.

Pour un nouvel utilisateur, les numéros gratuits de conférence par défaut sont affectés en fonction de l’emplacement d’utilisation qui est définie dans le centre d’administration Microsoft 365 de l’utilisateur lorsque l’utilisateur est activé pour le service d’audioconférence. Si le pont de conférence compte un numéro de téléphone qui correspond au pays de l’utilisateur, ce numéro est automatiquement affecté comme numéro de téléphone par défaut à l’utilisateur. S’il n’y en a pas, le numéro défini comme numéro toll par défaut du pont de conférence sera affecté au numéro de téléphone par défaut de l’utilisateur.  

Une fois le service d’audioconférence activé pour l’utilisateur, les numéros de téléphone gratuits et gratuits par défaut peuvent être modifiés à tout moment par l’administrateur client par rapport à leurs valeurs initiales.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Définir ou modifier le numéro de téléphone d’audioconférence par défaut pour un organisateur ou un utilisateur de la réunion

 **Utiliser le centre d’administration Microsoft Teams**

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](./using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Connectez-vous au Microsoft Teams d’administration.

2. Dans le groupe de navigation de gauche, cliquez sur **Utilisateurs.**

    ![Affiche la sélection d’utilisateurs dans le Microsoft Teams d’administration.](media/Admin-users.png)

3. Cliquez sur le nom d’utilisateur dans la liste des utilisateurs disponibles.

4. A côté de **Conférence Audio**, cliquez sur **Modifier**.

    ![Cliquez sur Modifier en cours d’audioconférence.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Utilisez les **champs Numéro gratuit** ou Numéro **gratuit** pour entrer les numéros de l’utilisateur.

> [!IMPORTANT]
> Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions périodiques et futures Microsoft Teams doivent être mises à jour et envoyées aux participants.

## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui simplifiera votre travail si vous devez effectuer de nombreuses tâches différentes. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures méthodes de gestion des Microsoft 365 des Office 365'Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour définir ou modifier le numéro de téléphone d’audioconférence par défaut d’un organisateur de réunion ou d’un utilisateur à l’aide de [Microsoft Teams PowerShell,](/powershell/module/teams/?view=teams-ps)définissez les paramètres ou les paramètres de la **`ServiceNumber`** **`TollFreeServiceNumber`** cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) sur l’un des numéros disponibles.

## <a name="related-topics"></a>Sujets associés

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Modifier les numéros de téléphone de votre pont d’audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
