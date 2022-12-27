---
title: Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
appliesto:
- Microsoft Teams
description: Découvrez les modèles de réunion personnalisés dans Microsoft Teams Premium.
ms.openlocfilehash: 0ed766141e09b9c26d8e8c6f5e8fdd12195ddb78
ms.sourcegitcommit: 4fdbd93aacb52a4fca68e31eb04d0495d4e27a10
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/27/2022
ms.locfileid: "69672914"
---
# <a name="overview-of-custom-meeting-templates-in-microsoft-teams"></a>Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

Microsoft Teams Premium offre la possibilité de créer des modèles de réunion personnalisés. Les modèles de réunion peuvent être utilisés pour contrôler les paramètres de réunion que l’organisateur de la réunion contrôle normalement. Avec les modèles, vous pouvez créer des expériences de réunion cohérentes dans votre organisation et vous aider à appliquer les exigences de conformité et les règles métier.

Les modèles de réunion peuvent être utilisés pour appliquer des paramètres ou pour définir des valeurs par défaut. Chaque paramètre de modèle peut être verrouillé afin que l’organisateur de la réunion ne puisse pas le modifier, ou peut être laissé déverrouillé pour que l’organisateur de la réunion change si nécessaire.

Les paramètres de réunion suivants peuvent être contrôlés à l’aide d’un modèle de réunion :

|Paramètres|Description|
|:------|:----------|
|Conversation|Spécifie si la conversation de réunion est disponible. Peut également être utilisé pour empêcher la conversation avant et après la réunion.|
|Chiffrement de bout en bout|Spécifie si la réunion est chiffrée.|
|Hall|Spécifie qui peut contourner la salle d’attente et rejoindre directement la réunion.|
|Gérer ce que voient les participants|Spécifie si les organisateurs de la réunion peuvent afficher un aperçu et approuver le contenu partagé à l’écran avant que les autres participants à la réunion puissent le voir.|
|Micro et caméra pour les participants|Spécifie si les participants peuvent activer et utiliser leur caméra.|
|Avertir quand les appelants rejoignent et quittent|Spécifie si un son est émis lorsque des personnes qui appellent par téléphone rejoignent ou quittent la réunion.|
|Q&R|Spécifie si les participants peuvent utiliser la fonctionnalité Q&A pour poser des questions pendant la réunion.|
|Réactions|Spécifie si les participants peuvent utiliser des réactions ou lever la main dans la réunion.|
|Enregistrement|Spécifie qui peut enregistrer et si la réunion est enregistrée automatiquement.|
|Étiquette de confidentialité|Spécifie l’étiquette de confidentialité à utiliser pour la réunion.|
|Filigranes|Spécifie si des filigranes sont utilisés pour les flux de caméra et le contenu partagé à l’écran dans la réunion.|

Voici quelques exemples de cas où un modèle peut être utile :

- Application de l’enregistrement automatique des réunions pour certains types de réunions.
- Restriction de la caméra et de l’audio de conversation et des participants, et utilisation de la fonctionnalité Q&A pour les réunions de style présentation.
- Utilisation d’une valeur par défaut plus stricte pour les personnes autorisées à contourner la salle d’attente, mais permettant à l’organisateur de la réunion de modifier le paramètre si nécessaire.

Pour savoir comment créer des modèles de réunion, consultez [Créer un modèle de réunion personnalisé dans Microsoft Teams](create-custom-meeting-template.md).

## <a name="templates-with-sensitivity-labels"></a>Modèles avec étiquettes de confidentialité

Les modèles ont la possibilité de spécifier une étiquette de confidentialité. Les étiquettes peuvent également être appliquées directement aux réunions, indépendamment des modèles. Les étiquettes de confidentialité peuvent contrôler certains des mêmes paramètres que les modèles :

- Chiffrement de bout en bout
- Conversation de réunion
- Enregistrer automatiquement
- Qui peut contourner la salle d’attente
- Qui peut présenter
- Qui peut enregistrer
- Filigranes

Si l’un de ces paramètres est configuré dans l’étiquette, ils remplacent ces paramètres dans le modèle.

## <a name="templates-included-with-teams"></a>Modèles inclus avec Teams

Teams Premium inclut plusieurs modèles de réunion par défaut que vous pouvez mettre à la disposition de vos utilisateurs :

- Grande réunion
- Réunion protégée
- Mairie
- [Rendez-vous virtuel](virtual-appointment-meeting-template.md)
- Webinaire

En outre, ces modèles sont disponibles dans Teams pour l'éducation :

- Classe
- Groupe de discussion
- Conférence
- Conférence des parents d’enseignants

Vous pouvez mettre à jour les paramètres de ces modèles si nécessaire.

## <a name="related-topics"></a>Rubriques connexes

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)

[Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble](meeting-templates-sensitivity-labels-policies.md)
