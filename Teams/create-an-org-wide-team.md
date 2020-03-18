---
title: Créer une équipe à l’échelle de l’organisation dans Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et gérer une équipe à l’échelle de l’organisation dans Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99acc2e1756c0915f404f6bf6b1bfab1e30fcaf6
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288732"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a>Créer une équipe à l’échelle de l’organisation dans Microsoft Teams

Les équipes à l’échelle de l’organisation fournissent un moyen automatique pour tous les membres d’une organisation, petite ou moyenne, de faire partie d’une équipe unique pour la collaboration.

Les équipes à l’échelle de l’organisation permettent aux administrateurs généraux de facilement créer une équipe publique qui incorpore chaque utilisateur dans votre organisation et actualise l’appartenance avec Active Directory lorsque les utilisateurs rejoignent et quittent l’organisation. Seuls les administrateurs généraux peuvent créer des équipes à l’échelle de l’organisation. Actuellement, une équipe à l’échelle de l’organisation est limitée aux organisations ne dépassant pas 5 000 utilisateurs. Il existe également une limite de cinq équipes à l’échelle de l’organisation par client. Si ces conditions sont remplies, les administrateurs généraux verront ** à l’échelle de l’organisation** en tant qu’une option lorsqu’ils sélectionnent **Créer une équipe à partir de zéro** lors de la création d’une équipe. 

![Capture d’écran de l’option à l’échelle de l’Organisation pour créer une équipe à l’échelle de l’Organisation](media/create-org-wide-team.png "Capture d’écran de l’option à l’échelle de l’Organisation pour créer une équipe à l’échelle de l’Organisation")

Lors de la création d’une équipe à l’échelle de l’organisation, tous les administrateurs généraux sont ajoutés en tant que propriétaires d’équipe et tous les utilisateurs actifs en tant que membres de l’équipe. Les utilisateurs sans licence sont également ajoutés à l’équipe. La première fois qu’un utilisateur sans licence se connecte à Teams, une licence d’essai du cloud commercial Microsoft Teams lui est attribuée. Pour en savoir plus sur la licence d’évaluation, consultez [Gérer l’offre d’évaluation cloud commercial Teams](iw-trial-teams.md). 

Ces types de comptes ne sont pas ajoutés à votre équipe à l’échelle de l’organisation :

- Comptes bloqués à la connexion
- Utilisateurs invités
- Comptes de service
- Comptes de salle ou de matériel
- Comptes reposant sur une boîte aux lettres partagée

Au fur et à mesure que le répertoire de votre organisation est mis à jour de manière à inclure les nouveaux utilisateurs actifs, ou si des utilisateurs ne travaillent plus au sein de votre entreprise et que leur compte est désactivée, les modifications sont automatiquement synchronisées et les utilisateurs ajoutés ou supprimés de l’équipe. Les membres d’équipe ne peuvent pas quitter une équipe à l’échelle de l’organisation. En tant que propriétaire d’équipe, vous pouvez manuellement ajouter ou supprimer des utilisateurs, si besoin.

> [!NOTE]
> - Si vous ne voyez pas l’option **à l’échelle de l’organisation** lors de la création d’une équipe et si vous êtes un administrateur général, il est possible que la fonctionnalité soit déployée, que vous ayez atteint la limite de cinq équipes à l’échelle de l’organisation ou que votre organisation ait atteint la limite de taille actuelle de 5 000 membres. Nous cherchons à augmenter cette limite à l’avenir. Les équipes à l’échelle de l’organisation sont actuellement indisponibles pour Teams pour l’éducation.
> - Les salles qui ne font pas partie d’une liste de salle, de ressources matérielles et de comptes de ressources peuvent être ajoutées ou synchronisées avec l’équipe à l’échelle de l’organisation. Les propriétaires d’équipe peuvent facilement supprimer ces comptes de l’équipe.
> - Toutes les actions effectuées par le système pour ajouter ou supprimer des membres sont publiées dans le canal général. Le canal est également marqué comme présentant une nouvelle activité dans le client Teams.
> - Nous créerons automatiquement une équipe à l'échelle de l'organisation pour votre organisation si celle-ci est nouvelle dans les équipes et ne compte pas plus de 5 000 utilisateurs. Le nom de l’équipe correspondra au nom du client et aura un canal général. Les administrateurs généraux peuvent modifier cette équipe de la même façon que n’importe quelle autre équipe. 

