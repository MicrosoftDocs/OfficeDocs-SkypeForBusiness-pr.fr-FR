---
title: Gérer de grandes équipes dans Microsoft teams-meilleures pratiques
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Découvrez les meilleures pratiques en matière de gestion des grandes équipes dans Microsoft teams pour répondre aux besoins de votre organisation.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638904"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Gérer de grandes équipes dans Microsoft teams-meilleures pratiques
======================================================

Microsoft teams permet également de faciliter les communications entre les petits groupes avec des dizaines de membres et des groupes de grande taille avec des milliers de membres. Passez en revue les [limites et les spécifications de](limits-specifications-teams.md) teams pour les mises à jour de tailles d’équipe. Augmentez la taille de l’équipe pour une gestion unique et des défis opérationnels. Cet article décrit les meilleures pratiques pour la création et la gestion de grandes équipes composées de milliers de membres.

## <a name="value-of-large-teams"></a>Valeur des équipes de grande taille

Les équipes de grande taille sont très utiles pour les scénarios de collaboration suivants :

- **Collaboration au niveau du service**: Si votre organisation possède plusieurs services tels que finance, Operations, R&D etc., vous pouvez créer une équipe unique incluant tous les membres d’un service spécifique. À présent, toutes les communications pertinentes pour un service peuvent être partagées dans cette équipe, ce qui facilite la portée et l’engagement instantanés des membres.

- **Collaboration dans les groupes de ressources des employés**: les organisations possèdent souvent de grands groupes de personnes ayant des intérêts mutuels appartenant à un autre service ou groupe de travail. Par exemple, vous pouvez avoir un groupe de personnes qui partagent une passion pour financer et investir. Il est souvent difficile de se connecter au sein d’une grande organisation. Pour développer les communautés de ces groupes, les administrateurs de clients peuvent créer une équipe de grande taille qui fait office de groupe de ressources à l’échelle de l’entreprise publique que tout le monde peut rejoindre et exploiter. Dans le cas du moment, ces communautés collectent des informations que les membres nouveaux et existants peuvent jouir.

- **Collaboration entre les membres internes et externes : les**produits populaires développent souvent une communauté d’anciens décideurs qui souhaitent essayer de nouvelles versions de produits et formuler des commentaires. Les premiers décideurs développent une relation avec des groupes de produits pour faciliter la mise en forme du produit. Dans ces scénarios, les administrateurs de clients peuvent configurer une équipe de grande envergure qui inclut à la fois des groupes de produits internes et des évaluateurs de produit externes pour faciliter le processus de développement d’un produit complet. Ces équipes peuvent également fournir un support technique à un ensemble de clients sélectionnés.

## <a name="create-teams-from-existing-groups"></a>Créer des équipes à partir de groupes existants

Utiliser des groupes de contacts, groupes de sécurité ou groupes Office pour démarrer votre équipe. Vous pouvez importer un groupe pour en faire une équipe ou créer une équipe à partir d’un groupe Office.

**Importer un groupe pour créer une équipe**: lorsque vous importez un groupe contenant jusqu’à 3 500 membres dans Teams, teams calcule automatiquement le nombre total de membres du groupe. Il s’agit d’une importation ponctuelle uniquement et des changements futurs du groupe ne seront pas automatiquement mis à jour dans Teams.

**Créer une équipe à partir d’un groupe microsoft 365 volumineux**: lorsque vous créez une équipe à partir d’un groupe Microsoft 365 volumineux, les membres font automatiquement partie du groupe Microsoft 365 **et** de l’équipe. À l’avenir, au fur et à mesure que les membres d’une équipe rejoignent ou quittent le groupe Microsoft 365, ils sont automatiquement ajoutés ou supprimés de l’équipe.

## <a name="create-channels-to-focus-discussions"></a>Créez des canaux pour orienter les discussions

