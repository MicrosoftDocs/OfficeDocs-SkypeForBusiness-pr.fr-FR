---
title: Contrôle d’accès en fonction du rôle dans le portail de gestion Microsoft Teams Pro
author: altsou
ms.author: altsou
manager: serdars
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Découvrez le contrôle d’accès en fonction du rôle dans le portail de gestion Salles Microsoft Teams Pro.
f1keywords: ''
ms.openlocfilehash: 2cc62699cb4f59c3f80726f18bc80323557f966f
ms.sourcegitcommit: baf29d244b428712052553f9e4484e72e727247e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2022
ms.locfileid: "69046881"
---
# <a name="role-based-access-control-in-the-microsoft-teams-pro-management-portal"></a>Contrôle d’accès en fonction du rôle dans le portail de gestion Microsoft Teams Pro

Le contrôle d’accès en fonction du rôle (RBAC) dans le portail de gestion des Salles Microsoft Teams Pro vous permet de gérer l’accès utilisateur aux données des ressources de salle dans votre organisation. En attribuant des rôles aux utilisateurs de votre portail, vous pouvez limiter ce qu’ils peuvent voir et modifier. Chaque rôle dispose d’un ensemble d’autorisations qui déterminent les utilisateurs disposant de ce rôle peuvent accéder et modifier au sein de votre organisation.

Pour créer, modifier ou attribuer des rôles, votre compte doit disposer de l’une des autorisations suivantes :

- Administrateur général via Azure Active Directory (Azure AD)
- Administrateur de services managés via le portail de gestion des Salles Microsoft Teams Pro

## <a name="what-is-a-role"></a>Qu’est-ce qu’un rôle ?

Un rôle définit l’ensemble des autorisations accordées aux utilisateurs affectés à ce rôle. Pour l’instant, le portail de gestion Salles Microsoft Teams Pro a trois rôles intégrés : Administrateur de **service géré**, **Responsable de site** et **Technique du site**. Ils couvrent certains scénarios courants pour les utilisateurs de votre organisation qui peuvent être impliqués dans la gestion de vos salles.

Pour afficher les rôles, dans le volet de navigation gauche du portail de gestion Salles Microsoft Teams Pro, accédez à **Rôles**, puis sélectionnez l’un des rôles pour voir les propriétés, les autorisations et les attributions du rôle.  

- **Propriétés** : nom, type de rôle et description
- **Autorisations** : répertorie les fonctionnalités et le niveau d’autorisations auxquels le rôle a accès.
- **Affectations** : liste des attributions de rôles définissant les utilisateurs qui disposent des autorisations configurées sur l’étendue des comptes de ressources de salle. Un rôle peut avoir plusieurs affectations et un utilisateur peut être dans plusieurs affectations.

## <a name="built-in-roles"></a>Rôles intégrés

Vous pouvez attribuer des rôles intégrés à des groupes ou des utilisateurs sans autre configuration. N’oubliez pas que vous ne pouvez pas supprimer ou modifier le nom, la description, le type ou les autorisations d’un rôle intégré.

- **Administrateur de services managés** : dispose d’un accès complet au portail de gestion microsoft Teams Room Pro.
- **Responsable de site** : organise les salles, a accès aux rapports et peut gérer les tickets. Impossible de réinitialiser la clé d’inscription ou d’apporter des modifications aux configurations de service.  
- **Technique du site** : gère les tickets pour des salles spécifiques. Ne dispose pas des autorisations nécessaires pour modifier les configurations de service ou organiser les salles.

Le tableau suivant récapitule ce que chaque rôle peut faire.

|Fonctionnalités |Autorisation |Administrateur de services managés  |Responsable de site  |Technique du site  |
|---------|---------|---------|---------|---------|
|Chambres     |Afficher        |&#10004;           |&#10004;           |&#10004;  |
|    |Modifier         |&#10004;           |&#10004;           |&#10004; |
|    |Réinitialiser la clé         |&#10004;           |         ||
|    |Télécharger la clé         |&#10004;           |&#10004;          |&#10004; |
|    |Désinscription         |&#10004;           |&#10004;           |&#10004; |
|Gestion des groupes   |Create         |&#10004;           |           ||
|    |Afficher       |&#10004;          |&#10004;           ||
|    |Modifier         |&#10004;           |           ||
|Mettre à jour la gestion des anneaux    |Create         |&#10004;           |           ||
|    |Afficher         |&#10004;           |           ||
|    |Modifier         |&#10004;           |           ||
|Rapports   |Afficher        |&#10004;           |&#10004;           ||
|Gestion des tickets   |Créer un incident client         |&#10004;           |&#10004;           |&#10004;  |
|    |Afficher         |&#10004;           |&#10004;           |&#10004;  |
|    |Mettre à jour         |&#10004;           |&#10004;           |&#10004;  |
|Paramètres du service de gestion des Salles Microsoft Teams Pro    |Afficher         |&#10004;           |         ||
|    |Modifier        |&#10004;           |         ||
|Gestion des rôles    |Afficher         |&#10004;           |         ||
|    |Modifier         |&#10004;           |         ||

