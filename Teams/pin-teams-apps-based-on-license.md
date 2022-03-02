---
title: Personnaliser vos applications Teams en fonction de leur licence
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment épingler des Teams pour les utilisateurs de votre organisation en fonction de leur licence.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d9c316c042230237089d57c23156cf6ac5284c6
ms.sourcegitcommit: 5b1d8d6f811fab0b350a09e5187d982f952d0edb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63047194"
---
# <a name="tailor-your-teams-apps-based-on-license"></a>Personnaliser vos applications Teams en fonction de leur licence

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

> [!NOTE]
> Actuellement, cette fonctionnalité s’applique aux licences F. Par conséquent, cet article se concentre sur l’expérience des employés en première ligne. D’autres types de licence seront pris en charge à l’avenir.

## <a name="overview"></a>Vue d’ensemble

Teams permet d’épingler des applications en fonction de leur licence. Lorsqu’un utilisateur se Teams l’expérience d’application personnalisée est activée, l’utilisateur reçoit une expérience d’application personnalisée en fonction de sa licence.

Cette fonctionnalité offre aux utilisateurs les applications les plus pertinentes dans Teams sans aucune action requise de la part de l’administrateur.

## <a name="tailored-app-experience"></a>Expérience d’application personnalisée

Les applications sont épinglées à la barre de l’application, qui est la barre sur le côté du client de bureau Teams et en bas des clients mobiles Teams (iOS et Android).

Applications épinglées pour les utilisateurs  titulaires d’une licence F :

- Viva Connections
- Activité
- Conversation
- Équipes
- Talkie-walkie
- Tâches
- Shifts
- Approbations

## <a name="admin-controls"></a>Contrôles d’administration

> [!NOTE]
> Pour que cette fonctionnalité prenne effet, l’épinglage d’utilisateur doit [](teams-app-setup-policies.md) être désactivé dans la stratégie de configuration de l’application globale (à l’échelle de l’organisation par défaut).

La fonctionnalité d’expérience d’application personnalisée est contrôlée par l’option Afficher les applications **personnalisées** en fonction du paramètre des licences à l’échelle de l’organisation sur [la page Gérer](manage-apps.md#manage-org-wide-app-settings) les applications du Centre d Teams’administration. Si la fonctionnalité est en cours, tous les utilisateurs de votre organisation  titulaires d’une licence F auront l’expérience d’application personnalisée.

N’oubliez pas que les stratégies de configuration d’application personnalisées attribuées aux utilisateurs sont prioritaire. Cela signifie que si un utilisateur possède déjà une stratégie de configuration d’application personnalisée, il reçoit la configuration définie dans la stratégie de configuration de l’application personnalisée. Pour en savoir plus sur l’utilisation de cette fonctionnalité avec les stratégies de configuration d’application existantes que vous avez [appliquées](#scenarios) dans votre organisation, voir la section Scénarios de cet article.

Cette fonctionnalité est activée par défaut. Toutefois, si vous ne souhaitez pas que l’expérience d’application personnalisée fournie par Microsoft soit fournie, vous pouvez désactiver la fonctionnalité. Pour désactiver ou activer la fonctionnalité :

1. Dans le navigation gauche du Microsoft Teams d’administration, sélectionnez Teams **applications De** >  **gestion des applications**, puis sélectionnez les paramètres de l’application à l’échelle **de l’organisation**.
2. Sous **Applications personnalisées**, basculez vers l’application Afficher les applications personnalisées en fonction du bouton bascule des **licences** **sur** **Off ou On**.

## <a name="scenarios"></a>Scénarios

Utilisez les informations de ce tableau pour découvrir le fonctionnement de la fonctionnalité d’expérience d’application personnalisée dans différents scénarios, notamment lorsque vous avez appliqué des stratégies de configuration d’application existantes.

|Si...  |Puis... |
|---------|---------|
|Un utilisateur dispose de la stratégie de configuration globale de l’application et la fonctionnalité est mise en place.     | L’expérience de l’application est personnalisée pour l’utilisateur. Les applications définies dans la stratégie de configuration d’application globale sont toujours épinglées et apparaissent plus bas dans la liste des applications épinglées.      |
|Un utilisateur a une stratégie de configuration d’application personnalisée et la fonctionnalité est mise en place.    |L’utilisateur obtient la configuration définie dans la stratégie de configuration de l’application personnalisée.          |
|La fonctionnalité est mise en place et vous mettez à jour la stratégie de configuration globale de l’application.     |L’utilisateur peut obtenir l’expérience d’application personnalisée en fonction de sa licence. Les applications définies dans la stratégie de configuration d’application globale sont toujours épinglées et apparaissent plus bas dans la liste des applications épinglées.          |
|La fonctionnalité est désactivée.   | L’utilisateur reçoit l’expérience définie dans la stratégie de configuration d’application globale ou la stratégie de configuration personnalisée qui lui est affectée.          |
|Un utilisateur dispose d’une licence E, A ou G et la fonctionnalité est en cours.   | L’expérience d’application personnalisée ne s’offre pas à l’utilisateur. Pour l’instant, l’expérience d’application personnalisée s’applique uniquement aux utilisateurs  titulaires d’une licence F.        |
|Une application dans l’expérience d’application personnalisée est bloquée pour un utilisateur ou votre organisation.      |L’expérience d’application personnalisée est adaptée à la stratégie d’autorisation de l’application. Si une application est bloquée, les utilisateurs ne peuvent pas l’être.           |
|Une application dans l’expérience d’application personnalisée est déjà définie dans une stratégie de configuration d’application et la fonctionnalité est mise en place. |L’application est épinglée selon l’ordre défini par l’expérience d’application personnalisée.        |

> [!NOTE]
> Vous ne pouvez pas modifier les applications ou l’ordre des applications dans l’expérience d’application personnalisée. Pour l’instant, si vous voulez apporter des modifications, vous pouvez configurer votre propre expérience personnalisée. Pour ce faire, vous pouvez tout d’abord désactiver la fonctionnalité. Ensuite, [créez une stratégie de configuration d’application](teams-app-setup-policies.md) personnalisée et [affectez-la à des utilisateurs ou des groupes](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Articles connexes

- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