Vous pouvez affiner les discussions de groupe en créant des canaux ciblés. Découvrez [les meilleures pratiques pour organiser teams](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Restreindre la création de canal

Si un membre d’équipe est autorisé à créer des canaux, cette équipe peut avoir une dispersion du canal. Les propriétaires d’équipe doivent désactiver la création, la mise à jour, la suppression et la restauration de canaux pour les membres des **paramètres > les autorisations des membres**. Voir [vue d’ensemble des équipes et des canaux](teams-channels-overview.md).

![Image de l’écran montrant la section autorisations des membres de l’onglet Paramètres de la console d’administration.](media/no-channel-creation.png "Capture d’écran de la section autorisations des membres de l’onglet Paramètres de la console d’administration. Les options autoriser les membres à créer ou supprimer des canaux sont décochées.")

## <a name="add-favorite-channels"></a>Ajouter des canaux favoris

Pour accélérer les nouvelles opérations de l’utilisateur et la découverte de contenu, vous pouvez sélectionner les canaux préférés disponibles pour l’utilisateur par défaut. Dans le volet **canaux** du centre d’administration, vérifiez les canaux sous la colonne **afficher pour les membres** .

![Image de l’écran montrant le volet canaux de la console d’administration.](media/favorite-channels.png "Capture d’écran de la fenêtre de canal de la console d’administration. Certains canaux sont cochés pour afficher les membres.")

 Pour plus d’informations, voir [créer vos premières équipes et canaux](get-started-with-teams-create-your-first-teams-and-channels.md) .

## <a name="regulate-applications-and-bots-in-large-teams"></a>Réglementer les applications et les robots dans de grandes équipes

Pour empêcher l’ajout d’applications ou de robots distrayants, les propriétaires d’équipe peuvent désactiver, ajouter, supprimer et charger des applications et connecteurs pour les membres de l’équipe. Dans le centre d’administration, sous **paramètres > les autorisations des membres**, désactivez les trois options permettant aux membres d’ajouter des applications ou des connecteurs.

![Image de l’écran montrant la section autorisations des membres du volet Paramètres](media/disable-bots-connectors.png "Image de l’écran montrant la section autorisation de membre du volet Paramètres Les options pour autoriser les membres à ajouter des applications ou des connecteurs ne sont pas cochées.")

Voir [applications, robots, & connecteurs](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Réguler les mentions d’équipe et de canal

Les mentions d’équipe et de canal peuvent être utilisées pour attirer l’attention de l’équipe entière sur certaines publications de canal. Lorsque la mention est utilisée dans un billet, une notification est envoyée à des milliers de membres de l’équipe. Si les notifications sont trop fréquentes, les membres de l’équipe peuvent être surchargés et peuvent se plaindres au propriétaire de l’équipe. Pour empêcher les mentions d’équipe ou de canal, désactivez les mentions d’équipe et de canal pour les membres en désactivant les cases à cocher dans les paramètres des équipes > volet de **@mentions** .

![Capture d’écran illustrant la section à l’adresse du volet Paramètres](media/no-at-mentions.png "Capture d’écran illustrant la section à l’adresse du volet Paramètres Les options permettant d’afficher et de autoriser les membres à accéder aux mentions ne sont pas cochées.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Envisagez de configurer la modération au sein de vos canaux

Les propriétaires d’équipe peuvent activer la modération dans un canal afin de contrôler qui peut lancer de nouvelles publications et répondre aux publications de ce canal. Lorsque vous configurez la modération, vous pouvez choisir un ou plusieurs membres de l’équipe à utiliser en tant que modérateurs. Par défaut, les propriétaires d’équipe sont modérateurs. Pour plus d’informations, reportez-vous à [configurer et gérer la modération de canal](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Rubriques connexes

- [Recommandations en matière d’organisation des équipes](best-practices-organizing.md)
- [Créer une équipe à l’échelle de l’Organisation](create-an-org-wide-team.md)
