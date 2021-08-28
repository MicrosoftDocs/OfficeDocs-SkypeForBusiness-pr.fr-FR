---
title: Gérer les stratégies de réunion dans Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- seo-marvel-apr2020
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams et les utiliser pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par les utilisateurs.
ms.openlocfilehash: f471d9513995a13eb32eaacd118cd2f3874cda7c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627336"
---
# <a name="manage-meeting-policies-in-microsoft-teams"></a>Gérer les stratégies de réunion dans Microsoft Teams

<a name="bkautomatically-admit-people"> </a>

<a name="bkallow-a-participant-to-give-or-request-control"> </a>

<a name="bkallow-transcription"> </a>

Stratégies de réunion: elles sont utilisées pour contrôler les fonctionnalités disponibles aux participants à la réunion pour les réunions planifiées par des utilisateurs au sein de votre organisation. Vous pouvez utiliser la stratégie globale (par défaut à l’échelle de l’organisation) qui est créée automatiquement ou créer et affecter de stratégies personnalisées. Vous pouvez gérer les stratégies de réunion dans le Centre d’administration Microsoft Teams ou à l’aide de [PowerShell](teams-powershell-overview.md).

> [!NOTE]
> Pour plus d’informations sur l’utilisation de rôles pour gérer les autorisations des présentateurs et des participants à une réunion, consultez [Rôles dans une réunion Teams](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us).

Vous pouvez implémenter des stratégies de plusieurs manières, ce qui affecte l’expérience de réunion pour les utilisateurs avant le début d’une réunion, pendant une réunion ou après une réunion.

|Type d’implémentation  |Description  |
|---------|---------|
|Par organisateur    |Lorsque vous appliquez une stratégie par organisateur, tous les participants à la réunion héritent de la stratégie de l’organisateur. Par exemple, le paramètre **Admettre automatiquement des personnes** est une stratégie par organisateur. Elle permet de contrôler si les utilisateurs rejoignent directement la réunion ou attendent dans la salle d’attente pour les réunions planifiées par l’utilisateur auquel la stratégie est attribuée.          |
|Par utilisateur    |Lorsque vous appliquez une stratégie par utilisateur, seule la stratégie par utilisateur s’applique pour restreindre certaines fonctionnalités pour l’organisateur et/ou les participants à la réunion. Par exemple, le paramètre **Autoriser la conférence maintenant dans les canaux** est une stratégie par utilisateur.     |
|Par organisateur et par utilisateur     |Lorsque vous appliquez une combinaison d’une stratégie par organisateur et par utilisateur, certaines fonctionnalités sont limitées aux participants à la réunion en fonction de leur stratégie et celle de l’organisateur. Par exemple, le paramètre **Autoriser l’enregistrement dans le Cloud** est une stratégie par organisateur et par utilisateur. Activez ce paramètre pour autoriser l’organisateur de la réunion et les participants à démarrer et arrêter un enregistrement.

Vous pouvez modifier les paramètres dans la stratégie globale ou créer et affecter une ou plusieurs stratégies personnalisées. Les utilisateurs recevront automatiquement la stratégie par défaut, sauf si vous créez et leur attribuez une stratégie personnalisée.

> [!NOTE]
> Le bouton Détails de la réunion est disponible si un utilisateur dispose des licences d’audioconférence activées, ou si l’utilisateur autorise l’audioconférence, si ce n’est pas le cas, les détails de la réunion ne sont pas disponibles.

## <a name="create-a-custom-meeting-policy"></a>Créer une stratégie de réunion personnalisée

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions** > **Stratégies de réunion**.
2. Cliquez sur **Ajouter**.
3. Entrez un nom pour votre stratégie, ainsi qu’une description. Le nom ne peut pas contenir de caractères spéciaux et ne doit pas dépasser 64 caractères.
4. Sélectionnez les paramètres de votre choix.
5. Cliquez sur **Enregistrer**.

Par exemple, imaginons que vous avez un grand nombre d’utilisateurs et que vous voulez limiter la quantité de bande passante requise par la réunion. Vous devez créer une stratégie personnalisée nommée « bande passante limitée » et désactiver les paramètres suivants :

Sous **Audio & vidéo** :

- Désactivez l’option Autoriser l’enregistrement Cloud.
- Désactivez Autoriser la vidéo IP.

Sous **Partage de contenu** :

- Désactiver le mode de partage d’écran.
- Désactivez  Autoriser le tableau blanc.
- Désactivez Autoriser les notes partagées.

Vous pouvez ensuite attribuer la stratégie aux utilisateurs.

## <a name="edit-a-meeting-policy"></a>Modifier une stratégie de réunion

Vous pouvez modifier la stratégie globale et les stratégies personnalisées que vous créez.

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez aux **Réunions** > **Stratégies de réunion**.
2. Sélectionnez la stratégie en cliquant à gauche du nom de celle-ci, puis cliquez sur **Modifier**.
3. À partir de là, apportez les modifications souhaitées.
4. Cliquez sur **Enregistrer**.

> [!NOTE]
> Un utilisateur ne peut être affecté qu’à une stratégie de réunion à la fois.

## <a name="assign-a-meeting-policy-to-users"></a>Affecter une stratégie de réunion aux utilisateurs

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> Vous ne pouvez pas supprimer une stratégie qui est attribuée à des utilisateurs. Vous devez d'abord attribuer une autre stratégie à tous les utilisateurs concernés, puis supprimer la stratégie d’origine.

## <a name="meeting-policy-settings"></a>Paramètres de stratégie de réunion

Lorsque vous sélectionnez une stratégie existante dans la page **Stratégies de réunion** ou que vous sélectionnez **Ajouter** pour ajouter une nouvelle stratégie, les paramètres suivants peuvent être configurés.

- [Général](meeting-policies-in-teams-general.md)
- [Vidéo et audio](meeting-policies-audio-and-video.md)
- [Partage de contenu](meeting-policies-content-sharing.md)
- [Participants et invités](meeting-policies-participants-and-guests.md)


## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
- [Attribuer des stratégies à vos utilisateurs](assign-policies.md)
- [Supprimer la stratégie de réunion Teams RestrictedAnonymousAccess des utilisateurs](meeting-policies-restricted-anonymous-access.md)