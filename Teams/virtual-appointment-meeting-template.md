---
title: Modèle de réunion de rendez-vous virtuel dans Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
audience: admin
description: Découvrez comment gérer le modèle de réunion de rendez-vous virtuel pour les utilisateurs Teams de votre organisation.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 459845115d8a705673f21b5e8a57dadac59841f6
ms.sourcegitcommit: f8da8f613fc3902d2607e322ad9dfbdeb8838c4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2022
ms.locfileid: "69624916"
---
# <a name="virtual-appointment-meeting-template-in-microsoft-teams"></a>Modèle de réunion de rendez-vous virtuel dans Microsoft Teams

## <a name="overview"></a>Vue d’ensemble

Le modèle de rendez-vous virtuel est un modèle de réunion par défaut dans Microsoft Teams que vos utilisateurs peuvent utiliser pour planifier des rendez-vous virtuels avec des clients, des clients et d’autres personnes extérieures à votre organisation. Par exemple, utilisez-le pour planifier et mener des entrevues, des séances de mentorat, des consultations financières, des expériences d’achat virtuelles, etc.

Le modèle vous permet de spécifier des valeurs pour les paramètres de réunion que les organisateurs de réunion contrôlent généralement. Cela vous donne la possibilité d’appliquer les paramètres par défaut et d’appliquer les paramètres. Vous pouvez choisir de verrouiller les paramètres afin que les organisateurs de réunion ne puissent pas les modifier lorsqu’ils utilisent le modèle.

Avec ce modèle, vous pouvez activer une expérience cohérente au sein de votre organisation pour les rendez-vous virtuels planifiés dans Teams et vous aider à appliquer les exigences de conformité.

Cet article vous donne une vue d’ensemble de l’affichage et de la gestion du modèle de réunion de rendez-vous virtuel dans le Centre d’administration Teams.

## <a name="view-or-change-virtual-appointment-meeting-template-settings"></a>Afficher ou modifier les paramètres du modèle de réunion de rendez-vous virtuel

1. Dans le volet de navigation gauche du Centre d’administration Teams, accédez à **Réunions** > **Modèles de réunion**.
1. Choisissez **Rendez-vous virtuel**, puis sélectionnez **Modifier**.
1. Pour apporter des modifications, sélectionnez une option, puis configurez les paramètres souhaités. Pour chaque option, vous pouvez définir les paramètres suivants :
    - **Valeur par défaut** : valeur appliquée au rendez-vous virtuel lorsque le modèle est utilisé.
    - **Visibilité** : choisissez **Masquer** ou **Afficher** pour spécifier si l’option est visible par les organisateurs de réunion dans les options de réunion Teams.
    - **État du verrouillage** : pour empêcher les organisateurs de la réunion de modifier la valeur que vous définissez, choisissez **Verrouiller**. Pour autoriser les organisateurs de la réunion à modifier la valeur que vous définissez, choisissez **Déverrouiller**.
1. Passez en revue vos modifications, puis choisissez **Enregistrer**.

## <a name="manage-the-virtual-appointment-meeting-template"></a>Gérer le modèle de réunion de rendez-vous virtuel

Vous utilisez des stratégies de modèle de réunion dans le Centre d’administration Teams pour contrôler les modèles de réunion disponibles pour les utilisateurs de votre organisation. Par défaut, la stratégie globale permet aux utilisateurs de voir et d’utiliser tous les modèles de réunion, y compris le modèle Rendez-vous virtuel et tous les modèles personnalisés que vous avez créés.

Si vous souhaitez rendre le modèle Rendez-vous virtuel disponible pour des utilisateurs ou des groupes d’utilisateurs spécifiques dans votre organisation, vous pouvez créer une stratégie de modèle de réunion personnalisée, puis l’affecter à ces utilisateurs ou groupes.

Pour plus d’informations, consultez [Gérer les modèles de réunion dans Teams](manage-meeting-templates.md).

## <a name="user-experience"></a>Expérience utilisateur

Lorsque les utilisateurs de votre organisation utilisent le modèle de réunion pour planifier un rendez-vous virtuel, les personnes extérieures à votre organisation (invités externes) obtiennent une invitation de réunion personnalisée qui inclut un **rendez-vous rejoindre en tant que bouton invité** et d’autres détails de rendez-vous. Ils peuvent utiliser ce bouton pour rejoindre facilement à partir de n’importe quel appareil sans avoir à télécharger et installer Teams.

Gardez à l’esprit que certaines options de réunion Teams peuvent ne pas s’appliquer aux invités externes ou aux personnes qui rejoignent à l’aide du **rendez-vous rejoindre en tant que bouton invité** . Les options de réunion suivantes sont prises en charge pour la participation d’invité :

- **Qui peut contourner la salle d’attente** : le paramètre **Tout le monde** permet aux invités externes de contourner la salle d’attente.
- **Choisir des co-organisateurs**
- **Enregistrer automatiquement**
- **Autoriser la conversation de réunion** : définissez sur **Désactivé** si vous souhaitez empêcher la conversation de réunion avant, pendant et après la réunion.

Personnes au sein de votre organisation reçoivent une invitation à une réunion et le rendez-vous s’affiche dans leur calendrier Teams et Outlook, où ils peuvent facilement participer comme à n’importe quelle autre réunion Teams. Toutes les options de réunion Teams s’appliquent aux participants qui rejoignent à l’aide du lien de réunion Teams dans l’invitation à la réunion ou à partir du calendrier Teams ou Outlook.

Pour en savoir plus sur l’utilisation du modèle de réunion de rendez-vous virtuel et l’expérience utilisateur, consultez [Utiliser un modèle de réunion Teams pour créer un rendez-vous virtuel](https://support.microsoft.com/office/6a9e8cbb-c0ed-4598-851e-3b1750a4a747).

## <a name="related-articles"></a>Articles connexes

- [Vue d’ensemble des modèles de réunion personnalisés dans Teams](custom-meeting-templates-overview.md)