## <a name="best-practices"></a>Meilleures pratiques

Pour tirer le meilleur parti de votre équipe à l’échelle de l’organisation, nous recommandons aux propriétaires d’équipes d’effectuer les opérations suivantes.

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Autoriser uniquement les propriétaires d’équipe à publier sur le canal général

Réduisez les bruits de canal en faisant en sorte que seuls les propriétaires d’équipe publient sur le canal général. Accédez à l’équipe, puis cliquez sur **˙˙˙Autres options** > **Gérer une équipe**. Sous l’onglet **Paramètres**, cliquez sur **Autorisations de membre** > sélectionnez **Seuls les propriétaires peuvent publier des messages**.

### <a name="turn-off-team-and-team-name-mentions"></a>Désactiver les mentions @team et @ [nom de l’équipe]

 Réduisez @mentions pour empêcher la surcharge de l’ensemble de l’organisation. Accédez à l’équipe, puis cliquez sur **˙˙˙Autres options** > **Gérer une équipe**. Sous l’onglet **Paramètres**, cliquez sur <strong>@mentions</strong> > désactivez l’option **Afficher les membres pour @team ou @[nom de l’équipe]**. 

### <a name="automatically-show-important-channels"></a>Afficher automatiquement les canaux importants

Afficher les canaux importants pour veiller à ce que tous les membres de votre organisation engagent des conversations spécifiques. Pour plus d’information, consultez [Ajouter automatiquement les canaux aux favoris pour toute l’équipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Configurer la modération des canaux

Envisagez de configurer la modération des canaux et d’octroyer des fonctionnalités de modérateur à certains membres de l’équipe. (Lorsque la modération est configurée, les propriétaires d’équipe reçoivent des fonctionnalités de modérateur automatiquement). Les modérateurs peuvent qui peut commencer un nouveau billet dans un canal, ajouter et supprimer des modérateurs, contrôler la possibilité pour les membres d’équipe de répondre aux messages du canal et contrôler si les bots et les connecteurs peuvent envoyer des messages. Pour plus d’informations, consultez [Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Supprimez les comptes sans propriétaire

Même si les membres ne peuvent pas quitter une équipe à l'échelle de l'organisation, en tant que propriétaire de l'équipe, vous pouvez gérer la liste de l'équipe en supprimant les comptes qui n'en font pas partie. **Veillez à utiliser Teams pour supprimer des utilisateurs de votre équipe à l’échelle de l’organisation**. Si vous utilisez une méthode différemment pour supprimer un utilisateur (Centre d’administration Microsoft 365 ou groupe dans Outlook, par exemple), l’utilisateur peut être à l’équipe à l’échelle de l’organisation.

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a>Y a-t-il un moyen de créer une équipe à l’échelle de l’organisation plutôt que d’utiliser le client Teams ?

Les administrateurs généraux peuvent uniquement créer une équipe à l’échelle de l’organisation à l’aide du client Teams. Si votre organisation limite la création d’équipes à l’aide de PowerShell, la solution de contournement recommandée consiste à ajouter vos administrateurs généraux au groupe de sécurité des utilisateurs qui peuvent créer une équipe. Pour plus d'informations, reportez-vous à l’article [Gérer qui peut créer des groupes Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).

Si ce n’est pas le cas, vous pouvez utiliser PowerShell pour créer une équipe publique et ajouter un administrateur général en tant que propriétaire de l’équipe. Ensuite, demandez à l’administrateur général de cliquer sur **Autres options** en regard du nom de l’équipe, de cliquer sur **Modifier l’équipe**, puis de modifier la confidentialité en **à l’échelle de l’organisation : tous les membres de votre organisation seront ajoutés automatiquement**. Notez que seuls les propriétaires d’équipe peuvent accéder à l’option **Modifier l’équipé**. Seuls les administrateurs généraux peuvent voir l’option ** à l’échelle de l’organisation**.

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a>Y a-t-il un moyen de convertir une équipe existante en une équipe à l’échelle de l’Organisation ?

Les administrateurs généraux peuvent convertir une équipe existante en une équipe à l’échelle de l’organisation en la modifiant dans le client Teams. Accédez au nom de l’équipe, cliquez sur **Autres options** > **Modifier l’équipe**.

## <a name="see-also"></a>Voir aussi

Visionnez une vidéo sur la[Création d’une équipe à l’échelle de l’entreprise dans Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).
