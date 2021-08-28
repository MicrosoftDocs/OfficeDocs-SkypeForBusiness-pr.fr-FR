---
title: Ajouter un invité à une équipe
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
search.appverid: MET150
ms.reviewer: rafarhi
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Les administrateurs peuvent découvrir comment ajouter de nouveaux invités à une organisation dans Microsoft Teams clients de bureau et web et Azure Active Directory portail de collaboration B2B.
ms.openlocfilehash: e70b32face0948446ba084f0150dc4da7c9a69b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611773"
---
# <a name="add-a-guest-to-a-team"></a>Ajouter un invité à une équipe

Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.

En tant qu’administrateur, vous pouvez ajouter un nouvel invité à l’organisation de deux façons :

- Les administrateurs généraux ou les administrateurs Teams et les propriétaires d’équipe ajoutent un invité à une équipe dans les clients Teams ou dans le centre d’administration Teams. Pour plus d’informations, voir [Ajouter des invités dans une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Si vous n’avez pas encore configuré l’accès invité, suivez les étapes décrites dans [Collaborer avec des invités au sein d’une équipe](/microsoft-365/solutions/collaborate-as-team).

- Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration. Pour plus d’informations, consultez le démarrage rapide : ajouter des invités à votre annuaire [dans le portail Azure.](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal)

Les administrateurs peuvent également déléguer dls autorisations d’ajout d’invités à d’autres membres de leur organisation en leur attribuant le rôle d’inviteur d’invités. Pour plus d’informations, consultez [Activer la collaboration externe B2B et gérer les utilisateurs pouvant inviter des invités](/azure/active-directory/external-identities/delegate-invitations).

Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B. Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation. Les stratégies MFA sont appliquées à l’organisation de ressources. Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](/azure/active-directory/external-identities/conditional-access). Les invités individuels ne peuvent pas être bloqués.

Les invités que vous avez déjà ajoutés via Azure AD B2B, Microsoft 365 groupes de personnes ou SharePoint sont prêts. L Microsoft 365 administrateur ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives. Si vous ajoutez un invité directement au groupe Microsoft 365 associé à une équipe, l’invité pourra accéder à l’équipe, mais le groupe Microsoft 365 ne génère pas d’e-mail d’invitation, un membres de l’équipe devra donc l’en informer.

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Microsoft 365 ou Office 365](/office365/servicedescriptions/office-365-service-descriptions-technet-library) et [Azure Active Directory](/azure/active-directory/external-identities/current-limitations).

Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de sécurité Microsoft 365. L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe». Pour plus d’informations, voir Audit et signalement d’un utilisateur de [collaboration B2B](/azure/active-directory/external-identities/auditing-and-reporting) et Effectuer des recherches dans le journal d’audit [dans le Centre de conformité.](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)


## <a name="related-topics"></a>Rubriques connexes

[Autoriser l’accès invité dans Microsoft Teams](teams-dependencies.md)

[Activer ou désactiver l’accès invité dans Microsoft Teams](set-up-guests.md)