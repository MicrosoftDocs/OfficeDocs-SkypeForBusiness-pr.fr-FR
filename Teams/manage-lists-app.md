---
title: Gérer l’application Lists pour votre organisation dans Teams
author: cichur
ms.author: v-cichur
ms.reviewer: anach,v-jasuk
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Découvrez comment gérer l’application Lists pour les utilisateurs de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365initiative-lists
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: fa5d9c3f1c74133b96eda81d7c56c3f353265b99
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615340"
---
# <a name="manage-the-lists-app-for-your-organization-in-microsoft-teams"></a>Gérer l’application Lists pour votre organisation dans Microsoft Teams

## <a name="overview-of-lists"></a>Présentation de Lists

L’application Lists dans Microsoft Teams permet aux utilisateurs de votre organisation de suivre les informations, d’organiser leur travail et de gérer les flux de travail. Avec Lists, les utilisateurs peuvent suivre des données telles que les problèmes, les ressources, les routines, les contacts, les inventaires, les incidents, les prêts, les patients, etc. à l’aide d’affichages, de règles et d’alertes personnalisables pour synchroniser tous les membres de l’équipe.

Dans Teams, les utilisateurs accèdent à Lists grâce à un onglet dans un canal. Cliquer sur **+** pour ouvrir la galerie dans un onglet et ajouter une nouvelle instance d’onglet d’application Lists à un canal pour commencer.

![Application Lists dans la galerie dans un onglet](media/lists-tab.png)

Les utilisateurs peuvent créer de nouvelles listes ou épingler des listes existantes à partir de la même équipe ou d’un autre site SharePoint auquel ils ont accès. De nouvelles listes peuvent être créées à partir de zéro, à partir de modèles intégrés, en fonction de la structure d’une liste existante ou en important des données à partir d’un classeur Excel. Lists est disponible dans les clients pour ordinateur de bureau, les clients web et les clients mobiles Teams.

![comment créer une liste dans l’application Lists](media/lists-create-list.png)

## <a name="templates"></a>Modèles

Les modèles dans Lists sont adaptés aux scénarios de suivi des informations courants pour les utilisateurs. Chaque modèle inclut une structure de liste prédéfinie, des dispositions de formulaire et des options de mise en forme dans l’affichage de liste et l’affichage des détails pour permettre aux utilisateurs de démarrer rapidement. Après avoir sélectionné un modèle, les utilisateurs obtiennent un aperçu de la liste, ainsi que des exemples de données. Voici quelques exemples de la manière dont les équipes de votre organisation peuvent utiliser les modèles prédéfinis dans les listes :

- Suivez les problèmes et résolvez-les à l’aide du modèle Suivi des problèmes.
- Organisez tous les détails de votre événement avec le modèle Programme de l’événement.
- Utilisez le modèle Patients pour enregistrer les besoins et l’état des patients pour les équipes chargées de la santé dans votre organisme de santé afin de surveiller et de coordonner les soins.
- Suivez l’état des demandes de prêt avec le modèle Prêts.

## <a name="example-scenario"></a>Exemple de scénario

Un bureau de poste local est responsable du tri et de la livraison du courrier dans son district. Chaque matin, le bureau de poste se réunit en équipe pour passer en revue les objectifs quotidiens, partager les annonces et discuter des incidents connus.

Après la réunion, les facteurs récupèrent leur courrier et commencent leur itinéraire de livraison. Des incidents peuvent survenir le long d’un itinéraire, par exemple, un accident de voiture, un problème lié à un chien ou une manifestation. Lorsque les facteurs rencontrent un incident, ils utilisent Teams sur leurs appareils mobiles pour enregistrer les détails de l’incident, qui sont suivis dans une liste dans le canal d’équipe. Tous les membres de l’équipe, y compris les facteurs sur le terrain, peuvent consulter ces informations et rester informés.

Avant de passer à Teams, les facteurs devaient retourner au bureau de poste pour remplir un formulaire papier afin de signaler un incident qui était inscrit dans un tableur Excel. Teams offre aux facteurs une expérience, en priorité sur mobile, dans laquelle ils peuvent utiliser Lists pour signaler les incidents sur le terrain quand ils se produisent, partager les détails des incidents avec les membres de l’équipe, avoir des conversations à leur sujet sur le canal et résoudre des incidents.

## <a name="what-you-need-to-know-about-lists"></a>Ce que vous devez savoir sur les Lists

### <a name="lists-is-available-in-every-team-and-channel"></a>Lists est disponible dans chaque équipe et dans chaque canal

Lists est pré-installée pour tous les utilisateurs de Teams et est disponible directement dans la galerie dans un onglet de chaque équipe et de chaque canal. Cela signifie que les utilisateurs n’ont pas besoin d’accéder à l’App Store Teams pour l’installer.

### <a name="lists-and-sharepoint"></a>Lists et SharePoint

Les données de Lists sont stockées dans le site d’équipe SharePoint Online. Pour en savoir plus sur la manière dont SharePoint Online interagit avec Teams, consultez l’article [Interaction de SharePoint Online et OneDrive Entreprise avec Teams](SharePoint-OneDrive-interact.md).

Les autorisations définies dans SharePoint s’appliquent aux listes créées dans l’application Lists. Par défaut, les listes héritent des autorisations du site auquel elles appartiennent. Ces autorisations régissent les types d’actions que les utilisateurs peuvent effectuer, par exemple s’ils peuvent créer ou modifier des listes. Pour en savoir plus, consultez les articles [Niveaux d’autorisation dans SharePoint](/sharepoint/understanding-permission-levels) et [Autorisations utilisateur et niveaux d’autorisation dans SharePoint Server](/sharepoint/sites/user-permissions-and-permission-levels).

