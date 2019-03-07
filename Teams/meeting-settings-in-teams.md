---
title: Gérer les paramètres de réunion
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment gérer les paramètres pour les réunions d’équipes qui planifient des utilisateurs dans votre organisation.
ms.openlocfilehash: ad48e44ef475d3643444cfb570e81d8224117133
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462643"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gérer les paramètres de réunion dans Microsoft Teams

En tant qu’administrateur, vous utilisez les paramètres de réunion équipes pour contrôler si les utilisateurs anonymes peuvent participer à des réunions d’équipes, personnaliser les invitations aux réunions et si vous souhaitez activer la qualité de Service (QoS), définissez des plages de ports pour le trafic en temps réel. Ces paramètres s’appliquent à toutes les réunions d’équipes cette planification, les utilisateurs de votre organisation. Vous gérer ces paramètres à partir de **réunions** > **paramètres de réunion** dans le centre d’administration Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Autoriser les utilisateurs anonymes à participer à des réunions

Avec la participation anonyme, tout le monde peut joindre la réunion en tant qu’utilisateur anonyme en cliquant sur le lien dans l’invitation à la réunion.

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la navigation de gauche, accédez à des **réunions** > **paramètres de réunion**.
2. Sous **Participants**, activez **les utilisateurs anonymes peuvent participer à une réunion**.

    ![réunion-paramètres-participants.png] (media/meeting-settings-participants.png "Capture d’écran des paramètres des participants pour les réunions d’équipes dans le centre d’administration Microsoft équipes")

Si vous ne voulez pas que les utilisateurs anonymes à participer à des réunions planifiées par les utilisateurs de votre organisation, désactivez ce paramètre.

## <a name="customize-meeting-invitations"></a>Personnaliser les invitations aux réunions

Vous pouvez personnaliser les invitations à des équipes pour répondre aux besoins de votre organisation. Vous pouvez ajouter le logo de votre organisation et inclure des informations utiles, telles que des liens vers votre site Web de support et exclusion de responsabilité et un pied de page en lecture seule.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Conseils pour la création d’un logo pour les invitations aux réunions  

1. Créer une image qui n’est pas plus de 188 pixels de large par 30 pixels de haut (il s’agit très petite).
2. Enregistrez l’image au format JPG.
3. Stocker l’image dans un emplacement central tout le monde dans votre organisation permettre accéder, par exemple un partage réseau.

### <a name="customize-your-meeting-invitations"></a>Personnaliser vos invitations aux réunions

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la navigation de gauche, accédez à des **réunions** > **paramètres de réunion**.
2. Sous **invitation par courrier électronique**, procédez comme suit :

    ![réunion-paramètres-invitation.png] (media/meeting-settings-invitation.png "Capture d’écran de la réunion paramètres de l’invitation que vous pouvez personnaliser pour les réunions des équipes")

    - **URL du logo** Entrez l’URL où est stockée votre logo.
    - **URL juridique** Si votre organisation dispose d’un site Web juridique que vous souhaitez communiquer à atteindre pour n’importe quel des implications juridiques, entrez l’URL ici.
    - **URL de l’aide** Si votre organisation dispose d’un site Web que vous souhaitez atteindre en cas de problèmes de personnes, entrez l’URL ici.
    - **Pied de page** Entrez le texte que vous souhaitez inclure dans le pied de page.
3. Attendez une heure pour propager les modifications. Planifier une réunion équipes pour afficher un aperçu de l’invitation à la réunion.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Définir la manière dont vous souhaitez gérer le trafic multimédia en temps réel pour les réunions d’équipes

<a name="bknetwork"> </a>

Si vous utilisez la qualité de Service [(QoS)](qos-in-teams.md) pour définir la priorité du trafic réseau, vous pouvez activer les indicateurs de qualité de service et vous pouvez définir des plages de ports pour chaque type de trafic multimédia.

 ![les équipes-logo-30x30.png](media/teams-logo-30x30.png) **à l’aide du centre d’administration Microsoft équipes**

1. Dans la navigation de gauche, accédez à des **réunions** > **paramètres de réunion**.
2. Sous **réseau**, procédez comme suit :

    ![réunion-paramètres-network.png] (media/meeting-settings-network.png "Capture d’écran des paramètres du réseau pour les réunions d’équipes dans le centre d’administration Microsoft équipes")

    - Pour autoriser le marquage DSCP à utiliser pour QoS, activer **marqueurs insérer qualité de Service (QoS) pour le trafic multimédia en temps réel**. Vous pouvez uniquement l’utilisation des marques ou pas, vous ne pouvez pas définir des marques personnalisées pour chaque type de trafic. Pour plus de marqueurs DSCP sur, voir [Sélectionnez une méthode de mise en œuvre QoS](QoS-in-Teams.md#select-a-qos-implementation-method) .
    - Pour spécifier les plages de ports, en regard de **Sélectionner une plage de ports pour chaque type de trafic multimédia en temps réel**, sélectionnez **spécifier les plages de ports**, puis entrez les ports de départ et de fin pour l’audio, vidéo et partage d’écran. Cette option est requis pour implémenter QoS.
    > [!IMPORTANT]
    > Si vous choisissez **d’utiliser automatiquement les ports disponibles**, les ports disponibles entre 1024 et 65535 sont utilisés. Utilisez cette option uniquement lorsque ne pas l’implémentation de QoS.
    >
    > Sélection d’une plage de ports est trop étroite entraîne appels abandonnés et appel de mauvaise qualité. Les recommandations ci-dessous doivent être un minimum.

 Si vous ne savez pas quel port plages pour l’utiliser dans votre environnement, les paramètres suivants sont un bon point de départ. Pour en savoir plus, lisez [Implémenter la qualité de Service (QoS) dans les équipes Microsoft](QoS-in-Teams.md). Voici les marques DSCP requis et le média correspondant suggéré le port utilisés par les équipes et ExpressRoute des plages.

_Plages de ports et d’un marquage DSCP_

Type de trafic multimédia| Plage de ports client source\* |Protocole|Valeur DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50 000 – 50,019               |TCP/UDP |46        |Acheminement accéléré (EF)|
|Vidéo            | 50,020 – 50,039               |TCP/UDP |34        |Acheminement assuré (AF41)|
|Partage d’application/écran| 50,040 – 50,059      |TCP/UDP |18        |Assured Forwarding (AF21)|
| | | | |

\*Vous assignez les plages de ports ne peuvent pas se superposer et doivent être adjacentes.

La définition de plages de ports pour différents types de trafic n'est qu’une seule étape dans la gestion des médias en temps réel, consultez [Qualité de Service (QoS) dans les équipes](qos-in-teams.md) de manière plus détaillée. Si vous activez ou modifiez les paramètres dans le centre d’administration équipes, vous devrez [appliquer les paramètres correspondants pour tous les périphériques de l’utilisateur](QoS-in-Teams-clients.md) et les périphériques réseau interne pour implémenter intégralement les modifications apportées à la qualité de service dans les équipes.

Une fois que la qualité de service a été utilisé pendant un certain temps, vous devez obtenir des informations sur la demande de chacun de ces trois charges de travail et vous pouvez choisir les modifications à apporter en fonction de vos besoins spécifiques. [Tableau de bord qualité des appels](turning-on-and-using-call-quality-dashboard.md) seront utiles avec qui.