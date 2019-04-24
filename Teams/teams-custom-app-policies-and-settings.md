---
title: Gérer les stratégies d’application personnalisée et les paramètres dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment gérer les stratégies des applications personnalisées et les paramètres pour contrôler les personnes dans votre organisation peuvent télécharger des applications personnalisées dans Microsoft Teams.
ms.openlocfilehash: 3cbd517cdfe8066eebff0164457c8e2e3aa37a5d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224621"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Gérer les stratégies d’application personnalisée et les paramètres dans Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

En tant qu’administrateur, vous pouvez utiliser des stratégies d’application personnalisée et les paramètres pour contrôler les personnes dans votre organisation peuvent télécharger des applications personnalisées à Microsoft Teams. Administrateurs de décider quels utilisateurs peuvent télécharger des applications personnalisées et propriétaires d’équipe et les administrateurs peuvent déterminer si des équipes spécifiques dans votre organisation autorisent les applications personnalisées à ajouter à leur.  

## <a name="overview-of-custom-apps"></a>Vue d’ensemble des applications personnalisées

Les utilisateurs peuvent ajouter une application personnalisée aux équipes en les téléchargeant un package d’application (dans un fichier .zip) directement à une équipe ou dans le contexte de personnel. Cela diffère comment les applications sont ajoutées par le biais de l’app store équipes. Ajout d’une application personnalisée en téléchargeant un package d’application, également appelé chargement de version test, vous permet de tester une application tel qu’il est en cours de développement, avant d’être prêt à être répartie. Elle vous permet également de créer une application pour un usage interne et le partager avec votre équipe sans l’envoyer au catalogue d’applications dans l’app store équipes équipes.

