---
title: Définir les numéros de téléphone inclus dans les invitations
ms.author: heidip
author: MicrosoftHeidi
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
description: Suivez ces étapes pour créer un numéro de téléphone par défaut pour que les appelants rejoignent une réunion Microsoft Teams.
ms.openlocfilehash: f0956007d5df72c1fd6c6ae905433e73bd855a56
ms.sourcegitcommit: 312ff79ecab91412918793ec882bfc6e0143d30a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66884843"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Définir les numéros de téléphone inclus sur les invitations dans Microsoft Teams.

L’audioconférence dans Microsoft 365 et Office 365 permet aux utilisateurs de votre organisation de créer des réunions Microsoft Teams, puis d’autoriser les utilisateurs à se connecter à ces réunions à l’aide d’un numéro de téléphone.

Un pont de conférence vous offre un ensemble de numéros de téléphone pour votre organisation. Tous ces ponts peuvent servir à participer à des réunions créées par un organisateur de réunion, mais vous pouvez sélectionner ceux qui doivent être inclus dans les invitations de réunion.

En plus des numéros de téléphone inclus dans l’invitation à la réunion pour un organisateur de réunion, il existe également un lien situé au bas de chaque invitation à la réunion qui ouvre la liste complète de tous les numéros de téléphone rendez-vous qui peuvent être utilisés pour participer à une réunion.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-users"></a>Affectation initiale des numéros de téléphone inclus dans les invitations à la réunion pour les utilisateurs

Les numéros de téléphone inclus dans les invitations aux réunions des utilisateurs activés pour l’audioconférence sont définis dans *teamsAudioConferencingPolicy* qui est affecté aux utilisateurs. Lorsqu’un *TeamsAudioConferencingPolicy* est affecté à un utilisateur, tous les numéros de téléphone payants et gratuits ajoutés dans la stratégie sont inclus dans les invitations aux réunions pour les utilisateurs disposant de cette stratégie. Si un utilisateur se voit attribuer une *stratégie TeamsAudioConferencing* Et qu’aucun numéro de téléphone payant ou gratuit n’est ajouté à la stratégie, les numéros de téléphone qui apparaissent dans les invitations à la réunion de ces utilisateurs sont définis par le numéro de téléphone payant de conférence par défaut et le numéro de téléphone gratuit de conférence par défaut dans les paramètres de chaque utilisateur.

> [!NOTE]
> Les numéros de téléphone payants ou gratuits ajoutés à *teamsAudioConferencingPolicy* d’un utilisateur sont prioritaires sur les numéros de téléphone définis individuellement à l’aide du numéro de téléphone payant de conférence par défaut et du numéro de téléphone gratuit de conférence par défaut dans les paramètres d’un utilisateur.

Comme indiqué ci-dessus, en plus des numéros de téléphone, chaque invitation à une réunion contient un lien qui ouvre la liste complète de tous les numéros de téléphone entrants qui peuvent être utilisés pour participer à une réunion donnée.

> [!IMPORTANT]
> Jusqu’à 24 heures peuvent être nécessaires pour que les numéros de téléphone attribués s’affichent sur votre invitation à la réunion. Si vous ne voyez pas les numéros mis à jour s’afficher, patientez au moins 24 heures avant de contacter le support technique.

### <a name="new-users"></a>Nouveaux utilisateurs

Les numéros de téléphone payants et gratuits inclus dans les invitations aux réunions pour les nouveaux utilisateurs sont également définis par *teamsAudioconferencingPolicy* qui est affecté à ces utilisateurs. Par défaut, l’objet *Global TeamsAudioconferencingPolicy* est attribué à tous les nouveaux utilisateurs. Aucun numéro de téléphone n’est ajouté à la stratégie globale (sauf si cela est modifié par l’administrateur client). Dans ce cas, les numéros de téléphone inclus dans les invitations à la réunion des utilisateurs activés pour l’audioconférence sont définis par le numéro de téléphone payant de conférence par défaut et le numéro de téléphone gratuit de conférence par défaut trouvé dans les paramètres de chaque utilisateur.

