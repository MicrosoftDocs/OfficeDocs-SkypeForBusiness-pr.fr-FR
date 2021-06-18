---
title: Prise en main des modèles Teams de vente au détail
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment utiliser les modèles Teams pour créer des structures d’équipe conçues pour les besoins d’un revendeur en fournissant des paramètres, des canaux et des applications préinstallées.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e0fecf419f6fc3ac0ef15097fe54571d85018587
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101200"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Prise en main des modèles Teams de vente au détail

Les modèles Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.

Les modèles Teams ont des définitions pré-conçues pour les structures d’équipe conçues autour des besoins d’un revendeur. Vous pouvez utiliser des modèles Teams pour créer rapidement les types d’équipes qui fonctionnent bien pour les revendeurs et les déployer au sein de votre organisation. Vous pouvez également étendre les modèles Teams pour créer des équipes adaptées aux besoins spécifiques de votre organisation.

Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de vente au détail. Vous avez déjà déployé le service Teams dans votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire l’article [Comment déployer Microsoft Teams](./deploy-overview.md).

Pour en savoir plus sur les modèles d’équipe en général, consultez [Prise en main des modèles Teams](get-started-with-teams-templates.md).

## <a name="store-template"></a>Modèle Store

Le modèle Store est idéal pour créer une équipe afin de représenter un emplacement de magasin de détail. Le modèle Store vous permet de créer une équipe pour chaque emplacement de vente au détail dans votre organisation.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canaux <ul><li>Procédure de transfert des Plannings\*</li><li>Apprentissage\*</li></ul>\*Canaux ajoutés automatiquement aux favoris<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Public</li></ul> <br>Autorisations de membre <ul><li>Impossible de créer/mettre à jour/supprimer des canaux </li><li>Impossible d’ajouter/supprimer des applications </li><li>Impossible de créer/mettre à jour/supprimer des onglets</li><li>Impossible de créer/mettre à jour/supprimer des connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle Store pour votre organisation :

- Si votre organisation comporte des départements au sein de chaque magasin, ajoutez un canal pour chaque département. L’ajout d’un canal facilite la communication et la collaboration au sein du service.

- Si votre organisation possède des sites web internes (par exemple, un site SharePoint), pensez à les épingler comme onglets dans le canal de l'équipe concernée. Pour obtenir des instructions, consultez [Prise en main des modèles Teams](get-started-with-teams-templates.md).

## <a name="manager-collaboration-template"></a>Modèle de collaboration entre responsables

Le modèle de collaboration entre responsables est un autre modèle de l'équipe conçu pour répondre aux besoins des détaillants. Le modèle de collaboration entre responsables est idéal pour créer une équipe permettant à un ensemble de responsables de collaborer entre magasins/régions, et plus encore. Par exemple, si votre organisation comporte des régions, vous pouvez créer une équipe de collaboration entre responsables pour la région de Californie et y inclure tous les responsables de magasin de cette région, ainsi que le responsable régional de cette région.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canaux <ul><li>Opérations\*</li><li>Apprentissage\*</li></ul>\*Canaux ajoutés automatiquement aux favoris<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> <br>Autorisations de membre <ul><li>Création/mise à jour/suppression de canaux </li><li>Ajout/suppression d’applications </li><li>Création/mise à jour/suppression d’onglets</li><li>Création/mise à jour/suppression des connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle de collaboration entre responsables pour votre organisation :

- Si votre organisation possède des sites web internes, tels qu'un site SharePoint, qui sont pertinents pour les responsables, pensez à les épingler comme onglets dans un canal d'équipe pertinent. Pour les instructions, vous pouvez consulter la [documentation sur les modèles Microsoft Teams](get-started-with-teams-templates.md).

## <a name="how-to-use-first-party-templates"></a>Comment utiliser les modèles de premier groupe

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.  Pour plus d’informations sur le déploiement des modèles Teams, consultez l’article Microsoft Graph sur la [création d’un groupe](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Les canaux dans le modèle seront automatiquement créés sous l’onglet Général.

### <a name="example-store-template-extension-script"></a>Exemple : script d’extension de modèle Store

``` PowerShell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('retailStore')",
  "DisplayName": "Contoso Store",
  "Description": "Team for all staff in Contoso Store",
  "Channels": [
    {
      "displayName": "Additional store channel",
      "IsFavoriteByDefault": false
    }
  ]
}
```
## <a name="relate-topic"></a>Rubrique concernée

[Prise en main des modèles Teams dans le Centre d'administration](get-started-with-teams-templates-in-the-admin-console.md)