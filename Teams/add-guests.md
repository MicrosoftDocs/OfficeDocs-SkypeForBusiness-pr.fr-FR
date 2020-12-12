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
localization_priority: Normal
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
description: Les administrateurs peuvent apprendre à ajouter de nouveaux invités à une organisation dans la version de bureau et les clients Web de Microsoft Teams, ainsi que dans le portail de collaboration sur Azure Active Directory B2B.
ms.openlocfilehash: 7f75589c5252998fb0389c743b951c0fe88e613b
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662439"
---
# <a name="add-a-guest-to-a-team"></a>Ajouter un invité à une équipe

Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.

En tant qu’administrateur, vous pouvez ajouter un nouvel invité à l’organisation de deux manières :

- Les administrateurs généraux ou les administrateurs Teams et les propriétaires d’équipe ajoutent un invité à une équipe dans les clients Teams ou dans le centre d’administration Teams. Pour plus d’informations, voir [Ajouter des invités dans une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f). Si vous n’avez pas encore configuré l’accès invité, suivez les étapes décrites dans [Collaborer avec des invités au sein d’une équipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).

- Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration. Pour plus d’informations, consultez [l’article démarrage rapide : ajouter des invités à votre annuaire dans le portail Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

Les administrateurs peuvent également déléguer dls autorisations d’ajout d’invités à d’autres membres de leur organisation en leur attribuant le rôle d’inviteur d’invités. Pour plus d’informations, consultez [Activer la collaboration externe B2B et gérer les utilisateurs pouvant inviter des invités](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations).

Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B. Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation. Les stratégies MFA sont appliquées à l’organisation de ressources. Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](https://go.microsoft.com/fwlink/?linkid=857454). Les invités ne peuvent pas être bloqués.

Les invités que vous avez déjà ajoutés par le biais d’Azure AD B2B, de groupes Microsoft 365 ou de SharePoint sont prêts à l’emploi. L’administrateur 365 Microsoft ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives. Si vous ajoutez un invité directement au groupe Microsoft 365 associé à une équipe, l’invité obtient l’accès à l’équipe, mais le groupe Microsoft 365 ne génère pas de message d’invitation à l’invité, de sorte qu’une personne de l’équipe doit notifier l’invité.

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Microsoft 365 ou Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de sécurité Microsoft 365. L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe». Pour plus d’informations, reportez-vous à la rubrique [audit et création de rapports sur un utilisateur de collaboration B2B](https://docs.microsoft.com/azure/active-directory/external-identities/auditing-and-reporting) et [recherchez le journal d’audit dans le centre de conformité](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).


## <a name="related-topics"></a>Sujets associés

[Autoriser l’accès invité dans Microsoft Teams](teams-dependencies.md)

[Activer ou désactiver l’accès invité dans Microsoft Teams](set-up-guests.md)
