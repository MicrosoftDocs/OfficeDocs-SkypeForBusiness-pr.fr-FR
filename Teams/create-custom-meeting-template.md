---
title: Créer un modèle de réunion personnalisé dans Microsoft Teams
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
- highpri
appliesto:
- Microsoft Teams
description: Découvrez comment les administrateurs Microsoft Teams peuvent créer un modèle de réunion personnalisé pour définir ou appliquer les paramètres de l’organisateur de réunion pour améliorer la sécurité et la conformité des réunions.
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800274"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>Créer un modèle de réunion personnalisé dans Microsoft Teams

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Les modèles de réunion personnalisés Microsoft Teams (fonctionnalité Teams Premium) vous permettent de spécifier des valeurs pour la plupart des paramètres de réunion disponibles pour les organisateurs de réunion. Les modèles peuvent configurer des paramètres que les organisateurs de réunion peuvent modifier ou verrouiller les paramètres afin que les organisateurs de la réunion ne puissent pas les modifier. Pour plus d’informations sur les modèles de réunion personnalisés, consultez [Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md).

Vous pouvez créer jusqu’à 50 modèles personnalisés. Pour plus d’informations sur la gestion des modèles de réunion disponibles pour vos utilisateurs [, consultez Gérer les modèles de réunion dans Microsoft Teams](manage-meeting-templates.md) .

Pour chaque option du modèle, vous pouvez définir les éléments suivants :

- **Valeur par défaut** : il s’agit de la valeur qui est appliquée à une réunion lorsque le modèle est utilisé.
- **Visible** : détermine si l’organisateur de la réunion peut voir ce paramètre dans les options de réunion. 
- **État de verrouillage** : détermine si l’organisateur de la réunion peut modifier le paramètre défini par le modèle. Si le paramètre est verrouillé, l’organisateur de la réunion ne peut pas le modifier.

Pour créer un modèle de réunion personnalisé

1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Modèles de réunion**.
1. Sélectionnez **Ajouter.**
1. Tapez un nom et une description pour le modèle.
1. Choisissez les paramètres que vous souhaitez utiliser pour ce modèle. (Consultez les sections ci-dessous pour obtenir une description de chaque paramètre.)
1. Pour empêcher l’organisateur de la réunion de modifier un paramètre, sélectionnez-le, puis **sélectionnez Verrouiller**.
1. Pour empêcher l’organisateur de la réunion de voir un paramètre, sélectionnez-le, puis **sélectionnez Masquer**.
1. Sélectionnez **Enregistrer**.

Une fois le modèle créé, il peut prendre jusqu’à 24 heures pour être disponible pour vos utilisateurs.

#### <a name="security"></a>Sécurité

|Paramètres|Description|
|:------|:----------|
|Étiquette de confidentialité|Spécifie l’étiquette de confidentialité de la réunion à utiliser pour la réunion. Notez que l’étiquette de confidentialité peut remplacer certains paramètres du modèle.|
|Qui peut contourner la salle d’attente ?|Spécifie qui peut contourner la salle d’attente et rejoindre directement la réunion.|
|Personnes la numérotation peut contourner la salle d’attente|Spécifie si les personnes qui appellent par téléphone peuvent contourner la salle d’attente et rejoindre la réunion directement.|
|Avertir quand les appelants rejoignent et quittent|Spécifiez si vous souhaitez qu’un son soit émis lorsque des personnes appelant par téléphone rejoignent ou quittent la réunion.|
|Activer le chiffrement de bout en bout des réunions|Spécifiez si vous souhaitez que la réunion utilise le chiffrement de bout en bout. L’enregistrement et la transcription ne fonctionnent pas si cette opération est activée.|
|Appliquer un filigrane au contenu partagé|Spécifie si un filigrane est superposé au contenu partagé à l’écran dans la réunion.|
|Appliquer un filigrane au flux vidéo de tout le monde|Spécifie si un filigrane est superposé sur les flux vidéo des participants dans la réunion.|

#### <a name="audio-and-video"></a>Audio et vidéo

|Paramètres|Description|
|:------|:----------|
|Autoriser le micro pour les participants|Lorsque cette opération est **activée**, les participants peuvent réactiver le son.|
|Autoriser la caméra pour les participants|Lorsqu’il **est activé**, les participants peuvent activer leurs caméras.|

#### <a name="recording-and-transcription"></a>Enregistrement et transcription

|Paramètres|Description|
|:------|:----------|
|Enregistrer automatiquement les réunions|Lorsque **les réunions sont** enregistrées automatiquement.|
|Qui peut enregistrer des réunions ?|Spécifie si les réunions peuvent être enregistrées par les organisateurs uniquement ou par les organisateurs et les présentateurs.|

#### <a name="meeting-engagement"></a>Engagement de réunion

|Paramètres|Description|
|:------|:----------|
|Les participants peuvent discuter|Spécifie si la conversation de réunion est disponible. Peut également être utilisé pour empêcher la conversation avant et après la réunion.|
|Les participants peuvent utiliser des réactions|Spécifie si les participants peuvent utiliser des réactions dans la réunion. Cette valeur doit être **Activée** pour que la fonctionnalité lever la main fonctionne.|
|Activer Q&R|Spécifie si les participants peuvent utiliser la fonctionnalité Q&A pour poser des questions pendant la réunion.|
|Gérer ce que voient les participants|Lorsque cette option est **activée**, les organisateurs de la réunion peuvent afficher un aperçu et approuver le contenu partagé à l’écran avant que les autres participants à la réunion puissent le voir.|

## <a name="related-topics"></a>Rubriques connexes

[Vue d’ensemble des modèles de réunion personnalisés dans Microsoft Teams](custom-meeting-templates-overview.md)

[Utiliser des modèles de réunion Teams, des étiquettes de confidentialité et des stratégies d’administration ensemble](meeting-templates-sensitivity-labels-policies.md)

[Configurer des réunions Teams avec trois niveaux de protection](configure-meetings-three-tiers-protection.md)
