---
title: Gérer l’accès aux applications Teams dans Microsoft 365
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Gérez l’accès aux applications Teams dans Microsoft 365.
ms.openlocfilehash: 336c550c4fdf506898d6471cb618652fada95a4f
ms.sourcegitcommit: c2a77ef9c1c9e6f00b3a4589bf02b100c37f5801
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64648983"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gérer l’accès aux applications Teams dans Microsoft 365

Les développeurs d’applications peuvent améliorer leurs applications Microsoft Teams pour qu’elles fonctionnent dans Outlook et sur Office.com, en plus de l’application qui travaille dans Teams. Les utilisateurs finaux peuvent utiliser les applications améliorées sur Teams, dans Microsoft Outlook et Microsoft Office.com après l’amélioration. Actuellement, seuls les utilisateurs finaux de la version ciblée peuvent afficher et utiliser ces applications spécifiques dans Teams, Outlook et Office.com. L’expérience d’administrateur Teams existante s’applique à la gouvernance de l’accès à ces applications. Une notification concernant cette modification est disponible dans le [centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). En tant qu’administrateur Teams, vous pouvez autoriser des utilisateurs finaux spécifiques à utiliser les applications améliorées ou à gérer leur accès aux applications améliorées dans Teams, dans Outlook et sur Office.com. Teams administrateurs utilisent le centre d’administration Teams pour gérer l’accès aux applications.

Pour une utilisation dans Outlook et Office.com, une application améliorée continue d’utiliser les autorisations existantes accordées dans Teams. Les [autorisations de l’application améliorée ne changent pas](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Voici une liste des applications améliorées :

* [Murale](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Projets Zoho](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube?source=app-details-dialog)

Vous pouvez contrôler l’accès des utilisateurs finaux aux applications Teams à l’aide des méthodes suivantes. Si vous êtes administrateur Office Apps, contactez votre administrateur général ou Teams administrateur pour gérer l’accès aux applications.

| Options de gestion de l’accès |Portail|Administrateur général|administrateur Teams|
|--|---|---|--|
| Seuls les utilisateurs finaux de la version ciblée peuvent accéder à la nouvelle application. Déplacez les utilisateurs vers la version Standard. Voir [Configurer les options de mise en production standard ou ciblée](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centre d'administration Microsoft 365 | Oui | Non |
| Gérer l’accès à la nouvelle application pour des utilisateurs finaux spécifiques. Voir [Ajouter une stratégie d’autorisation personnalisée](teams-app-permission-policies.md#create-a-custom-app-permission-policy) et [affecter la stratégie personnalisée à un utilisateur](policy-assignment-overview.md). | centre d’administration Teams | Oui | Oui |
| Gérez l’accès aux nouvelles applications pour tous les utilisateurs finaux de votre organisation. Consultez [Autoriser ou bloquer des applications](manage-apps.md#allow-and-block-apps). | centre d’administration Teams | Oui | Oui |

> [!NOTE]
> Nous vous recommandons [d’utiliser l’option de mise en production Standard](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) pour gérer l’accès des utilisateurs finaux. Les autres options suppriment l’accès de l’utilisateur final et ne pourront plus utiliser l’application existante dans Teams.

> [!NOTE]
> Les utilisateurs qui ont installé des compléments existants sur le marché de la même application dans Outlook et Office continueront d’utiliser cette application. Les compléments ne sont pas Teams applications et Teams administrateurs ne peuvent pas régir l’accès.

## <a name="see-also"></a>Voir aussi

* [Microsoft Teams applications conçues pour Microsoft 365 disponibles en préversion sur Outlook et Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Comprendre les rôles d’administrateur dans Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [À propos des compléments Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Comment les développeurs étendent Teams applications pour qu’elles fonctionnent sur Microsoft 365](/microsoftteams/platform/m365-apps/overview)
