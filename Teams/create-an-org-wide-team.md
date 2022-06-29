---
title: Créer une équipe à l’échelle de l’organisation dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et gérer une équipe à l’échelle de l’organisation dans Teams pour permettre automatiquement à tous les membres d’une petite ou moyenne organisation de collaborer.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cfb9cf174488cfc8043cf04ab08f7eadba920bc3
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66240753"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>Créer une équipe à l’échelle de l’organisation dans Microsoft Teams

Les équipes à l’échelle de l’organisation permettent automatiquement à tous les membres d’une petite ou moyenne organisation de faire partie d’une équipe unique et collaborative.

Avec les équipes à l’échelle de l’organisation, les administrateurs généraux peuvent facilement créer une équipe publique qui présente les caractéristiques suivantes :
- Extrait tous les utilisateurs de l’organisation
- Maintient l’appartenance à jour avec Active Directory à mesure que les utilisateurs rejoignent et quittent l’organisation.

Seuls les administrateurs généraux peuvent créer des équipes à l’échelle de l’organisation. Actuellement, une équipe à l’échelle de l’organisation est limitée aux organisations ne comptant pas plus de 10 000 utilisateurs. Il existe également une limite de cinq équipes à l’échelle de l’organisation par locataire. Lors de la création d’une équipe, si ces exigences sont remplies, les administrateurs généraux voient **l’organisation à l’échelle de l’organisation** comme une option lorsqu’ils sélectionnent **Créer une équipe à partir de zéro**.

![Capture d’écran de l’option à l’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation.](media/create-org-wide-team.png "Capture d’écran de l’option à l’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation")

Lorsqu’une équipe à l’échelle de l’organisation est créée, tous les administrateurs généraux et les administrateurs de service Teams sont ajoutés en tant que propriétaires d’équipe et tous les utilisateurs actifs sont ajoutés en tant que membres de l’équipe. Les utilisateurs sans licence sont également ajoutés à l’équipe. La première fois qu’un utilisateur sans licence se connecte à Teams, une licence exploratoire Microsoft Teams lui est attribuée. Pour en savoir plus sur la licence exploratoire, consultez [Gérer la licence exploratoire Microsoft Teams](teams-exploratory.md).

Les types de comptes suivants ne seront pas ajoutés à votre équipe à l’échelle de l’organisation :

- Comptes bloqués de la connexion
- Utilisateurs invités
- Comptes de ressource ou de service (par exemple, comptes associés aux standards automatiques et aux files d’attente d’appels)
- Comptes de salle ou de matériel
- Comptes reposant sur une boîte aux lettres partagée

À mesure que le répertoire de votre organisation est mis à jour pour inclure de nouveaux utilisateurs actifs ou pour désactiver les comptes d’utilisateurs qui ne travaillent plus dans votre entreprise, les modifications sont automatiquement synchronisées et les utilisateurs sont ajoutés ou supprimés de l’équipe. Les membres de l’équipe ne peuvent pas quitter une équipe à l’échelle de l’organisation. En tant que propriétaire d’équipe, vous pouvez manuellement ajouter ou supprimer des utilisateurs, si besoin.

> [!NOTE]
>
> - Si vous ne voyez pas l’option **à l’échelle de l’organisation** lors de la création d’une équipe et que vous êtes administrateur général, vous avez peut-être atteint la limite de cinq équipes à l’échelle de l’organisation, ou votre organisation peut avoir plus de 10 000 membres. Nous cherchons à augmenter cette limite à l’avenir. Les équipes à l’échelle de l’organisation sont actuellement indisponibles pour Teams pour l’éducation.
> - Les salles qui ne font pas partie d’une liste de salles, d’équipements et de comptes de ressources peuvent être ajoutées ou synchronisées avec l’équipe à l’échelle de l’organisation. Les propriétaires d’équipe peuvent facilement supprimer ces comptes de l’équipe.
> - Toutes les actions effectuées par le système pour ajouter ou supprimer des membres sont publiées dans le canal général. Le canal est également marqué comme présentant une nouvelle activité dans le client Teams.
> - Nous allons créer automatiquement une équipe à l’échelle de l’organisation pour votre organisation si votre organisation n’a pas plus de 5 000 utilisateurs. Le nom de l’équipe correspondra au nom du client et aura un canal général. Les administrateurs généraux peuvent modifier cette équipe de la même façon que n’importe quelle autre équipe.

## <a name="best-practices"></a>Meilleures pratiques

Pour tirer le meilleur parti de votre équipe à l’échelle de l’organisation, nous recommandons aux propriétaires d’équipe d’effectuer les tâches suivantes :

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Autoriser uniquement les propriétaires d’équipe à publier sur le canal général

