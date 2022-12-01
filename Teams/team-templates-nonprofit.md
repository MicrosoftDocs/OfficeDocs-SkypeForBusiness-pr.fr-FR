---
title: Utiliser les modèles d’équipe pour les associations
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
description: Découvrez comment gérer et utiliser le modèle d’équipe Gérer les bénévoles pour créer facilement et rapidement des équipes de membres du personnel de votre organisation à but non lucratif qui communiquent et collaborent sur des activités de gestion de bénévoles.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
- chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1818a4eee46cca88c873af35278453ab84b1341
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198956"
---
# <a name="use-nonprofit-team-templates"></a>Utiliser les modèles d’équipe pour les associations

Les modèles d’équipe dans Microsoft Teams vous permettent de créer rapidement et facilement des équipes en fournissant une structure d’équipe prédéfinie de paramètres, de canaux et d'applications préinstallées.

Pour les organisations à but non lucratif, les modèles d’équipe peuvent être particulièrement puissants, car ils vous aident à déployer rapidement des équipes cohérentes au sein de votre organisation. Les modèles aident également le personnel à s’orienter dans l’utilisation efficace de Teams.

Teams inclut un modèle d’équipe de gestion des bénévoles conçu pour simplifier les activités de gestion de bénévoles. Utilisez ce modèle pré-conçu pour créer rapidement des équipes pour le personnel afin de communiquer et de collaborer sur des tâches et des activités de gestion de volontariat.

Dans cet article, vous allez découvrir le modèle d’équipe de gestion des bénévoles et comment l’utiliser pour créer une équipe. Cet article vous donne également une vue d’ensemble de la gestion des modèles d’équipe dans le centre d’administration Teams.

## <a name="manage-volunteers-team-template"></a>Modèle d’équipe de gestion des bénévoles

Rassemblez votre personnel pour communiquer et collaborer sur des tâches et des activités de gestion de bénévoles.

Ce modèle inclut des canaux et des applications conçus pour simplifier les activités de gestion de bénévoles. Les membres du personnel peuvent organiser et partager les supports d’intégration et les documents fréquemment utilisés, consulter les rapports, se tenir au courant des annonces importantes concernant l’équipe et les événements, etc. Le modèle est également intégré à la [Gestion des bénévoles](/dynamics365/industry/nonprofit/volunteer-management-use), une application qui fait partie de [Microsoft Cloud pour les associations](/industry/nonprofit/), permettant aux membres du personnel de gérer les opportunités d’engagement de bénévole au sein de Teams.

Voici les canaux et applications qui sont disponibles avec le modèle d’équipe gestion des bénévoles.

| Type de modèle |TemplateId | Propriétés fournies avec ce modèle de base |
| ------------------|-- |----------------------------------------------------- |
|Gérer les bénévoles| `ManageVolunteers` |Canaux : <ul><li>Général<ul><li>Site web&sup1;</li></ul><li>Annonces</li><li>Rapports<ul><li>Power BI&sup1;</li></ul></li><li>Gestion des bénévoles<ul><li>Power Apps&sup1;</li></ul></li><li>Opportunités d’engagement<ul><li>Tâches&sup1;</li></ul></li><li>Intégration des volontaires<ul><li>SharePoint&sup1;</li><li>OneNote&sup1;</li></ul></li></ul> Applications : <ul><li>Site web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Tâches</li><li>Microsoft Office SharePoint Online</li><li>OneNote</li></ul>|

&sup1; Application ajoutée au canal en tant qu’onglet.

## <a name="create-a-team-using-the-manage-volunteers-team-template"></a>Créer une équipe à l’aide du modèle d’équipe de gestion des bénévoles

### <a name="create-the-team"></a>Créer l’équipe

La création d’une équipe à partir du modèle de gestion des bénévoles ne prend que quelques étapes rapides.

1. Dans Teams, allez á **Teams** > **Joindre ou créer une équipe** > **Créer une équipe**.
2. Choisissez le **modèle d’équipe de gestion des bénévoles.**
3. Choisissez un niveau de confidentialité :
    - **Privé :** les personnes ont besoin de l’autorisation du propriétaire de l’équipe pour rejoindre l’équipe.
    - **Public**: tous les membres de votre organisation peuvent rejoindre l’équipe.
4. Donnez un nom à votre équipe et ajoutez une description. Vous pouvez également renommer les canaux pour personnaliser l’équipe.
5. Sélectionnez **Créer**.

Pour en savoir plus, consultez [Créer une équipe avec un modèle d’équipe](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b).

### <a name="add-the-volunteer-management-app-to-the-power-apps-tab"></a>Ajouter l’application Gestion des bénévoles à l'onglet Power Apps

Pour utiliser l’application Gestion des bénévoles dans Teams, ajoutez-la à l’onglet Power Apps dans le canal de gestion du volontariat. 

1. Dans Teams, allez à l’équipe que vous avez créée, choisissez le canal gestion du volontariat, puis sélectionnez l’onglet **Power Apps**.
2. Dans la liste drop-down, sélectionnez **applications pilotées par un modèle** puis recherchez et sélectionnez **Gestion de volontariat**.
3. Sélectionnez **Enregistrer**.

Pour plus d’informations, consultez [Incorporer une application pilotée par un modèle en tant qu’application d’onglet dans Teams](/powerapps/teams/embed-model-driven-teams-tab).

## <a name="view-and-manage-team-templates-in-the-teams-admin-center"></a>Afficher et gérer des modèles d’équipe dans le Centre d’administration Teams

Si vous êtes un administrateur, vous pouvez afficher et gérer les modèles d’équipe dans le centre d'administration Microsoft Teams. Pour afficher le modèle de gestion des bénévoles, dans la gauche de la navigation du Centre Teams d’administration **Teams** > **des modèles d’équipe Teams**.

Vous pouvez également [créer et attribuer des stratégies de modèles](templates-policies.md) à vos utilisateurs afin de contrôler les modèles qu’ils voient dans Teams pour créer des équipes.

Pour en savoir plus sur les modèles d’équipe en général, voir [Commencer à utiliser les modèles d’équipe dans le Centre d'administration Teams](get-started-with-teams-templates-in-the-admin-console.md).

## <a name="related-articles"></a>Articles connexes

- [documentation d'aide Teams](https://support.microsoft.com/teams)
- [Documentation de Microsoft Cloud pour les associations](/industry/nonprofit/)
