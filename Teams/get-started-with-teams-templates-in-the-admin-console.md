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
ms.openlocfilehash: 8cb72ba0fce238a89b1d087baef16a30cb2d55d3
ms.sourcegitcommit: 3814db70796888f15ea47d7810e1621a92992870
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/11/2020
ms.locfileid: "46634730"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>Commencer à utiliser les modèles teams dans la console d’administration teams

[!INCLUDE [template](includes/preview-feature.md)]

**Les modèles personnalisés ne sont pas encore pris en charge pour les clients de la version EDU.**

> [!NOTE]
> Pour l’instant, les modèles Teams ne prennent pas en charge la création de canaux privés. La création d’un canal privé n’est pas incluse dans les définitions de modèle.

Les modèles teams sont des définitions prédéfinies d’une structure d’équipe conçue pour un projet ou une entreprise. Utilisez des modèles prédéfinis ou créez votre propre modèle. Les modèles d’équipes vous permettent de créer rapidement des espaces de collaboration riches avec des canaux pour différentes rubriques et des applications de préinstallation pour extraire des contenus et services stratégiques. Les modèles teams fournissent une structure d’équipe prédéfinie qui peut vous aider à créer facilement des équipes cohérentes au sein de votre organisation. Pour l’instant, vous pouvez créer une équipe à partir d’un modèle dans teams ou [Microsoft Graph](get-started-with-teams-templates.md).

Dans cet article, nous allons expliquer les propriétés qui peuvent être définies dans les modèles, les types de modèles de base et la façon dont vous pouvez utiliser quelques exemples de requête pour créer une équipe à partir d’un modèle.

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


| Type de modèle de base | Propriétés fournies avec ce modèle de base |
| ------------------ |----------------------------------------------------- |
| Adopter Office 365 |  Canaux <ul><li>Général</li> <li>Annonces</li> <li>Coin des champions</li> <li>Formulaires d’équipe</li></ul> Logiciels <ul><li>Wiki</li>  <li>Calendrier</li> |
| Gérer un projet | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Logiciels<ul><li>Wiki</li><li>OneNote</li></ul> |
| Gérer un événement | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et PR</li></ul> Logiciels<ul><li>Wiki</li><li>Associates</li> <li>YouTube</li> <li>Planificateur</li> <li>OneNote</li></ul> |
|Utilisateurs intégrés | Canaux <ul><li>Général</li> <li>Annonces</li> <li>Discussions des employés</li> <li>Formation</li></ul>Logiciels<ul><li>Wiki</li><li>Civile</li>|</ul>
|Organiser le support technique| Canaux<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Logiciels<ul><li>Wiki</li><li>OneNote</li></ul> |
| Collaborer sur les soins du patient | Canaux<ul><li>Général</li><li>Annonces</li><li>Huddles</li><li>Négative</li><li>Spécifient</li><li>Formation</li></ul> Logiciels <ul><li>Wiki</li>|
| Collaborer sur une crise générale ou un événement |Canaux <ul><li>Général<li>Annonces</li><li>Actualité du monde</li><li>Continuité de l’activité</li><li>Travail distant</li><li>Commes internes</li><li>Commes externes</li><li>Réclamations de clients</li><li>Complimenter</li><li>Mise à jour de la direction</li></ul>Logiciels <ul><li>Éloge</li><li>Wiki</li><li>Associates</li></ul>|
|Collaborer au sein d’une succursale bancaire |Canaux <ul><li>Général<li>Annonces</li><li>Huddles</li><li>Réunions des clients</li><li>Conseils</li><li>Développement de compétences</li><li>Traitement des prêts</li><li>Réclamations de clients</li><li>Complimenter</li><li>Outils amusants</li><li>Conformité</li></ul>|
|Coordonnées de la réponse d’incident |Canaux <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Restaurer</li><li>Examiné</li></ul> Logiciels <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planificateur</li></ul>|
|Hôpital |Canaux <ul><li>Général<li>Annonces</li><li>Conformité</li><li>Privatives/Li><li>Ressources humaines</li><li>Pharmaceutiques</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Organiser un Store |Canaux <ul><li>Général<li>Remise du Shift</li><li>LMS</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Qualité et sécurité |Canaux <ul><li>Général<li>Annonces</li><li>Ligne 1</li><li>Ligne 2</li><li>Ligne 3</li><li>Technologique</li><li>Formation</li><li>Tarification</li><li>Outils amusants</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|Collaboration avec le responsable commercial |Canaux <ul><li>Général<li>Opérations</li><li>LMS</li></ul> Logiciels <ul><li>Wiki</li></ul>|
|||

## <a name="related-topics"></a>Voir aussi

- [Créer un modèle d’équipe personnalisé](create-a-team-template.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
