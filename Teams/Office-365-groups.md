---
title: Groupes Microsoft 365 et Microsoft Teams
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
ms.openlocfilehash: cf84c58e05e65b187ebe9c0d5a4560cf861fb9be
ms.sourcegitcommit: d16fb01f752d186445893ea8e3b0d4450a4a0e67
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2022
ms.locfileid: "65125429"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Groupes Microsoft 365 et Microsoft Teams

Groupes Microsoft 365 est le service d’appartenance entre applications dans Microsoft 365. Au niveau de base, un groupe Microsoft 365 est un objet dans Azure Active Directory avec une liste de membres et un couplage aux charges de travail associées, notamment un site d’équipe SharePoint, une boîte aux lettres Exchange partagée, le Planificateur et OneNote notebook. Vous pouvez ajouter ou supprimer des personnes au groupe comme vous le feriez pour tout autre objet de sécurité basé sur un groupe dans Active Directory.

![Diagramme montrant Groupes Microsoft 365 et les services associés.](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Par défaut, les utilisateurs de Microsoft 365 peuvent créer et gérer des groupes. Pour plus d’informations sur Groupes Microsoft 365, consultez [l’affiche En savoir plus sur Groupes Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) et les [groupes dans Microsoft 365 pour les architectes informatiques](teams-architecture-solutions-posters.md#groups-in-microsoft-365).

## <a name="how-microsoft-365-groups-work-with-teams"></a>Comment Groupes Microsoft 365 utiliser Teams

Lorsque vous créez une équipe, un groupe Microsoft 365 est créé pour gérer l’appartenance à l’équipe. Les services associés au groupe, tels qu’un site SharePoint, une boîte aux lettres, etc. sont créés en même temps.

Les personnes qui créent des équipes peuvent choisir d’utiliser un groupe Microsoft 365 existant s’ils sont propriétaires de ce groupe. Chaque canal de l’équipe dispose d’un dossier distinct dans la bibliothèque de documents. La création de dossiers directement dans la bibliothèque de documents ne crée pas de canaux dans l’équipe.

Lors de la création d’un groupe Microsoft 365 dans Outlook ou SharePoint, la boîte aux lettres de groupe est visible dans Outlook. Lors de la création d’une équipe dans Teams, la boîte aux lettres de groupe est masquée par défaut. Vous pouvez utiliser l’applet [de commande Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) avec le paramètre **HiddenFromExchangeClientsEnabled** pour rendre une boîte aux lettres visible.

## <a name="group-membership"></a>Adhésion à un groupe

Si vous supprimez un membre d’une équipe, il est également supprimé du groupe Microsoft 365. La suppression du groupe supprime immédiatement l’équipe et les canaux du client Teams. Si vous supprimez une personne d’un groupe à l’aide de la Centre d'administration Microsoft 365, elle n’aura plus accès aux autres aspects collaboratifs tels que SharePoint bibliothèque de documents en ligne, Yammer groupe ou OneNote partagé. Toutefois, ils auront toujours accès aux fonctionnalités de conversation de l’équipe pendant environ deux heures.

Pour gérer les membres de l’équipe, nous vous recommandons de les ajouter et de les supprimer du client Teams pour vous assurer que les mises à jour des autorisations pour d’autres charges de travail connectées à un groupe se produisent rapidement. Si vous ajoutez ou supprimez des membres de l’équipe en dehors du client Teams (à l’aide de la Centre d'administration Microsoft 365, Azure AD ou Exchange Online PowerShell), la répercution des modifications dans Teams peut prendre jusqu’à 24 heures.

## <a name="deleting-groups-and-teams"></a>Suppression de groupes et d’équipes

La suppression d’un groupe de Microsoft 365 supprime l’alias de boîte aux lettres pour les conversations Outlook/OWA persistantes et les invitations à Teams réunion, et marque le site SharePoint à supprimer. Il faut environ 20 minutes entre la suppression d’une équipe et son effet sur Outlook. La suppression d’une équipe du client Teams la supprimera immédiatement de la vue de tous les membres de l’équipe. Si vous supprimez des membres d’un groupe Microsoft 365 dont la fonctionnalité Teams est activée, il peut y avoir un délai d’environ deux heures avant que l’équipe ne soit supprimée de la vue dans le client Teams pour les personnes concernées qui ont été supprimées.

Pour plus d’informations sur les options de fin de cycle de vie des groupes et des équipes, consultez [les options de fin de cycle de vie pour les groupes, les équipes et les Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) et [archiver ou supprimer une équipe dans Microsoft Teams](./archive-or-delete-a-team.md).

## <a name="related-topics"></a>Voir aussi

[Fondations de Microsoft Teams (vidéo)](https://aka.ms/teams-foundations)

[Restaurer un groupe supprimé](/microsoft-365/admin/create-groups/restore-deleted-group)
