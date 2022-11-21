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
- m365-frontline
- tier2
- highpri
description: Découvrez les modèles d’équipe et comment les gérer dans le Centre d’administration Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ca199dbe81b2636a895ca25386abf53f6277758
ms.sourcegitcommit: ff161779577ce9cc892f1b6b8861ad49ff4c3ca3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/21/2022
ms.locfileid: "69131333"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Utiliser des modèles d’équipe dans le Centre d’administration Teams

**La possibilité de créer des modèles personnalisés n’est pas encore prise en charge pour les clients EDU.**

> [!NOTE]
> - Les canaux privés et partagés ne sont actuellement pas pris en charge dans les modèles d’équipe. La création de canaux privés et partagés n’est pas incluse dans les définitions de modèle.
>
> - Les étiquettes de confidentialité ne sont pas prises en charge dans les modèles d’équipe dans les environnements GCC. L’option d’étiquette de confidentialité du flux Créer une équipe à partir du modèle ne sera pas appliquée à l’équipe.

## <a name="overview"></a>Vue d’ensemble

Un modèle d’équipe dans Microsoft Teams est une définition de la structure d’une équipe conçue autour d’un besoin ou d’un projet métier. En tant qu’administrateur, vous pouvez utiliser des modèles pour déployer facilement des équipes cohérentes au sein de votre organisation. Avec les modèles, vos utilisateurs peuvent rapidement créer des espaces de collaboration riches avec des paramètres, des canaux et des applications prédéfinis.