Réduisez les bruits de canal en faisant en sorte que seuls les propriétaires d’équipe publient sur le canal général.

1. Accédez à l’équipe, recherchez le canal Général, puis sélectionnez **... Autres options** > **Gérer le canal**.
2. Sous l’onglet **Paramètres du canal** , cliquez sur **Autorisations**, puis sélectionnez **Seuls les propriétaires peuvent publier des messages**.

### <a name="turn-off-team-and-team-name-mentions"></a>Désactiver les mentions @team et @ [nom de l’équipe]

Réduisez @mentions pour empêcher la surcharge de l’ensemble de l’organisation.

1. Accédez à l’équipe et cliquez sur **... Autres options** \> **Gérer l’équipe**.
2. Sous l’onglet **Paramètres** , cliquez sur **@mentions** \> désactiver **l’option Afficher les membres pour @team ou @[nom de l’équipe]**.

### <a name="automatically-show-important-channels"></a>Afficher automatiquement les canaux importants

Afficher les canaux importants pour veiller à ce que tous les membres de votre organisation engagent des conversations spécifiques. Pour plus d’information, consultez [Ajouter automatiquement les canaux aux favoris pour toute l’équipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).

### <a name="set-up-channel-moderation"></a>Configurer la modération des canaux

Envisagez de configurer la modération des canaux et d’octroyer des fonctionnalités de modérateur à certains membres de l’équipe. (Lorsque la modération est configurée, les propriétaires d’équipe reçoivent automatiquement des fonctionnalités de modérateur.) Les modérateurs peuvent :

- Contrôler qui peut démarrer un nouveau billet dans un canal
- Ajouter et supprimer des modérateurs
- Contrôler si les membres de l’équipe peuvent répondre aux messages de canal existants
- Contrôlez si les bots et les connecteurs peuvent envoyer des messages de canal.

Si vous souhaitez en savoir plus, consultez l’article [Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Supprimez les comptes sans propriétaire

Même si les membres ne peuvent pas quitter une équipe à l’échelle de l’organisation, en tant que propriétaire d’équipe, vous pouvez gérer la liste d’équipe en supprimant les comptes qui n’appartiennent pas. **Veillez à utiliser Teams pour supprimer des utilisateurs de votre équipe à l’échelle de l’organisation**. Si vous utilisez une autre façon de supprimer un utilisateur, tel que le Centre d'administration Microsoft 365 ou d’un groupe dans Outlook, l’utilisateur peut être ajouté à l’équipe à l’échelle de l’organisation.

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>Existe-t-il un moyen de créer une équipe à l’échelle de l’organisation autre que l’utilisation du client Teams ?

Seuls les administrateurs généraux peuvent créer une équipe à l’échelle de l’organisation à l’aide du client Teams. Si votre organisation limite la création d’équipes à l’aide de PowerShell, la solution de contournement recommandée consiste à ajouter vos administrateurs généraux au groupe de sécurité des utilisateurs qui peuvent créer une équipe.

Pour plus d’informations, consultez [Gérer qui peut créer des groupes](/microsoft-365/admin/create-groups/manage-creation-of-groups).

Si cette solution de contournement n’est pas une option, vous pouvez utiliser PowerShell pour créer une équipe publique et ajouter un administrateur général en tant que propriétaire de l’équipe. Ensuite, demandez à l’administrateur général de cliquer sur **Autres options** en regard du nom de l’équipe, de cliquer sur **Modifier l’équipe**, puis de modifier la confidentialité en **à l’échelle de l’organisation : tous les membres de votre organisation seront ajoutés automatiquement**.

> [!NOTE]
> Seuls les propriétaires d’équipe peuvent accéder à l’option **Modifier l’équipe** et seuls les administrateurs généraux peuvent voir l’option **à l’échelle de l’organisation** .

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>Existe-t-il un moyen de convertir une équipe existante en équipe à l’échelle de l’organisation ?

Les administrateurs généraux peuvent convertir une équipe existante en équipe à l’échelle de l’organisation en la modifiant dans le client Teams. Accédez au nom de l’équipe, cliquez sur **Autres options** > **Modifier l’équipe**.

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>Puis-je créer une équipe à l’échelle de l’organisation à l’aide d’un modèle d’équipe ?

Les modèles d’équipe ne peuvent pas être utilisés pour créer une équipe à l’échelle de l’organisation. Le travail de cette fonctionnalité est en cours.

## <a name="see-also"></a>Voir aussi

Regardez une vidéo sur [la création d’une équipe à l’échelle de l’organisation dans Microsoft Teams](https://www.youtube.com/watch?v=x3qGlwwCz_w).
