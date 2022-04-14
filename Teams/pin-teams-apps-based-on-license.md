---
title: Personnaliser Teams applications pour vos employés de première ligne
author: LanaChin
ms.author: v-lanachin
ms.reviewer: aaglick
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez l’expérience d’application personnalisée pour les employés de première ligne dans Teams.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: b526733558570e4903d9dce43094c7ffa0f7de17
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/14/2022
ms.locfileid: "63774183"
---
# <a name="tailor-teams-apps-for-your-frontline-workers"></a>Personnaliser Teams applications pour vos employés de première ligne

> [!NOTE]
> [!INCLUDE [new-feature-coming-soon-section](includes/new-feature-coming-soon-section.md)]

## <a name="overview"></a>Présentation

Teams offre un moyen simple d’épingler des applications pour les travailleurs de première ligne. Cette fonctionnalité épingle les applications basées sur une licence pour offrir à vos employés de première ligne une expérience de Teams adaptée à leurs besoins.

Grâce à l’expérience d’application de première ligne personnalisée, vos employés de première ligne obtiennent les applications les plus pertinentes dans Teams sans aucune action de la part de l’administrateur.

## <a name="tailored-frontline-app-experience"></a>Expérience d’application de première ligne personnalisée

Les applications sont épinglées à la barre des applications, qui est la barre située en bas de la Teams clients mobiles (iOS et Android) et sur le côté du client de bureau Teams. Les applications suivantes sont épinglées pour les utilisateurs disposant d’une [licence F](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt) :

