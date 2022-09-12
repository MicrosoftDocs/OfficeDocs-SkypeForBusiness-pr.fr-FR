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
ms.openlocfilehash: 9c2da438d3f88a172759ec13672aec663ae6add9
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647428"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gérer les balises dans Microsoft Teams

Les balises dans Microsoft Teams permettent aux utilisateurs de se connecter rapidement et facilement à un sous-ensemble de personnes d’une équipe. Vous pouvez créer et affecter des balises personnalisées pour catégoriser des personnes en fonction d’attributs, tels que le rôle, le projet, la compétence ou l’emplacement. Vous pouvez également attribuer automatiquement des balises aux personnes en fonction de leur planification et de leurs informations de décalage dans [l’application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6). Une fois qu’une balise est ajoutée à un ou plusieurs membres de l’équipe, elle peut être utilisée dans @mentions par toute personne de l’équipe dans un billet de canal pour notifier uniquement les personnes qui se voient attribuer cette balise d’une conversation.

Comme mentionné précédemment, il existe deux types de balises dans Teams.

- **Balises personnalisées** : les propriétaires d’équipe et les membres de l’équipe (s’ils disposent des autorisations) peuvent créer et affecter manuellement des balises à des personnes. Par exemple, une balise « Concepteur » ou « Radiologiste » atteindra ces ensembles de personnes d’une équipe sans avoir à taper leur nom.
- **Balisage par équipe** : avec cette fonctionnalité, les utilisateurs reçoivent automatiquement des balises qui correspondent à leur planification et à leur nom de groupe de shifts dans [l’application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) dans Teams. Par exemple, la balise « EngineerOnCall » atteint tous les ingénieurs qui sont planifiés dans Shifts pour travailler au moment où la balise est utilisée dans une conversation ou un billet de canal. Avec le balisage par équipe, Teams ne connaît pas le nom du personnel en équipe lorsque les utilisateurs ont besoin de relayer rapidement des informations.

> [!NOTE]
> Les balises ne sont pas prises en charge dans les canaux privés ou partagés.

## <a name="how-tags-work"></a>Fonctionnement des balises

Une balise peut être ajoutée manuellement (balise personnalisée) ou attribuée automatiquement à une personne d’une équipe spécifique (en configurant Shifts dans l’application Shifts). La balise peut ensuite être utilisée dans @mentions sur la ligne **À** dans une conversation ou dans un billet sur n’importe quel canal standard de l’équipe. Voici quelques exemples de la façon dont les balises peuvent être utilisées dans Teams :

- Un responsable de magasin publie une annonce sur un canal pour informer tous les caissier.
- Un administrateur d’hôpital envoie un message à tous les radiologues dans un canal.
- Un responsable marketing démarre une conversation de groupe avec tous les concepteurs.
- Une infirmière envoie un message à tous les cardiologues de garde.
- Un ingénieur système publie une annonce sur un canal pour informer tous les ingénieurs de terrain en équipe.

Lorsqu’une balise est @mentioned dans une conversation de canal, les membres de l’équipe associés à la balise sont avertis, comme n’importe quel autre @mention.

## <a name="manage-tags-for-your-organization"></a>Gérer les balises pour votre organisation

En tant qu’administrateur, vous pouvez contrôler la façon dont les balises sont utilisées au sein de votre organisation dans le Centre d’administration Microsoft Teams. Notez que vous ne pouvez pas utiliser PowerShell pour gérer les balises.

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Capture d’écran des paramètres d’étiquetage dans le Centre d’administration Microsoft Teams.":::

Une équipe peut avoir jusqu’à 100 balises, jusqu’à 200 membres d’équipe peuvent être affectés à une balise et jusqu’à 25 balises dans la même équipe sont affectées à un seul utilisateur.

### <a name="set-who-can-manage-tags"></a>Définir qui peut gérer les balises

Par défaut, les propriétaires d’équipe peuvent créer, modifier et supprimer des balises. Vous pouvez modifier le paramètre **Qui peut gérer les balises** pour permettre aux propriétaires d’équipe et aux membres de l’équipe de gérer les balises, ou vous pouvez désactiver les balises pour votre organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Paramètres** **Teams**\>.

2. Sous **Balisage**, en regard de **Qui peut gérer les balises**, sélectionnez l’une des options suivantes :

    - **Propriétaires et membres** de l’équipe : autorisez les propriétaires d’équipe et les membres à gérer les balises.
    - **Propriétaires d’équipe** : autorisez les propriétaires d’équipe à gérer les balises.
    - **Non activé** : désactivez les balises.

### <a name="configure-tagging-settings"></a>Configurer les paramètres d’étiquetage

Vous pouvez configurer les paramètres de balises suivants pour contrôler la façon dont les balises sont utilisées au sein de votre organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Paramètres** **Teams**\>.

2. Sous **Balisage**, définissez ce qui suit, en fonction des besoins de votre organisation.

    - **Les propriétaires d’équipe peuvent modifier qui peut gérer les balises** : lorsque vous activez ce paramètre, les propriétaires d’équipe peuvent définir si les membres de l’équipe peuvent créer et gérer des étiquettes au sein d’une équipe et la valeur du paramètre **Qui peut gérer les balises** est la valeur par défaut pour chaque équipe. Si vous désactivez ce paramètre, le paramètre **Qui peut gérer les balises** ne peut pas être modifié par équipe.
    - **Balises suggérées** : utilisez cette option pour ajouter un ensemble de balises par défaut. Vous pouvez ajouter jusqu’à 25 balises, et chaque balise peut contenir un maximum de 25 caractères. Les propriétaires et les membres de l’équipe (si la fonctionnalité est activée pour eux) peuvent utiliser ces suggestions, les ajouter ou créer un ensemble de balises.
    - **Balises personnalisées** : activez ce paramètre pour permettre aux utilisateurs d’ajouter des balises autres que les balises par défaut suggérées que vous avez définies. Si cette option est désactivée, les utilisateurs peuvent uniquement utiliser les balises par défaut suggérées. Si vous désactivez cette option, veillez à ajouter une ou plusieurs balises par défaut.
    - **L’application Shifts peut appliquer des balises** : activez ce paramètre pour permettre à l’application Shifts d’attribuer automatiquement des balises aux personnes en déplacement en temps réel. Ces balises correspondent à la planification et au nom de groupe d’un utilisateur dans Shifts. Les notifications sont envoyées uniquement aux personnes qui sont en équipe au moment où l’étiquette est utilisée dans une conversation ou un billet de canal.

## <a name="related-topics"></a>Rubriques connexes

[Utilisation de balises dans Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e)

[Gérer l’application Shifts](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentation de l’aide shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
