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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment gérer l’accès aux applications Teams dans Microsoft 365.
ms.openlocfilehash: 114b16dad2a574b217ebc9bf815f42e579b740e8
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271409"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gérer l’accès aux applications Teams dans Microsoft 365

Les développeurs d’applications peuvent améliorer leurs applications Microsoft Teams pour qu’elles fonctionnent dans Outlook et sur Office.com, en plus de l’application qui fonctionne dans Teams. Les utilisateurs finaux peuvent utiliser les applications améliorées sur Teams, dans Microsoft Outlook et Microsoft Office.com après l’amélioration. Actuellement, seuls les utilisateurs finaux de la version ciblée peuvent afficher et utiliser ces applications spécifiques dans Teams, Outlook et Office.com. L’expérience d’administration Teams existante s’applique pour régir l’accès à ces applications. Une notification concernant cette modification est disponible dans le [centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). En tant qu’administrateur Teams, vous pouvez autoriser des utilisateurs finaux spécifiques à utiliser les applications améliorées ou à gérer leur accès aux applications améliorées dans Teams, Dans Outlook et sur Office.com. Les administrateurs Teams utilisent le Centre d’administration Teams pour gérer l’accès aux applications.

Pour une utilisation dans Outlook et Office.com, une application améliorée continue d’utiliser les autorisations existantes accordées dans Teams. Les [autorisations de l’application améliorée ne changent pas](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Voici une liste des applications améliorées :

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)

Vous pouvez contrôler l’accès des utilisateurs finaux aux applications Teams à l’aide des méthodes suivantes. Si vous êtes un administrateur Office Apps, contactez votre administrateur général ou votre administrateur Teams pour gérer l’accès aux applications.

| Options pour gérer l’accès |Portail|Administrateur général|Administrateur de Teams|
|--|---|---|--|
| Seuls les utilisateurs finaux de la version ciblée peuvent accéder à la nouvelle application. Déplacez les utilisateurs vers la version Standard. Consultez [Configurer les options de mise en production standard ou ciblée](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centre d’administration Microsoft 365 | Oui | Non |
| Gérez l’accès à la nouvelle application pour des utilisateurs finaux spécifiques. Consultez [Ajouter une stratégie d’autorisation personnalisée](teams-app-permission-policies.md#create-a-custom-app-permission-policy) et [affecter la stratégie personnalisée à un utilisateur](policy-assignment-overview.md). | Centre d’administration Microsoft Teams | Oui | Oui |
| Gérez l’accès aux nouvelles applications pour tous les utilisateurs finaux au sein de votre organisation. Consultez [Autoriser ou bloquer des applications](manage-apps.md#allow-and-block-apps). | Centre d’administration Microsoft Teams | Oui | Oui |

> [!NOTE]
> Nous vous recommandons d’utiliser [l’option de publication Standard](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) pour gérer l’accès de l’utilisateur final. Les autres options suppriment l’accès de l’utilisateur final et ne pourront plus utiliser l’application existante dans Teams.

> [!NOTE]
> Les utilisateurs qui ont installé un complément sur le marché existant de la même application dans Outlook et Office continueront à utiliser cette application. Les compléments ne sont pas des applications Teams et les administrateurs Teams ne peuvent pas régir l’accès.

## <a name="see-also"></a>Voir aussi

* [Applications Microsoft Teams conçues pour Microsoft 365 disponibles en préversion dans Outlook et Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Comprendre les rôles d’administrateur dans Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [À propos des compléments Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Comment les développeurs étendent les applications Teams pour qu’elles fonctionnent dans Microsoft 365](/microsoftteams/platform/m365-apps/overview)