![télécharger une application personnalisée](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Paramètres et stratégies d’application personnalisée

Trois composants déterminent si un utilisateur peut télécharger une application personnalisée à une équipe, ce qui vous donne un contrôle plus précis qui peut ajouter des applications personnalisées à une équipe et les applications personnalisées qui les équipes peuvent être ajoutés à :

- [Stratégie d’utilisateur application personnalisée](#user-custom-app-policy)
- [Paramètre d’application personnalisée de l’équipe](#team-custom-app-setting)
- [Paramètre d’application personnalisée à l’échelle de l’organisation](#org-wide-custom-app-setting)

Ces paramètres n’affectent pas la possibilité de bloquer les applications tierces.  

### <a name="user-custom-app-policy"></a>Stratégie d’utilisateur application personnalisée

Dans le cadre de [stratégies d’application du programme d’installation](teams-app-setup-policies.md), les administrateurs peuvent utiliser un paramètre de stratégie, **Autoriser téléchargement des applications personnalisées**, pour contrôler si un utilisateur peut télécharger des applications personnalisées à des équipes.
 
Si ce paramètre est désactivé :

- L’utilisateur ne peuvent pas télécharger une application personnalisée à une équipe dans votre organisation ou dans le contexte de personnel.
- L’utilisateur peut interagir avec des applications personnalisées, selon le paramètre d’application personnalisée à l’échelle de l’organisation.

Si ce paramètre est activé :

- L’utilisateur peut télécharger des applications personnalisées à des équipes qui l’autorisent en et aux équipes dont ils sont propriétaires, selon le paramètre d’application personnalisée à l’échelle de l’organisation.
- L’utilisateur peut télécharger des applications personnalisées pour le contexte de personnel. 
- L’utilisateur peut interagir avec des applications personnalisées, selon le paramètre d’application personnalisée à l’échelle de l’organisation.

Vous pouvez modifier les paramètres dans la stratégie du programme d’installation d’application globaux afin d’inclure les applications que vous souhaitez. Si vous souhaitez personnaliser les équipes pour différents groupes d’utilisateurs de votre organisation, créer et affecter une ou plusieurs stratégies du programme d’installation d’application personnalisée.

#### <a name="set-a-user-custom-app-policy"></a>Définir une stratégie d’application personnalisée utilisateur

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez aux **applications équipes** > **du programme d’installation de stratégies**.
2. Sélectionnez **nouvelle stratégie**.
3. Activer ou désactiver les **Autoriser à télécharger des applications personnalisées**.
4. Choisissez tous les autres paramètres que vous souhaitez pour la stratégie.
5. Cliquez sur **Enregistrer**.

### <a name="team-custom-app-setting"></a>Paramètre d’application personnalisée de l’équipe

Les propriétaires de l’équipe et les administrateurs peuvent contrôler si une équipe autorise pour les applications personnalisées afin de lui être ajouté. Ce paramètre **Autoriser les membres à télécharger des applications personnalisées**, ainsi que de la stratégie d’application personnalisée d’un utilisateur détermine qui peut ajouter des applications personnalisées à une équipe.
 
Si ce paramètre est désactivé :

- Les propriétaires de l’équipe peuvent ajouter des applications personnalisées, si sa stratégie d’application personnalisée permet.
- Membres de l’équipe qui ne sont pas des propriétaires de l’équipe ne peut pas ajouter des applications personnalisées à l’équipe.

Si ce paramètre est activé :

- Les propriétaires de l’équipe peuvent ajouter des applications personnalisées, si sa stratégie d’application personnalisée permet.
- Membres de l’équipe qui ne sont pas des propriétaires de l’équipe peuvent ajouter des applications personnalisées, si sa stratégie d’application personnalisée permet.

#### <a name="configure-the-team-custom-app-setting"></a>Configurer le paramètre d’application personnalisée d’équipe

1. Dans les équipes, accédez à l’équipe, cliquez sur **plus d’options ˙˙˙** > **l’équipe de gestion**.
2. Cliquez sur **paramètres**, puis développez les **autorisations de membre**.
3. Activez ou désactivez la case à cocher **Autoriser les membres à télécharger des applications personnalisées** .

    ![paramètre d’application personnalisée de l’équipe](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Paramètre d’application personnalisée à l’échelle de l’organisation

Le paramètre d’application personnalisée à l’échelle de l’organisation, **Autoriser l’interaction avec des applications personnalisées**, s’applique à tout le monde dans votre organisation et détermine si elles peuvent télécharger ou interagir avec les applications personnalisées. Ce paramètre remplace l’utilisateur et la stratégie d’application personnalisée d’équipe et le paramètre. Elle est destinée à servir d’une forme de base interrupteur pendant les événements de sécurité.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurer le paramètre d’application personnalisée à l’échelle de l’organisation

1. Dans la navigation de gauche du centre d’administration Microsoft Teams, accédez aux **applications équipes** > **stratégies d’autorisation**.
2. Cliquez sur **paramètres d’application à l’échelle de l’organisation**.
3. Sous **applications personnalisées**, activez ou désactivez **Autoriser l’interaction avec des applications personnalisées**.

    ![Paramètre d’application personnalisée à l’échelle de l’organisation](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Comment les stratégies d’application personnalisée et les paramètres fonctionnent ensemble

Ce tableau récapitule la stratégie d’application personnalisée et les paramètres, leur fonctionnement coopératif et leur effet sur le contrôle des personnes de votre organisation peuvent télécharger des applications personnalisées aux équipes combiné.

Par exemple, par exemple, que vous souhaitez autoriser uniquement les propriétaires de l’équipe à télécharger des applications personnalisées pour des équipes spécifiques. Vous devez définir les éléments suivants :
- Activer le paramètre **Autoriser l’interaction avec des applications personnalisées** dans le centre d’administration Microsoft Teams.
- Désactivez l’option **Autoriser les membres à télécharger des applications personnalisées** pour chaque équipe à laquelle vous souhaitez restreindre l’accès.
- Créer et affecter une stratégie du programme d’installation d’application personnalisée dans le centre d’administration Microsoft Teams avec le paramètre **utilisateur peut télécharger des applications personnalisées** est activé et attribuez-le aux propriétaires de l’équipe.

|Paramètre d’application personnalisée à l’échelle de l’organisation |Paramètre d’application personnalisée de l’équipe |Stratégie d’utilisateur application personnalisée |Effet  |
|---------|---------|---------|---------|
| Désactivé    | Désactivé    | Désactivé     |Interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Applications personnalisées ne peuvent pas être téléchargées par tout le monde. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.   |
| Désactivé     | Désactivé     | Activé        |Interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Applications personnalisées ne peuvent pas être téléchargées par tout le monde. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Désactivé    | Activé        | Désactivé        |Interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Applications personnalisées ne peuvent pas être téléchargées par tout le monde. Vous pouvez utiliser Windows PowerShell pour supprimer des applications personnalisées.         |
| Désactivé    | Activé      | Activé       |Interaction avec toutes les applications personnalisées est bloquée pour votre organisation. Applications personnalisées ne peuvent pas être téléchargées par tout le monde. Vous pouvez utiliser PowerShell pour supprimer l’application personnalisée.         |
| Activé    | Désactivé       | Désactivé         |  L’utilisateur ne peuvent pas télécharger des applications personnalisées.      |
| Activé     | Désactivé       | Activé         | Si l’utilisateur est un propriétaire de l’équipe, ils peuvent télécharger des applications personnalisées à l’équipe. Si l’utilisateur n’est pas un propriétaire de l’équipe, ils ne peuvent pas télécharger des applications personnalisées à l’équipe. L’utilisateur peut télécharger des applications personnalisées dans le contexte de personnel.     |
| Activé     | Activé     | Désactivé         | L’utilisateur ne peuvent pas télécharger des applications personnalisées.       |
| Activé    | Activé        | Activé        | L’utilisateur peut télécharger des applications personnalisées à l’équipe, même si l’utilisateur est un propriétaire de l’équipe. L’utilisateur peut télécharger des applications personnalisées dans le contexte de personnel.       |

 ## <a name="related-topics"></a>Voir aussi
- [Paramètres d'administration pour les applications dans Microsoft Teams](admin-settings.md)
- [Gérer les stratégies de mise en application dans Microsoft Teams](teams-app-setup-policies.md)
- [Gérer les stratégies d’autorisation d’application dans Microsoft Teams](teams-app-permission-policies.md)
