---
title: Utiliser des modèles d’équipe de vente au détail
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Découvrez comment gérer et utiliser les modèles d’équipe de vente au détail dans le Centre d’administration Teams et avec Microsoft Graph pour créer rapidement et facilement des équipes pour votre organisation de vente au détail.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 073d9ee391b42a476b0657dbf910f8d019699358
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991203"
---
# <a name="use-retail-team-templates"></a>Utiliser des modèles d’équipe de vente au détail

Les modèles Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant un modèle prédéfini de paramètres, de canaux et d'applications préinstallées.

Pour les revendeurs, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams comprend des modèles conçus spécifiquement pour les besoins des revendeurs. Utilisez ces modèles pré-conçus pour créer rapidement des équipes de communication et de collaboration entre les membres du personnel. Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend de votre rôle d’administrateur ou de développeur.

|Si vous êtes : | Alors, vous : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Gérez les modèles d’équipe dans le Centre d'administration Teams](#manage-team-templates-in-the-teams-admin-center). Affichez les modèles d’équipe et appliquez des stratégies de modèles pour contrôler les modèles que les membres du personnel peuvent utiliser Teams pour créer des équipes. |
| Un développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir de modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d'administration Teams

En tant qu’administrateur, vous pouvez créer et gérer des équipes et des canaux dans le client Teams ou avec le centre d’administration de Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](templates-policies.md) à votre personnel afin de contrôler les modèles qu’il voit dans Teams pour [créer des équipes](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c). 

Pour en savoir plus sur les modèles d’équipe en général, consultez [Commencer à utiliser les modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles d’équipe de vente au détail pré-intégrés suivants. Pour les afficher, dans le volet de navigation gauche du Centre d’administration Teams, accédez à **modèles d’équipe** > **Teams**.

### <a name="organize-a-store"></a>Organiser un magasin

Rassemblez vos employés dans une expérience centralisée pour gérer les tâches, partager des documents et résoudre les problèmes des clients. Intégrez des applications supplémentaires pour simplifier les processus de démarrage et de fin des rotations.

| Type de modèle |TemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|-- |----------------------------------------------------- |
|Organiser un magasin| `retailStore` |Canaux : <ul><li>Général<li>Transfert de shift</li><li>Préparation du magasin<ul><li>Inspection&sup1;</li></ul></li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li><li>Quarts</li><li>Inspection</li></ul>|

&sup1; Application ajoutée au canal en tant qu’onglet.

### <a name="manager-collaboration"></a>Collaboration des responsables

Le modèle de collaboration entre responsables est idéal pour créer une équipe permettant à un ensemble de responsables de collaborer entre magasins/régions, etc. Par exemple, si vous êtes organisé par régions, vous pouvez créer une équipe de collaboration entre responsables pour la région Rhône-Alpes et y inclure tous les responsables de magasin de cette région, ainsi que le responsable régional de cette région.

| Type de modèle| TemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|- |----------------------------------------------------- |
|Vente au détail pour les responsables|`retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations<ul><li>Tâches (tâches opérationnelles)&sup1;</li><li>Inspection&sup1;</li></ul></li><li>Formation<ul><li>Tâches (tâches d’apprentissage)&sup1;</li></ul></li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li><li>Inspection</li></ul>|
||||

&sup1; Application ajoutée au canal en tant qu’onglet.

## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles d’équipe avec Microsoft Graph

Les développeurs peuvent utiliser Microsoft Graph pour créer des équipes à partir de modèles d’équipe pré-conçus. Pour en savoir plus sur l’utilisation de modèles d’équipe avec Microsoft Graph, consultez [Démarrage avec des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md), [Vue d’ensemble de l’API Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0)et [Type de ressource teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Voici les modèles pré-intégrés de l’équipe de vente au détail.

### <a name="store"></a>Magasin

Le modèle Store est idéal pour créer une équipe afin de représenter un emplacement de magasin de détail. Le modèle Store vous permet de créer une équipe pour chaque emplacement de vente au détail dans votre organisation.

| Type de modèle | TemplateId | Canaux de modèle |
| ------------------ | -------------- | ----------------------------------------------------- |
| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canaux <ul><li>Général</li><li>Transfert de quart&sup2;</li><li>Préparation du magasin</li><li>Formation&sup2;</li></ul>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Public</li></ul> <br>Autorisations de membre <ul><li>Ne peut pas créer, mettre à jour ou supprimer des canaux </li><li>Impossible d’ajouter ou de supprimer des applications </li><li>Ne peut pas créer, mettre à jour ou supprimer des onglets</li><li>Ne peut pas créer, mettre à jour ou supprimer des connecteurs</li><ul>|
||||

&sup2; Canaux favoris automatiques

Méthodes recommandées pour personnaliser le modèle Store pour votre organisation :

- Si votre organisation comporte des départements au sein de chaque magasin, ajoutez un canal pour chaque département. L’ajout d’un canal facilite la communication et la collaboration au sein du service.

- Si votre organisation possède des sites web internes (par exemple, un site SharePoint), pensez à les épingler comme onglets dans le canal de l'équipe concernée.

### <a name="manager-collaboration"></a>Collaboration des responsables

Le modèle de collaboration entre responsables est idéal pour créer une équipe permettant à un ensemble de responsables de collaborer entre magasins/régions, etc. Par exemple, si vous êtes organisé par régions, vous pouvez créer une équipe de collaboration entre responsables pour la région Rhône-Alpes et y inclure tous les responsables de magasin de cette région, ainsi que le responsable régional de cette région.

| Type de modèle | TemplateId | Canaux de modèle |
| ------------------ | -------------- | ----------------------------------------------------- |
| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')`| Canaux <ul><li>Général</li><li>Opérations&sup2 ;</li><li>Formation&sup2;</li></ul>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> <br>Autorisations de membre <ul><li>Peut créer, mettre à jour et supprimer des canaux </li><li>Peut ajouter et supprimer des applications </li><li>Peut créer, mettre à jour et supprimer des onglets</li><li>Peut créer, mettre à jour et supprimer des connecteurs</li><ul>|
||||

&sup2; Canaux favoris automatiques

Méthodes recommandées pour personnaliser le modèle de collaboration entre responsables pour votre organisation :

- Si votre organisation possède des sites web internes, tels qu'un site SharePoint, qui sont pertinents pour les responsables, pensez à les épingler comme onglets dans un canal d'équipe pertinent.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Comment utiliser des modèles d’équipe avec Microsoft Graph

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.  Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la [création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Les canaux dans le modèle seront automatiquement créés sous l’onglet **Général**.

### <a name="example-store-template-extension-script"></a>Exemple : script d’extension de modèle de magasin

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

## <a name="related-articles"></a>Articles connexes

- [Démarrage avec des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe à partir d’un modèle dans l’application Teams](https://support.microsoft.com/en-us/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [Démarrage avec des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)