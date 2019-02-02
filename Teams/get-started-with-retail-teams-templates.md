---
title: Les modèles d’équipe de vente au détail en main
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 02/01/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les modèles d’équipe pour créer des structures de l’équipe conçus autour des besoins.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e74a7d44709f93fd0ef74917e5fc21103d2a8bbd
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715436"
---
# <a name="get-started-with-retail-teams-templates"></a>Les modèles d’équipe de vente au détail en main 

Les modèles d’équipe permettent de rapidement et facilement créer des équipes en fournissant un modèle prédéfini de paramètres, les canaux et applications préinstallées.

Définitions des structures de l’équipe conçus autour des besoins, les modèles d’équipe commerciale ont prédéfinies. Vous pouvez utiliser les modèles d’équipe de vente au détail pour créer rapidement les types d’équipes qui fonctionnent correctement pour les détaillants et de les déploient dans votre organisation. Vous pouvez également étendre les modèles des équipes de vente au détail pour créer des équipes qui sont adaptées aux besoins spécifiques de votre organisation.

Dans cet article, nous allons présenter chacun des modèles des équipes de vente au détail et comment nous vous recommandons de les utiliser.

Cet article est pour vous si vous êtes responsable de la planification, le déploiement et la gestion de plusieurs équipes au sein de votre organisation vente au détail.

Pour en savoir plus sur l’équipe modèles en général, reportez-vous à [prendre en main les modèles d’équipe](get-started-with-teams-templates.md).

## <a name="store-template"></a>Modèle de magasin

Le modèle de banque d’informations est un des modèles d’équipes de vente au détail. Le modèle de magasin est idéal pour la création d’une équipe pour représenter un emplacement de magasin de vente au détail individuels. À l’aide du modèle de banque, vous pouvez créer une équipe pour chaque emplacement de magasin de vente au détail dans votre organisation.

| Type de modèle de base | baseTemplateId | Propriétés liées à ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Vente au détail- <br>Magasin | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore`| Canaux <ul><li>Déplace la remise\*</li><li>Formation\*</li></ul>\*Canaux auto-favorited<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Public</li></ul> <br>Autorisations de membre <ul><li>Ne peut pas créer mise à jour/supprimer/canaux </li><li>Ne peut pas ajouter/supprimer des applications </li><li>Impossible de créer/mettre à jour/supprimer onglets</li><li>Impossible de créer/mettre à jour/supprimer les connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle de banque de votre organisation :

- Si votre organisation a des services de chaque magasin, ajoutez un canal pour chaque service. Cela facilitera la communication et collaboration au sein du département.

- Si votre organisation a des sites Web interne (par exemple, un site SharePoint), prenez en compte les épinglage sous forme d’onglets dans le canal de l’équipe concernés. Reportez-vous à la documentation [ici](get-started-with-teams-templates.md) pour obtenir des instructions.

## <a name="manager-collaboration-template"></a>Modèle de gestionnaire de Collaboration

Le modèle de Collaboration de gestionnaire est différent de celui des modèles des équipes de vente au détail. Le modèle de Collaboration de gestionnaire est idéal pour la création d’une équipe pour un ensemble de gestionnaires de collaboration entre les magasins/régions/etc. Par exemple, si votre organisation comporte des zones, vous pourrez créer une équipe de Collaboration de gestionnaire de Californie et inclure tous les gestionnaires de magasin de cette région, ainsi que le directeur régional de cette région.

| Type de modèle de base | baseTemplateId | Propriétés liées à ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Vente au détail- <br>Magasin | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration`| Canaux <ul><li>Opérations\*</li><li>Formation\*</li></ul>\*Canaux auto-favorited<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe privée</li></ul> <br>Autorisations de membre <ul><li>Peut créer mise à jour/supprimer/canaux </li><li>Pouvez ajouter/supprimer des applications </li><li>Peut créer/mettre à jour/supprimer onglets</li><li>Peut créer/mettre à jour/supprimer les connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle de Collaboration Manager pour votre organisation :

- Si votre organisation a des sites Web internes (par exemple, un site SharePoint) qui sont pertinents pour les responsables, prenez en compte les épinglage sous forme d’onglets dans un canal d’équipe pertinents (reportez-vous à la documentation [ici](get-started-with-teams-templates.md) pour obtenir des instructions).