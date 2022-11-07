---
title: Gérer les étiquettes dans Microsoft Teams
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
description: Découvrez comment les étiquettes sont utilisées dans votre organisation dans Microsoft Teams.
ms.openlocfilehash: 56a2daf53c362accec8059b11fba400547a7b6ff
ms.sourcegitcommit: b535a70df5bc842f597889582df3eb86371f8139
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/07/2022
ms.locfileid: "68869559"
---
# <a name="manage-tags-in-microsoft-teams"></a>Gérer les étiquettes dans Microsoft Teams

Les balises dans Microsoft Teams permettent aux utilisateurs de se connecter rapidement et facilement à un sous-ensemble de personnes d’une équipe. Vous pouvez créer et attribuer des étiquettes personnalisées pour catégoriser les personnes en fonction d’attributs, tels que le rôle, le projet, la compétence ou l’emplacement. Vous pouvez également attribuer automatiquement des étiquettes à des personnes en fonction de leur planning et de leurs informations de décalage dans [l’application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6). Une fois qu’une balise est ajoutée à un ou plusieurs membres de l’équipe, elle peut être utilisée dans @mentions par toute personne de l’équipe dans un billet de canal pour informer uniquement les personnes auxquelles cette balise est affectée d’une conversation.

Si vous êtes propriétaire d’une équipe et que vous souhaitez gérer des balises dans votre équipe, consultez [Utilisation de balises dans Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).

Comme mentionné précédemment, il existe deux types d’étiquettes dans Teams.

- **Étiquettes personnalisées** : les propriétaires d’équipe et les membres de l’équipe (s’ils disposent des autorisations nécessaires) peuvent créer et attribuer manuellement des étiquettes à des personnes. Par exemple, une balise « Concepteur » ou « Radiologiste » atteint ces groupes de personnes d’une équipe sans avoir à taper leur nom.
- **Étiquetage par shift** : avec cette fonctionnalité, les personnes se voient attribuer automatiquement des étiquettes qui correspondent à leur planning et à leur nom de groupe de décalage dans [l’application Shifts](https://support.microsoft.com/office/get-started-in-shifts-5f3e30d8-1821-4904-be26-c3cd25a497d6#bkmk_usetags) dans Teams. Par exemple, la balise « EngineerOnCall » atteint tous les ingénieurs qui sont planifiés dans Shifts pour travailler au moment où la balise est utilisée dans une publication de conversation ou de canal. Avec l’étiquetage par équipe, Teams prend l’hypothèse de connaître le nom du personnel en équipe lorsque les utilisateurs doivent rapidement relayer des informations.

> [!NOTE]
> Les balises ne sont pas prises en charge dans les canaux privés ou partagés.

## <a name="how-tags-work"></a>Fonctionnement des balises

Une balise peut être ajoutée manuellement (balise personnalisée) ou automatiquement attribuée à une personne d’une équipe spécifique (en configurant Shifts dans l’application Shifts). La balise peut ensuite être utilisée dans @mentions sur la ligne **À** dans une conversation ou dans une publication sur n’importe quel canal standard de l’équipe. Voici quelques exemples d’utilisation des balises dans Teams :

- Un responsable de magasin publie une annonce sur un canal pour avertir tous les caissiers.
- Un administrateur d’hôpital envoie un message à tous les radiologistes d’un canal.
- Un responsable marketing démarre une conversation de groupe avec tous les concepteurs.
- Une infirmière envoie un message à tous les cardiologues de garde.
- Un ingénieur système publie une annonce dans un canal pour avertir tous les ingénieurs de terrain en équipe.

Lorsqu’une balise est @mentioned dans une conversation de canal, les membres de l’équipe associés à la balise sont avertis, comme n’importe quel autre @mention.

## <a name="manage-tags-for-your-organization"></a>Gérer les étiquettes pour votre organisation

En tant qu’administrateur, vous pouvez contrôler la façon dont les étiquettes sont utilisées au sein de votre organisation dans le Centre d’administration Microsoft Teams. Notez que vous ne pouvez pas utiliser PowerShell pour gérer les étiquettes.

:::image type="content" source="media/manage-tags-admin-settings-shifts.png" alt-text="Capture d’écran des paramètres d’étiquetage dans le Centre d’administration Microsoft Teams.":::

Une équipe peut avoir jusqu’à 100 balises, jusqu’à 200 membres de l’équipe peuvent être affectés à une balise et jusqu’à 25 balises dans la même équipe sont affectées à un seul utilisateur.

### <a name="set-who-can-manage-tags"></a>Définir qui peut gérer les étiquettes

Par défaut, les propriétaires d’équipe peuvent créer, modifier et supprimer des balises. Vous pouvez modifier le paramètre **Qui peut gérer les étiquettes** pour autoriser les propriétaires d’équipe et les membres de l’équipe à gérer les étiquettes, ou vous pouvez désactiver les étiquettes pour votre organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Paramètres** **Teams**\>.

2. Sous **Étiquetage**, en regard de **Qui peut gérer les étiquettes**, sélectionnez l’une des options suivantes :

    - **Propriétaires et membres** d’équipe : autorisez les propriétaires et les membres de l’équipe à gérer les étiquettes.
    - **Propriétaires d’équipe** : autorisez les propriétaires d’équipe à gérer les étiquettes.
    - **Non activé** : désactivez les balises.

### <a name="configure-tagging-settings"></a>Configurer les paramètres d’étiquetage

Vous pouvez configurer les paramètres d’étiquettes suivants pour contrôler la façon dont les étiquettes sont utilisées au sein de votre organisation.

1. Dans le volet de navigation gauche du Centre d’administration Microsoft Teams, cliquez sur **Paramètres** **Teams**\>.

2. Sous **Étiquetage**, définissez les éléments suivants, en fonction des besoins de votre organisation.

    - Les propriétaires d’équipe **peuvent modifier les personnes autorisées à gérer les étiquettes** : lorsque vous activez ce paramètre, les propriétaires d’équipe peuvent définir si les membres de l’équipe peuvent créer et gérer des étiquettes au sein d’une équipe et la valeur du paramètre **Qui peut gérer les balises** est la valeur par défaut pour chaque équipe. Si vous désactivez ce paramètre, le paramètre **Qui peut gérer les étiquettes** ne peut pas être modifié par équipe.
    - **Balises suggérées** : utilisez cette option pour ajouter un ensemble d’étiquettes par défaut. Vous pouvez ajouter jusqu’à 25 balises et chaque balise peut contenir un maximum de 25 caractères. Les propriétaires d’équipe et les membres (si la fonctionnalité est activée pour eux) peuvent utiliser ces suggestions, y ajouter ou créer un nouvel ensemble d’étiquettes.
    - **Balises personnalisées** : activez ce paramètre pour permettre aux utilisateurs d’ajouter des balises autres que les balises par défaut suggérées que vous définissez. Si cette option est désactivée, les utilisateurs peuvent uniquement utiliser les balises par défaut suggérées. Si vous désactivez cette option, veillez à ajouter une ou plusieurs balises par défaut.
    - **L’application Shifts peut appliquer des étiquettes** : activez ce paramètre pour permettre à l’application Shifts d’affecter automatiquement des étiquettes aux personnes qui sont en équipe en temps réel. Ces balises correspondent à la planification et au nom du groupe d’un utilisateur dans Shifts. Les notifications sont envoyées uniquement aux personnes qui sont en déplacement au moment où l’étiquette est utilisée dans une publication de conversation ou de canal.

## <a name="related-topics"></a>Rubriques connexes

[Gérer l’application Shifts](expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

[Documentation d’aide sur les shifts](https://support.microsoft.com/office/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
