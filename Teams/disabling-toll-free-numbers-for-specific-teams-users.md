---
title: Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
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
description: Découvrez comment contrôler comment les organisateurs peuvent utiliser des numéros gratuits pour leurs réunions de pont d’audioconférence.
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016626"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Désactiver les numéros gratuits pour des utilisateurs de Teams spécifiques

Si votre organisation dispose de numéros gratuits dans son pont d’audioconférence Microsoft, vous pouvez autoriser ou empêcher leur utilisation dans les réunions d’organisateurs spécifiques.  

Par défaut, tous les utilisateurs de votre organisation sont activés pour utiliser des numéros gratuits, ce qui signifie que ces numéros, s’ils sont disponibles, peuvent être utilisés par les participants pour participer à leurs réunions. S’il ne s’agit pas du comportement souhaité pour certains utilisateurs de votre organisation, vous pouvez empêcher des utilisateurs spécifiques d’utiliser ces numéros dans leurs réunions via un contrôle d’activation des numéros gratuits.

Lorsque les numéros gratuits sont désactivés pour un organisateur donné :

- Un numéro gratuit ne sera plus inclus dans ses invitations à la réunion.
- Les numéros gratuits ne seront plus répertoriés sur la page « Rechercher un numéro local » référencée dans ses invitations à la réunion.
- Les participants ne pourront pas participer à la réunion de l’organisateur donné s’ils composent un numéro gratuit de l’organisation.
- Les participants peuvent continuer à participer aux réunions de l’organisateur à l’aide de numéros payants.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Désactiver les numéros gratuits pour des utilisateurs spécifiques

Vous pouvez désactiver les numéros gratuits pour des utilisateurs spécifiques en modifiant le paramètre *AllowTollFreeDialIn* sur **Désactivé** dans *teamsAudioConferencingPolicy* affecté à ces utilisateurs. Une fois les nouvelles réunions créées par ces utilisateurs désactivées, aucun numéro gratuit n’est inclus. [Les paramètres de stratégie d’audioconférence pour les numéros payants et gratuits](audio-conferencing-toll-free-numbers-policy.md) contiennent plus d’informations.

> [!IMPORTANT]
> Les réunions périodiques anciennes et planifiées précédemment peuvent toujours afficher des numéros gratuits et les participants ne pourront pas participer à ces réunions à l’aide d’un numéro gratuit. Vous pouvez replanifier toutes les réunions anciennes et périodiques pour ces utilisateurs et supprimer des numéros gratuits à l’aide de MMS.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
