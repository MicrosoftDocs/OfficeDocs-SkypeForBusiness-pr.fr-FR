---
title: Appel de stratégies dans Microsoft Teams
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 04/15/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Découvrez les paramètres de stratégie d’appel dans Microsoft Teams.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20dc75dfeb39fbd7a00e6c389dc923617265cc0b
ms.sourcegitcommit: 946c77b847c1b2c5c43802ecfb0a918fa4f562d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/15/2019
ms.locfileid: "31869805"
---
<a name="calling-policies-in-microsoft-teams"></a>Appel de stratégies dans Microsoft Teams
==========================================

Dans Microsoft Teams, appel de contrôle des stratégies les appels et les fonctionnalités de transfert d’appel sont disponibles pour les utilisateurs. Les stratégies d’appel déterminent si un utilisateur peut effectuer des appels privées, utilisez le transfert d’appel ou acheminer les appels vers la messagerie vocale, envoyer les appels aux groupes d’appel, sonnerie simultanée à d’autres utilisateurs ou les numéros de téléphone externe, utilisent la délégation pour les appels entrants et sortants, et ainsi de suite. Une stratégie globale par défaut est créée automatiquement, mais les administrateurs peuvent également créer et affecter des stratégies appel personnalisés.

## <a name="calling-policy-settings"></a>Paramètres de stratégie de l’appel

|Paramètre de stratégie de l’appel | Description |
|-----------------------|-------------|
|Utilisateur peut passer des appels privées | Contrôle de toutes les fonctionnalités d’appel dans les équipes. Désactivation de cette désactiver toutes les fonctionnalités d’appel dans les équipes.|
|Le transfert d’appel et la sonnerie simultanée à d’autres utilisateurs | Contrôle si les appels entrants peuvent être transférés à d’autres utilisateurs ou une autre personne peut faire sonner en même temps. |
|Le transfert d’appel et la sonnerie simultanée aux numéros de téléphone externe | Contrôle si les appels entrants peuvent être transférés vers un numéro externe ou un numéro externe peut faire sonner en même temps.|
|Messagerie vocale est disponible pour acheminer les appels entrants vers les utilisateurs | Permet les appels entrants soient envoyées à la messagerie vocale. Les options valides sont **toujours activés**, **toujours désactivés**ou **définis par les utilisateurs**. |
|Les appels entrants peuvent être acheminés pour appeler des groupes | Contrôle si les appels entrants peuvent être transférés vers un groupe d’appel.  |
|Autoriser la délégation pour les appels entrants et sortants | Permet aux appels entrants destinés à être acheminés vers les délégués ; permet de délégués pour émettre des appels sortants part les utilisateurs pour lesquels ils ont délégué des autorisations. |
|Empêcher le contournement de média payant et envoyer les appels par le biais de la passerelle PSTN | La valeur **sur** pour envoyer les appels via RTC et provoquer des frais plutôt qu’à passer par le réseau et en contournant le cas. |
|Occupé (e) sur occupé (e) est disponible dans un appel.| Configure les appels entrants comment sont traités lorsqu’un utilisateur est déjà dans un appel ou une conférence. Nouveaux appels entrants peuvent être rejetées avec un signal occupé (e). |

### <a name="busy-options-busy-on-busy-setting"></a>Options de disponibilité (occupé (e) dans le paramètre occupé (e))

Options de disponibilité est un nouveau paramètre dans les équipes appelant stratégies qui permet de configurer les appels entrants comment sont traités lorsqu’un utilisateur est déjà dans un appel ou une conférence ou a un appel mis en attente. Nouveaux appels entrants peuvent être rejetées avec un signal occupé (e). Vous pouvez activer les options occupé (e) à un niveau client ou à un niveau de l’utilisateur. 

Quelle que soit la configuration des options de leurs disponibilitées, les utilisateurs dans un appel ou conférence ou par un appel en attente ne peuvent pas pas d’initier des nouveaux appels ou des conférences.

Vous pouvez utiliser les informations de disponibilité sur occupé (e) paramètre lors de l’appel des paramètres de stratégie pour configurer les options de disponibilité. Ce paramètre est désactivé par défaut.

## <a name="create-a-custom-calling-policy"></a>Créer une stratégie personnalisée appelante

Suivez ces étapes pour créer une nouvelle stratégie appelante personnalisée.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.
2. Sélectionnez **nouvelle stratégie**.
3. Activer les fonctionnalités que vous souhaitez utiliser dans la stratégie de votre appel. Toutes les sélections sont **désactivées** par défaut.
4. Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **toujours activé** ou **définis par les utilisateurs**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **toujours désactivé**.
5. Cliquez sur **Enregistrer**.

## <a name="modify-an-existing-calling-policy"></a>Modifier un appel de stratégie existant

Suivez ces étapes pour modifier une stratégie de l’appel.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.
2. Cliquez sur en regard de la stratégie que vous souhaitez modifier, puis sélectionnez **Modifier**.
3. Activer les fonctionnalités que vous souhaitez utiliser dans la stratégie de votre appel. Toutes les sélections sont **désactivées** par défaut.
4. Pour contrôler si les utilisateurs peuvent router les appels entrants vers la messagerie vocale, sélectionnez **toujours activé** ou **définis par les utilisateurs**. Pour empêcher le routage vers la messagerie vocale, sélectionnez **toujours désactivé**.
5. Cliquez sur **Enregistrer**.

## <a name="assign-a-calling-policy-to-a-user"></a>Affecter une stratégie appelante à un utilisateur

Suivez ces étapes pour attribuer une stratégie personnalisée appelante à un utilisateur.

1. Dans le centre d’administration Microsoft Teams, sélectionnez **voix** > **stratégie de l’appel**.
2. Cliquez sur en regard du nom de la stratégie pour le sélectionner, puis sélectionnez **Gérer les utilisateurs**.
3. Dans le volet **Gérer les utilisateurs** , recherchez le nom d’utilisateur. (Vous devez entrer au moins trois caractères).
4. Sélectionnez le nom d’utilisateur, puis sélectionnez **Ajouter**.
5. Cliquez sur **Enregistrer**.
