---
title: Créer une équipe à l’échelle de l’organisation dans Microsoft Teams
author: cichur
ms.author: v-mahoffman
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et gérer une équipe à l’échelle de l’organisation dans Teams afin de fournir une façon automatique à tous les membres d’une organisation de petite à moyenne taille de collaborer.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b266bf4cfef25761ce492cb93090ff3df380994d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60745610"
---
# <a name="create-an-organization-wide-team-in-microsoft-teams"></a>Créer une équipe à l’échelle de l’organisation dans Microsoft Teams

Les équipes à l’échelle de l’organisation permettent à tous les membres d’une organisation de petite à moyenne taille de faire partie d’une équipe unique et collaborative.

Avec les équipes à l’échelle de l’organisation, les administrateurs globaux peuvent facilement créer une équipe publique qui présente les caractéristiques suivantes :
- Permet de retirer tous les utilisateurs de l’organisation 
- Permet de maintenir l’appartenance à jour avec Active Directory, car les utilisateurs rejoignent et quittent l’organisation.

Seuls les administrateurs globaux peuvent créer des équipes à l’échelle de l’organisation. Actuellement, une équipe à l’échelle de l’organisation est limitée aux organisations qui ne comptent pas plus de 10 000 utilisateurs. Par ailleurs, cinq équipes à l’échelle de l’organisation par client sont limitées. Lors de la création d’une équipe, si  ces conditions sont remplies, les administrateurs globaux voient l’organisation comme option lorsqu’ils sélectionnent Créer une équipe de **toutes pièces.** 

![Capture d’écran de l’option à l’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation.](media/create-org-wide-team.png "Capture d’écran de l’option à l’échelle de l’organisation pour créer une équipe à l’échelle de l’organisation")

Lorsqu’une équipe est créée à l’échelle de l’organisation, tous les administrateurs globaux et administrateurs de services Teams sont ajoutés en tant que propriétaires d’équipe et tous les utilisateurs actifs sont ajoutés en tant que membres d’équipe. Les utilisateurs sans licence sont également ajoutés à l’équipe. La première fois qu’un utilisateur sans licence se Teams, une licence de licence Microsoft Teams’utilisateur s’affiche. Pour en savoir plus sur la licence Sous-licence, consultez Gérer la licence [Microsoft Teams de l’équipe.](teams-exploratory.md) 

Les types de comptes suivants ne sont pas ajoutés à l’équipe à l’échelle de votre organisation :

- Comptes bloqués à la connexion
- Utilisateurs invités
- Comptes de ressources ou de service (par exemple, les comptes associés aux files d’attente et aux files d’attente automatiques)
- Comptes de salle ou de matériel
- Comptes reposant sur une boîte aux lettres partagée

À mesure que l’annuaire de votre organisation est mis à jour pour inclure de nouveaux utilisateurs actifs ou pour désactiver les comptes des utilisateurs qui ne travaillent plus au sein de votre entreprise, les modifications sont automatiquement synchronisées et les utilisateurs sont ajoutés ou supprimés de l’équipe. Les membres d’une équipe ne peuvent pas quitter une équipe à l’échelle de l’organisation. En tant que propriétaire d’équipe, vous pouvez manuellement ajouter ou supprimer des utilisateurs, si besoin.

> [!NOTE]
> - Si vous ne voyez  pas l’option à l’échelle de l’organisation lors de la création d’une équipe et que vous êtes un administrateur général, vous pouvez avoir atteint la limite de cinq équipes à l’échelle de l’organisation, ou votre organisation peut avoir plus de 10 000 membres. Nous cherchons à augmenter cette limite à l’avenir. Les équipes à l’échelle de l’organisation sont actuellement indisponibles pour Teams pour l’éducation.
> - Les salles qui ne font pas partie d’une liste de salles, d’équipements et de comptes de ressources peuvent être ajoutées ou synchronisées avec l’équipe à l’échelle de l’organisation. Les propriétaires d’équipe peuvent facilement supprimer ces comptes de l’équipe.
> - Toutes les actions effectuées par le système pour ajouter ou supprimer des membres sont publiées dans le canal général. Le canal est également marqué comme présentant une nouvelle activité dans le client Teams.
> - Nous créerons automatiquement une équipe à l’échelle de l’organisation pour votre organisation si celle-ci ne possède pas l’expérience Teams et qu’elle ne compte pas plus de 5 000 utilisateurs. Le nom de l’équipe correspondra au nom du client et aura un canal général. Les administrateurs généraux peuvent modifier cette équipe de la même façon que n’importe quelle autre équipe.

## <a name="best-practices"></a>Meilleures pratiques

Pour 100%2010, nous recommandons aux propriétaires d’équipe d’effectuer les tâches suivantes :

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a>Autoriser uniquement les propriétaires d’équipe à publier sur le canal général

Réduisez les bruits de canal en faisant en sorte que seuls les propriétaires d’équipe publient sur le canal général. 

