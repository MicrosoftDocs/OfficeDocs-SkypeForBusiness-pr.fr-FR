---
title: Gérer des équipes volumineuses dans Microsoft Teams - Bonnes pratiques
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Découvrez les meilleures pratiques de gestion des grandes équipes dans Microsoft Teams pour répondre aux besoins de votre organisation.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- chat-teams-channels-revamp
ms.openlocfilehash: fddf4b5cf80c51977b2a57ceceac8a07e529c51f
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69199076"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gérer des équipes volumineuses dans Microsoft Teams - Meilleures pratiques

Microsoft Teams est tout aussi efficace pour faciliter les communications entre les petits groupes avec des dizaines de membres et les grands groupes avec des milliers de membres. Passez en revue [les limites et spécifications de Teams](limits-specifications-teams.md) pour connaître les mises à jour sur les tailles d’équipe. L’augmentation de la taille de l’équipe entraîne des défis opérationnels et de gestion uniques. Cet article décrit les meilleures pratiques pour la création et la gestion de grandes équipes composées de milliers de membres.

## <a name="value-of-large-teams"></a>Valeur des grandes équipes

Les grandes équipes sont très utiles pour activer les scénarios de collaboration suivants :

- **Collaboration à l’échelle du service** : si votre organisation a plusieurs services tels que Finance, Operations, R&D, etc., vous pouvez créer une seule équipe qui inclut tous les membres d’un service spécifique. Désormais, toutes les communications pertinentes pour un service peuvent être partagées dans cette équipe, ce qui facilite la communication et l’engagement instantanés des membres.

- **Collaboration dans des groupes de ressources d’employés** : les organisations ont souvent de grands groupes de personnes ayant des intérêts mutuels qui appartiennent à un autre service ou groupe de travail. Par exemple, il peut y avoir un groupe de personnes qui partagent une passion pour les finances personnelles et l’investissement. Il est souvent difficile de se connecter dans une grande organisation. Pour développer des communautés pour ces groupes, les administrateurs de locataires peuvent créer une grande équipe qui sert de groupe de ressources à l’échelle de l’entreprise publique que tout le monde peut rejoindre et utiliser. Finalement, ces communautés recueillent des renseignements dont les membres nouveaux et existants peuvent profiter.

- **Collaboration entre les membres internes et externes** : les produits populaires développent souvent une communauté d’utilisateurs précoces qui sont désireux d’essayer de nouvelles versions de produits et de fournir des commentaires. Les utilisateurs précoces développent une relation avec des groupes de produits pour aider à façonner le produit. Dans de tels scénarios, les administrateurs de locataire peuvent configurer une grande équipe qui comprend à la fois des groupes de produits internes et des évaluateurs de produits externes pour faciliter un processus de développement de produit riche. Ces équipes peuvent également fournir un support client à un ensemble sélectionné de clients.

## <a name="create-teams-from-existing-groups"></a>Créer des équipes à partir de groupes existants

Utilisez des groupes de contacts, des groupes de sécurité ou des groupes Office pour démarrer votre équipe. Vous pouvez importer un groupe pour créer une équipe ou créer une équipe à partir d’un groupe Office.

**Importer un groupe pour créer une équipe** : lorsque vous importez un groupe comptant jusqu’à 3 500 membres dans Teams, Teams calcule automatiquement le nombre total de membres dans le groupe. Il s’agit d’une importation unique uniquement et les modifications futures dans le groupe ne seront pas automatiquement mises à jour dans Teams.

**Créer une équipe à partir d’un grand groupe Microsoft 365** : lorsque vous créez une équipe à partir d’un grand groupe Microsoft 365, les membres font automatiquement partie du groupe Microsoft 365 **et** de l’équipe. À l’avenir, à mesure que les membres de l’équipe rejoignent ou quittent le groupe Microsoft 365, ils sont automatiquement ajoutés ou supprimés de l’équipe.

## <a name="bulk-importexportremove-members-in-a-team"></a>Importer/exporter/supprimer des membres en bloc dans une équipe

Le Portail Azure permet aux utilisateurs d’importer/exporter/supprimer en bloc des membres dans un groupe Microsoft 365. Pour plus d’informations, consultez [Pour importer en bloc des membres du groupe](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).

