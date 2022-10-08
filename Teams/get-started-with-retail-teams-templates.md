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
- m365-frontline
- highpri
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
ms.openlocfilehash: 69644ce0261d37fb6a7a5e4270a68fb2a79a7d19
ms.sourcegitcommit: 507e186972bcbc56c1547a1b9f357bfd38170b5a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68046914"
---
# <a name="use-retail-team-templates"></a>Utiliser des modèles d’équipe de vente au détail

## <a name="overview"></a>Vue d’ensemble

Les modèles d’équipe dans Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant une structure d’équipe prédéfinie de paramètres, de canaux et d'applications préinstallées.

Pour les revendeurs, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams comprend des modèles conçus spécifiquement pour les besoins des revendeurs. Utilisez ces modèles pré-conçus pour créer rapidement des équipes de communication et de collaboration entre les membres du personnel. Cet article présente chacun des modèles Teams et vous explique comment les utiliser.

La façon dont vous gérez et travaillez avec les modèles d’équipe dépend de votre rôle d’administrateur ou de développeur.

|Si vous êtes : | Ensuite, vous : |
| ---- | --------- |
| Un administrateur ou un professionnel de l’informatique |[Manage team templates in the Teams admin center](#manage-team-templates-in-the-teams-admin-center). View team templates and apply templates policies to control which templates your staff can use in Teams for creating teams. |
| Un développeur | [Utilisez Microsoft Graph](#use-team-templates-with-microsoft-graph) pour créer des équipes à partir de modèles d’équipe. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

En tant qu’administrateur, vous pouvez gérer des modèles d’équipe dans le Centre d’administration de Microsoft Teams. Ici, vous pouvez afficher des détails sur chaque modèle. Vous pouvez également [créer et attribuer des stratégies de modèles](templates-policies.md) à votre personnel afin de contrôler les modèles qu’ils voient dans Teams pour [la création d’équipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe dans le Centre d'administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

Nous proposons actuellement les modèles d’équipe de vente au détail pré-intégrés suivants. Pour les afficher, dans le volet de navigation gauche du centre d'administration Teams, accédez à **Modèles d’équipes** >  **Teams**.

> [!NOTE]
> Un astérisque (*) indique que le modèle est un *modèle connecté à Microsoft 365*. Lorsque les utilisateurs créent une équipe à l’aide du modèle, le modèle SharePoint connecté est appliqué au site et à l’équipe. Les composants SharePoint tels que les pages, les listes et les intégrations Power Platform sont automatiquement ajoutés et épinglés sous forme d’onglets au canal Général de l’équipe. Les utilisateurs peuvent modifier ces pages et listes directement à partir de Teams.
>
> Pour en savoir plus sur les modèles SharePoint, consultez [Appliquer et personnaliser des modèles de site SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Gérer un Magasin*

Rassemblez vos employés dans une expérience centralisée pour gérer les tâches, partager des documents et résoudre les problèmes des clients. Intégrez des applications supplémentaires pour simplifier les processus de début et de fin de décalage.

> [!div class="mx-tdBreakAll"]
>| Type de modèle |TemplateId | Propriétés fournies avec ce modèle de base |
>| ------------------|-- |----------------------------------------------------- |
>| Gérer un Magasin| `retailStore` |Canaux : <ul><li>Général<li>Transfert de décalage</li><li>Disponibilité du magasin</li><li>Formation</li></ul> Applications : <ul><li>Approbations</li><li>Inspection</li><li>Listes<ul><li>Liste d’inventaire</li></ul></li><li>SharePoint Pages<ul><li>Notre magasin</li></ul></li><li>Shifts</li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul>|

### <a name="retail-for-managers"></a>Vente au détail pour les gestionnaires*

Créez une équipe pour un ensemble de gestionnaires afin de collaborer entre les magasins ou les régions. Par exemple, si votre organisation a des régions, vous pouvez créer une équipe pour la région californienne et inclure tous les responsables de magasin dans cette région, ainsi que le responsable régional de cette région.

> [!div class="mx-tdBreakAll"]
>| Type de modèle| TemplateId | Propriétés fournies avec ce modèle de base |
>| ------------------|- |----------------------------------------------------- |
>| Vente au détail pour les gestionnaires| `retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations</li><li>Apprentissage</li></ul> Applications : <ul><li>Approbations</li><li>Inspection</li><li>SharePoint Pages<ul><li>Notre magasin</li></ul></li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul>|

## <a name="use-team-templates-with-microsoft-graph"></a>Utiliser les modèles Teams avec Microsoft Graph

Developers can use Microsoft Graph to create teams from pre-built team templates. To learn more about using team templates with Microsoft Graph, see [Get started with team templates using Microsoft Graph](get-started-with-teams-templates.md), [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0), and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Voici les modèles pré-intégrés de l’équipe de vente au détail.

> [!NOTE]
> Un astérisque (*) indique que le modèle est un *modèle connecté à Microsoft 365*. Lorsque les utilisateurs créent une équipe à l’aide du modèle, le modèle SharePoint connecté est appliqué au site et à l’équipe. Les composants SharePoint tels que les pages, les listes et les intégrations Power Platform sont automatiquement ajoutés et épinglés sous forme d’onglets au canal Général de l’équipe. Les utilisateurs peuvent modifier ces pages et listes directement à partir de Teams.
>
> Pour en savoir plus sur les modèles SharePoint, consultez [Appliquer et personnaliser des modèles de site SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

### <a name="manage-a-store"></a>Gérer un Magasin*

Utilisez ce modèle pour créer une équipe pour chaque emplacement de magasin de détail de votre organisation.

> [!div class="mx-tdBreakAll"]
>| Type de modèle | TemplateId | Canaux modèles |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Commerce - <br>Magasin | `https://graph.microsoft.com/beta/teamsTemplates('retailStore')`| Canaux <ul><li>Général</li><li>Transfert de décalage</li><li>Disponibilité du magasin</li><li>Formation</li></ul>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Public</li></ul> <br>Autorisations de membre <ul><li>Impossible de créer, mettre à jour ou supprimer des canaux </li><li>Ajout ou suppression d’applications impossible </li><li>Création, mise à jour ou suppression d’onglets impossible</li><li>Création, mise à jour ou suppression de connecteurs impossible</li><ul>|

Méthodes recommandées pour personnaliser le modèle Store pour votre organisation :

- Si votre organisation comporte des départements au sein de chaque magasin, ajoutez un canal pour chaque département. L’ajout d’un canal facilite la communication et la collaboration au sein du service.

- Si votre organisation possède des sites web internes (par exemple, un site SharePoint), pensez à les épingler comme onglets dans le canal de l'équipe concernée.

### <a name="retail-for-managers"></a>Vente au détail pour les gestionnaires*

Utilisez ce modèle pour créer une équipe pour un ensemble de gestionnaires afin de collaborer entre les magasins ou les régions. Par exemple, si votre organisation a des régions, vous pouvez créer une équipe pour la région californienne et inclure tous les responsables de magasin dans cette région, ainsi que le responsable régional de cette région.

> [!div class="mx-tdBreakAll"]
>| Type de modèle | TemplateId | Canaux modèles |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Commerce - <br>Collaboration des responsables | `https://graph.microsoft.com/beta/teamsTemplates('retailManagerCollaboration')`| Canaux <ul><li>Général</li><li>Opérations</li><li>Apprentissage</li></ul>Propriétés de l’équipe <ul><li>Visibilité de l’équipe définie sur Privé</li></ul> <br>Autorisations de membre <ul><li>Peut créer, mettre à jour et supprimer des canaux </li><li>Peut ajouter et supprimer des applications </li><li>Peut créer, mettre à jour et supprimer des onglets</li><li>Peut créer, mettre à jour et supprimer des connecteurs</li><ul>|

Méthodes recommandées pour personnaliser le modèle de collaboration entre responsables pour votre organisation :

- Si votre organisation possède des sites web internes, tels qu'un site SharePoint, qui sont pertinents pour les responsables, pensez à les épingler comme onglets dans un canal d'équipe pertinent.

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Comment utiliser des modèles d’équipe avec Microsoft Graph

Pour utiliser ces modèles, modifiez la propriété « template@odata.bind » dans le corps de la demande de « standard » en valeurs TemplateID ci-dessus.  Pour plus d’informations sur le déploiement de modèles d’équipe, consultez l’article Graph Microsoft sur la [création d’une équipe](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Les canaux dans le modèle seront automatiquement créés sous l’onglet **Général**.

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

> [!NOTE]
> Si vous utilisez Microsoft Graph pour créer une équipe à partir d’un groupe ou d’une équipe Microsoft 365 existant à l’aide d’un modèle connecté à Microsoft 365, le modèle SharePoint connecté n’est pas automatiquement appliqué au site ou à l’équipe. Vous devez appliquer manuellement le modèle de site SharePoint après la création de l’équipe. Dans Teams, accédez à l’équipe, sélectionnez **Plus d’options** dans le coin supérieur droit > **Ouvrir dans SharePoint**. Choisissez Ensuite **Paramètres** > **Appliquer un modèle de site** , puis sélectionnez le modèle de site correspondant.

## <a name="related-articles"></a>Articles connexes

- [Utiliser des modèles d’équipe dans le Centre d’administration Teams](get-started-with-teams-templates-in-the-admin-console.md)
- [Créer une équipe à partir d’un modèle](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Utiliser des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)