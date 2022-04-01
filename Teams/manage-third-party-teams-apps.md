---
title: Gérer l’accès Teams aux applications dans Microsoft 365
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
description: Gérez l’accès Teams d’applications dans Microsoft 365.
ms.openlocfilehash: a9a0eb67323874e725510342e1e6810dcc5c0b0d
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592999"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gérer l’accès Teams aux applications dans Microsoft 365

Les développeurs d’applications peuvent améliorer Microsoft Teams applications pour qu’elles fonctionnent dans Outlook et sur Office.com, en plus de l’application qui fonctionne dans Teams. Les utilisateurs finaux peuvent utiliser les applications améliorées sur Teams, dans Microsoft Outlook et Microsoft Office.com après l’amélioration. Actuellement, seuls les utilisateurs finaux dans le programme de publication ciblée peuvent afficher et utiliser ces applications spécifiques dans Teams, Outlook et Office.com. L’expérience Teams actuelle de l’administrateur s’applique au contrôle de l’accès à ces applications. Une notification concernant cette modification est disponible dans le centre [de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280). En tant qu’administrateur Teams, vous pouvez autoriser des utilisateurs finaux spécifiques à utiliser les applications améliorées ou à gérer leur accès aux applications améliorées dans Teams, Outlook et sur Office.com. Teams les administrateurs utilisent le centre Teams’administration pour gérer l’accès aux applications.

Pour une utilisation dans Outlook et Office.com, une application améliorée continue d’utiliser les autorisations existantes accordées dans Teams. Les [autorisations de l’application améliorée ne changent pas](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-building-apps-for-collaboration-in-a-hybrid-world/#personal-tabs).

Voici une liste des applications améliorées :

* [Mur](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9?source=app-details-dialog)
* [Projets Zoho](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d?source=app-details-dialog)

Vous pouvez contrôler l’accès des utilisateurs aux applications Teams’aide des méthodes suivantes. Si vous êtes un administrateur Office applications, contactez votre administrateur global ou votre administrateur Teams pour gérer l’accès aux applications.

| Options de gestion de l’accès |Portail|Administrateur global|Teams administrateur|
|--|---|---|--|
| Seuls les utilisateurs finaux dans le programme de publication ciblée peuvent accéder à la nouvelle application. Déplacez les utilisateurs vers la version standard. Voir [Configurer les options de publication standard ou ciblée](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centre d'administration Microsoft 365 | Oui | Non |
| Gérez l’accès à la nouvelle application pour des utilisateurs finaux spécifiques. Voir [Ajouter une stratégie d’autorisation personnalisée](teams-app-permission-policies.md#create-a-custom-app-permission-policy) et [l’affecter à un utilisateur](policy-assignment-overview.md). | Teams d’administration | Oui | Oui |
| Gérez l’accès aux nouvelles applications pour tous les utilisateurs finaux au sein de votre organisation. Voir [Autoriser ou bloquer des applications](manage-apps.md#allow-and-block-apps). | Teams d’administration | Oui | Oui |

> [!NOTE]
> Nous vous recommandons [d’utiliser l’option de publication standard](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) pour gérer l’accès des utilisateurs finux. Les autres options suppriment l’accès des utilisateurs finux, qui ne pourront plus utiliser l’application existante dans Teams.

> [!NOTE]
> Les utilisateurs qui ont installé un des modules logiciels sur le marché existants de la même application dans Outlook et Office continueront d’utiliser cette application. Les Teams ne peuvent pas être ajoutés et Teams administrateurs ne peuvent pas en régir l’accès.

## <a name="see-also"></a>Voir aussi

* [Microsoft Teams applications conçues pour les Microsoft 365 disponibles en version Preview pour Outlook et Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Comprendre les rôles d’administrateur dans Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [À propos Outlook les modules](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Comment les développeurs étendent Teams aux applications pour qu’Microsoft 365](/microsoftteams/platform/m365-apps/overview)
