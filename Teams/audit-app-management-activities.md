---
title: Rechercher des événements de gestion des applications dans les journaux d’audit
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Découvrez comment auditer les activités d’application Teams des utilisateurs et des administrateurs de votre organisation.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5aee5bf00d486586b4bc8e9583504be5e4a9b922
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251877"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>Rechercher dans les journaux d’audit les activités et événements de gestion des applications

Microsoft Purview Audit (Standard) dans Microsoft 365 vous permet de rechercher les enregistrements d’audit des activités effectuées dans les différents services Microsoft 365 par les utilisateurs finaux et les administrateurs.

Avant de pouvoir effectuer une recherche dans les enregistrements d’audit, veillez à remplir les conditions préalables suivantes :

* [Obtenez l’abonnement de l’organisation et la licence utilisateur](/microsoft-365/compliance/set-up-basic-audit).
* [Activez l’audit dans le portail de conformité Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Attribuez des autorisations pour rechercher dans le journal d’audit](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Rechercher des événements d’application dans les journaux d’audit

Les journaux d’audit des événements d’application dans Teams vous aident à examiner des actions spécifiques liées à la gestion des applications par les administrateurs. Bien que vous puissiez rechercher dans les journaux un large éventail d’actions, le tableau suivant répertorie certaines actions de ce type qui sont journalisées.

| Action de l’application Teams | Nom de l’activité dans le portail | Description  |
|-------|-------|:-------|
| **Application installée**                 | `AppInstalled`               | Une application est installée ou ajoutée à un client Teams. |
| **Application mise à niveau**                  | `AppUpgraded`                | Une application est mise à niveau vers sa dernière version dans le catalogue. |
| **Application désinstallée**               | `AppUninstalled`             | Une application est désinstallée ou supprimée d’un client Teams.                                   |
| **Application publiée**                 | `AppPublishedToCatalog`      | Une application est ajoutée au catalogue.                          |
| **Application mise à jour**                   | `AppUpdatedInCatalog`        | Une application est mise à jour dans le catalogue.                        |
| **Application supprimée**                   | `AppDeletedFromCatalog`      | Une application est supprimée du catalogue.                      |
| **Toutes les applications de l’organisation ont été supprimées** | `DeletedAllOrganizationApps` | Toutes les applications de l’organisation ont été supprimées du catalogue.          |

<!--- organization apps = custom or 3p --->

Pour obtenir la liste complète des activités Teams auditées, consultez [Activités Teams](audit-log-events.md#teams-activities) et [Plannings dans les activités Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Les événements d’application provenant de canaux privés sont également enregistrés à mesure que ces événements sont effectués dans Teams et dans les canaux standard.

Pour effectuer une recherche dans les journaux d’audit des activités d’application Teams, procédez comme suit :

1. Connectez-vous au portail de conformité Microsoft Purview et accédez à **Solutions** > **[Audit](https://compliance.microsoft.com/auditlogsearch)**.
1. Dans la page **Audit** , mettez à jour les champs suivants en fonction des besoins :

   * **Plage de dates et d’heures** : sélectionnez les dates de début et de fin de la période pour laquelle vous souhaitez vérifier les journaux d’audit.
   * **Activités**: entrez les activités Microsoft Teams. Dans la liste, sélectionnez une ou plusieurs activités d’application. Pour trouver rapidement les activités Teams, vous pouvez rechercher le mot `Teams activities` dans le champ de recherche **Activités** .
   * **Fichier, dossier ou site**: entrez un nom de fichier, une URL ou une partie de celui-ci.
   * **Utilisateurs**: ajoutez les utilisateurs dont vous souhaitez rechercher le journal d’audit.

1. Sélectionner **Rechercher**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Recherchez des activités Teams dans le portail de conformité Microsoft Purview pour auditer les événements Teams." lightbox="media/compliance-search-teams-activities.png":::

Vous pouvez exporter les enregistrements d’audit recherchés sous forme de fichier CSV. Pour plus d’informations, consultez [Exporter, configurer et afficher les journaux d’audit](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Lorsque l’une des activités ci-dessus est effectuée par un utilisateur ou un administrateur, Teams génère et stocke un enregistrement d’audit. Dans Audit (Standard), les enregistrements sont conservés pendant 90 jours, ce qui signifie que vous pouvez rechercher des activités qui se sont produites au cours des trois derniers mois.

> [!TIP]
> En tant qu’administrateur, si vous souhaitez créer un rapport par utilisateur pour savoir si un utilisateur a bloqué ou désactivé un bot, consultez [Comprendre qui a bloqué, désactivé ou désinstallé un bot](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Articles connexes

* [Utiliser les journaux d’audit pour examiner l’activité d’installation de Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Recherchez le signe d’audit dans le portail de conformité](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Vue d’ensemble de Microsoft Purview Audit Premium](/microsoft-365/compliance/advanced-audit).
* [Activez ou désactivez l’audit](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
