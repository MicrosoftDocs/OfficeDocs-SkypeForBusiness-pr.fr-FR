---
title: Gérer les balises dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: acolonna, salu
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
description: Découvrez comment les balises sont utilisées dans votre organisation dans Microsoft Teams.
ms.openlocfilehash: bdb4fcbdd4c4d197dcdc778b9c15130071ad37fc
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267949"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gérer les balises dans Microsoft Teams

## <a name="overview"></a>Vue d’ensemble

Les balises dans Microsoft Teams permettent aux utilisateurs de se connecter rapidement et facilement à un sous-ensemble de personnes d’une équipe. Vous pouvez créer et affecter des balises personnalisées pour catégoriser des personnes en fonction d’attributs, tels que le rôle, le projet, la compétence ou l’emplacement. Vous pouvez également attribuer automatiquement des balises aux personnes en fonction de leur planification et de leurs informations de décalage dans [l’application Shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Shifts). Une fois qu’une balise a été ajoutée à un ou plusieurs membres de l’équipe, elle peut être utilisée dans @mentions par toute personne de l’équipe dans un billet de canal ou pour notifier uniquement les personnes qui se voient attribuer cette balise d’une conversation

Comme mentionné précédemment, il existe deux types de balises dans Teams.

- **Balises personnalisées** : les propriétaires d’équipe et les membres de l’équipe (si la fonctionnalité est activée pour eux) peuvent créer et attribuer manuellement des balises à des personnes. Par exemple, une balise « Concepteur » ou « Radiologiste » atteindra ces ensembles de personnes d’une équipe sans avoir à taper leur nom.
- **Balisage par équipe** : avec cette fonctionnalité, les utilisateurs reçoivent automatiquement des balises qui correspondent à leur planification et à leur nom de groupe de shifts dans [l’application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_openshiftsappdesktop) dans Teams. Par exemple, la balise « EngineerOnCall » atteint tous les ingénieurs qui sont planifiés dans Shifts pour travailler au moment où la balise est utilisée dans une conversation ou un billet de canal. Avec le balisage par équipe, Teams ne connaît pas le nom du personnel en équipe lorsque les utilisateurs ont besoin de relayer rapidement des informations.

> [!NOTE]
> Les balises ne sont pas prises en charge dans les canaux privés ou partagés.

## <a name="how-tags-work"></a>Fonctionnement des balises

Une balise peut être ajoutée manuellement ou automatiquement affectée à une personne d’une équipe spécifique. Il peut ensuite être utilisé dans @mentions sur la ligne **À** dans une conversation ou dans un billet sur n’importe quel canal standard de l’équipe. Voici quelques exemples de la façon dont les balises peuvent être utilisées dans Teams :

- Un responsable de magasin publie une annonce sur un canal pour informer tous les caissier.
- Un administrateur d’hôpital envoie un message à tous les radiologues dans un canal.
- Un responsable marketing démarre une conversation de groupe avec tous les concepteurs.

Lorsqu’une balise est @mentioned dans une conversation de canal, les membres de l’équipe associés à la balise sont avertis, comme n’importe quel autre @mention.

## <a name="manage-custom-tags-for-your-organization"></a>Gérer les balises personnalisées pour votre organisation

En tant qu’administrateur, vous pouvez contrôler la façon dont les balises sont utilisées au sein de votre organisation dans le Centre d’administration Microsoft Teams. Notez que vous ne pouvez pas utiliser PowerShell pour gérer les balises.

:::image type="content" source="media/manage-tags-admin-settings.png" alt-text="Capture d’écran des paramètres d’étiquetage dans le Centre d’administration Microsoft Teams.":::

Une équipe peut avoir jusqu’à 100 balises, jusqu’à 100 membres d’équipe peuvent être affectés à une balise et jusqu’à 25 balises peuvent être attribuées à un seul utilisateur.

### <a name="set-who-can-add-custom-tags"></a>Définir qui peut ajouter des balises personnalisées

Par défaut, les propriétaires d’équipe peuvent ajouter des balises personnalisées. Vous pouvez modifier ce paramètre pour autoriser les propriétaires d’équipe et les membres de l’équipe à créer, modifier, supprimer et gérer des balises, ou vous pouvez désactiver les balises pour votre organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Paramètres** **Teams**\>.

2. Sous **Balisage**, en regard des **balises,** sélectionnez l’une des options suivantes :

    - **Propriétaires et membres** de l’équipe : autorisez les propriétaires d’équipe et les membres à gérer les balises.
    - **Propriétaires d’équipe** : autorisez les propriétaires d’équipe à gérer les balises.
    - **Désactivé** : désactivez les balises.

### <a name="configure-custom-tags-settings"></a>Configurer les paramètres des balises personnalisées

Vous pouvez configurer les paramètres de balises suivants pour contrôler la façon dont les balises personnalisées sont utilisées au sein de votre organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Paramètres** **Teams**\>.

2. Sous **Balisage**, définissez ce qui suit, en fonction des besoins de votre organisation.

    - **Laissez les propriétaires d’équipe remplacer ceux qui peuvent gérer les balises** : lorsque vous activez ce paramètre, les propriétaires d’équipe peuvent définir si les membres de l’équipe peuvent créer et gérer des balises au sein d’une équipe et la valeur des **balises est gérée par** paramètre comme valeur par défaut pour chaque équipe. Si vous désactivez ce paramètre, les **balises sont gérées par** le paramètre ne peuvent pas être modifiées par équipe.
    - **Balises par défaut suggérées** : utilisez-la pour ajouter un ensemble de balises par défaut. Vous pouvez ajouter jusqu’à 25 balises, et chaque balise peut contenir un maximum de 25 caractères. Les propriétaires et les membres de l’équipe (si la fonctionnalité est activée pour eux) peuvent utiliser ces suggestions, les ajouter ou créer un ensemble de balises.
    - **Laissez des balises personnalisées être créées** : activez ce paramètre pour permettre aux utilisateurs d’ajouter des balises autres que les balises par défaut suggérées que vous avez définies. Si cette option est désactivée, les utilisateurs peuvent uniquement utiliser les balises par défaut suggérées. Si vous désactivez cette option, veillez à ajouter une ou plusieurs balises par défaut.

## <a name="related-topics"></a>Voir aussi

[Utilisation de balises dans Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gérer l’application Shifts pour votre organisation dans Teams](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentation de l’aide shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