Étant donné que chaque équipe est soutenue par un groupe Microsoft 365, vous pouvez utiliser le Portail Azure pour effectuer ces opérations dans le groupe correspondant à l’équipe. Les opérations des membres seront reflétées dans l’équipe dans les 24 heures.

## <a name="create-channels-to-focus-discussions"></a>Créez des canaux pour orienter les discussions

Vous pouvez limiter les discussions de groupe en créant des canaux ciblés. Consultez [Bonnes pratiques pour l’organisation des équipes](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Restreindre la création de canaux

Si un membre de l’équipe est autorisé à créer des canaux, cette équipe peut avoir des canaux étendus. Les propriétaires d’équipe doivent désactiver la création, la mise à jour, la suppression et la restauration de canaux pour les membres dans **Paramètres > Autorisations des membres**. Consultez [Vue d’ensemble des équipes et des canaux](teams-channels-overview.md).

![Image d’écran montrant la section Autorisations de membre de l’onglet Paramètres de la console d’administration.](media/no-channel-creation.png "Image d’écran de la section Autorisations des membres de l’onglet Paramètres de la console d’administration. Les options Autoriser les membres à créer ou supprimer des canaux sont décochées.")

## <a name="add-favorite-channels"></a>Ajouter des canaux favoris

Pour accélérer l’engagement de l’utilisateur et la découverte de contenu, vous pouvez sélectionner les canaux favoris disponibles par défaut pour l’utilisateur. Dans le volet **Canaux** du Centre d’administration, vérifiez les canaux sous la colonne **Afficher les membres** .

![Image d’écran montrant le volet canaux de la console d’administration.](media/favorite-channels.png "Image d’écran montrant le volet canaux de la console d’administration. Certains canaux sont vérifiés pour Afficher les membres.")

 Pour plus d’informations, consultez [Créer vos premières équipes et canaux](get-started-with-teams-create-your-first-teams-and-channels.md) .

## <a name="regulate-applications-and-bots-in-large-teams"></a>Réglementer les applications et les bots dans les grandes équipes

Pour empêcher l’ajout d’applications ou de bots gênants, les propriétaires d’équipe peuvent désactiver, ajouter, supprimer et charger des applications et des connecteurs pour les membres de l’équipe. Dans le Centre d’administration, sous **Paramètres > Autorisations de membre**, décochez les trois options qui permettent aux membres d’ajouter des applications ou des connecteurs.

![Image d’écran montrant la section Autorisations de membre du volet Paramètres.](media/disable-bots-connectors.png "Image d’écran montrant la section Autorisation membre du volet Paramètres. Les options permettant aux membres d’ajouter des applications ou des connecteurs sont décochées.")

Consultez [vue d’ensemble des applications Teams](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Réglementer les mentions d’équipe et de canal

Les mentions d’équipe et de canal peuvent être utilisées pour attirer l’attention de toute l’équipe sur certains billets de canal. Une fois qu’une mention est utilisée dans une publication, une notification est envoyée à des milliers de membres de l’équipe. Si les notifications sont trop fréquentes, les membres de l’équipe peuvent devenir surchargés et peuvent se plaindre auprès des propriétaires de l’équipe. Pour empêcher les mentions d’équipe ou de canal, désactivez les mentions d’équipe et de canal pour les membres en décochant les cases dans le volet **> @mentions paramètres** des équipes.

![Image d’écran montrant la section Mentions du volet Paramètres.](media/no-at-mentions.png "Image d’écran montrant la section Mentions du volet Paramètres. Les options permettant d’afficher et d’accorder aux membres l’accès aux mentions sont décochées.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Envisagez de configurer la modération au sein de vos canaux

Les propriétaires d’équipe peuvent activer la modération dans un canal afin de contrôler qui peut lancer de nouvelles publications et répondre aux publications de ce canal. Lorsque vous configurez la modération, vous pouvez choisir un ou plusieurs membres de l’équipe à utiliser en tant que modérateurs. Les propriétaires d’équipe sont des modérateurs par défaut. Pour plus d’informations, consultez [Configurer et gérer la modération des canaux](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Rubriques connexes

- [Bonnes pratiques pour l’organisation de Teams](best-practices-organizing.md)
- [Créer une équipe à l’échelle de l’organisation](create-an-org-wide-team.md)