---
title: Gérer les paramètres de réunion
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez comment gérer les paramètres des réunions d’équipes planifiées par les utilisateurs au sein de votre organisation.
ms.openlocfilehash: 1e5b3fd1c76f4ff925b23b838e2719ec93077f14
ms.sourcegitcommit: 332817f49ec1e6767334fdd4c2ec3f791020a26c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/05/2019
ms.locfileid: "36767193"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>Gérer les paramètres de réunion dans Microsoft Teams

En tant qu’administrateur, vous pouvez utiliser les paramètres de réunion d’équipes pour contrôler si les utilisateurs anonymes peuvent participer à des réunions d’équipes, personnaliser les invitations aux réunions et, si vous souhaitez activer la qualité de service (QoS), définir des plages de ports pour le trafic en temps réel. Ces paramètres s’appliquent à toutes les réunions d’équipes planifiées par les utilisateurs dans votre organisation. Vous gérez ces paramètres à partir des**paramètres de réunion** **réunions** > dans le centre d’administration Microsoft Teams.

## <a name="allow-anonymous-users-to-join-meetings"></a>Autoriser les utilisateurs anonymes à participer à des réunions

Avec Join anonyme, n’importe qui peut rejoindre la réunion en tant qu’utilisateur anonyme en cliquant sur le lien dans l’invitation à la réunion.

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation gauche, accédez à paramètres de la**réunion** **réunions** > .
2. Sous **participants**, activez **les utilisateurs anonymes peuvent participer à une réunion**.

    ![Capture d’écran des paramètres des participants pour les réunions dans le centre d’administration] (media/meeting-settings-participants.png "Capture d’écran des paramètres des participants pour les réunions teams dans le centre d’administration Microsoft teams")

Si vous ne souhaitez pas que les utilisateurs anonymes puissent participer aux réunions planifiées par les utilisateurs de votre organisation, désactivez ce paramètre.

## <a name="customize-meeting-invitations"></a>Personnaliser les invitations aux réunions

Vous pouvez personnaliser les invitations aux réunions teams selon les besoins de votre organisation. Vous pouvez ajouter le logo de votre organisation et inclure des informations utiles, telles que des liens vers le site Web de l’assistance et l’exclusion de responsabilité, et un pied de page uniquement.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>Conseils pour la création d’un logo pour les invitations aux réunions  

1. Créez une image de plus de 188 pixels de large par 30 pixels de hauteur (c’est assez petit).
2. Enregistrez l’image au format JPG ou PNG.
3. Stockez l’image dans un emplacement central accessible par tous les membres de votre organisation, par exemple un partage réseau.

    Vous pouvez désormais l’ajouter aux invitations aux réunions. Voir les étapes suivantes.

### <a name="customize-your-meeting-invitations"></a>Personnaliser les invitations aux réunions

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation gauche, accédez à paramètres de la**réunion** **réunions** > .
2. Sous **invitation électronique**, procédez comme suit :

    ![Capture d’écran des paramètres d’invitation à une réunion que vous pouvez personnaliser] (media/meeting-settings-invitation.png "Capture d’écran des paramètres d’invitation à une réunion que vous pouvez personnaliser pour les réunions teams")

    - **URL du logo** Entrez l’URL de stockage de votre logo.
    - **URL légale** Si votre organisation dispose d’un site Web légal auquel vous souhaitez que les personnes accèdent en cas de problèmes légaux, entrez l’URL ici.
    - **URL de l’aide** Si votre organisation dispose d’un site Web de support auquel vous souhaitez que les personnes accèdent en cas de problème, entrez l’URL ici.
    - **Pied de page** Entrez le texte que vous souhaitez inclure comme pied de page.
3. Attendez une heure pour que les modifications soient propagées. Planifiez une réunion teams pour voir à quoi ressemble l’invitation à la réunion.  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>Définir la manière dont vous souhaitez gérer le trafic multimédia en temps réel pour les réunions teams

<a name="bknetwork"> </a>

