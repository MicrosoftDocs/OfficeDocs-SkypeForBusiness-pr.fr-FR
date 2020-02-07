---
title: Prise en main des modèles Teams de vente au détail
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les modèles teams pour créer des structures d’équipe conçues pour les besoins des détaillants.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 31c6b04531b21996f897b3d668fdb6515f1e953f
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836814"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Prise en main des modèles Teams de vente au détail 

Les modèles d’équipes vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d’applications déjà installées.

Les modèles d’équipes sont dotés de définitions prédéfinies de structures d’équipe conçues en fonction des besoins des détaillants. Vous pouvez utiliser les modèles teams pour créer rapidement des types d’équipes adaptées aux détaillants et à déployer au sein de votre organisation. Vous pouvez également développer les modèles teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.

Dans cet article, nous allons présenter chacun des modèles d’équipes et la façon dont nous vous conseillons de les utiliser.

Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation commerciale. Nous partons du principe que vous avez déjà déployé teams service au sein de votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire la rubrique [comment déployer Microsoft teams](How-to-roll-out-teams.md).

Pour en savoir plus sur les modèles d’équipe en général, consultez la rubrique [commencer à utiliser les modèles](get-started-with-teams-templates.md)Teams.

## <a name="store-template"></a>Modèle du Windows Store

Le modèle Windows Store est idéal pour créer une équipe et représenter une adresse de magasin commerciale individuelle. À l’aide du modèle Windows Store, vous pouvez créer une équipe pour chaque emplacement de magasin commercial au sein de votre organisation.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Revendeur <br>Enregistrer | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canaux <ul><li>Transfert de décalage\*</li><li>LMS\*</li></ul>\*Canaux favoris automatiquement<br><br>Propriétés d’équipe <ul><li>Visibilité de l’équipe définie sur publique</li></ul> <br>Autorisations des membres <ul><li>Création/mise à jour/suppression de canaux impossible </li><li>Impossible d’ajouter/supprimer des applications </li><li>Impossible de créer/mettre à jour/supprimer des onglets</li><li>Création/mise à jour/suppression de connecteurs impossible</li><ul>|
||||

Méthodes conseillées pour personnaliser le modèle Windows Store pour votre organisation :

- Si votre organisation a des services dans chaque banque, ajoutez un canal pour chaque service. Cela facilite la communication et la collaboration au sein du service.

- Si votre organisation a des sites Web internes (par exemple, un site SharePoint), envisagez de les épingler en tant qu’onglets du canal d’équipe approprié. Pour obtenir des instructions, voir [commencer à utiliser les modèles teams](get-started-with-teams-templates.md) .

## <a name="manager-collaboration-template"></a>Modèle de collaboration responsable

Le modèle de collaboration responsable est l’un des modèles d’équipe pour les besoins des détaillants. Le modèle de collaboration responsable est idéal pour créer une équipe pour un ensemble de responsables pour collaborer entre des boutiques et des régions, etc. Par exemple, si votre organisation a des régions, vous pouvez créer une équipe de collaboration en chef pour la région Californie et inclure tous les responsables du Windows Store de cette région ainsi que le responsable régional de cette région.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Revendeur <br>Enregistrer | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canaux <ul><li>Opérations\*</li><li>LMS\*</li></ul>\*Canaux favoris automatiquement<br><br>Propriétés d’équipe <ul><li>Visibilité de l’équipe définie sur privée</li></ul> <br>Autorisations des membres <ul><li>Création/mise à jour/suppression de canaux </li><li>Ajout/suppression d’applications </li><li>Peut créer/mettre à jour/supprimer des onglets</li><li>Création/mise à jour/suppression de connecteurs possibles</li><ul>|
||||

Méthodes conseillées pour personnaliser le modèle de collaboration responsable de votre organisation :

- Si votre organisation a des sites Web internes (par exemple, un site SharePoint) qui sont appropriés pour les responsables, envisagez de les épingler en tant qu’onglets dans un canal d’équipe approprié (voir la documentation [ici](get-started-with-teams-templates.md) pour obtenir des instructions).
