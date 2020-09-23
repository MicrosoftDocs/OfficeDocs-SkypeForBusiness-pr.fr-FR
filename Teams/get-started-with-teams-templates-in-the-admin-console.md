---
title: Utiliser les modèles teams pour créer une équipe
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez comment utiliser les modèles teams pour créer des espaces de collaboration avec des canaux pour différentes rubriques utilisant des modèles préinstallés.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e75d7c73393fe57f7ae3eaf8611ef3a3311386d8
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218575"
---
# <a name="get-started-with-teams-templates-in-the-admin-console"></a>Commencer à utiliser les modèles teams dans la console d’administration

[!INCLUDE [template](includes/preview-feature.md)]

**Les modèles personnalisés ne sont pas encore pris en charge pour les clients de la version EDU.**

> [!NOTE]
> Pour l’instant, les modèles Teams ne prennent pas en charge la création de canaux privés. La création d’un canal privé n’est pas incluse dans les définitions de modèle.

Les modèles teams sont des définitions prédéfinies d’une structure d’équipe conçue pour un projet ou une entreprise. Utilisez des modèles prédéfinis ou créez votre propre modèle. Les modèles d’équipes vous permettent de créer rapidement des espaces de collaboration riches avec des canaux pour différentes rubriques et des applications de préinstallation pour extraire des contenus et services stratégiques. Les modèles teams fournissent une structure d’équipe prédéfinie qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation. Pour l’instant, vous pouvez créer une équipe à partir d’un modèle dans teams ou [Microsoft Graph](get-started-with-teams-templates.md).

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

Les types de modèles de base sont des modèles spécifiques créés par Microsoft pour des industries spécifiques. Ces modèles de base contiennent souvent des applications propriétaires disponibles dans le Windows Store.

Une fois qu’un type de modèle de base est défini, vous pouvez étendre ou remplacer ces modèles spéciaux par d’autres propriétés que vous souhaitez spécifier. Toutefois, certains types de modèles de base contiennent des propriétés qui ne peuvent pas être remplacées.

> [!NOTE]
> Les modèles de base prédéfinis fournis par Microsoft teams peuvent être dupliqués mais ne peuvent pas être modifiés.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ |----|----------------------------------------------------- |
| Adopter Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canaux <ul><li>Général</li> <li>Annonces</li> <li>Coin des champions</li> <li>Formulaires d’équipe</li></ul> Logiciels <ul><li>Wiki</li>  <li>Calendrier</li> |
| Gérer un projet |`com.microsoft.teams.template.ManageAProject`| Canaux <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Logiciels<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gérer un événement|`com.microsoft.teams.template.ManageAnEvent` | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et PR</li></ul> Logiciels<ul><li>Wiki</li><li>Associates</li> <li>YouTube</li> <li>Planificateur</li> <li>OneNote</li></ul> |
|Utilisateurs intégrés|`com.microsoft.teams.template.OnboardEmployees` | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Discussions des employés</li> <li>Formation</li></ul>Logiciels<ul><li>Wiki</li><li>Civile</li></ul>|
|Organiser le support technique| `com.microsoft.teams.template.OrganizeHelpDesk`|Canaux<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Logiciels<ul><li>Wiki</li><li>OneNote</li></ul> |
| Collaborer sur les soins du patient| `healthcareWard `| Canaux<ul><li>Général</li><li>Annonces</li><li>Huddles</li><li>Négative</li><li>Spécifient</li><li>Formation</li></ul> Logiciels <ul><li>Wiki</li>|
| Collaborer sur une crise générale ou un événement |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canaux <ul><li>Général<li>Annonces</li><li>Actualité du monde</li><li>Continuité de l’activité</li><li>Travail distant</li><li>Commes internes</li><li>Commes externes</li><li>Réclamations de clients</li><li>Complimenter</li><li>Mise à jour de la direction</li></ul>Logiciels <ul><li>Éloge</li><li>Wiki</li><li>Associates</li></ul>|
|Collaborer au sein d’une succursale bancaire| `com.microsoft.teams.template.CollaborateWithinABankBranch `|Canaux <ul><li>Général<li>Annonces</li><li>Huddles</li><li>Réunions des clients</li><li>Conseils</li><li>Développement de compétences</li><li>Traitement des prêts</li><li>Réclamations de clients</li><li>Complimenter</li><li>Outils amusants</li><li>Conformité</li></ul>|
|Coordonnées de la réponse d’incident| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canaux <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Restaurer</li><li>Examiné</li></ul> Logiciels <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planificateur</li></ul>|
|Hôpital| `healthcareHospita`compt |Canaux <ul><li>Général<li>Annonces</li><li>Conformité</li><li>Privatives de Troie</li><li>Ressources humaines</li><li>Pharmaceutiques</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Organiser un Store| `retailStore` |Canaux <ul><li>Général<li>Remise du Shift</li><li>LMS</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Qualité et sécurité |`com.microsoft.teams.template.QualitySafety`|Canaux <ul><li>Général<li>Annonces</li><li>Ligne 1</li><li>Ligne 2</li><li>Ligne 3</li><li>Technologique</li><li>Formation</li><li>Tarification</li><li>Outils amusants</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Collaboration avec le responsable commercial| `retailManagerCollaboration` |Canaux <ul><li>Général<li>Opérations</li><li>LMS</li></ul> Logiciels <ul><li>Wiki</li></ul>|
||||

Pour plus d’informations sur les catégories de modèles, voir les catégories suivantes :

- [Modèles financiers](financial-teams-templates-in-the-admin-console.md)
- [Modèles généraux](general-teams-templates-in-the-admin-console.md)
- [Modèles gouvernementaux](government-teams-templates-in-the-admin-console.md)
- [Modèles de soins de santé](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modèles de fabrication](manufacturing-teams-templates-in-the-admin-console.md)
- [Modèles commerciaux](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Limites de taille de modèle

Les modèles sont limités à un nombre déterminé de canaux, d’onglets et d’applications.

 > [!Note]
 > Vous pouvez ajouter d’autres canaux, onglets et applications à l’équipe après leur création à partir d’un modèle.

|Fonctionnalité | Plafond|
|-|-|
|Canaux par modèle | 0,15 |
|Onglets par canal dans un modèle | CX3-20 |
|Applications par modèle | 50|
|||

Pour plus d’informations [, voir limites et spécifications de teams](limits-specifications-teams.md) .

## <a name="related-topics"></a>Sujets associés

- [Créer un modèle d’équipe personnalisé](create-a-team-template.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