Pour un nouvel utilisateur, les numéros payants de conférence par défaut sont attribués en fonction de l’emplacement d’utilisation défini dans le centre d’administration Microsoft 365 de l’utilisateur lorsque l’utilisateur est activé pour le service d’audioconférence. S’il existe un numéro de péage dans le pont de conférence qui correspond au pays de l’utilisateur, ce numéro est automatiquement attribué comme numéro de péage par défaut de l’utilisateur. S’il n’y en a pas, le numéro défini comme numéro de péage par défaut du pont de conférence est attribué en tant que numéro de péage par défaut de l’utilisateur.  

Une fois que l’utilisateur est activé pour le service d’audioconférence, les numéros de téléphone payants et gratuits par défaut de l’utilisateur peuvent être modifiés par l’administrateur client à partir de leurs valeurs initiales en fonction des besoins.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-users-in-powershell-using-the-teamsaudioconferencingpolicy-cmdlet"></a>Définir ou modifier le numéro de téléphone d’audioconférence par défaut pour les utilisateurs dans PowerShell à l’aide de l’applet de commande *TeamsAudioConferencingPolicy*

Consultez [les paramètres de stratégie d’audioconférence pour les numéros payants et gratuits](audio-conferencing-toll-free-numbers-policy.md)

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user-individually"></a>Définir ou modifier le numéro de téléphone d’audioconférence par défaut pour un organisateur de réunion ou un utilisateur individuellement

Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](./using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Connectez-vous au Centre d’administration Microsoft Teams.

2. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**.

    ![Affiche la sélection d’utilisateurs dans le Centre d’administration Microsoft Teams.](media/Admin-users.png)

3. Cliquez sur le nom d’utilisateur dans la liste des utilisateurs disponibles.

4. A côté de **Conférence Audio**, cliquez sur **Modifier**.

    ![Cliquez sur Modifier en regard de l’audioconférence.](media/teams-set-phone-numbers-on-invites-image3.png)

5. Utilisez les champs **Numéro payant** ou **Numéro gratuit** pour entrer les numéros de l’utilisateur.

> [!IMPORTANT]
> Lorsque vous modifiez les paramètres d’audioconférence d’un utilisateur, les réunions Microsoft Teams périodiques et futures doivent être mises à jour et envoyées aux participants.

> [!NOTE]
> Les numéros de téléphone entrés dans ce paramètre sont utilisés uniquement si *teamsAudioConferencingPolicy* affecté à l’utilisateur n’a pas de numéros de téléphone ajoutés.

## <a name="want-to-use-windows-powershell"></a>Vous souhaitez utiliser Windows PowerShell

Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. Avec Windows PowerShell, vous pouvez gérer Microsoft 365 ou Office 365 à l’aide d’un seul point d’administration qui peut simplifier votre travail quotidien lorsque vous avez plusieurs tâches à effectuer. Pour prendre en main Windows PowerShell, consultez ces rubriques :

- [Windows PowerShell est axé sur la gestion des utilisateurs et sur les actions qu'ils sont autorisés ou non à effectuer. En utilisant Windows PowerShell, vous pouvez gérer Office 365 depuis un seul point d'administration, ce qui simplifiera votre travail quotidien si vous devez effectuer de nombreuses tâches différentes. Pour commencer à utiliser Windows PowerShell, reportez-vous aux rubriques suivantes :](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Meilleures façons de gérer Microsoft 365 ou Office 365 avec Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Pour définir ou modifier le numéro de téléphone d’audioconférence par défaut d’un organisateur ou d’un utilisateur de réunion à l’aide de [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps), définissez le **`ServiceNumber`** ou **`TollFreeServiceNumber`** les paramètres de l’applet de commande [Set-CsOnlineDialInConferencingUser sur](/powershell/module/skype/set-CsOnlineDialInConferencingUser?view=skype-ps) l’un des numéros disponibles.

## <a name="related-topics"></a>Sujets associés

[Essayez ou achetez l’audioconférence dans Microsoft 365 ou Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Modifier les numéros de téléphone de votre pont d’audioconférence](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
