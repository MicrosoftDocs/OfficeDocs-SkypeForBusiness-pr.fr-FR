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
description: Découvrez comment créer et gérer une équipe à l’échelle de l’organisation dans Teams.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b999419f8fec9c205ec9713181596fba1fb38999
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494044"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Créer une équipe à l’échelle de l’organisation dans Microsoft Teams

Les équipes à l’échelle de l’organisation offrent une méthode automatique pour tous les utilisateurs d’une petite entreprise pour collaborer. 
 
Grâce aux équipes au sein de l’organisation, les administrateurs généraux peuvent facilement créer une équipe publique qui collecte chaque utilisateur au sein de l’organisation et reste l’appartenance à la mise à jour d’Active Directory à mesure que les utilisateurs rejoignent et quittent l’organisation. Seuls les administrateurs généraux peuvent créer des équipes à l’échelle de l’organisation et actuellement une équipe à l’échelle de l’organisation est limitée aux organisations ne disposant pas de plus de 5 000 utilisateurs. Si ces conditions sont remplies, les administrateurs généraux pourront voir l’échelle de l' **organisation** en tant qu’option lors de la création **d’une équipe à partir de zéro lors de** la création d’une équipe. 

![Capture d’écran de l’option de création d’une équipe à l’échelle de l’organisation] (media/create-org-wide-team.png "Capture d’écran de l’option de création d’une équipe à l’échelle de l’organisation")

Lorsque vous créez une équipe à l’échelle de l’organisation, tous les administrateurs globaux sont ajoutés en tant que propriétaires d’équipe, et tous les utilisateurs actifs sont ajoutés en tant que membres de l’équipe. Les utilisateurs désactivés pour les équipes, les utilisateurs invités et la plupart des salles ne sont pas ajoutés à l’équipe. Dans la mesure où l’annuaire de votre organisation est mis à jour de manière à inclure les nouveaux utilisateurs actifs ou que les utilisateurs ne travaillent plus dans votre société et qu’elle est désactivée, les modifications sont automatiquement synchronisées et les utilisateurs sont ajoutés ou supprimés de l’équipe. Les membres d’une équipe ne peuvent pas quitter une équipe à l’échelle de l’organisation. En tant que propriétaire de l’équipe, vous pouvez ajouter ou supprimer des utilisateurs manuellement, si nécessaire.

> [!NOTE]
> - Si vous ne voyez pas l’option **à l’échelle** de l’Organisation lors de la création d’une équipe et que vous êtes un administrateur global, il est possible que la fonctionnalité soit en cours de déploiement ou que votre organisation ait plus de la limite de taille actuelle des membres 5 000. Nous cherchons à augmenter cette limite à l’avenir.
> - Les salles qui ne font pas partie d’une liste de salles, de ressources de matériel et de ressources peuvent être ajoutées ou synchronisées à l’équipe au sein de l’organisation. Les propriétaires d’équipe peuvent facilement supprimer ces comptes de l’équipe.

## <a name="best-practices"></a>Meilleures pratiques
Pour tirer le meilleur parti de votre équipe au sein de l’organisation, nous recommandons aux propriétaires d’équipe de procéder comme suit.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Autoriser uniquement les propriétaires d’équipe à publier dans le canal général
Réduisez le bruit du canal en permettant uniquement aux propriétaires d’équipe de valider le canal général. Accédez à l’équipe et cliquez sur **plus d’options (...)**  >  **Gérer l’équipe**. Dans l’onglet **paramètres** , cliquez sur **autorisations des membres** > ne sélectionner que les **propriétaires peuvent publier des messages**.
### <a name="turn-off-team-and-team-name-mentions"></a>Désactiver les mentions @team et @ [nom de l’équipe]
 Réduisez les @mentions pour les empêcher de surcharger l’ensemble de l’organisation. Accédez à l’équipe et cliquez sur **plus d’options (...)**  >  **Gérer l’équipe**. Dans l’onglet **paramètres** , cliquez sur <strong>@mention</strong> _GT_ désactiver **l’option Afficher les membres sur @team ou @ [nom de l’équipe]**. 
### <a name="automatically-favorite-important-channels"></a>Ajouter automatiquement aux favoris les canaux importants
 Canaux importants importants pour garantir que tous les membres de votre organisation entreprennent des conversations spécifiques. Pour en savoir plus, reportez-vous à la section ajouter [des canaux aux favoris pour toute l’équipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="remove-accounts-that-might-not-belong"></a>Supprimer des comptes qui ne font pas partie
Même si les membres ne peuvent pas quitter une équipe à l’échelle de l’organisation, en tant que propriétaire d’une équipe, vous pouvez gérer la liste de l’équipe en supprimant les comptes qui ne font pas partie. Veillez à utiliser teams pour supprimer des utilisateurs de votre équipe au sein de l’organisation.  Si vous utilisez une autre méthode de suppression d’un utilisateur (par exemple, le centre d’administration Microsoft 365 ou un groupe dans Outlook), l’utilisateur peut être rajouté à l’équipe au sein de l’organisation. 

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Est-il possible de créer une équipe à l’échelle de l’organisation à l’aide du client teams? 

Les administrateurs généraux peuvent uniquement créer une équipe à l’échelle de l’organisation à l’aide du client Teams. Si votre organisation limite la création d’équipes à l’aide de PowerShell, vous pouvez utiliser la solution de contournement recommandée pour ajouter vos administrateurs globaux au groupe de sécurité des utilisateurs qui peuvent créer une équipe. Pour plus d'informations, reportez-vous à l’article [Gérer qui peut créer des groupes Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups). 

S’il ne s’agit pas d’une option, vous pouvez créer une équipe publique à l’aide de PowerShell et ajouter un administrateur global en tant que propriétaire de l’équipe. Ensuite, demandez à l’administrateur général de cliquer sur **̇ ̇ ̇ plus d’options** en regard du nom de l’équipe, de cliquer sur **modifier l’équipe**, puis de changer la confidentialité en niveau de l’organisation, tous les membres **de votre organisation seront automatiquement ajoutés**. Notez que seuls les propriétaires d’équipe peuvent accéder à l’option **modifier l’équipe** et seuls les administrateurs généraux peuvent voir l’option à l’échelle de l' **organisation** .

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Est-il possible de convertir une équipe existante en équipe au sein de l’Organisation?

Les administrateurs généraux peuvent convertir une équipe existante en équipe à l’échelle de l’organisation dans le client Teams.
Accédez au nom de l’équipe et cliquez sur autres options... (points de suspension) > modifier l’équipe.
