---
title: Gérer les paramètres d’audioconférence pour les utilisateurs
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 0f39dc9d-eb60-4c5a-9ae3-e34a01834d9b
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
description: Un administrateur Microsoft 365 ou Office 365 peut modifier les paramètres de l’audioconférence Teams, notamment le fournisseur, le numéro payant ou gratuit par défaut, l’ID de conférence ou le code confidentiel d’un utilisateur.
ms.openlocfilehash: 9b68ea4452928ce739ec8429ed9b71bfaca91cf4
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641905"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Gérer les paramètres d'audioconférence d'un utilisateur dans Microsoft Teams

En tant qu’administrateur Microsoft 365 ou Office 365, vous pouvez modifier les paramètres de l’audioconférence, tels que le fournisseur, le numéro payant ou gratuit par défaut, l’ID de conférence ou le code CONFIDENTIEL, pour un utilisateur individuel de votre organisation. Si vous souhaitez modifier les paramètres de votre organisation, consultez [Gérer les paramètres d’audioconférence de votre organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).

## <a name="using-the-microsoft-teams-admin-center"></a>Utiliser le centre d’administration Microsoft Teams

1. Dans le volet de navigation de gauche, cliquez sur **Utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **Modifier**.

3. Sous **Audioconférence**, modifiez l’une des options suivantes :

|**Paramètres**|**Description**|
|:-----|:-----|
|**Audioconférence**|Pour activer ou désactiver l’audioconférence pour l’utilisateur, cliquez sur **Modifier** en regard de **l’audioconférence**, puis dans le volet **Audioconférence** , activer ou désactiver **l’audioconférence** .|
|**Envoyer des informations de conférence par e-mail**  |Cliquez sur ce lien uniquement si vous souhaitez envoyer immédiatement un message électronique à l’utilisateur avec son identifiant de conférence et son numéro de téléphone. (Ce message n’inclut pas le code confidentiel). Voir [Envoyer un message électronique à un utilisateur avec ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).  |
|**ID de conférence**  |Cliquez sur **Réinitialiser l’ID de conférence** si vous devez réinitialiser l’ID de conférence pour l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser un identifiant de conférence pour un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).  |
|**Épingler** |Cliquez sur **Réinitialiser le code confidentiel** si vous devez réinitialiser le code confidentiel de l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md). |
|**Numéro de téléphone payant de conférence par défaut** (obligatoire) |Nombres définis sur le pont d’audioconférence. Mettez en forme les nombres tels que vous souhaitez qu’ils apparaissent dans les demandes de réunion Teams. Pour modifier le numéro de péage par défaut, cliquez sur **Modifier** en regard de **l’audioconférence** et, dans le volet **Audioconférence** , sélectionnez un nombre sous **Numéro payant**. Vous pouvez également définir des numéros de téléphone en les ajoutant à TeamsAudioConferencingPolicy et en affectant la stratégie à vos utilisateurs. Les numéros de téléphone ajoutés à la stratégie sont prioritaires sur les numéros de téléphone définis à l’aide du **numéro de téléphone payant de conférence par défaut**. Si aucun numéro de téléphone n’est ajouté à TeamsAudioConferencingPolicy, le numéro de téléphone défini à l’aide du **numéro de téléphone payant de conférence par défaut** s’affiche dans les demandes de réunion Microsoft Teams. |
|**Les invitations de cet utilisateur peuvent inclure un numéro gratuit**|Ce paramètre ne peut être modifié qu’à l’aide de TeamsAudioconferecningPolicy. |
|**Les utilisateurs non authentifiés peuvent être la première personne à participer à la réunion**|Pour modifier ce paramètre, les **utilisateurs non authentifiés peuvent être la première personne à participer à la réunion** activée ou désactivée.
|**Autorisations de numérotation**|Pour modifier ce paramètre, cliquez sur **Modifier** en regard de **l’audioconférence** et, dans le volet **Audioconférence** , choisissez une option sous **Numérotation à partir des réunions**.|

![Affiche les paramètres d’audioconférence d’un utilisateur.](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Rubriques connexes

[Gérer les paramètres d’audioconférence pour votre organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[Questions fréquentes à propos de l’audioconférence](audio-conferencing-common-questions.md)
