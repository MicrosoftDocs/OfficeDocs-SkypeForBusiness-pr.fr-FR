---
title: Rechercher des événements de gestion des applications dans les journaux d’audit
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Découvrez comment auditer les activités d’application Teams des utilisateurs et des administrateurs de votre organisation.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 54cf634fb8da78081023fad3940daf4ef33450c2
ms.sourcegitcommit: 89904ab4116294ad9e4fd407feba8d7e3eefef10
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/19/2022
ms.locfileid: "66880398"
---
# <a name="audit-for-app-management-activities-and-events"></a>Auditer les activités et les événements de gestion des applications

Microsoft Purview Audit (Standard) dans Microsoft 365 vous permet de rechercher les enregistrements d’audit des activités effectuées dans les différents services Microsoft 365 par les utilisateurs finaux et les administrateurs.

Avant de pouvoir effectuer une recherche dans l’audit, veillez à remplir les conditions préalables suivantes :

* [Obtenez l’abonnement de l’organisation et les licences utilisateur](/microsoft-365/compliance/set-up-basic-audit).
* [Activez l’audit dans le portail de conformité Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Attribuez des autorisations pour rechercher dans le journal d’audit](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Rechercher des événements d’application dans les journaux d’audit

Les journaux d’audit des événements d’application dans Teams vous aident à examiner des actions spécifiques. Bien que vous puissiez rechercher un large éventail d’actions dans les journaux d’activité, le tableau suivant répertorie certaines des actions d’application Teams enregistrées. En outre, vous pouvez rechercher des activités liées aux connecteurs, aux bots, aux onglets, etc.

| Action de l’application Teams                  | Nom de l’activité                | Description                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **Application installée**                 | `AppInstalled`               | Une application est installée.                                     |
| **Application mise à niveau**                  | `AppUpgraded`                | Une application est mise à niveau vers sa dernière version dans le catalogue. |
| **Application désinstallée**               | `AppUninstalled`             | Une application est désinstallée.                                   |
| **Application publiée**                 | `AppPublishedToCatalog`      | Une application est ajoutée au catalogue.                          |
| **Application mise à jour**                   | `AppUpdatedInCatalog`        | Une application est mise à jour dans le catalogue.                        |
| **Application supprimée**                   | `AppDeletedFromCatalog`      | Une application est supprimée du catalogue.                      |
| **Toutes les applications de l’organisation ont été supprimées** | `DeletedAllOrganizationApps` | Toutes les applications de l’organisation ont été supprimées du catalogue.          |

Pour obtenir la liste complète des activités Teams auditées, consultez [Activités Teams](audit-log-events.md#teams-activities) et [Plannings dans les activités Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> Les événements d’application provenant de canaux privés sont également enregistrés, car ces événements sont destinés à Teams et aux canaux standard.

Utilisez l’outil de recherche de journaux d’audit dans le portail de conformité pour rechercher des enregistrements d’audit. Pour rechercher des journaux d’audit des événements d’application, procédez comme suit :

1. Connectez-vous au portail de conformité Microsoft Purview et accédez à **Solutions** > **[Audit](https://compliance.microsoft.com/auditlogsearch)**.
1. Dans la page d’audit, mettez à jour les champs suivants en fonction de vos besoins :

   * **Plage de dates et d’heures**: sélectionnez les dates de début et de fin.
   * **Activités**: entrez les activités Microsoft Teams. Dans la liste, sélectionnez une ou plusieurs activités d’application. Pour trouver rapidement les activités Teams, vous pouvez rechercher le mot `Teams activities` dans le champ de recherche **Activités** .
   * **Fichier, dossier ou site**: entrez un nom de fichier, une URL ou une partie de celui-ci.
   * **Utilisateurs**: ajoutez les utilisateurs dont vous souhaitez rechercher le journal d’audit.

1. Sélectionner **Rechercher**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Recherchez des activités Teams dans le portail de conformité Microsoft Purview pour auditer les événements Teams." lightbox="media/compliance-search-teams-activities.png":::

Après avoir recherché la connexion d’audit dans le portail de conformité, vous pouvez exporter les enregistrements d’audit en tant que fichier CSV. Pour plus d’informations, consultez [Exporter, configurer et afficher les journaux d’audit](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Lorsque l’une des activités ci-dessus est effectuée par un utilisateur ou un administrateur, Teams génère et stocke un enregistrement d’audit. Dans Audit (Standard), les enregistrements sont conservés pendant 90 jours, ce qui signifie que vous pouvez rechercher des activités qui se sont produites au cours des trois derniers mois.

## <a name="see-also"></a>Voir aussi

* [Utiliser les journaux d’audit pour examiner l’activité d’installation de Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Recherchez le signe d’audit dans le portail de conformité](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Vue d’ensemble de Microsoft Purview Audit Premium](/microsoft-365/compliance/advanced-audit).
* [Activez ou désactivez l’audit](/microsoft-365/compliance/turn-audit-log-search-on-or-off).