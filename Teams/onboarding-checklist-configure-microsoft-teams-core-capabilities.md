---
title: Liste de contrôle d’intégration-configurer les fonctionnalités principales de Microsoft teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Suivez les tâches principales et les activités de cette liste de vérification lorsque vous configurez Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 117486fe944fac080ada57639d6249c917a02a22
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43138334"
---
# <a name="configure-microsoft-teams-core-capabilities"></a>Configurer les fonctionnalités principales de Microsoft teams

| Non | Activité ou tâche | Description | Terminé ? | Informations supplémentaires |
|----|-----------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | Vérifier que votre environnement inclut toutes les conditions préalables pour teams | Teams dépend d’autres plateformes pour créer une solution de collaboration de bout en bout. Travaillez avec vos équipes informatiques pour vous assurer que vous avez déployé et correctement configuré Exchange, SharePoint Online et OneDrive entreprise. | | [Interaction de SharePoint Online et OneDrive Entreprise avec Microsoft Teams](sharepoint-onedrive-interact.md) <br/><br/>[Interaction entre Exchange et Microsoft Teams](exchange-teams-interact.md) |
| deuxième  | Vérifier que l’équipe est activée pour le client | L’option équipes est activée par défaut pour toutes les organisations. Accédez à la page des **compléments & services** dans le centre d’administration Microsoft 365 pour vérifier que teams est activé pour votre client et activez-le si nécessaire. | | [Configurer Microsoft Teams dans votre organisation Office 365](office-365-set-up.md) |
| 3  | Configurer les rôles et les autorisations | Teams prend en charge deux types de rôles : membre et propriétaire. <br/><br/>Une fois qu’un membre a été ajouté à une équipe, il peut également promouvoir un membre au rôle de propriétaire. Il est recommandé d’avoir au moins deux propriétaires attribués à chaque équipe. <br/><br/>Par défaut, tous les membres de l’organisation qui disposent d’une boîte aux lettres hébergée sur Exchange Online peuvent créer une équipe. Un utilisateur qui crée une nouvelle équipe dispose automatiquement du rôle de propriétaire pour cette équipe. <br/><br/>Le cas échéant, vous pouvez configurer les paramètres des groupes Office 365 pour autoriser les utilisateurs spécifiques à créer des équipes. | | [Assigner des rôles et des autorisations dans Microsoft Teams](assign-roles-permissions.md) <br/><br/>[Groupes Office 365 et Microsoft teams](office-365-groups.md) <br/><br/>[Gérer les utilisateurs autorisés à créer des groupes Office 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618) |
| 4  | Configurer les paramètres d’équipes à l’échelle du client | Vous pouvez configurer certains paramètres d’équipes au niveau du client. Les utilisateurs qui sont activés pour les équipes héritent de ces paramètres de la configuration du client :<ul><li>Général</li><li>Intégration de courrier électronique</li><li>Applications</li><li>Stockage cloud personnalisé</li><li>Appels et réunions</li><li>Messagerie</li></ul>| | [Gérer les paramètres de Microsoft Teams pour votre organisation](enable-features-office-365.md) |
| 5  | FACULTATIF : configurer l’accès invité | Vous utilisez l’accès invité dans Microsoft teams pour collaborer avec des personnes extérieures à votre organisation en leur accordant un accès aux équipes et aux canaux. L’accès invité est un paramètre au niveau du client dans Teams. Cette option est désactivée par défaut. <br/>Activez l’accès invité et configurez les paramètres d’invité à l’échelle du client si votre organisation envisage d’utiliser cette fonctionnalité. | | [Accès invité dans Microsoft Teams](guest-access.md) |
| 6  | FACULTATIF : configurer une stratégie d’appellation des équipes | Teams exploite les stratégies d’appellation pour les groupes Office 365 lorsque les utilisateurs créent et modifient les noms des équipes. <br/><br/>Par défaut, aucune restriction d’appellation n’est appliquée lorsqu’un utilisateur crée une équipe. <br/><br/>Si vous devez appliquer des règles pour les noms d’équipes, configurez les stratégies d’attribution de noms de groupes Office 365 qui s’appliquent à votre organisation. Vous pouvez définir des préfixes et des suffixes obligatoires et spécifier des mots bloqués. | | [Planifier les groupes Office 365 lors de la création d’équipes dans Microsoft teams](plan-office-365-groups.md) <br/><br/>[Stratégie d’attribution de noms de groupes Office 365](https://support.office.com/article/Office-365-Groups-naming-policy-6ceca4d3-cad1-4532-9f0f-d469dfbbb552) |
| 7  | Configurer Exchange pour le domaine SMTP teams | Teams utilise Exchange Online pour envoyer des notifications aux membres d’une équipe à l’aide du domaine SMTP, email.teams.microsoft.com, lorsqu’ils ont été ajoutés ou supprimés. <br/><br/>Veillez à ajouter ce domaine SMTP à la liste domaines approuvés dans votre infrastructure Exchange. | | [Ajouter le domaine SMTP de Microsoft Teams comme domaine accepté dans Exchange Online](smtp-accepted-domain.md) |
| version8  | Configurer et gérer l’accès des utilisateurs à teams | Même s’il est vivement recommandé d’activer tous les utilisateurs pour les équipes, vous pouvez autoriser ou interdire l’accès aux équipes par utilisateur en attribuant ou en supprimant la licence de produit Teams. | | [Gérer l’accès des utilisateurs à Microsoft Teams](user-access.md) |
| 09  | Attribution de licences à des utilisateurs | Attribution de licences à vos utilisateurs pour des fonctionnalités telles que l’audioconférence, le système téléphonique et les offres d’appels | | [Affectation de licences Skype entreprise et Microsoft teams](assign-teams-licenses.md)|
| 0,10 | Facultatif : utiliser PowerShell pour gérer teams | Vous pouvez utiliser les applets de applet PowerShell plutôt que le centre d’administration Microsoft 365 pour administrer et gérer les paramètres d’équipe. | | [Microsoft teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) |
