---
title: Contrôle d’accès en fonction du rôle avec Microsoft Teams service Premium salle
author: dstrome
ms.author: dstrome
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
ms.localizationpriority: medium
search.appverid: MET150
description: En savoir plus sur le contrôle d’accès en fonction du rôle avec Salles Microsoft Teams service géré.
f1keywords: ''
ms.openlocfilehash: 9b1a3a770c8b56c9d9ed3b589fa13163d955c294
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728073"
---
# <a name="role-based-access-control-with-the-microsoft-teams-rooms-managed-service"></a>Contrôle d’accès en fonction du rôle avec le service Salles Microsoft Teams géré

Le contrôle d’accès basé sur un rôle dans Salles Microsoft Teams service géré vous aide à gérer l’accès des utilisateurs aux données de ressources de salle dans votre organisation. En attribuant des rôles aux utilisateurs de votre portail de services, vous pouvez limiter ce qu’ils peuvent voir et modifier. Chaque rôle dispose d’un ensemble d’autorisations qui détermine quels utilisateurs disposent de ce rôle peuvent accéder à votre organisation et les modifier.

Pour créer, modifier ou attribuer des rôles, votre compte doit avoir l’une des autorisations suivantes :

- Administrateur général via Azure Active Directory (Azure AD)
- Administrateur de services gérés via le Salles Microsoft Teams de service géré

## <a name="what-is-a-role"></a>Qu’est-ce qu’un rôle ?

Un rôle définit l’ensemble des autorisations accordées aux utilisateurs qui le sont. Pour l’instant, le service géré Salles Microsoft Teams a trois rôles intégrés : Administrateur de **services** gérés, Responsable de **site** et **Tech de site.** Ils couvrent certains scénarios courants pour les utilisateurs de votre organisation qui peuvent être impliqués dans la gestion de vos salles.

Pour voir les rôles, dans le navigation gauche du portail du service géré par Salles Microsoft Teams, sélectionnez Rôles, puis sélectionnez un des rôles pour voir les propriétés, autorisations et affectations du rôle.  

- **Propriétés**: le nom, le type de rôle et la description
- **Autorisations**: répertorie les fonctionnalités et le niveau d’autorisations auquel le rôle a accès.
- **Affectations :** liste des affectations de rôle définissant quels utilisateurs ont les autorisations configurées dans le cadre des comptes de ressources de salle. Un rôle peut avoir plusieurs affectations et un utilisateur peut avoir plusieurs affectations.

## <a name="built-in-roles"></a>Rôles intégrés

Vous pouvez attribuer des rôles intégrés à des groupes ou des utilisateurs sans autre configuration. N’oubliez pas que vous ne pouvez pas supprimer ou modifier le nom, la description, le type ou les autorisations d’un rôle intégré.

- **Administrateur de services gérés**: il dispose d’un accès complet au portail Microsoft Teams salle Premium service.
- **Chef de site**: organise des salles, a accès aux rapports et peut gérer les tickets. Vous ne pouvez pas réinitialiser la clé d’inscription ni apporter de modifications à la configuration du service.  
- **Technique du site**: gère les tickets pour des salles spécifiques. Ne dispose pas des autorisations pour modifier le service ou organiser des salles dans le service.

Le tableau suivant récapitule les opérations que chaque rôle peut faire.

|Fonctionnalités |Autorisation |Administrateur de services gérés  |Chef de site  |Site Tech  |
|---------|---------|---------|---------|---------|
|Salles     |Afficher        |&#10004;           |&#10004;           |&#10004;  |
|    |Modifier         |&#10004;           |&#10004;           |&#10004; |
|    |Réinitialiser la touche         |&#10004;           |         ||
|    |Clé de téléchargement         |&#10004;           |&#10004;          |&#10004; |
|    |Désinscrire         |&#10004;           |&#10004;           |&#10004; |
|Gestion de groupe   |Create         |&#10004;           |           ||
|    |Afficher       |&#10004;          |&#10004;           ||
|    |Modifier         |&#10004;           |           ||
|Mettre à jour la gestion de l’anneau    |Create         |&#10004;           |           ||
|    |Afficher         |&#10004;           |           ||
|    |Modifier         |&#10004;           |           ||
|Rapports   |Afficher        |&#10004;           |&#10004;           ||
|Gestion des tickets   |Créer un incident client         |&#10004;           |&#10004;           |&#10004;  |
|    |Afficher         |&#10004;           |&#10004;           |&#10004;  |
|    |Mettre à jour         |&#10004;           |&#10004;           |&#10004;  |
|Salles Microsoft Teams de service géré    |Afficher         |&#10004;           |         ||
|    |Modifier        |&#10004;           |         ||
|Gestion de rôle    |Afficher         |&#10004;           |         ||
|    |Modifier         |&#10004;           |         ||

## <a name="assign-a-role"></a>Attribuer un rôle

Pour attribuer des rôles, vous devez être administrateur général ou administrateur de service géré.

1. Dans le navigation gauche du portail Salles Microsoft Teams service géré, voir Rôles **Paramètres**  >  **gérés.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-roles.png" alt-text="Capture d’écran de la page de contrôle Access affichant les rôles.":::

2. Sélectionnez le rôle que vous voulez attribuer.
3. Dans le volet rôle, sélectionnez **Ajouter des**  >  **affectations.**

    :::image type="content" source="../media/microsoft-teams-rooms-premium-role-assignments.png" alt-text="Capture d’écran de l’option Ajouter pour ajouter un rôle.":::

4. Dans la page **Paramètres généraux,** sous **Propriétés du devoir,** entrez un nom pour ce devoir. La description est facultative. Sélectionnez **Suivant.**
5. Dans la **page** Membres, dans la zone Rechercher un utilisateur ou un groupe de sécurité, entrez le nom d’un utilisateur ou d’un groupe de sécurité dans votre client auquel vous voulez accorder des autorisations, puis complétez la sélection.  Sélectionnez **Suivant.** 
6. Dans la page **Étendue,** dans la zone Rechercher une salle ou un groupe de salles, tapez le nom d’une salle ou d’un groupe de salles que l’utilisateur sera autorisé à gérer.  Sélectionnez **Suivant.**
7. Dans la page **Fin,** examinez les détails du devoir. Si vous êtes satisfait de la configuration, sélectionnez **Ajouter un devoir.** Si vous voulez modifier une section, utilisez le **bouton** Précédent ou sélectionnez l’étape dans le volet de navigation de gauche.  

## <a name="related-topics"></a>Sujets associés

- [Salles Microsoft Teams service géré](microsoft-teams-rooms-premium.md)
