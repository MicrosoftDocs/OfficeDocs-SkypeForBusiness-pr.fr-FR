---
title: Découvrir les modèles teams à l’aide de Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les modèles teams dans Microsoft Graph pour créer des espaces de collaboration avec des canaux pour différentes rubriques et des applications de préinstallation pour fournir du contenu et des services.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772195"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Découvrir les modèles teams à l’aide de Microsoft Graph

> [!NOTE]
> Pour l’instant, les modèles Teams ne prennent pas en charge la création de canaux privés. La création d’un canal privé n’est pas incluse dans les définitions de modèle.

Les modèles teams sont des définitions prédéfinies d’une structure d’équipe conçue pour un projet ou une entreprise. Vous pouvez [créer votre propre modèle dans la console d’administration](get-started-with-teams-templates-in-the-admin-console.md). Microsoft Graph vous permet d’utiliser les modèles prédéfinis. Vous pouvez utiliser les modèles teams pour créer rapidement des espaces de collaboration riches avec des canaux pour différentes rubriques et des applications de préinstallation pour extraire du contenu et des services critiques. Les modèles teams fournissent une structure d’équipe prédéfinie qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation.

Dans cet article, nous allons expliquer les propriétés qui peuvent être définies dans les modèles, les types de modèles de base et la façon dont vous pouvez utiliser quelques requêtes d’exemples pour créer une équipe à partir d’un modèle.

Cet article est pour vous si vous êtes :

- Responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation<br>
- Développeur souhaitant créer par programme une équipe avec des canaux et applications prédéfinis.

## <a name="teams-template-capabilities"></a>Fonctionnalités du modèle équipes

La plupart des propriétés d’une équipe sont incluses et prises en charge par les modèles. Toutefois, certaines propriétés et fonctionnalités ne sont pas prises en charge pour le moment. Le tableau suivant décrit brièvement ce qui est inclus et ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe prises en charge par les modèles teams** | **Propriétés d’équipe non encore prises en charge par les modèles teams** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle de base | Appartenance à une équipe |
| Nom de l’équipe | Image d’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal de favoris automatique | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Dans la prochaine version de Microsoft Teams, nous ajouterons de nouvelles fonctionnalités de modèles, vous retrouverez donc les informations les plus récentes sur les propriétés prises en charge.

## <a name="what-are-base-template-types"></a>Présentation des types de modèles de base

Les types de modèles de base sont des modèles spécifiques créés par Microsoft pour des industries spécifiques. Ces modèles de base contiennent souvent des applications propriétaires qui ne sont pas disponibles dans le Windows Store. De plus, les modèles de base contiennent souvent des propriétés d’équipe qui ne sont pas encore prises en charge individuellement dans les modèles Teams. Découvrez comment utiliser les [modèles d’équipe dans Microsoft Graph](get-started-with-teams-templates.md).

Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux par d’autres propriétés que vous souhaitez spécifier. Certains types de modèles de base contiennent des propriétés qui ne peuvent pas être remplacées.

Par défaut, le modèle de base est défini sur **standard** , qui ne contient aucune application ou propriété spéciale supplémentaire. Vous trouverez ci-dessous la liste actuelle des types de modèles de base disponibles.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Aucune application et aucune propriété supplémentaires |
| Expliquer<br>Équipe de classe | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Logiciels<ul><li>Bloc-notes OneNote pour la classe (épinglé à l’onglet **général** ) </li><li>Application devoirs (épinglée à l’onglet **général** )</li></ul> Propriétés d’équipe :<ul><li>Visibilité de l’équipe définie sur **HiddenMembership** (ne peut pas être substitué)</li></ul> |
| Expliquer<br>Équipe du personnel enseignant | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Logiciels<ul><li>Carnet de notes OneNote du personnel enseignant (ajouté à l’onglet **général** )</li></ul> |
|Expliquer<br>Équipe PLC |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Logiciels<ul><li>Bloc-notes OneNote PLC (épinglé à l’onglet **général** )</ul></li>|
| Revendeur<br>Boutique d’applications | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Canaux<ul><li>Remise du Shift</li><li>LMS</li></ul>Propriétés d’équipe<ul><li>Visibilité de l’équipe définie sur publique</li></ul>Autorisations des membres<ul><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des canaux</li><li>Empêcher les membres d’ajouter ou de supprimer des applications</li><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des connecteurs</li></ul> |
| Revendeur<br>Collaboration avec les responsables | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Canaux<ul><li>LMS</li><li>Opérations</li></ul>Propriétés d’équipe :<ul><li>Visibilité de l’équipe définie sur privée</li></ul>Autorisations des membres :<ul><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des canaux</li><li>Empêcher les membres d’ajouter ou de supprimer des applications</li><li>Empêcher les membres de créer, de mettre à jour ou de supprimer des connecteurs</li></ul>|
| Organisme<br>Rétrocompatibles |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Canaux <ul><li>Annonces\*</li><li>Huddles\*</li><li>Négative</li><li>Spécifient\*</li><li>Formation\*</li></ul>\*Canaux favoris automatiquement |
|Organisme<br>Hôpital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Canaux<ul><li>Annonces\*</li><li>Conformité\*</li><li>Privatives de Troie</li><li>Ressources humaines</li></li><li>Pharmaceutiques</li></ul>\*Canal avec favoris automatique|
|||


