---
title: Gérer l’accès aux applications Teams dans Microsoft 365
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 10/24/2022
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment gérer l’accès aux applications Teams dans Microsoft 365.
ms.openlocfilehash: 01aee1ebd59b52f05db36303d60358b86b95cf84
ms.sourcegitcommit: c2d8c7f779f4f938f8355632ecfbfc9147b53bb2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68738800"
---
# <a name="manage-access-to-teams-apps-across-microsoft-365"></a>Gérer l’accès aux applications Teams dans Microsoft 365

Les développeurs d’applications peuvent améliorer leurs applications Microsoft Teams pour qu’elles fonctionnent dans Outlook et sur Office.com, en plus de l’application qui fonctionne dans Teams. Les utilisateurs finaux peuvent utiliser les applications améliorées sur Teams, dans Microsoft Outlook et Microsoft Office.com après l’amélioration. Actuellement, seuls les utilisateurs finaux de [la version ciblée](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) peuvent afficher et utiliser ces applications spécifiques dans Teams, Outlook et Office.com. Une notification concernant cette modification est disponible dans le [centre de messages](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter/:/messages/MC334280).

## <a name="manage-users-access-to-the-enhanced-apps"></a>Gérer l’accès de l’utilisateur aux applications améliorées

L’expérience d’administration Teams existante s’applique pour régir l’accès à ces applications. Les administrateurs Teams utilisent le Centre d’administration Teams pour gérer l’accès aux applications. En tant qu’administrateur Teams, vous pouvez autoriser des utilisateurs finaux spécifiques à utiliser les applications améliorées ou à gérer leur accès aux applications améliorées dans Teams, Dans Outlook et sur Office.com.

Pour une utilisation dans Outlook et Office.com, une application améliorée continue d’utiliser les autorisations existantes accordées dans Teams. Aucune modification n’est apportée aux autorisations de l’application améliorée. Les utilisateurs qui ont installé des compléments existants sur le marché de la même application dans Outlook et Office continueront à utiliser cette application. Les compléments ne sont pas des applications Teams et les administrateurs Teams ne peuvent pas régir l’accès.

Les administrateurs Des applications Office peuvent contacter l’administrateur général ou l’administrateur Teams pour gérer l’accès aux applications améliorées. Pour plus d’informations, consultez [Rôles d’administrateur dans Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true).

Vous pouvez contrôler l’accès des utilisateurs finaux à l’aide des méthodes suivantes.