- [Activité](https://support.microsoft.com/office/explore-the-activity-feed-in-teams-91c635a1-644a-4c60-9c98-233db3e13a56)
- [Conversation](https://support.microsoft.com/office/get-started-with-chat-0b506ce2-eb6d-4fca-9668-e56980ba755e)
- [Teams](https://support.microsoft.com/office/teams-and-channels-in-microsoft-teams-c6d0e61d-a61e-44a6-a972-04f2a8fa4155)
- [Talkie-walkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [Tâches](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)
- [Shifts](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821)
- [Approbations](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)

**Teams mobile**

:::image type="content" source="media/tailored-teams-apps-mobile.png" alt-text="L’expérience d’application de première ligne personnalisée sur Teams mobile" lightbox="media/tailored-teams-apps-mobile.png"::: 

**bureau Teams**

:::image type="content" source="media/tailored-teams-apps-desktop.png" alt-text="L’expérience d’application de première ligne personnalisée sur Teams bureau" lightbox="media/tailored-teams-apps-desktop.png"::: 

## <a name="admin-controls"></a>Contrôles d’administration

> [!NOTE]
> Le paramètre **d’épinglage utilisateur** doit être activé dans la [stratégie d’installation d’application](teams-app-setup-policies.md) globale (par défaut à l’échelle de l’organisation) pour que cette fonctionnalité prenne effet.

L’expérience d’application de première ligne personnalisée est contrôlée par le paramètre **Afficher les applications personnalisées** à l’échelle de l’organisation sur la page [Gérer les applications](manage-apps.md#manage-org-wide-app-settings) du centre d’administration Teams. Si la fonctionnalité est activée, tous les utilisateurs de votre organisation qui disposent d’une licence F bénéficieront de l’expérience d’application personnalisée.

N’oubliez pas que toutes les [stratégies d’installation d’application](teams-app-setup-policies.md) personnalisées affectées aux utilisateurs sont prioritaires. Cela signifie que si une stratégie d’installation d’application personnalisée lui est déjà affectée, l’utilisateur obtient la configuration définie dans la stratégie d’installation d’application personnalisée. Pour en savoir plus sur le fonctionnement de la fonctionnalité avec Teams stratégies d’application, notamment la stratégie d’installation d’application globale, consultez la section [Scénarios](#scenarios) plus loin dans cet article.

Cette fonctionnalité est activée par défaut. Toutefois, si vous ne souhaitez pas utiliser l’expérience d’application de première ligne personnalisée fournie par Microsoft, vous pouvez désactiver la fonctionnalité. Pour désactiver ou activer la fonctionnalité :

1. Dans le volet de navigation gauche du centre d’administration Microsoft Teams, accédez à **Teams applications** **appsManage** > , puis sélectionnez **paramètres d’application à l’échelle de l’organisation**.
2. Sous **Applications personnalisées**, activez **ou** désactivez l’option **Afficher les applications personnalisées**.

    :::image type="content" source="media/tailored-teams-apps-admin-center.png" alt-text="Capture d’écran du paramètre Afficher les applications personnalisées sur la page Gérer les applications du Centre d’administration Teams" lightbox="media/tailored-teams-apps-admin-center.png":::

## <a name="scenarios"></a>Scénarios

### <a name="how-does-the-tailored-frontline-app-experience-affect-my-global-app-setup-policy"></a>Comment l’expérience d’application de première ligne personnalisée affecte-t-elle ma stratégie d’installation d’application globale ?

Découvrez comment l’expérience d’application de première ligne personnalisée fonctionne avec la stratégie d’installation d’application globale. Les scénarios de ce tableau s’appliquent aux travailleurs de première ligne qui disposent d’une licence F et de la stratégie globale d’installation de l’application, avec **l’épinglage utilisateur** activé.

|Si... |Puis... |
|---------|---------|
|Un worker de première ligne a la stratégie d’installation d’application globale et la fonctionnalité est désactivée. |Le worker de première ligne obtient les applications définies dans la stratégie d’installation d’application globale.|
|Un worker de première ligne a la stratégie d’installation d’application globale et la fonctionnalité est activée.     | Le worker de première ligne obtient l’expérience d’application de première ligne personnalisée. Les applications définies dans la stratégie globale d’installation des applications sont épinglées sous les applications personnalisées.      |
|Vous mettez à jour la stratégie d’installation de l’application globale et la fonctionnalité est activée.     |Le worker de première ligne obtient l’expérience d’application de première ligne personnalisée et les applications définies dans la stratégie globale d’installation des applications sont épinglées sous les applications personnalisées.         |
|Un worker de première ligne a la stratégie d’installation d’application globale et **l’épinglage utilisateur** est désactivé. |Le worker de première ligne obtient les applications définies dans la stratégie d’installation d’application globale.|
|Un worker de première ligne a la stratégie d’installation d’application globale, et la stratégie d’installation d’application globale est modifiée pour inclure une application métier à la deuxième position dans la liste des applications. |L’application métier est épinglée sous les applications personnalisées. Le worker de première ligne peut modifier l’ordre de l’application si **l’épinglage de l’utilisateur** est activé.         |
|Un worker de première ligne a la stratégie d’installation globale et la stratégie d’installation d’application globale est modifiée pour inclure Shifts en première position.  |Les décalages sont épinglés à la sixième position, comme défini par l’expérience d’application de première ligne personnalisée. Le worker de première ligne peut modifier l’ordre de l’application si **l’épinglage de l’utilisateur** est activé.          |

### <a name="how-does-the-tailored-frontline-app-experience-work-with-other-teams-app-policies"></a>Comment l’expérience d’application de première ligne personnalisée fonctionne-t-elle avec d’autres stratégies d’application Teams ?

Découvrez comment l’expérience d’application de première ligne personnalisée fonctionne avec d’autres stratégies d’application Teams.

|Si...  |Puis... |
|---------|---------|
La fonctionnalité est désactivée.   | Le worker de première ligne obtient les applications définies dans la stratégie d’installation d’application globale ou la stratégie d’installation d’application personnalisée qui leur est affectée.          |
|Un worker de première ligne a une stratégie de configuration d’application personnalisée et la fonctionnalité est activée.    |Le worker de première ligne obtient les applications définies dans la stratégie d’installation d’application personnalisée.          |
|Une application dans l’expérience d’application de première ligne personnalisée est bloquée pour un utilisateur ou pour votre organisation.      |L’expérience d’application de première ligne personnalisée respecte la [stratégie d’autorisation de l’application](teams-app-permission-policies.md). Si une application est bloquée, le worker de première ligne ne voit pas l’application bloquée.           |
|Une application dans l’expérience d’application de première ligne personnalisée est déjà définie dans une stratégie d’installation d’application et la fonctionnalité est activée. |L’application est épinglée en fonction de l’ordre défini par la liste des applications personnalisées.        |
|Un utilisateur dispose d’une licence E, A ou G et la fonctionnalité est activée.   | L’utilisateur n’obtient pas l’expérience d’application de première ligne personnalisée. Actuellement, l’expérience s’applique uniquement aux utilisateurs disposant d’une licence F.        |

> [!NOTE]
> Vous ne pouvez pas modifier les applications ou l’ordre des applications dans l’expérience d’application de première ligne personnalisée. Pour l’instant, si vous souhaitez apporter des modifications, vous pouvez configurer votre propre expérience personnalisée. Pour ce faire, commencez par désactiver la fonctionnalité. Ensuite, [créez une stratégie d’installation d’application personnalisée](teams-app-setup-policies.md) et [attribuez-la à des utilisateurs ou des groupes](assign-policies-users-and-groups.md).

## <a name="related-articles"></a>Articles connexes

- [Gérer l’application Walkie Talkie dans Teams](walkie-talkie.md)
- [Gérer l’application Tâches dans Teams](manage-tasks-app.md)
- [Gérer l’application Shifts dans Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gérer l’application Approbations dans Teams](approval-admin.md)
- [Gérer les stratégies de mise en application dans Teams](teams-app-setup-policies.md)
- [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md)