Utilisez les modèles suivants pour créer des équipes dans le client Microsoft Teams, ainsi que dans Microsoft Graph.


| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adopter Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Canaux <ul><li>Général</li> <li>Annonces</li> <li>Coin des champions</li> <li>Formulaires d’équipe</li></ul> Logiciels <ul><li>Wiki</li>  <li>Calendrier</li> |
| Gérer un projet |`com.microsoft.teams.template.`<br>`ManageAProject`| Canaux <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Logiciels<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gérer un événement|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et PR</li></ul> Logiciels<ul><li>Wiki</li><li>Associates</li> <li>YouTube</li> <li>Planificateur</li> <li>OneNote</li></ul> |
|Utilisateurs intégrés|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Discussions des employés</li> <li>Formation</li></ul>Logiciels<ul><li>Wiki</li><li>Civile</li></ul>|
|Organiser le support technique| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Canaux<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Logiciels<ul><li>Wiki</li><li>OneNote</li></ul> |
| Collaborer sur les soins du patient| `healthcareWard `| Canaux<ul><li>Général</li><li>Annonces</li><li>Huddles</li><li>Négative</li><li>Spécifient</li><li>Formation</li></ul> Logiciels <ul><li>Wiki</li>|
| Collaborer sur une crise générale ou un événement |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Canaux <ul><li>Général<li>Annonces</li><li>Actualité du monde</li><li>Continuité de l’activité</li><li>Travail distant</li><li>Commes internes</li><li>Commes externes</li><li>Réclamations de clients</li><li>Complimenter</li><li>Mise à jour de la direction</li></ul>Logiciels <ul><li>Éloge</li><li>Wiki</li><li>Associates</li></ul>|
|Collaborer au sein d’une succursale bancaire| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Canaux <ul><li>Général<li>Annonces</li><li>Huddles</li><li>Réunions des clients</li><li>Conseils</li><li>Développement de compétences</li><li>Traitement des prêts</li><li>Réclamations de clients</li><li>Complimenter</li><li>Outils amusants</li><li>Conformité</li></ul>|
|Coordonnées de la réponse d’incident| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Canaux <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Restaurer</li><li>Examiné</li></ul> Logiciels <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planificateur</li></ul>|
|Hôpital| `healthcareHospita`compt |Canaux <ul><li>Général<li>Annonces</li><li>Conformité</li><li>Privatives de Troie</li><li>Ressources humaines</li><li>Pharmaceutiques</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Organiser un Store| `retailStore` |Canaux <ul><li>Général<li>Remise du Shift</li><li>LMS</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Qualité et sécurité |`com.microsoft.teams.`<br>`template.QualitySafety`|Canaux <ul><li>Général<li>Annonces</li><li>Ligne 1</li><li>Ligne 2</li><li>Ligne 3</li><li>Technologique</li><li>Formation</li><li>Tarification</li><li>Outils amusants</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Collaboration avec le responsable commercial| `retailManagerCollaboration` |Canaux <ul><li>Général<li>Opérations</li><li>LMS</li></ul> Logiciels <ul><li>Wiki</li></ul>|
||||

Pour plus d’informations, voir [prendre en main les modèles teams dans le centre d’administration](get-started-with-teams-templates-in-the-admin-console.md) .

## <a name="related-topics"></a>Sujets associés

- [Commencer à utiliser les modèles teams dans la console d’administration](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en Preview)
- [Nouvelle équipe](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Formation à Microsoft Teams pour les administrateurs](itadmin-readiness.md)