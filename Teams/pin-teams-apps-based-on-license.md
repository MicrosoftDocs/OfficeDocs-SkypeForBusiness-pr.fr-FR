---
title: Personnaliser des Teams adaptées à vos employés en ligne
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez l’expérience d’application personnalisée pour les employés en ligne Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: b91d83739a078b175770c797c17d602eb5c83a4f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2022
ms.locfileid: "63774183"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personnaliser des Teams adaptées à vos employés en ligne

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>Présentation

Teams fournit un moyen simple d’épingler des applications pour les employés en ligne. Cette fonctionnalité épingle les applications en fonction de leur licence pour offrir à vos employés en ligne une expérience pré-adaptée à Teams leurs besoins.

Grâce à l’expérience personnalisée des applications en avant-première, vos employés de première ligne obtiennent les applications les plus pertinentes au Teams sans aucune action requise de la part de l’administrateur.

## <a name="tailored-frontline-app-experience"></a>Expérience personnalisée de l’application en ligne

Les applications sont épinglées à la barre de l’application, qui est la barre dans la partie inférieure des clients mobiles Teams (iOS et Android) et sur le côté du client de bureau Teams. Les applications suivantes sont épinglées pour les utilisateurs titulaires d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) :

- [Activité](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Conversation](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Talkie-walkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Tâches](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Approbations](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams mobile**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="Expérience personnalisée de l’application en ligne sur Teams mobile" lightbox="media/tailored-teams-apps-mobile.png"::: 

**Teams bureau**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="Expérience personnalisée de l’application en ligne sur Teams bureau" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Contrôles d’administration

> [!NOTE]
> Pour **que cette** fonctionnalité prenne effet, le paramètre d’épinglage utilisateur doit être désactivé [](teams-app-setup-policies.md) dans la stratégie de configuration de l’application globale (à l’échelle de l’organisation par défaut).

L’expérience personnalisée en ligne des applications est contrôlée par  le paramètre d’application Afficher les applications personnalisées à l’échelle de l’organisation sur [la page Gérer](manage-apps.md#manage-org-wide-app-settings) les applications du Teams d’administration. Si la fonctionnalité est en cours, tous les utilisateurs de votre organisation  titulaires d’une licence F auront l’expérience d’application personnalisée.

N’oubliez pas que les stratégies [de configuration d’application](teams-app-setup-policies.md) personnalisées attribuées aux utilisateurs sont prioritaire. Cela signifie que si un utilisateur possède déjà une stratégie de configuration d’application personnalisée, il reçoit la configuration définie dans la stratégie de configuration de l’application personnalisée. Pour en savoir plus sur le fonctionnement de la fonctionnalité avec Teams d’application, notamment la stratégie de configuration globale de l’application, voir la section [Scénarios](#scenarios) plus loin dans cet article.

Cette fonctionnalité est activée par défaut. Toutefois, si vous ne souhaitez pas que l’expérience personnalisée de l’application en ligne fournie par Microsoft soit fournie, vous pouvez désactiver la fonctionnalité. Pour désactiver ou activer la fonctionnalité :

1. Dans le navigation gauche du Microsoft Teams d’administration, sélectionnez Teams **applications De** >  **gestion des applications**, puis sélectionnez les paramètres de l’application à l’échelle **de l’organisation**.
2. Sous **Applications personnalisées**, basculez  le bouton bascule Afficher les applications personnalisées **sur Off** ou **On**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Capture d’écran du paramètre Afficher les applications personnalisées dans la page Gérer les applications Teams centre d’administration" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Scénarios

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>En quoi l’expérience de l’application en avant-première personnalisée affecte-t-elle ma stratégie de configuration globale des applications ?

Découvrez comment l’expérience personnalisée de l’application en avant-première fonctionne avec la stratégie de configuration globale de l’application. Les scénarios présentés dans ce tableau s’appliquent aux employés en ligne qui ont une licence F et à la stratégie de configuration globale des applications, avec **l’épinglage** utilisateur désactivé.

|Si... |Puis... |
|---------|---------|
|Un employé en ligne dispose de la stratégie de configuration globale de l’application et la fonctionnalité est off. |Les applications sont définies par le travailleur en ligne dans la stratégie de configuration globale des applications.|
|Un employé en ligne dispose de la stratégie de configuration globale des applications et la fonctionnalité est mise en place.     | L’employé en première ligne obtient l’expérience personnalisée de l’application en première ligne. Les applications définies dans la stratégie de configuration d’application globale sont épinglées sous les applications personnalisées.      |
|Vous mettez à jour la stratégie de configuration de l’application globale et la fonctionnalité est mise en place.     |Les employés en ligne sont en mesure de se faire une expérience d’application en avant-première personnalisée, et les applications définies dans la stratégie de configuration globale des applications sont épinglées sous les applications personnalisées.         |
|Un employé en ligne a la stratégie de configuration globale de l’application et **l’épinglage** d’utilisateurs est désactivé. |Les applications sont définies par le travailleur en ligne dans la stratégie de configuration globale des applications.|
|Un collègue en ligne dispose de la stratégie de configuration globale des applications, et la stratégie de configuration globale de l’application est modifiée pour inclure une application métier à la deuxième position dans la liste d’applications. |L’applicationob est épinglée sous les applications personnalisées. L’employé en ligne peut modifier l’ordre de l’application **si l’épinglage d’utilisateur** est déjà en cours.         |
|Un employé en ligne a la stratégie de configuration globale, et la stratégie de configuration d’applications globale est modifiée pour inclure Shifts à la première position.  |Shifts est épinglé à la sixième position, telle que définie par l’expérience personnalisée de l’application en ligne. L’employé en ligne peut modifier l’ordre de l’application **si l’épinglage d’utilisateur** est déjà en cours.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Comment l’expérience d’application personnalisée en ligne fonctionne-t-elle avec d’Teams d’application ?

Découvrez comment l’expérience personnalisée de l’application en ligne fonctionne avec d’Teams d’application.

|Si...  |Puis... |
|---------|---------|
La fonctionnalité est off.   | Les applications sont définies par les employés en ligne dans la stratégie de configuration globale des applications ou la stratégie de configuration personnalisée de l’application qui leur est affectée.          |
|Un employé en ligne dispose d’une stratégie de configuration d’application personnalisée et la fonctionnalité est mise en place.    |Les applications sont définies par le travailleur en ligne dans la stratégie de configuration de l’application personnalisée.          |
|Une application en première ligne personnalisée est bloquée pour un utilisateur ou votre organisation.      |L’expérience personnalisée de l’application en ligne est adaptée à la stratégie [d’autorisation de l’application](teams-app-permission-policies.md). Si une application est bloquée, le travailleur en première ligne ne verra pas l’application bloquée.           |
|Une application de l’expérience personnalisée en ligne est déjà définie dans une stratégie de configuration d’application et la fonctionnalité est mise en place. |L’application est épinglée selon l’ordre défini par la liste d’applications personnalisée.        |
|Un utilisateur dispose d’une licence E, A ou G et la fonctionnalité est en cours.   | L’utilisateur n’a pas accès à l’expérience personnalisée de l’application en ligne. Pour l’instant, l’expérience s’applique uniquement aux utilisateurs  titulaires d’une licence F.        |

> [!NOTE]
> Vous ne pouvez pas modifier les applications ou l’ordre des applications selon l’expérience personnalisée en ligne des applications. Pour l’instant, si vous voulez apporter des modifications, vous pouvez configurer votre propre expérience personnalisée. Pour ce faire, vous pouvez tout d’abord désactiver la fonctionnalité. Ensuite, [créez une stratégie de configuration d’application](teams-app-setup-policies.md) personnalisée et [affectez-la à des utilisateurs ou des groupes](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Articles connexes

- [Gérer l’application Talkie-walkie dans Teams](walkie-talkie.md)
- [Gérer l’application Tâches dans Teams](manage-tasks-app.md)
- [Gérer l’application Shifts dans Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gérer l’application Approbations dans Teams](approval-admin.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
