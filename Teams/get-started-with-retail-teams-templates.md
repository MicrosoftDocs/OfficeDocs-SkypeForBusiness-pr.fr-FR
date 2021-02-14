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
description: Découvrez comment utiliser les modèles Teams pour créer des structures d’équipe conçues pour les besoins des revendeurs en fournissant des paramètres, des canaux et des applications préinstallées.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f226b60bfc3a054166eb48596c505ccd7fa5ac9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424634"
---
# <a name="get-started-with-teams-templates-in-retail"></a>Prise en main des modèles Teams de vente au détail

Les modèles Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfindé de paramètres, de canaux et d’applications préinstallées.

Les modèles Teams ont des définitions pré-intégrées de structures d’équipe conçues autour des besoins des revendeurs. Vous pouvez utiliser les modèles Teams pour créer rapidement les types d’équipes qui fonctionnent bien pour les revendeurs et les déployer dans votre organisation. Vous pouvez également étendre les modèles Teams pour créer des équipes adaptées aux besoins de votre organisation.

Dans cet article, nous allons présenter chacun des modèles Teams et leur recommander comment les utiliser.

Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de vente au détail. Vous avez déjà déployé le service Teams dans votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire comment [déployer Microsoft Teams.](How-to-roll-out-teams.md)

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles Teams.](get-started-with-teams-templates.md)

## <a name="store-template"></a>Modèle Store

Le modèle de Magasin est idéal pour créer une équipe représentant un emplacement de magasin individuel. En utilisant le modèle du Store, vous pouvez créer une équipe pour chaque emplacement de magasin de votre organisation.

| Type de modèle de base | baseTemplateId | Propriétés de ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Vente au détail - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canaux <ul><li>Transfert des shifts\*</li><li>Formation\*</li></ul>\*Canaux favoris automatiquement<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Public</li></ul> <br>Autorisations des membres <ul><li>Création/mise à jour/suppression de canaux intéléments </li><li>Ajout/suppression d’applications non disponibles </li><li>Création/mise à jour/suppression d’onglets</li><li>Créer/mettre à jour/supprimer des connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle du Store pour votre organisation :

- Si votre organisation possède des services au sein de chaque magasin, ajoutez un canal pour chaque service. L’ajout d’un canal facilite la communication et la collaboration au sein du service.

- Si votre organisation possède des sites web internes (par exemple, un site SharePoint), vous pouvez les épingler sous la la direction d’onglets dans le canal d’équipe approprié. [Reportez-vous aux modèles De mise en page de Teams](get-started-with-teams-templates.md) pour obtenir des instructions.

## <a name="manager-collaboration-template"></a>Modèle de collaboration avec les responsables

Le modèle Collaboration avec le responsable est un autre des modèles Teams conçus selon les besoins des revendeurs. Le modèle collaboration avec les responsables est idéal pour créer une équipe pour un ensemble de responsables qui collaborent entre plusieurs magasins/régions, et bien plus encore. Par exemple, si votre organisation possède des régions, vous pouvez créer une équipe de collaboration de responsable pour la région Californie et y inclure tous les responsables de magasin, ainsi que le responsable régional de cette région.

| Type de modèle de base | baseTemplateId | Propriétés de ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Vente au détail - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canaux <ul><li>Opérations\*</li><li>Formation\*</li></ul>\*Canaux favoris automatiquement<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> <br>Autorisations des membres <ul><li>Peut créer/mettre à jour/supprimer des canaux </li><li>Peut ajouter/supprimer des applications </li><li>Création/mise à jour/suppression d’onglets</li><li>Peut créer/mettre à jour/supprimer des connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle de collaboration avec les responsables pour votre organisation :

- Si votre organisation possède des sites web internes, tels qu’un site SharePoint, qui sont appropriés pour les responsables, vous envisagez de les épingler en tant qu’onglets dans un canal d’équipe approprié. Pour obtenir des instructions, vous pouvez vous baser sur la documentation du modèle [Microsoft Teams.](get-started-with-teams-templates.md)

## <a name="how-to-use-first-party-templates"></a>Comment utiliser des modèles de premier groupe

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » à la propriété TemplateIDs ci-dessus.  Pour plus d’informations sur le déploiement de modèles Teams, voir l’article Microsoft Graph sur la création [d’une équipe.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Les canaux du modèle sont automatiquement créés sous l’onglet Général.

### <a name="example-store-template-extension-script"></a>Exemple : Script d’extension de modèle Store

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
## <a name="relate-topic"></a>Sujet lié

[Utiliser les modèles Teams dans le Centre d’administration](get-started-with-teams-templates-in-the-admin-console.md)
