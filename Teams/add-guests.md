---
title: Ajouter un invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Découvrez les outils disponibles pour qu'un administrateur ajoute de nouveaux utilisateurs invités à une organisation, y compris les clients web et de bureau de Microsoft Teams et le portail de collaboration Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9a4418600b3ce6d0da99b8b3f18fba186c8b49f
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706282"
---
<a name="add-a-guest-to-a-team"></a>Ajouter un invité à une équipe
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Toute personne possédant un compte de messagerie consommateur ou de l’entreprise, comme Outlook, Gmail ou d’autres personnes, peut participer à en tant qu’invité dans les équipes.

En tant qu'administrateur, vous pouvez ajouter un nouvel utilisateur invité à l'organisation de deux manières : 
- Les administrateurs globaux qui sont propriétaires d'une équipe et les propriétaires d'équipe peuvent ajouter un invité à une équipe via les clients de bureau ou Web Microsoft Teams.
- Ajoutez des invités à votre organisation via Azure Active Directory B2B Collaboration. Azure Active Directory B2B Collaboration permet à un administrateur global d'inviter et d'autoriser un ensemble d'utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) de 2 000 lignes au maximum dans le portail B2B Collaboration. Pour plus d'informations, consultez la section [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).

Azure Active Directory B2B Collaboration permet aux organisations d'imposer l'accès conditionnel et les stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B. Ces stratégies peuvent être imposées au niveau du client, de l'application ou d'un utilisateur spécifique, de la même manière qu'elles sont activées pour les employés à plein temps et les membres de l'organisation. Ces stratégies sont imposées au niveau de l'organisation des ressources. Pour plus d'informations, reportez-vous à la rubrique [Accès conditionnel pour les utilisateurs de B2B collaboration](https://go.microsoft.com/fwlink/?linkid=857454). Les utilisateurs invités individuels ne peuvent pas être bloqués.

Les utilisateurs invités que vous avez déjà été ajoutés par le biais d’Azure Active Directory B2B, groupes d’Office 365 ou SharePoint Online êtes prêts à commencer. L'administrateur Office 365 ou un propriétaire d'équipe peut les ajouter dans ses équipes respectives. Si une équipe est déjà rattachée à un groupe Office 365 et qu'un invité est ajouté au groupe, l'invité obtient l'accès à l'équipe. L'ajout d'un invité via le groupe Office 365 ne génère pas d'e-mail d'invitation, un membre de l'équipe devra donc l'en informer.

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Vous pouvez suivre l'ajout d'invités dans Azure Active Directory ou dans le Centre de sécurité &amp; conformité d'Office 365. L'ajout d'un invité dans Microsoft Teams est audité et journalisé comme activité d'administration de groupe Azure AD « Membre ajouté au groupe ». Pour plus de détails, reportez-vous aux documents [Audit et création de rapports relatifs à un utilisateur B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=858884) et [Effectuer des recherches dans le journal d'audit dans le Centre de sécurité &amp; conformité d'Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).

## <a name="guest-access-vs-external-access-federation"></a>Accès invité et l’accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Plus d’informations

[Autoriser l'accès invité dans Microsoft Teams](teams-dependencies.md)</br>
[Activer ou désactiver l’accès invité dans Microsoft Teams](set-up-guests.md)</br>
[Utiliser PowerShell pour contrôler l'accès invité à une équipe](guest-access-powershell.md)