1. Allez dans l’équipe, recherchez le canal Général, puis sélectionnez « contrôle général » et « Canal de gestion » plus   >  **d’options.** 
2. Sous **l’onglet Paramètres du** canal, cliquez **sur Autorisations,** puis sélectionnez **Seuls les propriétaires peuvent publier des messages.**

### <a name="turn-off-team-and-team-name-mentions"></a>Désactiver les mentions @team et @ [nom de l’équipe]

Réduisez @mentions pour empêcher la surcharge de l’ensemble de l’organisation. 

1. Accédez à l’équipe, puis cliquez sur **˙˙˙Autres options** > **Gérer une équipe**. 
2. Sous l’onglet **Paramètres**, cliquez sur <strong>@mentions</strong> > désactivez l’option **Afficher les membres pour @team ou @[nom de l’équipe]**. 

### <a name="automatically-show-important-channels"></a>Afficher automatiquement les canaux importants

Afficher les canaux importants pour veiller à ce que tous les membres de votre organisation engagent des conversations spécifiques. Pour plus d’information, consultez [Ajouter automatiquement les canaux aux favoris pour toute l’équipe](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6). 

### <a name="set-up-channel-moderation"></a>Configurer la modération des canaux

Envisagez de configurer la modération des canaux et d’octroyer des fonctionnalités de modérateur à certains membres de l’équipe. (Lorsque la modération est définie, les propriétaires d’équipe ont automatiquement des capacités de modérateur.) Les modérateurs peuvent :

- Contrôler qui peut commencer une nouvelle publication dans un canal
- Ajouter et supprimer des modérateurs
- Contrôler si les membres de l’équipe peuvent répondre aux messages de canal existants
- Contrôler si les robots et connecteurs peuvent envoyer des messages de canal.

Pour plus d’informations, consultez [Configurer et gérer la modération des canaux dans Microsoft Teams](manage-channel-moderation-in-teams.md).

### <a name="remove-accounts-that-might-not-belong"></a>Supprimez les comptes sans propriétaire

Même si les membres ne peuvent pas quitter une équipe à l’échelle de l’organisation, en tant que propriétaire de l’équipe, vous pouvez gérer la liste de l’équipe en supprimant les comptes qui n’appartiennent pas. **Veillez à utiliser Teams pour supprimer des utilisateurs de votre équipe à l’échelle de l’organisation**. Si vous utilisez une autre manière de supprimer un utilisateur, tel que le Centre d'administration Microsoft 365 ou d’un groupe dans Outlook, l’utilisateur peut être rajouté à l’équipe à l’échelle de l’organisation.

## <a name="faq"></a>FAQ

### <a name="is-there-a-way-to-create-an-organization-wide-team-other-than-using-the-teams-client"></a>Existe-t-il un moyen de créer une équipe à l’échelle de l’organisation autre que l’Teams client ?

Seuls les administrateurs globaux peuvent créer une équipe à l’échelle de l’organisation à l’aide Teams client. Si votre organisation limite la création d’équipes à l’aide de PowerShell, la solution de contournement recommandée consiste à ajouter vos administrateurs généraux au groupe de sécurité des utilisateurs qui peuvent créer une équipe.

Pour plus d’informations, [voir Gérer les personnes qui peuvent créer des groupes.](/microsoft-365/admin/create-groups/manage-creation-of-groups)

Si cette solution de contournement n’est pas une option, vous pouvez utiliser PowerShell pour créer une équipe publique et ajouter un administrateur général en tant que propriétaire de l’équipe. Ensuite, demandez à l’administrateur général de cliquer sur **Autres options** en regard du nom de l’équipe, de cliquer sur **Modifier l’équipe**, puis de modifier la confidentialité en **à l’échelle de l’organisation : tous les membres de votre organisation seront ajoutés automatiquement**. 

> [!NOTE]
> Seuls les propriétaires d’équipe peuvent **accéder** à l’option Modifier l’équipe et seuls les administrateurs globaux peuvent voir l’option à **l’échelle de l’organisation.**

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-organization-wide-team"></a>Existe-t-il un moyen de convertir une équipe existante en équipe à l’échelle de l’organisation ?

Les administrateurs globaux peuvent convertir une équipe existante en équipe à l’échelle de l’organisation en la Teams client. Accédez au nom de l’équipe, cliquez sur **Autres options** > **Modifier l’équipe**.

### <a name="can-i-create-an-organization-wide-team-using-a-team-template"></a>Puis-je créer une équipe à l’échelle de l’organisation à l’aide d’un modèle d’équipe ?

Les modèles d’équipe ne peuvent pas être utilisés pour créer une équipe à l’échelle de l’organisation. Les travaux pour cette fonctionnalité sont actuellement en cours. 

## <a name="see-also"></a>Voir aussi

Regardez une vidéo sur [la création d’une équipe à l’échelle de l’Microsoft Teams.](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)
