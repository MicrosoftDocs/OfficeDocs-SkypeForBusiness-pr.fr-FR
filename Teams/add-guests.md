---
title: Ajouter un invité à une équipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Découvrez les outils mis à la disposition d’un administrateur pour ajouter de nouveaux utilisateurs invités à une organisation, notamment la version de bureau et les clients Web Microsoft teams ainsi que le portail de collaboration inter-entreprise d’Azure Active Directory.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b23ee82e90dea1bc302f14f305274d3ba64d471
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516119"
---
<a name="add-a-guest-to-a-team"></a>Ajouter un invité à une équipe
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

Toutes les personnes ayant un compte de messagerie professionnel ou un compte de particulier tel que Outlook, Gmail, etc. peuvent participer en tant qu’invitées dans Teams.

En tant qu’administrateur, vous pouvez ajouter un nouvel utilisateur invité à l’organisation de deux manières :
- Les administrateurs généraux qui sont propriétaires d’une équipe et les propriétaires d’une équipe peuvent ajouter un invité à une équipe par le biais de la version de bureau de Microsoft teams ou des clients Web. Pour plus d’informations, voir [Ajouter des invités à une équipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).

> [!NOTE] 
> Cela ne s’applique pas lorsque **Les administrateurs et les utilisateurs membres du rôle Inviteur d’invités peuvent inviter** est activé. En effet, le rôle Inviteur d’invités n’est pas pris en charge dans Teams.

- Ajoutez des invités à votre organisation via Azure Active Directory (Azure AD) B2B Collaboration. Azure AD B2B Collaboration permet à un administrateur général d’inviter et d’autoriser un ensemble d’utilisateurs externes en chargeant un fichier de valeurs séparées par des virgules (CSV) comportant au maximum 2 000 lignes via le portail de collaboration B2B. Pour plus d’informations, voir [Azure Active Directory B2B Collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).

Azure AD B2B Collaboration permet aux organisations d'imposer un accès conditionnel et des stratégies d'authentification multifacteur (MFA) aux utilisateurs B2B. Ces stratégies peuvent être appliquées au niveau locataire, application ou utilisateur individuel, de la même façon qu’elles peuvent être activées pour les employés à plein temps et les membres de l’organisation. Les stratégies MFA sont appliquées à l’organisation de ressources. Pour plus d’informations, consultez la page [Accès conditionnel pour les utilisateurs B2B Collaboration](https://go.microsoft.com/fwlink/?linkid=857454). Non, il n’est pas possible de bloquer des utilisateurs invités individuels.

Les invités que vous avez déjà ajoutés via Azure AD B2B, des Groupes Office 365 ou SharePoint Online sont déjà prêts. L’administrateur 365 d’Office ou un propriétaire d’équipe peut ajouter ces invités à leurs équipes respectives. Si une équipe est déjà associée à un groupe Office 365 et qu’un invité est ajouté au groupe, celui-ci est accessible à l’équipe. L’ajout d’un invité par le biais du groupe Office 365 ne génère pas de message d’invitation à l’invité, de sorte qu’une personne de l’équipe doit avertir l’invité.

> [!NOTE]
> Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).

Vous pouvez suivre l'ajout d'invités dans Azure AD ou dans le Centre de conformité de la sécurité &amp; d'Office 365. L’ajout d’un invité dans Microsoft teams est audité et consigné en tant qu’activité d’administration des groupes Azure AD «membre ajouté au groupe». Pour plus d’informations, [voir audit et création de rapports sur un](https://go.microsoft.com/fwlink/p/?linkid=858884) utilisateur [de collaboration B2B et effectuez une recherche dans le &amp; journal d'](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c)audit dans le centre de conformité de la sécurité Office 365.

## <a name="guest-access-vs-external-access-federation"></a>Accès invité et accès externe (fédération)

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a>Plus d’informations

[Autoriser l’accès invité dans Microsoft Teams](teams-dependencies.md)</br>
[Activer ou désactiver l’accès invité dans Microsoft Teams](set-up-guests.md)</br>
[Utiliser PowerShell pour contrôler l’accès invité à une équipe](guest-access-powershell.md)
