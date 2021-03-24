---
title: Groupes Microsoft 365 et Microsoft Teams
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: Découvrez comment les groupes Microsoft 365 et les appartenances aux groupes fonctionnent avec Microsoft Teams.
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105240"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Groupes Microsoft 365 et Microsoft Teams

Groupes Microsoft 365 est le service d’appartenance entre applications dans Microsoft 365. À un niveau de base, un groupe Microsoft 365 est un objet dans Azure Active Directory qui comprend une liste de membres et une couplage à des charges de travail associées, notamment un site d’équipe SharePoint, une boîte aux lettres Exchange partagée, un planificateur et un espace de travail Power BI. Vous pouvez ajouter ou supprimer des personnes au groupe comme vous le feriez pour n’importe quel autre objet de sécurité basé sur un groupe dans Active Directory.

![Diagramme montrant les groupes Microsoft 365 et les services associés](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Par défaut, les utilisateurs de Microsoft 365 peuvent créer et gérer des groupes. Pour plus d’informations sur les groupes Microsoft 365, voir La poster Sur les groupes [Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) et les groupes [dans l’affiche Microsoft 365 pour les](teams-architecture-solutions-posters.md#groups-in-microsoft-365) architectes de l’information.

## <a name="how-microsoft-365-groups-work-with-teams"></a>Fonctionnement des groupes Microsoft 365 avec Teams

Lorsque vous créez une équipe, un groupe Microsoft 365 est créé pour gérer l’appartenance à une équipe. Les services associés au groupe, tels qu’un site SharePoint, un espace de travail Power BI, etc., sont créés en même temps.

Les personnes qui créent des équipes peuvent choisir d’utiliser un groupe Microsoft 365 existant s’ils sont propriétaires de ce groupe. Chaque canal de l’équipe dispose d’un dossier distinct dans la bibliothèque de documents. La création de dossiers directement dans la bibliothèque de documents ne crée pas de canaux dans l’équipe.

Lors de la création d’un groupe Microsoft 365 dans Outlook ou SharePoint, la boîte aux lettres du groupe est visible dans Outlook. Lorsque vous créez une équipe dans Teams, la boîte aux lettres du groupe est masquée par défaut. Vous pouvez utiliser [l’cmdlet Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) avec le paramètre **HiddenFromExchangeClientsEnabled** pour rendre une boîte aux lettres visible.

## <a name="group-membership"></a>Adhésion à un groupe

Si vous supprimez un membre d’une équipe, il est également supprimé du groupe Microsoft 365. La suppression du groupe supprime immédiatement l’équipe et les canaux du client Teams. Si vous supprimez une personne d’un groupe à l’aide du Centre d’administration Microsoft 365, celle-ci n’aura plus accès aux autres aspects de collaboration tels que la bibliothèque de documents SharePoint Online, le groupe Yammer ou OneNote partagé. Toutefois, ils auront toujours accès aux fonctionnalités de conversation de l’équipe pendant environ deux heures.

Il est préférable de gérer les membres d’une équipe en les ajoutez et en les supprimez du client Teams pour vous assurer que les mises à jour des autorisations pour les autres charges de travail liées aux groupes se produisent rapidement. Si vous ajoutez ou supprimez des membres d’équipe en dehors du client Teams (à l’aide du Centre d’administration Microsoft 365, d’Azure AD ou d’Exchange Online PowerShell), jusqu’à 24 heures peuvent être nécessaires pour que les modifications soient reflétées dans Teams.

## <a name="deleting-groups-and-teams"></a>Supprimer des groupes et des équipes

La suppression d’un groupe Microsoft 365 supprime l’alias de boîte aux lettres pour les conversations Outlook/OWA persistantes et les invitations aux réunions Teams, et marque le site SharePoint pour suppression. La suppression d’une équipe et son effet sur Outlook prennent environ 20 minutes. La suppression d’une équipe du client Teams supprimera immédiatement l’affichage de tous les membres de l’équipe. Si vous supprimez des membres d’un groupe Microsoft 365 qui avait activé les fonctionnalités Teams, il peut y avoir un délai d’environ deux heures avant que l’équipe ne soit supprimée de l’affichage dans le client Teams pour les personnes affectées qui ont été supprimées.

Pour plus d’informations sur les options de fin de cycle de vie des groupes et équipes, consultez les options de fin de cycle de vie des [groupes,](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) équipes et Yammer et archivez ou supprimez une équipe dans [Microsoft Teams.](./archive-or-delete-a-team.md)

## <a name="related-topics"></a>Rubriques connexes

[Bases de Microsoft Teams (vidéo)](https://aka.ms/teams-foundations)

[Restaurer un groupe supprimé](/microsoft-365/admin/create-groups/restore-deleted-group)