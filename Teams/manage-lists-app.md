---
title: Gérer l’application listes de votre organisation
author: LanaChin
ms.author: v-lanac
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment gérer l’application listes dans teams pour les utilisateurs de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 1423c17d57c0074f9e6db1091791eb3f17370414
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158692"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application listes de votre organisation dans Microsoft teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview-of-lists"></a>Vue d’ensemble des listes

L’application listes de Microsoft teams permet aux utilisateurs de votre organisation de suivre les informations, d’organiser le travail et de gérer les flux de travail. Les listes permettent aux utilisateurs de suivre des données telles que des problèmes, des ressources, des routines, des contacts, des stocks, des incidents, des prêts, des patients et bien plus encore en utilisant des affichages, des règles et des alertes personnalisés pour permettre à tous les membres de l’équipe de rester synchronisés.

Dans Teams, les utilisateurs accèdent aux listes en tant qu’onglet dans un canal. Cliquez sur **+** pour ouvrir la Galerie d’onglets et ajouter une nouvelle instance de l’onglet application de listes à un canal pour commencer. 

![Capture d’écran de l’application listes dans la Galerie d’onglets](media/lists-tab.png)

Les utilisateurs peuvent créer de nouvelles listes ou épingler des listes existantes à partir d’une même équipe ou d’un autre site SharePoint auquel ils ont accès. Les nouvelles listes peuvent être créées à partir de zéro, de modèles prédéfinis en fonction de la structure d’une liste existante ou en important des données à partir d’un classeur Excel. L’application listes est disponible dans les applications de bureau, Web et mobiles Teams.

![Capture d’écran de la création d’une liste dans l’application listes](media/lists-create-list.png)

## <a name="templates"></a>Modèles

Les modèles dans les listes sont adaptés aux scénarios de suivi des informations courants pour les utilisateurs. Chaque modèle inclut une structure de liste, des dispositions de formulaire et des options de mise en forme prédéfinies dans un affichage de liste et un niveau d’affichage détaillé pour aider les utilisateurs à démarrer rapidement. Après avoir sélectionné un modèle, les utilisateurs obtiennent un aperçu de l’aspect de la liste, ainsi que des exemples de données. Voici quelques exemples de la manière dont les équipes de votre organisation peuvent utiliser les modèles prédéfinis dans les listes :

- Suivez les problèmes et mettez-les en sortie à l’aide du modèle de suivi des problèmes.
- Organisez tous les détails de votre événement à l’aide du modèle d’itinéraire des événements.
- Le modèle patients vous permet d’enregistrer les besoins et le statut des patients pour les équipes de soins de votre organisation pour la santé afin de surveiller et de coordonner votre attention.
- Effectuez le suivi de l’état des candidatures avec le modèle prêts.

## <a name="example-scenario"></a>Exemple de scénario

Un bureau de poste local est tenu de trier et de remettre des messages dans leur quartier. Chaque matin, le Bureau de poste possède une équipe Huddle pour passer en revue les objectifs quotidiens, partager des annonces et discuter d’incidents connus.

Après le Huddle, les opérateurs de messagerie captent leurs messages et commencent leur itinéraire de remise. Les incidents peuvent se produire le long d’un itinéraire, par exemple un accident de véhicule, un problème lié à un chien ou une impayée de réseaux sociaux. Lorsque les opérateurs de messagerie rencontrent un problème, ils utilisent teams sur leurs appareils mobiles pour enregistrer les détails de l’incident, qui sont répertoriés dans une liste du canal d’équipe. Tout le monde au sein de l’équipe, y compris les opérateurs de messagerie dans le champ, peut voir ces informations et rester informé.

Avant de migrer vers les équipes, les opérateurs de messagerie doivent retourner au bureau de poste pour compléter un formulaire de copie papier afin de signaler un incident entré dans une feuille de calcul Excel. Teams permet aux transporteurs de courrier électronique d’abord d’utiliser des listes pour signaler les incidents dans le champ au fur et à mesure, partager les détails de l’incident avec les membres de l’équipe, avoir des conversations sur celles-ci et résoudre les problèmes liés à la résolution du problème.

## <a name="what-you-need-to-know-about-lists"></a>Ce que vous devez savoir sur les listes

### <a name="lists-is-available-in-every-team-and-channel"></a>Les listes sont disponibles dans toutes les équipes et tous les canaux

Les listes sont préinstallées pour tous les utilisateurs d’teams et sont disponibles directement dans la Galerie d’onglets de chaque équipe ou canal. Cela signifie que les utilisateurs n’ont pas besoin d’accéder à l’App Store teams pour l’installer.

### <a name="lists-and-sharepoint"></a>Listes et SharePoint

Listes les données sont stockées dans le site d’équipe SharePoint Online. Pour en savoir plus sur le fonctionnement de SharePoint Online avec Teams, voir [comment SharePoint Online et OneDrive entreprise interagissent avec teams](SharePoint-OneDrive-interact.md).

