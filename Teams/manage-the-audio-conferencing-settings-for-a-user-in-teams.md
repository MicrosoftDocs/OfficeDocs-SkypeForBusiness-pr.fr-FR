---
title: Gérer les paramètres d'audioconférence d'un utilisateur dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "En tant qu’administrateur d’Office 365, vous pouvez modifier les paramètres d’audioconférence Microsoft Teams tels que le fournisseur, le numéro payant ou gratuit par défaut, l’ID de conférence ou le code confidentiel d'un utilisateur dans votre organisation. "
ms.openlocfilehash: 673441acebf9b31893925539471040bffa621f38
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571922"
---
# <a name="manage-the-audio-conferencing-settings-for-a-user-in-microsoft-teams"></a>Gérer les paramètres d'audioconférence d'un utilisateur dans Microsoft Teams

En tant qu’administrateur Office 365, vous pouvez modifier les paramètres d’Audioconférence, tels que le fournisseur, le numéro payant ou gratuit par défaut, l’identifiant de conférence ou le code confidentiel — pour un utilisateur individuel dans votre organisation. Pour modifier les paramètres de votre organisation, reportez-vous à [la section gérer les paramètres de conférence audio de votre organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Icône affichant le logo Microsoft teams](media/teams-logo-30x30.png) Utilisation du centre d’administration Microsoft teams

1. Dans le volet de navigation de gauche, cliquez sur **utilisateurs**, puis sélectionnez l’utilisateur dans la liste des utilisateurs disponibles.

2. Cliquez sur **modifier**.

3. Sous **audioconférence**, modifiez l’une des options suivantes :

|**Paramètre**|**Description**|
|:-----|:-----|
|**Audioconférence**|Pour activer ou désactiver la fonctionnalité d’audioconférence pour l’utilisateur, cliquez sur **modifier** en regard de **audioconférence**, puis dans le volet **audioconférence** , activez ou désactivez l’option **conférence audio** .|
|**Envoyer les informations sur la Conférence par courrier électronique**  |Cliquez sur ce lien uniquement si vous souhaitez envoyer immédiatement un message électronique à l’utilisateur avec son identifiant de conférence et son numéro de téléphone. (Ce message n’inclut pas le code confidentiel). Voir [Envoyer un message électronique à un utilisateur avec ses informations d’audioconférence](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).  |
|**ID de conférence**  |Cliquez sur **réinitialisation** de l’ID de conférence si vous devez réinitialiser l’ID de conférence de l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser un identifiant de conférence pour un utilisateur](reset-a-conference-id-for-a-user-in-teams.md).  |
|**ÉPINGL** |Cliquez sur **Réinitialiser le code confidentiel** si vous avez besoin de réinitialiser le code confidentiel de l’utilisateur. Pour plus d’informations, consultez la rubrique [Réinitialiser le code confidentiel d’audioconférence](reset-the-audio-conferencing-pin-in-teams.md). |
|**Numéro de téléphone payant de la Conférence par défaut** (obligatoire) |Il s’agit des numéros définis dans le pont de conférence audio. Mettez en forme les numéros comme vous voulez qu’ils apparaissent dans les demandes de réunion Skype entreprise et Microsoft Teams. Pour modifier le numéro payant par défaut, cliquez sur **modifier** en regard de **audioconférence** et dans le volet **audioconférence** , sélectionnez un numéro sous **numéro**de téléphone. |
|**Les invitations de cet utilisateur peuvent inclure un numéro gratuit**|Pour modifier ce paramètre, cliquez sur **modifier** en regard de l’option **audioconférence** et dans le volet **audioconférence** , activez ou désactivez les cases à **copointr dans les demandes de réunion de la part de cet utilisateur** . |
|**Les utilisateurs non authentifiés peuvent être la première personne de la réunion.**|Pour modifier ce paramètre, faites basculer les **utilisateurs non authentifiés peuvent être la première personne de la réunion** .
|**Autorisations de numérotation**|Pour modifier ce paramètre, cliquez sur **modifier** en regard de **audioconférence** et dans le volet **audioconférence** , choisissez une option sous **appel sortant pour les réunions**.|

![Affiche les paramètres de l’audioconférence pour un utilisateur](media/teams-manage-audio-conferencing-settings-for-a-user-image1.png)
 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="related-topics"></a>Voir aussi

[Gérer les paramètres d’audioconférence pour votre organisation](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

[Questions fréquentes à propos de l'audioconférence](audio-conferencing-common-questions.md)
