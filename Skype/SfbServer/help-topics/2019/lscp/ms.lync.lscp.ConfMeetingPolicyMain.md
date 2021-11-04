---
title: Stratégie de conférence
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 90eaa64e-369e-448d-bac4-2574c7c598b8
ROBOTS: NOINDEX, NOFOLLOW
description: Une stratégie de conférence définit les fonctionnalités dont disposent les utilisateurs au cours d’une conférence (également appelée réunion).
ms.openlocfilehash: 885efa5a8f172106939517d44431ded71fbc5e24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767072"
---
# <a name="conferencing-policy"></a>Stratégie de conférence

Une stratégie de conférence définit les fonctionnalités dont disposent les utilisateurs au cours d’une conférence (également appelée réunion).

Les stratégies de conférence incluent la stratégie globale, ainsi qu’éventuellement une ou plusieurs stratégies de site et utilisateur :

- **Stratégie globale :** La stratégie globale est créée par défaut. Vous pouvez modifier la stratégie globale mais vous ne pouvez pas la supprimer. Si vous essayez de supprimer la stratégie globale, toutes les valeurs par défaut des paramètres sont réinitialisées.

- **Stratégies de site (facultatives) :** Vous pouvez créer une ou plusieurs stratégies de conférence de site, chacune s’applique à un site spécifique. Les stratégies de site remplacent la stratégie globale.

- **Stratégies utilisateur (facultatives) :** Vous pouvez créer une ou plusieurs stratégies de conférence utilisateur, chacune s’applique à un utilisateur ou à un groupe d’utilisateurs spécifique. Les stratégies utilisateur remplacent la stratégie globale et les stratégies de site.

La page **Stratégie de conférence** affiche la liste de toutes les stratégies de conférence définies pour votre organisation.

## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Vous pouvez effectuer les tâches suivantes à partir de la page **Stratégie d’emplacement** :

- Créer une nouvelle stratégie de conférence de site ou stratégie de conférence utilisateur

- Modifier la stratégie globale ou une stratégie de site ou stratégie utilisateur existante

- Supprimer une stratégie de site ou une stratégie utilisateur

## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste suivante décrit les commandes de la page.

- **Nouveau** Démarre une nouvelle stratégie de conférence de site ou de conférence utilisateur.

- **Modifier** Ouvre la stratégie de conférence sélectionnée pour la modifier, sélectionne toutes les stratégies de conférence dans la liste ou supprime la stratégie de site ou la stratégie utilisateur sélectionnée.

    > [!NOTE]
    > Pour la stratégie globale, **Supprimer** rétablit les valeurs par défaut des paramètres.

- **Actualiser** Actualise la liste des stratégies de conférence.

La liste suivante décrit les champs de la page.

- **Nom** Identifie la stratégie de conférence.

- **Étendue** Identifie l’étendue de la stratégie de conférence : globale, de site ou d’utilisateur.

- **Collaboration de données** Vérifié si la stratégie de conférence spécifie que la collaboration de données est autorisée dans les conférences.

- **Partage d’application** Cette vérification indique si la stratégie de conférence spécifie que le partage d’application est autorisé dans les conférences.

- **Audio** Cette vérification est vérifiée si la stratégie de conférence spécifie que l’audio est autorisé dans les conférences.

- **Vidéo** Cette vérification est vérifiée si la stratégie de conférence spécifie que la vidéo est autorisée dans les conférences.

- **PSTN** Cette vérification indique si la stratégie de conférence indique que la conférence d’accès PSTN est autorisée.

- **Enregistrement** Cette vérification indique si la stratégie de conférence spécifie que l’enregistrement est autorisé dans les conférences.

Pour plus d’informations sur les fonctionnalités de conférence, voir [Overview of Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-conferencing) dans la documentation de planification. Pour plus d’informations sur l’utilisation des stratégies de conférence, voir [Conferencing Policies](/previous-versions/office/lync-server-2013/lync-server-2013-conferencing-policies) dans la documentation des opérations.