## <a name="create-a-custom-role"></a>Créer un rôle personnalisé

Si les rôles intégrés ne répondent pas aux besoins de votre organisation, vous pouvez créer un rôle et configurer ses autorisations comme vous le souhaitez. Pour créer un rôle, vous devez être administrateur général ou administrateur de services gérés. 

1. Dans le volet de navigation gauche du portail de gestion Salles Microsoft Teams Pro, accédez à **Paramètres** > **Rôles**.
2. Sélectionnez **Créer un rôle**.
3. Dans la page **Paramètres généraux** , sous **Propriétés du rôle**, entrez un nom pour ce rôle. Sous **Description**, entrez des détails sur ce rôle. Choisissez **Suivant**.
4. Dans la page **Autorisations** , sous **Autorisations de rôle**, choisissez les autorisations pour ce rôle en cochées les cases appropriées. Choisissez **Suivant** pour créer la première affectation de ce rôle.
5. Dans la page **Affectations** , sous **Propriétés d’affectation**, entrez un nom pour cette affectation. La description est facultative. Sous **Paramètres de notification**, cochez la case **Notifications par e-mail** si les utilisateurs de ce rôle doivent recevoir des notifications par e-mail du service dans les salles dans l’étendue de cette affectation. Choisissez **Suivant**.
6. Dans la page **Membres** , dans la **zone Rechercher un utilisateur ou un groupe de sécurité** , entrez le nom d’un utilisateur ou d’un groupe de sécurité dans votre locataire auquel vous souhaitez accorder des autorisations, puis terminez la sélection. Choisissez **Suivant**. 
7. Dans la page **Étendue** , dans la **zone Rechercher une salle ou un groupe de salles** , tapez le nom d’une salle ou d’un groupe de salles que l’utilisateur sera autorisé à gérer. Choisissez **Suivant**.
8. Dans la page **Terminer** , passez en revue les détails du rôle et de l’attribution. Si vous êtes satisfait de la configuration, choisissez **Ajouter un nouveau rôle**. Si vous souhaitez modifier une section, utilisez le bouton **Précédent** ou sélectionnez l’étape dans le volet de navigation de gauche.  

## <a name="assign-a-role"></a>Attribuer un rôle

Pour attribuer des rôles, vous devez être administrateur général ou administrateur de services managés ou disposer d’un rôle disposant d’autorisations de gestion des rôles.

1. Dans le volet de navigation gauche du portail de gestion Salles Microsoft Teams Pro, accédez à **Paramètres** > **Rôles**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Capture d’écran de la page Contrôle d’accès montrant les rôles.":::

2. Sélectionnez le rôle que vous souhaitez attribuer.
3. Dans le volet de rôle, sélectionnez **Affectations** > **Ajouter**.

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Capture d’écran de l’option Ajouter pour ajouter un rôle.":::

4. Dans la page **Paramètres généraux** , sous **Propriétés d’affectation**, entrez un nom pour cette affectation. La description est facultative. Sous **Paramètres de notification**, cochez la case **Notifications par e-mail** si les utilisateurs de ce rôle doivent recevoir des notifications par e-mail du service dans les salles dans l’étendue de cette affectation. Choisissez **Suivant**. 
5. Dans la page **Membres** , dans la **zone Rechercher un utilisateur ou un groupe de sécurité** , entrez le nom d’un utilisateur ou d’un groupe de sécurité dans votre locataire auquel vous souhaitez accorder des autorisations, puis terminez la sélection. Choisissez **Suivant**. 
6. Dans la page **Étendue** , dans la **zone Rechercher une salle ou un groupe de salles** , tapez le nom d’une salle ou d’un groupe de salles que l’utilisateur sera autorisé à gérer. Choisissez **Suivant**.
7. Dans la page **Terminer** , passez en revue les détails de l’affectation. Si vous êtes satisfait de la configuration, choisissez **Ajouter une affectation**. Si vous souhaitez modifier une section, utilisez le bouton **Précédent** ou sélectionnez l’étape dans le volet de navigation de gauche.  

## <a name="related-topics"></a>Rubriques connexes

- [portail de gestion Salles Microsoft Teams Pro](rooms-pro-management.md)
