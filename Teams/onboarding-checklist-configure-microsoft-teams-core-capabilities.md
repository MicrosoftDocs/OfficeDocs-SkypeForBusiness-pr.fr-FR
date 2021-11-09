---
title: Liste de contrôle d’intégration - Configurer les fonctionnalités principales - Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Suivez les tâches principales et les activités de cette liste de vérification lorsque vous configurez les tâches Teams de votre organisation.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7bce0a3d1b55e0cb0f8c8130c89f390a309967d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865643"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurer Microsoft Teams principales fonctionnalités

| Non | Activité ou tâche | Description | Terminé ? | Informations supplémentaires |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Vérifier que votre environnement inclut toutes les conditions Teams requises | Teams dépend d’autres plateformes pour créer une solution de collaboration de bout en bout. Travaillez avec vos équipes d’it it pour vous assurer que vous avez déployé et correctement configuré Exchange, SharePoint Online et OneDrive Entreprise. | | [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md) |
| 2  | Vérifier qu Teams est activé pour le client | Teams est désactivé par défaut pour toutes les organisations. Consultez la page **&** de l’Centre d'administration Microsoft 365 pour vérifier que Teams est activé pour votre organisation et le cas échéant. | | [Configurer des Microsoft Teams dans Microsoft 365 ou Office 365](office-365-set-up.md) |
| 3  | Configurer les rôles et les autorisations | Teams deux types de rôles : Membre et Propriétaire. <br/><br/>Après avoir ajouté un membre à une équipe, un propriétaire peut également le promouvoir au rôle Propriétaire. Nous vous recommandons d’attribuer au moins deux propriétaires à chaque équipe. <br/><br/>Par défaut, tous les membres de l’organisation qui ont une boîte aux lettres hébergée sur Exchange Online peuvent créer une équipe. Un utilisateur qui crée une équipe se vu automatiquement accorder le rôle Propriétaire pour cette équipe. <br/><br/>Si nécessaire, vous pouvez configurer les paramètres Microsoft 365 groupe pour que des utilisateurs spécifiques créent des équipes. | | [Assigner des rôles et des autorisations dans Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Microsoft 365 groupes et groupes Microsoft Teams](office-365-groups.md) <br/><br/>[Gérer les personnes qui peuvent créer Microsoft 365 groupes](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurer les paramètres d’Teams à l’échelle du client | Vous pouvez configurer certains paramètres Teams client. Les utilisateurs activés pour l Teams héritent de ces paramètres de la configuration client :<ul><li>Général</li><li>Intégration de courrier électronique</li><li>Applications</li><li>Stockage cloud personnalisé</li><li>Appels et réunions</li><li>Messagerie</li></ul>| | [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md) |
| 5  | FACULTATIF : Configurer l’accès invité | Vous utilisez l’accès invité dans Teams pour collaborer avec des personnes extérieures à votre organisation en leur octroyant l’accès aux équipes et aux canaux. L’accès invité est un paramètre au niveau du client Teams. Cette option est désactivée par défaut. <br/>Activez l’accès invité et configurez les paramètres invités à l’échelle du client si votre organisation envisage d’utiliser cette fonctionnalité. | | [Accès invité dans Microsoft Teams](guest-access.md) |
| 6  | FACULTATIF : Configurer Teams de noms | Teams utilise les stratégies d’appellation pour Microsoft 365 de groupes lorsque les utilisateurs créent ou modifient des noms d’équipe. <br/><br/>Par défaut, aucune restriction d’attribution de noms n’est appliquée lorsqu’un utilisateur crée une équipe. <br/><br/>Si vous avez besoin d’appliquer des règles pour les noms d’équipe, configurez Microsoft 365 de noms de groupes applicables à votre organisation. Vous pouvez définir des préfixes et suffixes obligatoires et spécifier des mots bloqués. | | [Planifier des groupes Microsoft 365 lors de la création d’équipes dans Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Microsoft 365 Stratégie de noms de groupes](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurer les Exchange pour le Teams SMTP | Teams utilise Exchange Online pour envoyer des notifications aux membres de l’équipe à l’aide du domaine SMTP (email.teams.microsoft.com) lorsqu’ils ont été ajoutés ou supprimés. <br/><br/>N’oubliez pas d’ajouter ce domaine SMTP à la liste des domaines acceptés de Exchange infrastructure. | | [Créer des listes d’expéditeurs sûrs dans Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurer et gérer l’accès des utilisateurs aux Teams | Bien qu’il soit vivement recommandé d’activer tous les utilisateurs pour Teams, vous pouvez autoriser ou ne pas autoriser l’accès à Teams pour chaque utilisateur en attribuant ou en supprimant la licence Teams produit. | | [Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md) |
| 9  | Attribuer des licences aux utilisateurs | Attribuer des licences à vos utilisateurs pour des fonctionnalités telles que les plans d’audioconférence, de Système téléphonique et d’appel | | [Attribuer Microsoft Teams licences de modules add-on](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Facultatif : utiliser PowerShell pour administrer les Teams | Vous pouvez utiliser des cmdlets PowerShell plutôt que le Centre d'administration Microsoft 365 pour administrer et gérer Teams paramètres. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |