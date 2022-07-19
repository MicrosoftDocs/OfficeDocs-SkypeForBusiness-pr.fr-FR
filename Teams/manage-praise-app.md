---
title: Gérer l’application Praise dans le Centre d’administration Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.reviewer: rjam
audience: admin
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
description: Découvrez comment gérer l’application Praise dans le Centre d’administration Microsoft Teams.
ms.openlocfilehash: 0b2e733478f309df8ff1c8253b21f01f92d800f9
ms.sourcegitcommit: ea9cbb8e32b7f23c17930eadc0a1dcbd906449ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66842240"
---
# <a name="manage-the-praise-app-in-the-microsoft-teams-admin-center"></a>Gérer l’application Praise dans le Centre d’administration Microsoft Teams

L’application Compliment dans Microsoft Teams aide les utilisateurs à exprimer leur gratitude aux membres de votre organisation ou de votre classe. Les badges de La louange sont conçus pour aider à reconnaître l’effort qui va dans le large éventail de travail que les utilisateurs de Teams font, des enseignants aux travailleurs de première ligne. Pour en savoir plus, consultez [Envoyer des compliments aux gens](https://support.microsoft.com/office/send-praise-to-people-50f26b47-565f-40fe-8642-5ca2a5ed261e).

Les administrateurs doivent disposer d’une licence Teams pour accéder à cette fonctionnalité. Si vous essayez d’accéder à cette fonctionnalité sans licence Teams, un message d’erreur s’affiche.

> [!NOTE]
> L’application Praise est disponible pour l’environnement cloud GCC, mais pas pour GCC High ou DoD.

## <a name="enable-or-disable-praise-in-your-organization"></a>Activer ou désactiver l’éloge dans votre organisation

Les éloges sont activés par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

:::image type="content" source="media/manage-praise-app-admin-center.png" alt-text="Capture d’écran de la page de détails de l’application Compliment dans le Centre d’administration Teams, montrant le bouton bascule État.":::

1. Dans le volet gauche du Centre d’administration Microsoft Teams, accédez à **Applications Teams** > **Gérer les applications**.
2. Dans la liste des applications, recherchez l’application Compliment, sélectionnez-la, puis basculez le bouton bascule **État** sur **Bloqué** ou **Autorisé**.

N’oubliez pas que ce paramètre affecte à la fois l’application Praise et la fonctionnalité Praise dans l’application Viva Insights dans Teams.

Si vous définissez l’état sur Bloquer, l’application Praise est bloquée en quelques minutes pour Teams. Toutefois, les éloges dans Viva Insights peuvent prendre 7 à 9 jours pour être bloqués.

## <a name="enable-or-disable-praise-for-specific-users-in-your-organization"></a>Activer ou désactiver l’éloge pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Praise, assurez-vous que praise est activé pour votre organisation sur la page [Gérer les applications](manage-apps.md) . Créez ensuite une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

## <a name="badges"></a>Badges

Voici l’ensemble de badges par défaut dans Praise. Les utilisateurs Teams de votre organisation peuvent utiliser ces badges pour reconnaître leurs pairs pour aller au-delà de leur travail.

:::image type="content" source="media/default-set-praise.png" alt-text="Image des badges dans le jeu de badges par défaut.":::

> [!NOTE]
> À compter de février 2022, les utilisateurs peuvent uniquement envoyer et recevoir des badges par défaut. Les badges personnalisés ne sont plus disponibles et les options des badges personnalisés ont été supprimées du Centre d’administration Teams.

## <a name="related-articles"></a>Articles connexes

[Gérer vos applications dans le Centre d’administration Microsoft Teams](manage-apps.md)
