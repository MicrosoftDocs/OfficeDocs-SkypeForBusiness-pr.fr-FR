---
title: Groupes Microsoft 365 et Microsoft teams
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
description: En savoir plus sur l’utilisation des groupes et des appartenances aux groupes Microsoft 365 avec Microsoft Teams.
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456078"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a>Groupes Microsoft 365 et Microsoft teams

Microsoft 365 groups est le service d’appartenance à plusieurs applications de Microsoft 365. À un niveau de base, un groupe Microsoft 365 est un objet dans Azure Active Directory avec une liste de membres et un couplage aux charges de travail associées, y compris un site d’équipe SharePoint, une boîte aux lettres Exchange partagée, un planificateur et un espace de travail Power BI. Vous pouvez ajouter ou supprimer des personnes dans le groupe comme vous le feriez pour n’importe quel autre objet de sécurité en groupe dans Active Directory.

![Diagramme montrant les groupes Microsoft 365 et les services associés](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

Par défaut, les utilisateurs de Microsoft 365 peuvent créer et gérer des groupes. Pour plus d’informations sur les groupes Microsoft 365, voir [en savoir plus sur les groupes microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) et les [groupes dans Microsoft 365 pour les architectes informatiques](teams-architecture-solutions-posters.md#groups-in-microsoft-365) .

## <a name="how-microsoft-365-groups-work-with-teams"></a>Fonctionnement des groupes Microsoft 365 avec teams

Lorsque vous créez une équipe, un groupe Microsoft 365 est créé pour gérer l’appartenance à une équipe. Les services liés du groupe, tels qu’un site SharePoint, l’espace de travail Power BI, etc., sont créés en même temps.

Les personnes qui créent des équipes peuvent choisir d’utiliser un groupe Microsoft 365 existant s’il s’agit d’un propriétaire de ce groupe. Chaque canal de l’équipe possède un dossier distinct dans la bibliothèque de documents. La création de dossiers directement dans la bibliothèque de documents ne crée pas de canaux dans l’équipe.

Lors de la création d’un groupe Microsoft 365 dans Outlook ou SharePoint, la boîte aux lettres de groupe est visible dans Outlook. Lors de la création d’une équipe dans Teams, la boîte aux lettres du groupe est masquée par défaut. Vous pouvez utiliser l’applet de cmdlet [Set-unifiedgrouphttps](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) avec le paramètre **HiddenFromExchangeClientsEnabled** pour rendre une boîte aux lettres visible.

## <a name="group-membership"></a>Adhésion à un groupe

Si vous supprimez un membre d’une équipe, il est également supprimé du groupe Microsoft 365. La suppression du groupe entraîne la suppression immédiate de l’équipe et des canaux du client Teams. Si vous supprimez un membre d’un groupe à l’aide du centre d’administration Microsoft 365, il n’aura plus accès aux autres aspects de la collaboration tels que la bibliothèque de documents SharePoint Online, le groupe Yammer ou le partage OneNote. Toutefois, ils pourront toujours accéder à la fonctionnalité de conversation de l’équipe pendant environ deux heures.

Dans le cadre de la gestion des membres de l’équipe, ajoutez-les ou supprimez-les dans le client teams pour vous assurer que les mises à jour des autorisations pour les autres charges de travail connectées au groupe se produisent rapidement. Si vous ajoutez ou supprimez des membres d’équipe en dehors du client Teams (à l’aide du centre d’administration Microsoft 365, d’Azure AD ou d’Exchange Online PowerShell), les modifications peuvent être répercutées dans Teams.

## <a name="deleting-groups-and-teams"></a>Supprimer des groupes et des équipes

La suppression d’un groupe Microsoft 365 entraîne la suppression de l’alias de boîte aux lettres pour les invitations aux réunions Outlook Le retrait d’une équipe et son impact sur Outlook sont d’environ 20 minutes. La suppression d’une équipe du client teams le supprime immédiatement de l’affichage de tous les membres de l’équipe. Si vous supprimez des membres d’un groupe Microsoft 365 pour lequel la fonctionnalité d’équipe est activée, il peut y avoir un délai d’environ deux heures avant la suppression de l’équipe dans le client teams pour les personnes concernées qui ont été supprimées.

Pour plus d’informations sur les groupes et les équipes, reportez-vous à la section  [de la fin de vie pour les groupes, équipes et Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) et [archiver ou supprimer une équipe dans Microsoft teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).

## <a name="related-topics"></a>Rubriques connexes

[Notions de bases de Microsoft Teams (vidéo)](https://aka.ms/teams-foundations)

[Restaurer un groupe supprimé](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)