Vous pouvez gérer les modèles d’équipe dans le Centre d’administration Microsoft Teams ou à l’aide de PowerShell. Vous pouvez utiliser les modèles prédéfinis que nous fournissons et vous pouvez également [créer vos propres modèles personnalisés](#create-your-own-team-templates). Vous pouvez également [appliquer des stratégies de modèle](#apply-team-template-policies) pour contrôler les modèles disponibles pour vos utilisateurs dans Teams.

Cet article vous donne une vue d’ensemble de l’utilisation des modèles d’équipe dans le Centre d’administration Teams. Vous découvrirez les propriétés prises en charge dans les modèles, les modèles prédéfinis que nous fournissons, les limites de taille des modèles, la création et la gestion des modèles, etc.

> [!NOTE]
> Vos utilisateurs peuvent [créer des équipes à partir de modèles d’équipe prédéfinis ou personnalisés](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) dans l’application Teams. Les développeurs peuvent également créer des équipes par programmation à partir de modèles d’équipe prédéfinis ou personnalisés à l’aide de Microsoft Graph. Pour en savoir plus, consultez [Prise en main des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md).

## <a name="team-template-capabilities"></a>Fonctionnalités de modèle d’équipe

La plupart des propriétés d’une équipe sont incluses et prises en charge par les modèles d’équipe. Toutefois, certaines propriétés et fonctionnalités ne sont actuellement pas prises en charge. Voici un résumé de ce qui est inclus et de ce qui n’est pas inclus dans les modèles d’équipe.

| **Propriétés d’équipe prises en charge par les modèles d’équipe** | **Les propriétés d’équipe ne sont pas encore prises en charge par les modèles d’équipe** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Type de modèle | Appartenance à une équipe |
| Nom de l’équipe | Image de l’équipe |
| Description de l’équipe | Paramètres du canal |
| Visibilité de l’équipe (publique ou privée) | Connecteurs |
| Paramètres d’équipe (par exemple, membre, invité, @ mentions) | Fichiers et contenu |
| Canal defavorite automatique | |
| Application installée | |
| Onglets épinglés | |

> [!NOTE]
> Nous allons ajouter d’autres fonctionnalités de modèle dans les prochaines versions de Microsoft Teams. Par conséquent, vérifiez les informations les plus récentes sur les propriétés prises en charge.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Modèles d’équipe prédéfinis dans le Centre d’administration Teams

Voici les modèles d’équipe prédéfinis qui sont disponibles dans le Centre d’administration Teams. Les modèles prédéfinis sont des modèles que nous avons créés pour des secteurs spécifiques. Pour afficher ces modèles, dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Modèles d’équipe** **Teams** > .

Vous pouvez dupliquer des modèles prédéfinis, mais vous ne pouvez pas les modifier. Si vous souhaitez modifier les propriétés d’un modèle prédéfini, vous pouvez créer un modèle à partir d’un modèle existant, puis ajouter ou supprimer les propriétés souhaitées. Gardez à l’esprit que certaines propriétés de certains modèles ne peuvent pas être modifiées.

> [!NOTE]
> Un astérisque (*) indique que le modèle est un *modèle connecté à Microsoft 365*. Lorsque les utilisateurs créent une équipe à l’aide du modèle, le modèle SharePoint connecté est appliqué au site et à l’équipe. Les composants SharePoint tels que les pages, les listes et les intégrations Power Platform sont automatiquement ajoutés et épinglés en tant qu’onglets au canal Général de l’équipe. Les utilisateurs peuvent modifier ces pages et listes directement à partir de Teams.
>
> Pour en savoir plus sur les modèles SharePoint, voir [Appliquer et personnaliser des modèles de site SharePoint](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

>[!div class="mx-tdBreakAll"]
>| Type de modèle | TemplateId | Propriétés fournies avec ce modèle de base |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Gérer un projet* |`com.microsoft.teams.template.ManageAProject`| Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Ressources</li> <li>Planification</li></ul> Applications :<ul><li>Approbations</li><li>Bulletins</li><li>Listes<ul><li>Suivi de projet</li><li>Suivi des problèmes</li></ul></li><li>Étapes</li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>Notre site</li></ul></li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul> |
| Gérer un événement*|`com.microsoft.teams.template.ManageAnEvent` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Budget</li> <li>Contenu</li><li>Logistique</li> <li>Planification</li> <li> Marketing et pr.</li></ul> Applications :<ul><li>Approbations</li><li>Bulletins</li> <li>Idées des employés</li><li>Listes<ul><li>Planificateur de contenu</li></ul></li><li>Étapes</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint Pages<ul><li>Notre site</li><li>À propos de notre événement</li></ul><li>Tâches par planificateur et à faire</li><li>Wiki</li> |
|Intégrer les employés*|`com.microsoft.teams.template.OnboardEmployees` | Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Conversation avec les employés</li> <li>Formation</li></ul>Applications :<ul><li>Bulletins</li><li>Idées des employés</li><li>Listes<ul><li>Liste de vérification de l’intégration</li></ul></li><li>Étapes</li><li>Power Automate</li> <li>SharePoint Pages<ul><li>Prise en main</li><li>Formation</li></ul><li>Tâches par planificateur et à faire</li><li>Viva Engage</li><li>Wiki</li></ul>|
| Adopter Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Canaux : <ul><li>Général</li> <li>Annonces</li> <li>Champions Corner</li> <li>Formulaires d’équipe</li><li>Calendrier</li></ul> Applications : <ul><li>Wiki</li>  <li>Calendrier du canal</li> <li>Étapes</li><li>Bulletins</li></ul>
|Organiser le support technique*| `com.microsoft.teams.template.OrganizeHelpDesk`|Canaux :<ul><li>Général</li><li>Annonces</li><li>FAQ</li></ul>Applications :<ul><li>Signalement des problèmes</li><li>Listes<ul><li>Appareils</li><li>Billets</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>Notre site</li><li>Foire aux questions</li></ul></li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul> |
|Réponse aux incidents| `com.microsoft.teams.template.CoordinateIncidentResponse`|Canaux : <ul><li>Général<li>Annonces</li><li>Logistique</li><li>Planification</li><li>Récupération</li><li>Urgent</li></ul> Applications : <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>Microsoft Office SharePoint Online</li><li>Tâches</li> <li>Approbations</li> <li>Inspection</li> <li>Power Automate</li><li>Bulletins</li><li>Étapes</li></ul>|
| Communications de crise* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Canaux : <ul><li>Général<li>Annonces</li><li>Mise à jour de l’exécutif</li><li>Planification</li><li>Logistique</li></ul>Applications : <ul><li>Approbations</li><li>Signalement des problèmes</li><li>Listes<ul><li>Planificateur de contenu</li><li>Plan de projet</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint Pages<ul><li>Notre site</li><li>Dernière mise à jour</li></ul><li>Tâches par planificateur et à faire</li>|
| Gérer un Store*| `com.microsoft.teams.template.retailStore` |Canaux : <ul><li>Général<li>Shift Handoff</li><li>Préparation du magasin</li><li>Formation</li></ul> Applications : <ul><li>Approbations</li><li>Inspection</li><li>Listes<ul><li>Liste d’inventaire</li></ul></li><li>SharePoint Pages<ul><li>Notre magasin</li></ul></li><li>Shifts</li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul>|
|Succursale bancaire| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Canaux : <ul><li>Général<li>Annonces</li><li>Blotti</li><li>Réunions avec des clients</li><li>Demande d’approbations </li><li>Accompagnement</li><li>Développement des compétences</li><li>Traitement des prêts</li><li>Plaintes des clients</li><li>Félicitations</li><li>Trucs amusants</li><li>Conformité</li></ul>Applications :<ul><li>Compliment </li><li>Signalement de problèmes</li><li>Page Wiki</li><li>Calendrier</li><li>Approbations</li><li>Bulletins</li><li>Idées</li></ul>|
| Soins aux patients| `com.microsoft.teams.template.healthcareWard`| Canaux :<ul><li>Général</li><li>Annonces</li><li>Blotti</li><li>Rondes</li><li>Personnel</li><li>Formation</li></ul> Applications : <ul><li>Wiki</li><li>Listes  </li><li>Approbations</li><li>Bulletins</li><li>Inspection</li></ul>|
|Hôpital| `com.microsoft.teams.template.healthcareHospital` |Canaux : <ul><li>Général</li><li>Annonces</li><li>Conformité</li><li>Consignataires</li><li>Ressources humaines</li><li>Pharmacie</li></ul> Applications : <ul><li>Wiki</li><li>Listes</li><li>Tâches</li><li>Approbations</li><li>Shifts</li><li>Bulletins</li><li>Inspection</li><li>Idées</li></ul>|
|Qualité et sécurité |`com.microsoft.teams.template.QualitySafety`|Canaux : <ul><li>Général<li>Annonces</li><li>Leadership</li><li>Entretien</li><li>Ligne de production 1</li><li>Ligne de production 2</li><li>Ligne de production 3</li><li>Santé et sécurité</li><li>Formation</li><li>Trucs amusants</li></ul> Applications : <ul><li>Wiki</li><li>Tâches</li> <li>Signalement de problèmes</li> <li>Inspection</li> </ul>|
|Vente au détail pour les gestionnaires*| `com.microsoft.teams.template.retailManagerCollaboration` |Canaux : <ul><li>Général<li>Opérations</li><li>Apprentissage</li></ul> Applications : <ul><li>Approbations</li><li>Inspection</li><li>SharePoint Pages<ul><li>Notre magasin</li></ul></li><li>Tâches par planificateur et à faire</li><li>Wiki</li></ul>|
|Gérer les bénévoles| `com.microsoft.teams.template.ManageVolunteers` |Canaux : <ul><li>Général<li>Annonces</li><li>Rapports</li><li>Gestion des bénévoles</li><li>Opportunités d’engagement</li><li>Intégration des volontaires</li></ul> Applications : <ul><li>Site web</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Tâches</li><li>Microsoft Office SharePoint Online</li><li>OneNote</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>Modèles d’équipe par catégorie et secteur d’activité

Pour plus d’informations sur les façons d’utiliser les modèles prédéfinis dans votre secteur d’activité, consultez :

- [Modèles d’équipe généraux](general-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe financière](financial-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe du secteur public](government-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe de soins de santé](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Modèles d’équipe de fabrication](manufacturing-teams-templates-in-the-admin-console.md)
- [Modèles d’équipe à but non lucratif](team-templates-nonprofit.md)
- [Modèles d’équipe de vente au détail](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>Limites de taille du modèle d’équipe

Les modèles sont limités à un nombre spécifique de canaux, d’onglets et d’applications.

 > [!Note]
 > Vous pouvez ajouter d’autres canaux, onglets et applications à l’équipe après sa création à partir d’un modèle.

|Fonctionnalité | Limite|
|-|-|
|Canaux par modèle | 15 |
|Onglets par canal dans un modèle | 20 |
|Applications par modèle | 50|

Pour plus d’informations, consultez [Limites et spécifications de Teams](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Gérer les modèles d’équipe

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Gérer les modèles d’équipe dans le Centre d’administration Teams

#### <a name="view-team-templates"></a>Afficher les modèles d’équipe

Pour afficher les modèles d’équipe, dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Modèles d’équipe Teams** > . Sélectionnez un modèle pour afficher plus de détails, notamment les canaux et les applications qu’il contient.

#### <a name="create-your-own-team-templates"></a>Créer vos propres modèles d’équipe

Vous pouvez créer vos propres modèles personnalisés à partir de zéro, à partir d’une équipe existante et à partir d’un modèle existant. Pour en savoir plus, consultez les articles :

- [Créer un modèle d’équipe personnalisé](create-a-team-template.md)
- [Créer un modèle à partir d’une équipe existante](create-template-from-existing-team.md)
- [Créer un modèle d’équipe à partir d’un modèle d’équipe existant](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Appliquer des stratégies de modèle d’équipe

Pour contrôler les modèles que les utilisateurs voient dans Teams pour [créer des équipes](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b), vous pouvez définir des stratégies de modèles et les affecter aux utilisateurs et aux groupes de votre organisation. Pour en savoir plus, consultez [Gérer les modèles d’équipe dans le Centre d’administration Teams](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Gérer les modèles d’équipe à l’aide de PowerShell

Utilisez les applets de commande suivantes pour gérer vos modèles dans PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>Articles connexes

- [Créer une équipe à partir d’un modèle](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Utiliser des modèles d’équipe à l’aide de Microsoft Graph](get-started-with-teams-templates.md)
- [Cloner une équipe](/graph/api/team-clone)
- [Vue d’ensemble de l’intégration de Teams et SharePoint](/sharepoint/teams-connected-sites)