Dans certains scénarios, vous souhaiterez peut-être restreindre les actions que les utilisateurs peuvent effectuer dans les listes. Par exemple, une personne dans une équipe modifie l’affichage des listes, ce qui le modifie pour tous les membres de l’équipe, et vous souhaitez autoriser uniquement le propriétaire de l’équipe ou certains membres de l’équipe à modifier les affichages des listes. Pour en savoir plus, consultez l’article [Personnaliser les autorisations pour une liste ou une bibliothèque SharePoint](https://support.microsoft.com/office/customize-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782#ID0EAACAAA=Online,_2019,_2016,_2013).

> [!NOTE]
> À ce stade, les autorisations de propriétaire et de membre d’une équipe ne sont en aucun cas liées aux autorisations du site d’équipe qui régissent le comportement des listes ou de l’application Lists. Cependant, en fonction des commentaires et de l’utilisation des clients, cela sera pris en compte pour une future itération du produit.  

### <a name="limitations"></a>Limites

Avec Lists, les utilisateurs bénéficient d’une expérience web, mobile et pour ordinateur de bureau. Il est important de savoir que les utilisateurs ne peuvent pas créer de nouvelles listes ou épingler des listes existantes en utilisant Lists sur le client mobile Teams. Pour afficher ou modifier une liste sur le client mobile Teams, une liste doit d’abord être créée ou ajoutée avec Lists sur le client Teams web ou pour ordinateur de bureau.

Les invités peuvent ajouter des éléments de liste à des listes existantes, démarrer de nouvelles conversations à propos des éléments de liste et répondre aux conversations existantes concernant les éléments de liste.

### <a name="lists-and-the-sharepoint-app"></a>Lists et l’application SharePoint

Si les utilisateurs de votre organisation ont créé des listes à l’aide de l’application SharePoint, ces listes seront automatiquement déplacées vers Lists sans qu’aucune action ne soit nécessaire de la part de l’utilisateur. Pour obtenir la meilleure et la plus riche expérience d’intégration de listes dans Teams, utilisez l’application Lists et épinglez vos listes existantes.

## <a name="set-up-lists"></a>Configurer Lists

### <a name="enable-or-disable-lists-in-your-organization"></a>Activer ou désactiver Lists dans votre organisation

Lists est activé par défaut pour tous les utilisateurs Teams de votre organisation. Vous pouvez désactiver ou activer l’application au niveau de l’organisation sur la page [Gérer les applications](manage-apps.md) dans le centre d’administration Microsoft Teams.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, accédez aux **applications Teams** > **Gérer les applications**.
2. Effectuez l’une des opérations suivantes :

    - Pour désactiver Lists pour votre organisation, recherchez l’application Lists, sélectionnez-la, puis cliquez sur **Bloquer**.
    - Pour activer Lists pour votre organisation, recherchez l’application Lists, sélectionnez-la, puis cliquez sur **Autoriser**.

### <a name="enable-or-disable-lists-for-specific-users-in-your-organization"></a>Activer ou désactiver Lists pour des utilisateurs spécifiques de votre organisation

Pour autoriser ou empêcher des utilisateurs spécifiques de votre organisation d’utiliser Lists, assurez-vous que Lists est activé pour votre organisation sur la page [Gérer les applications](manage-apps.md), puis créez une stratégie d’autorisation d’application personnalisée et attribuez-la à ces utilisateurs. Pour plus d’informations, consultez [Gérer les stratégies d’autorisation d’application dans Teams](teams-app-permission-policies.md).

## <a name="search-the-audit-log-for-list-events"></a>Rechercher des événements de liste dans le journal d’audit 

Les listes sont activées avec l’audit au niveau de l’entreprise afin que vous puissiez rechercher des listes et des événements d’élément de liste dans le journal d’audit du Centre de sécurité et conformité. Pour en savoir plus, consultez l’article [Rechercher dans le journal d’audit dans le Centre de sécurité et de conformité](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).

Pour obtenir la liste des événements d’audit pertinents pour l’application Lists dans Teams, consultez la rubrique [Activités de liste SharePoint](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#sharepoint-list-activities).

Pour effectuer une recherche dans le journal d’audit, vous devez au préalable activer la fonctionnalité d’audit dans le [Centre de sécurité et de conformité](https://protection.office.com). N’oubliez pas que les données d’audit ne sont disponibles qu’à partir du moment où vous avez activé l’audit.

## <a name="power-automate-power-apps-and-graph-api"></a>Power Automate, Power Apps et API Graph

Lists prend en charge [Power Automate](/power-automate/flow-types) pour les flux de travail et [Power Apps](/powerapps/maker/canvas-apps/customize-list-form) pour les formulaires de liste. Les développeurs peuvent utiliser l’[API Lists](/sharepoint/dev/sp-add-ins/working-with-lists-and-list-items-with-rest) pour connecter des données de liste en tant que source via Microsoft Graph.

## <a name="give-feedback-or-report-an-issue"></a>Envoyer des commentaires ou signaler un problème
  
Pour nous envoyer des commentaires ou signaler un problème, cliquez sur **Aide** en bas de la navigation de gauche dans Teams, puis sélectionnez **Signaler un problème**. Sélectionnez **Lists**, puis saisissez vos commentaires ou donnez des détails sur le problème que vous rencontrez.

## <a name="related-topics"></a>Rubriques connexes

- [Documentation d’aide pour Lists](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Lists)