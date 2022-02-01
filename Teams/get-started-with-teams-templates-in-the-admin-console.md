---
title: Utiliser des modèles d’équipe dans le Centre d’administration Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Découvrez les modèles d’équipe et comment les gérer dans le Centre Microsoft Teams’administration.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: dd07e375a35ea212bccd988395b5c1adbd721011
ms.sourcegitcommit: d3c48f0c147cf0c47d5eb4ea1128b5bca13be718
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/01/2022
ms.locfileid: "62299049"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Utiliser des modèles d’équipe dans le Centre d’administration Teams

**La possibilité de créer des modèles personnalisés n’est pas encore prise en charge pour les clients EDU.**

> [!NOTE]
> Les canaux privés et les étiquettes de sensibilité ne sont actuellement pas pris en charge dans les modèles d’équipe. La création de canaux privés n’est pas incluse dans les définitions de modèle. L’option d’étiquette de sensibilité dans **Créer une** équipe à partir du flux de modèles ne sera pas appliquée à l’équipe.

## <a name="overview"></a>Présentation

Un modèle d’équipe Microsoft Teams est une définition de la structure d’une équipe conçue autour d’un besoin ou d’un projet d’entreprise. En tant qu’administrateur, vous pouvez utiliser des modèles pour déployer facilement des équipes cohérentes au sein de votre organisation. Les modèles permettent à vos utilisateurs de créer rapidement des espaces de collaboration enrichis avec des paramètres, des canaux et des applications prédéfinés.

