---
title: Gérer l’application Compliment dans le Centre d’administration Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: how-to
ms.service: msteams
ms.localizationpriority: medium
description: Découvrez comment gérer l’application Compliment dans le centre d’administration Microsoft Teams.
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.openlocfilehash: 9b1155560c0f901b88d3983e2ff3738e5ffa6e47
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251767"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gérer l’application Compliment dans le centre d’administration Microsoft Teams

L’application Compliment dans Microsoft Teams permet aux utilisateurs de montrer leur appréciation aux membres de votre organisation ou de votre classe. Les badges dans Compliment sont conçus pour aider à reconnaître l’effort qui va dans le vaste éventail de tâches que les utilisateurs de Teams effectuent, des enseignants aux employés de première ligne. Pour en savoir plus, consultez [Envoyer des éloges aux personnes](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Les administrateurs doivent disposer d’une licence Teams pour accéder à cette fonctionnalité. Si vous essayez d’accéder à cette fonctionnalité sans licence Teams, un message d’erreur s’affiche.

> [!NOTE]
> L’application Compliment est disponible pour l’environnement cloud gcc, mais pas pour GCC High ou DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Activer ou désactiver l’éloge dans votre organisation

L’option Compliment est activée par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Capture d’écran de la page des détails de l’application Compliment dans le Centre d’administration Teams, montrant le bouton bascule État.":::

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **Applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, recherchez l’application Compliment, sélectionnez-la, puis basculez le bouton bascule **État** sur **Bloqué** ou **Autorisé**.

Gardez à l’esprit que ce paramètre affecte à la fois l’application Compliment et la fonctionnalité Compliment dans l’application Viva Insights dans Teams.

Si vous définissez l’état sur **Bloqué**, l’application Compliment est bloquée en quelques minutes pour Teams. Toutefois, praise dans Viva Insights peut prendre 7 à 9 jours pour être bloqué.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Activer ou désactiver l’éloge pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Compliment, assurez-vous que l’option Compliment est activée pour votre organisation dans la page [Gérer les applications](manage-apps.md) . Créez ensuite une stratégie personnalisée pour les autorisations d’application et affectez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

## <a name="composer"></a>Compositeur

Les utilisateurs Teams de votre organisation peuvent utiliser le compositeur de compliments pour reconnaître leurs pairs pour aller au-delà de leur travail. Tout en créant leur message, ils peuvent choisir parmi 14 titres&mdash;comme **Courage**, **Optimisme**, **Bon cœur** et **Créatif**&mdash;pour reconnaître les contributions de leurs collègues.

:::image type="content" source="media/praise.png" alt-text="Capture d’écran du compositeur d’éloges.":::

## <a name="related-articles"></a>Articles connexes

Vous gérez les applications pour votre organisation dans les [applications Teams au sein du centre d’administration Microsoft Teams](manage-apps.md).
