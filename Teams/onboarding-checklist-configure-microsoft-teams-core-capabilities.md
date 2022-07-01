---
title: Liste de vérification de l’intégration - Configurer les fonctionnalités principales - Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Suivez les tâches et activités principales de cette liste de vérification lorsque vous configurez Teams pour votre organisation.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 200edfcbe8c93c2f629f176a17959e60f70cb902
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564242"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurer les fonctionnalités principales de Microsoft Teams

| Non | Activité ou tâche | Description | Terminé ? | Informations supplémentaires |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Vérifiez que votre environnement inclut tous les prérequis Teams | Teams dépend d’autres plateformes pour construire une solution de collaboration de bout en bout. Collaborez avec vos équipes informatiques pour vous assurer que vous avez déployé et correctement configuré Exchange, SharePoint Online et OneDrive Entreprise. | | [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md) |
| 2  | Vérifier que Teams est activé pour le locataire | Teams est activé par défaut pour toutes les organisations. Consultez la page **Services & compléments** dans le Centre d'administration Microsoft 365 pour vérifier que Teams est activé pour votre organisation et l’activer si nécessaire. | | [Configurer Microsoft Teams dans Microsoft 365 ou Office 365](office-365-set-up.md) |
| 3  | Configurer des rôles et des autorisations | Teams prend en charge deux types de rôles : Membre et Propriétaire. <br/><br/>Après avoir ajouté un membre à une équipe, un propriétaire peut également promouvoir un membre au rôle Propriétaire. Nous vous recommandons d’affecter au moins deux propriétaires à chaque équipe. <br/><br/>Par défaut, tous les membres de l’organisation qui disposent d’une boîte aux lettres hébergée sur Exchange Online peuvent créer une équipe. Un utilisateur qui crée une équipe reçoit automatiquement le rôle Propriétaire pour cette équipe. <br/><br/>Si nécessaire, vous pouvez configurer les paramètres de groupe Microsoft 365 pour permettre uniquement à des utilisateurs spécifiques de créer des équipes. | | [Assigner des rôles et des autorisations dans Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Groupes Microsoft 365 et Microsoft Teams](office-365-groups.md) <br/><br/>[Gérer qui peut créer Groupes Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurer les paramètres Teams à l’échelle du locataire | Vous pouvez configurer certains paramètres Teams au niveau du locataire. Les utilisateurs qui sont activés pour Teams héritent de ces paramètres de la configuration du locataire :<ul><li>Général</li><li>Intégration de courrier électronique</li><li>Applications</li><li>Stockage cloud personnalisé</li><li>Appels et réunions</li><li>Messagerie</li></ul>| | [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md) |
| 5  | FACULTATIF : Configurer l’accès invité | Vous utilisez l’accès invité dans Teams pour collaborer avec des personnes extérieures à votre organisation en leur accordant l’accès aux équipes et aux canaux. L’accès invité est un paramètre au niveau du locataire dans Teams. Cette option est désactivée par défaut. <br/>Activez l’accès invité et configurez les paramètres invités à l’échelle du locataire, si votre organisation envisage d’utiliser cette fonctionnalité. | | [Accès invité dans Microsoft Teams](guest-access.md) |
| 6  | FACULTATIF : Configurer la stratégie d’affectation de noms Teams | Teams tire parti des stratégies d’affectation de noms pour Groupes Microsoft 365 lorsque les utilisateurs créent ou modifient des noms d’équipe. <br/><br/>Par défaut, aucune restriction d’affectation de noms n’est appliquée lorsqu’un utilisateur crée une équipe. <br/><br/>Si vous devez appliquer des règles pour les noms d’équipes, configurez Groupes Microsoft 365 stratégies de nommage qui s’appliquent à votre organisation. Vous pouvez définir des préfixes et suffixes obligatoires et spécifier des mots bloqués. | | [Planifier des groupes Microsoft 365 lors de la création d’équipes dans Microsoft Teams](plan-office-365-groups.md) <br/><br/>[Groupes Microsoft 365 stratégie de nommage](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurer Exchange pour le domaine SMTP Teams | Teams utilise Exchange Online pour envoyer des notifications aux membres de l’équipe à l’aide du domaine SMTP ( email.teams.microsoft.com ) lorsqu’ils ont été ajoutés ou supprimés. <br/><br/>Veillez à ajouter ce domaine SMTP à la liste des domaines acceptés dans votre infrastructure Exchange. | | [Créer des listes d’expéditeurs fiables dans Exchange](/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365?view=o365-worldwide) |
| 8  | Configurer et gérer l’accès utilisateur à Teams | Bien que nous vous recommandons vivement d’activer tous les utilisateurs pour Teams, vous pouvez autoriser ou interdire l’accès à Teams par utilisateur en attribuant ou en supprimant la licence de produit Teams. | | [Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md) |
| 9  | Attribuer des licences aux utilisateurs | Attribuer des licences à vos utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les forfaits d’appels | | [Attribuer des licences de module complémentaire Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md)|
| 10 | Facultatif : Utiliser PowerShell pour administrer Teams | Vous pouvez utiliser des applets de commande PowerShell plutôt que la Centre d'administration Microsoft 365 pour administrer et gérer les paramètres Teams. | | [Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) |