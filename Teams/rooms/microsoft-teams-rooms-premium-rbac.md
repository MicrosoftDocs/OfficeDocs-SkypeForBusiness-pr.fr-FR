---
title: Contrôle d’accès basé sur les rôles avec le service Microsoft teams Premium
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Apprenez-en davantage sur le contrôle d’accès basé sur les rôles grâce au service géré par Microsoft Teams.
f1keywords: ''
ms.openlocfilehash: ec8bb770f1dd843c569a98dd909c87ef3ca14dd0
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788781"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Contrôle d’accès basé sur un rôle avec le service géré Microsoft teams

Le contrôle d’accès basé sur les rôles (RBAC) dans le service géré Microsoft teams vous permet de gérer l’accès des utilisateurs aux données des ressources de la salle au sein de votre organisation. En attribuant des rôles aux utilisateurs de service Portal, vous pouvez limiter ce qu’ils peuvent afficher et modifier. Chaque rôle dispose d’un ensemble d’autorisations qui déterminent le niveau d’accès et de modification des utilisateurs avec ce rôle dans votre organisation.

Pour créer, modifier ou affecter des rôles, votre compte doit avoir une des autorisations suivantes :

- Administrateur général via Azure Active Directory (Azure AD)
- Administrateur de service géré via le portail de service géré de Microsoft teams

## <a name="what-is-a-role"></a>Qu’est-ce qu’un rôle ?

Un rôle définit le jeu d’autorisations accordé aux utilisateurs attribués à ce rôle. Pour le moment, le service géré en salle Microsoft teams comporte trois rôles intégrés : **administrateur de service géré**, **site Web**et **site Tech**. Ils couvrent certains scénarios courants liés aux utilisateurs de votre organisation qui peuvent être impliqués dans la gestion de vos salles.

Pour afficher les rôles, dans le volet de navigation de gauche du portail de service géré de Microsoft Teams, accédez à **rôles**, puis sélectionnez l’un des rôles pour afficher les propriétés, les autorisations et les affectations du rôle.  

- **Propriétés**: nom, type de rôle et description
- **Autorisations**: affiche les fonctionnalités et le niveau d’autorisation auxquelles le rôle a accès.
- **Affectations**: liste des affectations de rôles définissant quels utilisateurs disposent des autorisations configurées sur l’étendue des comptes de ressources de salle. Un rôle peut avoir plusieurs affectations, et un utilisateur peut être dans plusieurs affectations.

## <a name="built-in-roles"></a>Rôles prédéfinis

Vous pouvez affecter des rôles intégrés à des groupes ou des utilisateurs sans configuration supplémentaire. Gardez à l’esprit que vous ne pouvez pas supprimer ou modifier le nom, la description, le type ou les autorisations d’un rôle intégré.

- **Administrateur de service géré**: dispose d’un accès complet au portail Microsoft teams Premium Service.
- **Responsable de site**: organise les salles, a accès aux rapports et peut gérer les tickets. Impossible de réinitialiser la clé d’inscription ou d’apporter des modifications à la configuration du service.  
- **Site Tech**: gère les tickets pour des salles spécifiques. Ne disposez pas des autorisations nécessaires pour modifier le service ou organiser des salles dans le service.

Le tableau suivant récapitule ce que chaque rôle peut faire.

|Fonctionnalités |Permission |Administrateur de service géré  |Responsable de site  |Site Tech  |
|---------|---------|---------|---------|---------|
|Vestiaire     |Afficher        |&#10004;           |&#10004;           |&#10004;  |
|    |Modifiant         |&#10004;           |&#10004;           |&#10004; |
|    |Clé de réinitialisation         |&#10004;           |         ||
|    |Télécharger la clé         |&#10004;           |&#10004;          |&#10004; |
|    |Désinscrivent         |&#10004;           |&#10004;           |&#10004; |
|Gestion des groupes   |Create         |&#10004;           |&#10004;           ||
|    |Afficher       |&#10004;          |&#10004;           ||
|    |Modifiant         |&#10004;           |&#10004;           ||
|Gestion de la sonnerie de mise à jour    |Create         |&#10004;           |&#10004;           ||
|    |Afficher         |&#10004;           |&#10004;           ||
|    |Modifiant         |&#10004;           |&#10004;           ||
|Rapports   |Afficher        |&#10004;           |&#10004;           ||
|Gestion des tickets   |Créer un incident client         |&#10004;           |&#10004;           |&#10004;  |
|    |Afficher         |&#10004;           |&#10004;           |&#10004;  |
|    |Mettre à jour         |&#10004;           |&#10004;           |&#10004;  |
|Paramètres de service géré de Microsoft teams    |Afficher         |&#10004;           |         ||
|    |Modifiant        |&#10004;           |         ||
|Gestion des rôles    |Afficher         |&#10004;           |         ||
|    |Modifiant         |&#10004;           |         ||

## <a name="assign-a-role"></a>Attribuer un rôle

Pour attribuer des rôles, vous devez être un administrateur général ou un administrateur de service géré.

1. Dans le volet de navigation de gauche du portail de service géré de Microsoft Teams, accédez à **rôles**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Capture d’écran de la page de contrôle d’accès montrant les rôles":::

2. Sélectionnez le rôle que vous voulez attribuer.
3. Dans le volet de rôles, sélectionnez **affectations**  >  **Ajouter**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Capture d’écran de l’option Ajouter pour ajouter un rôle.":::

4. Dans la page **paramètres généraux** , sous **Propriétés**de l’affectation, entrez un nom pour ce devoir. La description est facultative. Cliquez sur **suivant.**
5. Dans la page **membres** , dans la zone **Rechercher un utilisateur ou un groupe de sécurité** , entrez le nom d’un utilisateur ou d’un groupe de sécurité de votre client auquel vous voulez accorder des autorisations, puis terminez la sélection. Cliquez sur **suivant**. 
6. Dans la page **étendue** , dans la zone de **recherche de salle ou de groupe** , tapez le nom d’une salle ou d’un groupe de pièces que l’utilisateur est autorisé à gérer. Cliquez sur **suivant**.
7. Dans la page **Terminer** , passez en revue les détails de votre devoir. Si vous êtes satisfait de la configuration, sélectionnez **Ajouter une affectation**. Si vous voulez modifier une section, utilisez le bouton **précédent** ou sélectionnez l’étape dans le volet de navigation de gauche.  

## <a name="related-topics"></a>Voir aussi

- [Service géré en salle Microsoft teams](microsoft-teams-rooms-premium.md)
