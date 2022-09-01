---
title: Gérer l’accès aux applications Teams dans Microsoft 365
author: ashishguptaiitb
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
ms.openlocfilehash: a555343fc8207a3c538b6b2d8901ad5a3602cf9f
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486969"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gérer l’accès aux applications Teams dans Microsoft 365

Les développeurs d’applications peuvent améliorer leurs applications Microsoft Teams pour qu’elles fonctionnent dans Outlook et sur Office.com, en plus de l’application qui fonctionne dans Teams. Les utilisateurs finaux peuvent utiliser les applications améliorées sur Teams, dans Microsoft Outlook et Microsoft Office.com après l’amélioration. Actuellement, seuls les utilisateurs finaux de la version ciblée peuvent afficher et utiliser ces applications spécifiques dans Teams, Outlook et Office.com. L’expérience d’administration Teams existante s’applique pour régir l’accès à ces applications. Une notification concernant cette modification est disponible dans le [centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). En tant qu’administrateur Teams, vous pouvez autoriser des utilisateurs finaux spécifiques à utiliser les applications améliorées ou à gérer leur accès aux applications améliorées dans Teams, Dans Outlook et sur Office.com. Les administrateurs Teams utilisent le Centre d’administration Teams pour gérer l’accès aux applications.

Pour une utilisation dans Outlook et Office.com, une application améliorée continue d’utiliser les autorisations existantes accordées dans Teams. Les [autorisations de l’application améliorée ne changent pas](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Les applications améliorées sont répertoriées ci-dessous :

* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Outils PDF](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Cerveaux plus grands eLearning](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Waldo](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)

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