Les autorisations définies dans SharePoint s’appliquent aux listes créées dans l’application listes. Par défaut, les listes héritent des autorisations du site auxquelles elles appartiennent. Ces autorisations gouvernent les types d’actions que les utilisateurs peuvent effectuer, par exemple pour savoir s’ils peuvent créer ou modifier des listes. Pour en savoir plus, voir [niveaux d’autorisation dans SharePoint](https://docs.microsoft.com/sharepoint/understanding-permission-levels) et [autorisations utilisateur et niveaux d’autorisation dans SharePoint Server](https://docs.microsoft.com/sharepoint/sites/user-permissions-and-permission-levels).

Dans certains scénarios, vous souhaiterez peut-être limiter les actions que les utilisateurs peuvent faire dans les listes. Par exemple, une personne qui travaille sur une équipe modifie un affichage de liste qui la modifie pour tous les membres de l’équipe et vous ne souhaitez autoriser que le propriétaire de l’équipe ou certains membres de l’équipe à modifier les affichages de liste. Pour en savoir plus, voir [personnaliser des autorisations pour une liste ou une bibliothèque SharePoint](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> À ce stade, les autorisations de propriétaire et de membre d’une équipe ne sont pas liées de quelque manière que ce soit aux autorisations sur le site d’équipe qui régissent le comportement des listes ou de l’application listes. Toutefois, en fonction des commentaires des clients et de leur utilisation, ce dernier est considéré comme une itération future du produit.  

### <a name="limitations"></a>Conditions

Avec les listes, les utilisateurs peuvent bénéficier d’une expérience de bureau, Web ou mobile. Il est important de savoir que les utilisateurs ne peuvent pas créer de nouvelles listes ou épingler des listes existantes dans le client Microsoft teams mobile. Pour afficher ou modifier une liste dans le client mobile Teams, une liste doit d’abord être créée ou ajoutée à l’aide de listes sur le bureau teams ou le client Web.

Les invités de [canaux privés](private-channels.md) ne peuvent pas créer ou supprimer une liste ou commencer une nouvelle conversation sur un élément de liste. Ils peuvent ajouter des éléments de liste aux listes existantes et répondre à des conversations existantes sur un élément de liste. Gardez à l’esprit que ces limitations s’appliquent uniquement aux canaux privés.

### <a name="lists-and-the-sharepoint-app"></a>Listes et applications SharePoint

Si les utilisateurs de votre organisation ont créé des listes à l’aide de l’application SharePoint, celles-ci sont déplacées automatiquement vers des listes sans action de l’utilisateur. Pour tirer parti de l’expérience d’intégration des listes les plus complètes dans Teams, utilisez l’application listes et épinglez vos listes existantes.

## <a name="set-up-lists"></a>Définir des listes

### <a name="enable-or-disable-lists-in-your-organization"></a>Activation ou désactivation de listes au sein de votre organisation

La liste est activée par défaut pour tous les utilisateurs d’équipes de votre organisation. Vous pouvez activer ou désactiver l’application au niveau de l’organisation sur la page [gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation de gauche du centre d’administration de Microsoft Teams, accédez à **teams**  >  **Manage** apps.
2. Effectuez l’une des opérations suivantes :

    - Pour désactiver les listes de votre organisation, recherchez l’application listes, sélectionnez-la, puis cliquez sur **bloquer**.
    - Pour activer les listes pour votre organisation, recherchez l’application listes, sélectionnez-la, puis cliquez sur **autoriser**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Activer ou désactiver des listes pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser des listes, assurez-vous que les listes sont activées pour votre organisation dans la page [gérer les applications](manage-apps.md) , puis créez une stratégie d’autorisations d’application personnalisée et attribuez-la à ces utilisateurs. Pour en savoir plus, voir [gérer les stratégies d’autorisation d’applications dans Microsoft teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Effectuer une recherche dans le journal d’audit pour les événements de liste

Les listes sont activées avec l’audit de niveau entreprise afin que vous puissiez Rechercher des listes et des événements d’éléments de liste dans le journal d’audit dans le centre de sécurité & conformité. Pour en savoir plus, voir [effectuer des recherches dans le journal d’audit dans le centre de sécurité & conformité](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Pour obtenir la liste des événements d’audit pertinents pour l’application listes dans Microsoft Teams, voir activités de la [liste SharePoint](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Pour pouvoir effectuer une recherche dans le journal d’audit, vous devez d’abord activer l’audit dans le [Centre de sécurité & conformité](https://protection.office.com). Gardez à l’esprit que les données d’audit sont uniquement disponibles à partir du point d’activation de l’audit.

## <a name="power-automate-power-apps-and-graph-api"></a>Gestion de l’alimentation, applications Power et API Graph

Les listes prennent en charge l' [automate Power](https://preview.flow.microsoft.comconnectors/shared_sharepointonline/?slug=sharepoint) up pour les flux de travail et les [applications Power](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form) pour les formulaires de liste. Les développeurs peuvent utiliser l' [API lists](https://docs.microsoft.com/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) pour lier les données de liste sous forme de sources via Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Envoyer des commentaires ou signaler un problème
  
Pour nous envoyer des commentaires ou signaler un problème, cliquez sur **aide** en bas de la barre de navigation gauche dans équipes, puis sélectionnez **signaler un problème**. Sélectionnez **listes**, puis entrez vos commentaires ou détails sur le problème que vous rencontrez.
