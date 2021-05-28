---
title: Utiliser un modèle d’équipe dans le commerce de détail
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
description: Découvrez comment utiliser des modèles d’équipe pour créer des structures d’équipe conçues pour les besoins des revendeurs en fournissant des paramètres, des canaux et des applications préinstallées.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: edc3b646af4577199b13a5803837625b8a9ea354
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684552"
---
# <a name="create-a-team-using-retail-team-templates"></a>Créer une équipe à l’aide de modèles d’équipe de vente au détail

Les modèles Microsoft Team vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéféré de paramètres, de canaux et d’applications préinstallées.

Les modèles d’équipe ont des définitions pré-intégrées de structures d’équipe conçues autour des besoins des revendeurs. Vous pouvez utiliser des modèles d’équipe pour créer rapidement les types d’équipes qui fonctionnent bien pour les revendeurs et les déployer au sein de votre organisation. Vous pouvez également étendre les modèles d’équipe pour créer des équipes adaptées aux besoins de votre organisation.

Dans cet article, nous présenterons chacun des modèles d’équipe et vous recommandons de les utiliser.

Cet article est pour vous si vous êtes responsable de la planification, du déploiement et de la gestion de plusieurs équipes au sein de votre organisation de vente au détail. Vous avez déjà déployé le service Teams dans votre organisation. Si vous n’avez pas encore déployé Teams, commencez par lire l’article [Comment déployer Microsoft Teams](./deploy-overview.md).

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe.](get-started-with-teams-templates.md)

| Qui | Méthode à utiliser : |
| ---- | --------- |
| Administrateurs et professionnels de l’informatique | [Utilisez le centre Teams d’administration](#use-the-team-templates-in-the-teams-admin-center) pour créer des équipes basées sur les modèles d’équipe de vente au détail.|
| Développeurs et intégrateurs de systèmes | [Utilisez le service de Graph Microsoft](#use-the-team-templates-with-the-microsoft-graph) pour créer des équipes basées sur les modèles d’équipe de vente au détail. |

## <a name="use-the-team-templates-in-the-teams-admin-center"></a>Utiliser les modèles d’équipe dans le Centre Teams’administration

### <a name="organize-a-store"></a>Organiser un magasin

Rassemblez vos employés dans une expérience centralisée pour gérer les tâches, partager des documents et résoudre les problèmes des clients. Intégrez des applications supplémentaires pour simplifier les processus de démarrage et de fin des shifts.

| Type de modèle de base |baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|-- |----------------------------------------------------- |
|Organiser un magasin|`retailStore`|Canaux : <ul><li>Général<li>Transfert de shift</li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li></ul>|
||||

### <a name="manager-collaboration"></a>Collaboration des responsables

Le modèle Collaboration avec les responsables est idéal pour créer une équipe de responsables collaborant entre plusieurs magasins/régions, etc. Par exemple, si votre organisation possède des régions, vous pouvez créer une équipe de collaboration de responsable pour la région Californie et y inclure tous les responsables de magasin, ainsi que le responsable régional de cette région.

| Type de modèle de base| baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|- |----------------------------------------------------- |
|Vente au détail : collaboration entre responsables|`retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations</li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li></ul>|
||||

## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Utiliser les modèles d’équipe avec l’Graph

### <a name="store-template"></a>Modèle Store

Le modèle Store est idéal pour créer une équipe afin de représenter un emplacement de magasin de détail. Le modèle Store vous permet de créer une équipe pour chaque emplacement de vente au détail dans votre organisation.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')`| Canaux <ul><li>Procédure de transfert des Plannings\*</li><li>Apprentissage\*</li></ul>\*Canaux ajoutés automatiquement aux favoris<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Public</li></ul> <br>Autorisations de membre <ul><li>Impossible de créer/mettre à jour/supprimer des canaux </li><li>Impossible d’ajouter/supprimer des applications </li><li>Impossible de créer/mettre à jour/supprimer des onglets</li><li>Impossible de créer/mettre à jour/supprimer des connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle Store pour votre organisation :

- Si votre organisation comporte des départements au sein de chaque magasin, ajoutez un canal pour chaque département. L’ajout d’un canal facilite la communication et la collaboration au sein du service.

- Si votre organisation possède des sites web internes (par exemple, un site SharePoint), pensez à les épingler comme onglets dans le canal de l'équipe concernée. Pour obtenir des [instructions, voir Commencer à utiliser les modèles](get-started-with-teams-templates.md) d’équipe.

### <a name="manager-collaboration-template"></a>Modèle de collaboration entre responsables

Le modèle Collaboration avec le responsable est un autre modèle d’équipe conçu autour des besoins d’un revendeur. Le modèle de collaboration entre responsables est idéal pour créer une équipe permettant à un ensemble de responsables de collaborer entre magasins/régions, et plus encore. Par exemple, si votre organisation comporte des régions, vous pouvez créer une équipe de collaboration entre responsables pour la région de Californie et y inclure tous les responsables de magasin de cette région, ainsi que le responsable régional de cette région.

| Type de modèle de base | baseTemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canaux <ul><li>Opérations\*</li><li>Apprentissage\*</li></ul>\*Canaux ajoutés automatiquement aux favoris<br><br>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> <br>Autorisations de membre <ul><li>Création/mise à jour/suppression de canaux </li><li>Ajout/suppression d’applications </li><li>Création/mise à jour/suppression d’onglets</li><li>Création/mise à jour/suppression des connecteurs</li><ul>|
||||

Méthodes recommandées pour personnaliser le modèle de collaboration entre responsables pour votre organisation :

- Si votre organisation possède des sites web internes, tels qu'un site SharePoint, qui sont pertinents pour les responsables, pensez à les épingler comme onglets dans un canal d'équipe pertinent. Pour obtenir des instructions, vous pouvez vous baser sur la documentation du modèle d’équipe [Microsoft.](get-started-with-teams-templates.md)

## <a name="how-to-use-first-party-templates"></a>Comment utiliser les modèles de premier groupe

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.  Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la création [d’une équipe.](/graph/api/team-post?view=graph-rest-beta)

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