Si vous utilisez la qualité de service [(QoS)](qos-in-teams.md) pour définir la priorité du trafic réseau, vous pouvez activer les marqueurs de QoS et vous pouvez définir des plages de ports pour chaque type de trafic multimédia. La définition de plages de ports pour différents types de trafic est une étape de la gestion du contenu multimédia en temps réel ; Pour plus de détails, voir [qualité de service (QoS) dans teams](qos-in-teams.md) .

> [!IMPORTANT]
> Si vous activez la fonction QoS ou modifiez les paramètres dans le centre d’administration Microsoft teams pour le service Microsoft Teams, vous devrez également [appliquer des paramètres de correspondance à tous les appareils utilisateur](QoS-in-Teams-clients.md) et à tous les périphériques réseau internes pour appliquer les modifications à QoS dans Teams.

 ![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation gauche, accédez à paramètres de la**réunion** **réunions** > .
2. Sous **réseau**, procédez comme suit :

    ![Capture d’écran des paramètres réseau pour les réunions dans le centre d’administration] (media/meeting-settings-network.png "Capture d’écran de la page Paramètres du réseau pour les réunions teams dans le centre d’administration Microsoft teams")

    - Pour autoriser l’utilisation de la marque DSCP pour la qualité de **service (QoS), activez insérer des marqueurs de qualité de service (QoS) pour le trafic multimédia en temps réel**. Vous avez la possibilité d’utiliser des marqueurs uniquement. vous ne pouvez pas définir de marqueurs personnalisés pour chaque type de trafic. Pour plus d’informations sur les marqueurs DSCP, voir [Sélectionner une méthode d’implémentation QoS](QoS-in-Teams.md#select-a-qos-implementation-method) .
    > [!NOTE] 
    > L’activation de **marqueurs de qualité de service (QoS) pour le trafic multimédia en temps réel** permet également de communiquer avec le relais de transport avec les ports UDP 3479 (audio), 3480 (vidéo) et 3481 (partage).
    - Pour spécifier des plages de ports, en regard de l' **option Sélectionner une plage de ports pour chaque type de trafic multimédia en temps réel**, sélectionnez **spécifier les plages de ports**, puis entrez les ports de début et de fin pour le partage d’écran, audio et vidéo. Sélectionner cette option est requis pour implémenter QoS.
    > [!IMPORTANT]
    > Si vous sélectionnez **utiliser automatiquement tout port disponible, les**ports disponibles entre 1024 et 65535 sont utilisés. Utilisez cette option uniquement en cas de non-application de QoS.
    >
    > Le fait de sélectionner une plage de port trop étroite entraînera des appels interrompus et une mauvaise qualité d’appel. Les recommandations ci-dessous doivent être minimales.

Si vous ne savez pas quelles plages de ports utiliser dans votre environnement, les paramètres suivants constituent un bon point de départ. Pour en savoir plus, voir [implémenter la qualité de service (QoS) dans Microsoft teams](QoS-in-Teams.md). Il s’agit des marques DSCP requises et des plages de ports multimédias correspondant aux suggestions utilisées par teams et ExpressRoute.

_Plages de port et marques DSCP_

Type de trafic multimédia| Plage de ports sources du client\* |Protocole|Valeur DSCP|Classe DSCP|
|:---             |:---                         |:---    |:---      |:---      |
|Audio            | 50000 – 50019               |TCP/UDP |46        |Acheminement accéléré (EF)|
|Vidéo            | 50,020 – 50039               |TCP/UDP |34        |Acheminement assuré (AF41)|
|Partage d’écran ou d’application| 50,040 – 50059      |TCP/UDP |19        |Transfert assuré (AF21)|
| | | | |

\*Les plages de port que vous attribuez ne peuvent pas se chevaucher et doivent être adjacentes.

Lorsque la qualité de service (QoS) est utilisée depuis un certain temps, vous disposez des informations d’utilisation à la demande de chacune de ces trois charges de travail, vous pouvez choisir les modifications à apporter en fonction de vos besoins spécifiques. Le [tableau de bord de qualité des appels](turning-on-and-using-call-quality-dashboard.md) sera utile.
