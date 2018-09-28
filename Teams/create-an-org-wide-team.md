---
title: Créer une équipe à l’échelle de l’organisation dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et gérer une équipe à l’échelle de l’organisation dans les équipes.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f86cf706d7bf507fb77fac7becf9bd48168eac6
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/28/2018
ms.locfileid: "25348207"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Créer une équipe à l’échelle de l’organisation dans Microsoft Teams

Les équipes à l’échelle de l’organisation offrent un moyen automatique pour tout le monde dans une petite ou moyenne organisation soit une partie d’une équipe unique pour la collaboration. 
 
Avec les équipes à l’échelle de l’organisation, les administrateurs globaux peuvent créer facilement une équipe publique qui extrait tous les utilisateurs de l’organisation et conserve l’appartenance à jour avec Active Directory en tant qu’utilisateurs join et laissez l’organisation. Seuls les administrateurs globaux peuvent créer des équipes à l’échelle de l’organisation et actuellement une équipe à l’échelle de l’organisation est limitée aux organisations comptant pas plus de 1 000 utilisateurs. Si ces conditions sont remplies, les administrateurs voir **à l’échelle de l’organisation** comme option de **confidentialité** lors de la création d’une équipe.

![Capture d’écran de l’option d’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation] (media/create-org-wide-team.png "Capture d’écran de l’option d’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation")

> [!NOTE]
> Si vous ne voyez pas l’option **d’échelle de l’organisation** lors de la création d’une équipe et que vous êtes un administrateur global, la fonctionnalité peut toujours être présentant ou votre organisation peut avoir plus de la limite de taille de 1000 membres. Nous recherchons pour augmenter cette limite à l’avenir.

Lors de la création d’une équipe à l’échelle de l’organisation, les administrateurs globaux sont ajoutés en tant que les propriétaires de l’équipe et tous les utilisateurs actifs sont ajoutés en tant que membres de l’équipe. Les utilisateurs qui sont désactivés pour les équipes, les utilisateurs invités et la plupart des salles ne sont pas ajoutés à l’équipe. Annuaire de votre organisation est mis à jour pour inclure les nouveaux utilisateurs actifs, ou si les utilisateurs ne fonctionnent plus dans votre société et sa licence équipes est désactivée, les modifications sont automatiquement synchronisés et les utilisateurs sont ajoutés ou supprimés de l’équipe. Membres de l’équipe ne peut pas quitter une équipe à l’échelle de l’organisation. En tant que propriétaire de l’équipe, vous pouvez manuellement ajouter ou supprimer des utilisateurs si nécessaire.

> [!NOTE]
> Salles qui ne sont pas d’une liste, d’équipement et de ressources les comptes salle peuvent être ajoutés ou synchronisés vers l’équipe à l’échelle de l’organisation. Les propriétaires de l’équipe peuvent facilement supprimer ces comptes de l’équipe.

## <a name="best-practices"></a>Meilleures pratiques
Pour obtenir le meilleur parti de votre équipe à l’échelle de l’organisation, nous vous recommandons de propriétaires d’équipe, procédez comme suit.
### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Autoriser uniquement les propriétaires de l’équipe à publier le canal général
Réduire le bruit de canal par l’équipe uniquement de publier des propriétaires pour le canal d’échange général. Accédez à l’équipe et cliquez sur **autres options (...)**  >  **Gérer l’équipe**. Dans l’onglet **paramètres** , cliquez sur **autorisations de membre** > sélectionnez **peuvent publier des propriétaires uniquement**.
### <a name="turn-off-team-and-team-name-mentions"></a>Désactiver @team et @ mentions de [nom de l’équipe]
 Réduire @mentions pour empêcher toute la surcharge de l’organisation toute entière. Accédez à l’équipe et cliquez sur **autres options (...)**  >  **Gérer l’équipe**. Dans l’onglet **paramètres** , cliquez sur **@mentions** > désactiver **Afficher les membres de l’option à @team ou @[nom de l’équipe]**. 
### <a name="automatically-favorite-important-channels"></a>Canaux importantes automatiquement favoris
 Conversations spécifiques engage favoris canaux importantes pour tout le monde dans votre organisation. Pour plus d’informations, voir [canaux Auto-favori pour l’ensemble de l’équipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).