Vous pouvez gérer les modèles d’équipe dans le Microsoft Teams d’administration ou à l’aide de PowerShell. Vous pouvez utiliser les modèles pré-intégrés que nous vous fournissons et vous pouvez [également créer vos propres modèles personnalisés](#create-your-own-team-templates). Vous pouvez également appliquer [des stratégies de](#apply-team-template-policies) modèle pour contrôler quels modèles sont disponibles pour vos utilisateurs dans Teams.

Cet article vous donne une vue d’ensemble de l’utilisation des modèles d’équipe dans le Teams d’administration. Vous découvrirez les propriétés qui sont pris en charge dans les modèles, les modèles pré-intégrés que nous fournissons, les limites de taille des modèles, comment créer et gérer les modèles, et bien plus encore.

> [!NOTE]
> Vos utilisateurs peuvent [créer des équipes à partir de modèles](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) d’équipe pré-créés ou personnalisés dans l Teams appeil de messagerie. Les développeurs peuvent également créer des équipes par programme à partir de modèles d’équipe pré-créés à l’aide de Microsoft Graph. Pour en savoir plus, voir [Mise en place des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Fonctionnalités des modèles d’équipe

La plupart des propriétés d’une équipe sont incluses et prise en charge par les modèles d’équipe. Certaines propriétés et fonctionnalités ne sont actuellement pas pris en charge. Voici un résumé de ce qui est inclus et de ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe pris en charge par les modèles d’équipe** | **Propriétés de l’équipe non encore pris en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle | Appartenance à une équipe |
| Nom de l’équipe | Image de l’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres de l’équipe (par exemple, membre, invité, @mentions) | Fichiers et contenu |
| Canal des masons automatiques | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Nous ajouterons d’autres fonctionnalités de modèle dans les prochaines version de Microsoft Teams. Vérifiez donc que vous avez besoin des informations les plus à jour sur les propriétés prise en charge.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Modèles d’équipe pré-créés dans le Centre Teams’administration

Voici les modèles d’équipe pré-intégrés qui sont disponibles dans le Centre Teams’administration. Les modèles pré-conçus sont des modèles que nous avons créés pour des secteurs spécifiques. Pour afficher ces modèles, dans le navigation gauche du Teams d’administration, voir **Teams** >  **Team templates**.

Vous pouvez dupliquer des modèles pré-créés, mais vous ne pouvez pas les modifier. Si vous voulez modifier les propriétés d’un modèle pré-conçu, vous pouvez créer un modèle à partir d’un modèle existant, puis ajouter ou supprimer les propriétés de votre souhaitez. N’oubliez pas que certaines propriétés de certains modèles ne peuvent pas être modifiées.

| Type de modèle | TemplateId | Propriétés fournies avec ce modèle de base |
| ------------------ | -------------- | ----------------------------------------------------- |
| Adopter une Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Coin Champions</li> <li>Formulaires d’équipe</li><li>Calendrier</li></ul> Applications : <ul><li>Wiki</li>  <li>Calendrier de canal</li> <li>Jalons</li><li>Bulletins</li></ul>|
| Gérer un projet |`com.microsoft.teams.template.ManageAProject`| Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Applications :<ul><li>Wiki</li><li>OneNote</li><li>Tâches</li><li>Listes</li><li>Power Automate</li></ul> |
| Gérer un événement|`com.microsoft.teams.template.ManageAnEvent` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et relations publiques</li></ul> Applications :<ul><li>Wiki</li><li>Site web</li> <li>YouTube</li> <li>Tâches</li> <li>OneNote</li> <li>Idées des employés</li> <li>Signalement de problèmes</li><li>Power Automate</li><li>Bulletins</li><li>Jalons</li></ul> |
|Intégrer des employés|`com.microsoft.teams.template.OnboardEmployees` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Conversation employé</li> <li>Formation</li></ul>Applications :<ul><li>Wiki</li><li>Communautés</li><li>Tâches</li><li>Idées des employés</li><li>Power Automate</li><li>Bulletins</li><li>Jalons</li></ul>|
|Organiser le service d’aide| `com.microsoft.teams.template.OrganizeHelpDesk`|Canaux :<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Applications :<ul><li>Wiki</li><li>OneNote</li><li>Tâches </li><li>Compliment</li><li>Signalement de problèmes</li><li>Power Automate</li><li>Bulletins</li></ul> |
| Soins du patient| `com.microsoft.teams.template.healthcareWard`| Canaux :<ul><li>Général</li><li>Annonces</li><li>Blotti</li><li>Rondes</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Listes  </li><li>Approbations</li><li>Bulletins</li><li>Inspection</li></ul>|
| Communication en cas de crise |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canaux : <ul><li>Général<li>Annonces</li><li>Actualités mondiales</li><li>Communications internes</li><li>Comms externe</li><li>Demande d’approbation</li><li>Escalades de clients</li><li>Mise à jour pour la direction</li><li>Planification</li><li>Logistique</li></ul>Applications : <ul><li>Site web</li><li>Tâches</li><li>Signalement de problèmes</li><li>Approbations</li><li>Bulletins</li><li>OneNote</li><li>Power Automate</li><li>Microsoft Office SharePoint Online</li></ul>|
|Agence bancaire| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canaux : <ul><li>Général<li>Annonces</li><li>Blotti</li><li>Réunions avec des clients</li><li>Demande d’approbation </li><li>Accompagnement</li><li>Développement de compétences</li><li>Traitement des emprunts</li><li>Réclamations des clients</li><li>Félicitations</li><li>Outils amusants</li><li>Conformité</li></ul>Applications :<ul><li>Compliment </li><li>Signalement de problèmes</li><li>Page Wiki</li><li>Calendrier</li><li>Approbations</li><li>Bulletins</li><li>Idées</li></ul>|
|Réponse à un incident| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canaux : <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Récupération</li><li>Urgent</li></ul> Applications : <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>Microsoft Office SharePoint Online</li><li>Tâches</li> <li>Approbations</li> <li>Inspection</li> <li>Power Automate</li><li>Bulletins</li><li>Jalons</li></ul>|
|Hôpital| `com.microsoft.teams.template.healthcareHospital` |Canaux : <ul><li>Général</li><li>Annonces</li><li>Conformité</li><li>Consignataires</li><li>Ressources humaines</li><li>Pharmacie</li></ul> Applications : <ul><li>Wiki</li><li>Listes</li><li>Tâches</li><li>Approbations</li><li>Shifts</li><li>Bulletins</li><li>Inspection</li><li>Idées</li></ul>|
|Organiser un magasin| `com.microsoft.teams.template.retailStore` |Canaux : <ul><li>Général<li>Transfert de shift</li><li>Préparation du magasin</li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li><li>Shifts</li><li>Inspection</li></ul>|
|Vente au détail pour les responsables| `com.microsoft.teams.template.retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations</li><li>Apprentissage</li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li><li>Inspection</li></ul>|
|Qualité et sécurité |`com.microsoft.teams.template.QualitySafety`|Canaux : <ul><li>Général<li>Annonces</li><li>Leadership</li><li>Maintenance</li><li>Ligne de production 1</li><li>Ligne de production 2</li><li>Ligne de production 3</li><li>Santé et sécurité</li><li>Formation</li><li>Outils amusants</li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li> <li>Signalement de problèmes</li> <li>Inspection</li> </ul>|
|Gérer les bénévoles| `com.microsoft.teams.template.ManageVolunteers` |Canaux : <ul><li>Général<li>Annonces</li><li>Rapports</li><li>Gestion des bénévoles</li><li>Opportunités d’engagement</li><li>Intégration des volontaires</li></ul> Applications : <ul><li>Site web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Tâches</li><li>Microsoft Office SharePoint Online</li><li>OneNote</li></ul>|
||||

### <a name="team-templates-by-category-and-industry"></a>Modèles d’équipe par catégorie et secteur d’activité

Pour plus d’informations sur les façons d’utiliser les modèles pré pré-intégrés dans votre secteur d’activité, voir :

- [Modèles d’équipe financière](financial-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe généraux](general-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe gouvernementale](government-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe de santé](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modèles d’équipe de fabrication](manufacturing-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe pour les associations](team-templates-nonprofit.md)
- [Modèles d’équipe de vente au détail](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>Limites de taille des modèles d’équipe

Les modèles sont limités à un nombre spécifique de canaux, d’onglets et d’applications.

 > [!Note]
 > Vous pouvez ajouter des canaux, des onglets et des applications à l’équipe après sa création à partir d’un modèle.

|Fonctionnalité | Limite|
|-|-|
|Canaux par modèle | 15 |
|Onglets par canal dans un modèle | 20 |
|Applications par modèle | 50|
|||

Pour plus d’informations, [voir Limites et spécifications de Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Gérer les modèles d’équipe

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

#### <a name="view-team-templates"></a>Afficher les modèles d’équipe

Pour afficher les modèles d’équipe, dans le navigation gauche du Teams d’administration, voir **Teams** >  **Team templates**. Sélectionnez un modèle pour en savoir plus, y compris les canaux et applications qu’il contient.

#### <a name="create-your-own-team-templates"></a>Créer vos propres modèles d’équipe

Vous pouvez créer vos propres modèles personnalisés à partir de zéro, d’une équipe existante et d’un modèle existant. Pour en savoir plus, consultez les articles :

- [Créer un modèle d’équipe personnalisé](create-a-team-template.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Appliquer des stratégies de modèles d’équipe

Pour contrôler les modèles que les utilisateurs voient dans Teams pour créer des équipes[, vous](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) pouvez définir des stratégies de modèles et les affecter à des utilisateurs et des groupes de votre organisation. Pour en savoir plus, voir [Gérer les modèles d’équipe dans Teams d’administration.](templates-policies.md)

### <a name="manage-team-templates-using-powershell"></a>Gérer les modèles d’équipe à l’aide de PowerShell

Utilisez les cmdlets suivantes pour gérer vos modèles dans PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>Articles connexes

- [Créer une équipe à partir d’un modèle](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Utiliser des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)
- [Cloner une équipe](/graph/api/team-clone?view=graph-rest-1.0&tabs=http)
