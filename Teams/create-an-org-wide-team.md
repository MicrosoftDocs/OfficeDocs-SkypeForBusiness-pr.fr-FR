---
title: Créer une équipe à l’échelle de l’organisation dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et gérer une équipe à l’échelle de l’organisation dans les équipes.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a63b39d0b0ef51326b253e87be99889e9a018a03
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30461059"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Créer une équipe à l’échelle de l’organisation dans Microsoft Teams

Les équipes à l’échelle de l’organisation offrent un moyen automatique pour tout le monde dans une petite ou moyenne organisation soit une partie d’une équipe unique pour la collaboration. 
 
Avec les équipes à l’échelle de l’organisation, les administrateurs globaux peuvent créer facilement une équipe publique qui extrait tous les utilisateurs de l’organisation et conserve l’appartenance à jour avec Active Directory en tant qu’utilisateurs join et laissez l’organisation. Seuls les administrateurs globaux peuvent créer des équipes à l’échelle de l’organisation et actuellement une équipe à l’échelle de l’organisation est limitée aux organisations comptant pas plus de 2 500 utilisateurs. Si ces conditions sont remplies, les administrateurs globaux voir **à l’échelle de l’organisation** en tant qu’option sous **confidentialité** lors de la création d’une équipe. 

![Capture d’écran de l’option d’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation] (media/create-org-wide-team.png "Capture d’écran de l’option d’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation")

> [!NOTE]
> Si vous ne voyez pas l’option **d’échelle de l’organisation** lors de la création d’une équipe et que vous êtes un administrateur global, la fonctionnalité peut toujours être présentant ou votre organisation peut avoir plus de la limite de taille de 2 500 membres. Nous recherchons pour augmenter cette limite à l’avenir.

Lors de la création d’une équipe à l’échelle de l’organisation, les administrateurs globaux sont ajoutés en tant que les propriétaires de l’équipe et tous les utilisateurs actifs sont ajoutés en tant que membres de l’équipe. Les utilisateurs qui sont désactivés pour les équipes, les utilisateurs invités et la plupart des salles ne sont pas ajoutés à l’équipe. Annuaire de votre organisation est mis à jour pour inclure les nouveaux utilisateurs actifs, ou si les utilisateurs ne fonctionnent plus dans votre société et sa licence équipes est désactivée, les modifications sont automatiquement synchronisés et les utilisateurs sont ajoutés ou supprimés de l’équipe. Membres de l’équipe ne peut pas quitter une équipe à l’échelle de l’organisation. En tant que propriétaire de l’équipe, vous pouvez manuellement ajouter ou supprimer des utilisateurs si nécessaire.

> [!NOTE]
> Salles qui ne sont pas d’une liste, d’équipement et de ressources les comptes salle peuvent être ajoutés ou synchronisés vers l’équipe à l’échelle de l’organisation. Les propriétaires de l’équipe peuvent facilement supprimer ces comptes de l’équipe.

## <a name="best-practices"></a>Meilleures pratiques
Pour obtenir le meilleur parti de votre équipe à l’échelle de l’organisation, nous vous recommandons de propriétaires d’équipe, procédez comme suit.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Autoriser uniquement les propriétaires de l’équipe à publier le canal général
Réduire le bruit de canal par l’équipe uniquement de publier des propriétaires pour le canal d’échange général. Accédez à l’équipe et cliquez sur **autres options (...)**  >  **Gérer l’équipe**. Dans l’onglet **paramètres** , cliquez sur **autorisations de membre** > sélectionner **uniquement les propriétaires peuvent publier des messages**.
### <a name="turn-off-team-and-team-name-mentions"></a>Désactiver @team et @ mentions de [nom de l’équipe]
 Réduire @mentions pour empêcher toute la surcharge de l’organisation toute entière. Accédez à l’équipe et cliquez sur **autres options (...)**  >  **Gérer l’équipe**. Dans l’onglet **paramètres** , cliquez sur **@mentions** > désactiver **Afficher les membres de l’option à @team ou @[nom de l’équipe]**. 
### <a name="automatically-favorite-important-channels"></a>Canaux importantes automatiquement favoris
 Conversations spécifiques engage favoris canaux importantes pour tout le monde dans votre organisation. Pour plus d’informations, voir [canaux Auto-favori pour l’ensemble de l’équipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Supprimer des comptes qui ne peuvent pas appartenir
Même si les membres ne peut pas quitter une équipe à l’échelle de l’organisation, en tant que propriétaire de l’équipe, vous pouvez gérer la liste de l’équipe en supprimant des comptes qui n’appartiennent pas. Assurez-vous que les équipes vous permet de supprimer des utilisateurs de votre équipe à l’échelle de l’organisation.  Si vous utilisez une autre façon de supprimer un utilisateur, telles que le centre d’administration Microsoft 365 ou d’un groupe dans Outlook, l’utilisateur peut être ajouté à l’équipe de l’échelle de l’organisation. 

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Y a-t-il un moyen pour créer une équipe à l’échelle de l’organisation autre que l’aide du client équipes ? 

Les administrateurs globaux peuvent uniquement créer une équipe à l’échelle de l’organisation à l’aide du client équipes. Si votre organisation limite la création d’équipes à l’aide de PowerShell, la solution recommandée consiste à ajouter votre Administrateurs global au groupe de sécurité d’utilisateurs qui peut créer une équipe. Pour plus d'informations, reportez-vous à l’article [Gérer qui peut créer des groupes Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups). 

Si ce n’est pas une option, vous pouvez créer une équipe public à l’aide de PowerShell et ajouter un administrateur global en tant que propriétaire de l’équipe. Ensuite, ont l’administrateur global cliquez sur **˙˙˙ options plus** en regard du nom de l’équipe et cliquez sur **Modifier l’équipe**, puis modifier la confidentialité pour **toute l’organisation - tout le monde dans votre organisation sera automatiquement ajoutée**. Notez que seuls les propriétaires de l’équipe peuvent accéder à l’option **Modifier l’équipe** et les administrateurs globaux uniquement peuvent voir l’option **d’échelle de l’organisation** .
