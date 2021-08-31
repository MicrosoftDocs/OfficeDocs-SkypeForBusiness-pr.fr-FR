---
title: Microsoft 365 Groupes et groupes Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Découvrez comment les groupes Microsoft 365 et les appartenances aux groupes fonctionnent avec Microsoft Teams.
ms.openlocfilehash: 4e140d50bb16c9ed99f126662545fb026c3df60a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729733"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 Groupes et groupes Microsoft Teams

Microsoft 365 Les groupes sont le service d’appartenance entre applications dans Microsoft 365. À un niveau de base, un groupe Microsoft 365 est un objet dans Azure Active Directory qui comprend une liste de membres et une couplage aux charges de travail associées, notamment un site d’équipe SharePoint, une boîte aux lettres Exchange partagée, le Planificateur et un espace de travail Power BI. Vous pouvez ajouter ou supprimer des personnes au groupe comme vous le feriez pour n’importe quel autre objet de sécurité basé sur un groupe dans Active Directory.

![Diagramme montrant Microsoft 365 groupes et services associés.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Par défaut, les utilisateurs Microsoft 365 peuvent créer et gérer des groupes. Pour plus d’informations sur Microsoft 365 [](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) de groupe, voir Groupes d’Microsoft 365 et groupes dans [Microsoft 365 poster sur les architectes](teams-architecture-solutions-posters.md#groups-in-microsoft-365) de l’information.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Fonctionnement des Microsoft 365 groupes avec Teams

Lorsque vous créez une équipe, un groupe Microsoft 365 est créé pour gérer l’appartenance à l’équipe. Les services associés au groupe, tels qu’un site SharePoint, un espace Power BI de travail, etc., sont créés en même temps.

Les personnes qui créent des équipes peuvent choisir d’utiliser un groupe Microsoft 365 existant s’ils sont propriétaires de ce groupe. Chaque canal de l’équipe dispose d’un dossier distinct dans la bibliothèque de documents. La création de dossiers directement dans la bibliothèque de documents ne crée pas de canaux dans l’équipe.

Lorsque vous créez un Microsoft 365 groupe dans Outlook ou SharePoint, la boîte aux lettres du groupe est visible dans Outlook. Lors de la création d’une équipe Teams, la boîte aux lettres du groupe est masquée par défaut. Vous pouvez utiliser [l’cmdlet Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) avec le paramètre **HiddenFromExchangeClientsEnabled** pour rendre une boîte aux lettres visible.

## <a name="group-membership"></a>Adhésion à un groupe

Si vous supprimez un membre d’une équipe, il est également supprimé du Microsoft 365 groupe. La suppression du groupe supprime immédiatement l’équipe et les canaux du client Teams client. Si vous supprimez une personne d’un groupe à l’aide du Centre d’administration Microsoft 365, elle n’aura plus accès aux autres aspects de collaboration tels que la bibliothèque de documents SharePoint Online, le groupe Yammer ou les groupes partagés OneNote. Toutefois, ils auront toujours accès aux fonctionnalités de conversation de l’équipe pendant environ deux heures.

Pour gérer les membres d’une équipe, il est préférable de les ajouter et de les supprimer du client Teams pour vous assurer que les mises à jour des autorisations pour les autres charges de travail liées aux groupes se produisent rapidement. Si vous ajoutez ou supprimez des membres d’équipe en dehors du client Teams (à l’aide de Centre d’administration Microsoft 365, Azure AD ou Exchange Online PowerShell), jusqu’à 24 heures peuvent être nécessaires pour que les modifications soient reflétées dans Teams.

## <a name="deleting-groups-and-teams"></a>Supprimer des groupes et des équipes

La suppression d’un groupe Microsoft 365 supprime l’alias de boîte aux lettres des conversations Outlook/OWA persistantes et les invitations aux réunions Teams et marque le site SharePoint pour suppression. La suppression d’une équipe et son effet sur les Outlook prennent environ 20 minutes. La suppression d’une équipe du client Teams supprimera immédiatement la vue de tous les membres de l’équipe. Si vous supprimez des membres d’un groupe Microsoft 365 qui avait activé les fonctionnalités d’Teams, il peut y avoir un délai d’environ deux heures avant que l’équipe ne soit supprimée du client Teams pour les personnes concernées qui ont été supprimées.

Pour plus d’informations sur les options de fin de cycle de vie des groupes et équipes, consultez les options de fin de cycle de vie des [groupes,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) équipes et Yammer et archivez ou supprimez une équipe [dans Microsoft Teams.](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>Sujets associés

[Bases de Microsoft Teams (vidéo)](https://aka.ms/teams-foundations)

[Restaurer un groupe supprimé](/microsoft-365/admin/create-groups/restore-deleted-group)