| Options pour gérer l’accès |Portail|Administrateur général|Administrateur de Teams|
|--|---|---|--|
| Seuls les utilisateurs finaux de la version ciblée peuvent accéder à la nouvelle application. Déplacez les utilisateurs vers la version Standard. Consultez [Configurer les options de mise en production standard ou ciblée](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) | Centre d’administration Microsoft 365 | Oui | Non |
| Gérez l’accès à la nouvelle application pour des utilisateurs finaux spécifiques. Consultez [Ajouter une stratégie d’autorisation personnalisée](teams-app-permission-policies.md#create-an-app-permission-policy) et [affecter la stratégie personnalisée à un utilisateur](policy-assignment-overview.md). | Centre d’administration Microsoft Teams | Oui | Oui |
| Gérez l’accès aux nouvelles applications pour tous les utilisateurs finaux au sein de votre organisation. Consultez [Autoriser ou bloquer des applications](manage-apps.md#allow-and-block-apps). | Centre d’administration Microsoft Teams | Oui | Oui |

> [!NOTE]
> Nous vous recommandons d’utiliser [l’option de publication Standard](/microsoft-365/admin/manage/release-options-in-office-365?view=o365-worldwide&preserve-view=true) pour gérer l’accès de l’utilisateur final. Les autres options suppriment l’accès de l’utilisateur final et ne pourront plus utiliser l’application existante dans Teams.

## <a name="list-of-enhanced-apps"></a>Liste des applications améliorées

La liste des applications améliorées est ci-dessous :

* [Adobe Acrobat Sign](https://teams.microsoft.com/l/app/0f56a9d1-f502-40f9-a9e8-816d7adbb68b?source=app-details-dialog)
* [Plus gros cerveaux eLearning](https://teams.microsoft.com/l/app/12345514-afee-abcd-acde-c5b34109abcd?source=app-details-dialog)
* [Bookings](https://teams.microsoft.com/l/app/4c4ec2e8-4a2c-4bce-8d8f-00fc664a4e5b?source=app-details-dialog)
* [e2e-assure](https://teams.microsoft.com/l/app/8bdf3437-e038-4a93-abdc-00461630f6c3?source=app-details-dialog)
* [ESi-Tik](https://teams.microsoft.com/l/app/fe9627db-f23e-42b1-b454-d4d1ca5af33e?source=app-details-dialog)
* [Lentille](https://teams.microsoft.com/l/app/cfaeb687-adc7-4e36-a847-39bb35bfb631?source=app-details-dialog)
* [Monday.com](https://teams.microsoft.com/l/app/eab2d3ce-6d6a-4415-abc4-5f40a8317b1f)
* [Mural](https://teams.microsoft.com/l/app/c738b607-88dd-4f16-aefe-6a824c65d25d)
* [Mes autocollants](https://teams.microsoft.com/l/app/46fae4d0-faf5-11e9-80f3-53ad33b77bce?source=app-details-dialog)
* [Outils PDF](https://teams.microsoft.com/l/app/ca4b5141-5c46-47bc-a05e-2733d9bd69aa?source=app-details-dialog)
* [Power BI](https://teams.microsoft.com/l/app/1c4340de-2a85-40e5-8eb0-4f295368978b)
* [Priority Matrix](https://teams.microsoft.com/l/app/5be2b320-a5b7-4221-893c-dee506e4e365?source=app-details-dialog)
* [Smart Connect pour Jira](https://teams.microsoft.com/l/app/6402de97-ce33-4386-bf28-b37e9e139c09?source=app-details-dialog)
* [Bientôt la planification](https://teams.microsoft.com/l/app/bf280b0d-b87d-4158-9f2a-70b63674cd27?source=app-details-dialog)
* [Rationaliser](https://teams.microsoft.com/l/app/aa6e7fb6-34ac-4947-9c13-3565c66e368b?source=app-details-dialog)
* [SurveyMonkey](https://teams.microsoft.com/l/app/0fd925a0-357f-4d25-8456-b3022aaa41a9)
* [Transcription Assistant TNA2](https://teams.microsoft.com/l/app/32c31ccd-b878-470e-9259-98c079ae5528?source=app-details-dialog)
* [Umbiko](https://teams.microsoft.com/l/app/23fc1de6-dda0-4043-9ebb-a555e845843d?source=app-details-dialog)
* [Waldo](https://teams.microsoft.com/l/app/1d041f16-ab49-4627-bfda-6b60ad2cab6a?source=app-details-dialog)
* [YouTube](https://teams.microsoft.com/l/app/com.microsoft.teamspace.tab.youtube)
* [Zoho Projects](https://teams.microsoft.com/l/app/4a39aea9-8537-4c2f-b66d-ca364eb3b80d)

## <a name="related-articles"></a>Articles connexes

* [Applications Microsoft Teams conçues pour Microsoft 365 disponibles en préversion dans Outlook et Office.com](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-teams-apps-designed-for-microsoft-365-coming-in/ba-p/3269538)
* [Comprendre les rôles d’administrateur dans Microsoft 365](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide&preserve-view=true)  
* [À propos des compléments Outlook](/office/dev/add-ins/outlook/outlook-add-ins-overview)
* [Comment les développeurs étendent les applications Teams pour qu’elles fonctionnent dans Microsoft 365](/microsoftteams/platform/m365-apps/overview)
