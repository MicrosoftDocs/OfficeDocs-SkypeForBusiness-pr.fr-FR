---
title: Gérer les stratégies de réunion pour l’enregistrement et la transcription
author: KarliStites
ms.author: kastites
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jastark
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.recordingandtranscription
description: Découvrez comment gérer les paramètres de stratégie de réunion dans Teams pour l’enregistrement et la transcription.
ms.openlocfilehash: c89fc88c46ae8b614021417ab2aa02832f64fce1
ms.sourcegitcommit: 69a5d4994ef75b9c16efa99554fb7f2ee1ccf52a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/10/2021
ms.locfileid: "58973191"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Paramètres de stratégie de réunion pour l’enregistrement & transcription

Cet article décrit les paramètres de stratégie de réunion spécifiques à l’enregistrement et la transcription, notamment les suivants :

- [Autoriser la transcription](#allow-transcription)
- [Autoriser l’enregistrement dans le cloud](#allow-cloud-recording)
- [Stocker des enregistrements en dehors de votre pays ou région](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Autoriser la transcription

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. Si vous la désactiverez, les options **Rechercher** et **Cc** ne seront pas disponibles pendant la lecture de l’enregistrement d’une réunion. La personne qui a démarré l’enregistrement a besoin de ce paramètre activé de sorte que l’enregistrement inclut également la transcription.

Pour l’instant, la transcription des réunions enregistrées n’est prise en charge que pour les utilisateurs qui définissent leur langue ou parlent anglais dans Teams réunions.

## <a name="allow-cloud-recording"></a>Autoriser l’enregistrement dans le cloud

Ce paramètre est une combinaison d’une stratégie par organisateur et par utilisateur, et contrôle si les réunions peuvent être enregistrées. L’enregistrement peut être démarré par l’organisateur de la réunion ou par un autre participant à la réunion si le paramètre de stratégie est activé pour le participant et s’il s’agit d’un utilisateur authentifié de la même organisation.

Les personnes extérieures à votre organisation, telles que les utilisateurs fédérés et anonymes, ne peuvent pas démarrer l’enregistrement. Les utilisateurs invités ne peuvent ni démarrer ni arrêter l’enregistrement.

![Capture d’écran montrant les options d’enregistrement](media/meeting-policies-recording.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser l’enregistrement dans le Cloud |
|---------|---------|---------|
|Daniela | Global   | Désactivé |
|Geneviève | Location1MeetingPolicy | Activé|
|John (utilisateur externe) | Non applicable | Non applicable|

- Les réunions organisées par Daniela ne peuvent pas être enregistrées.
- Il n’est pas possible d’enregistrer les réunions organisées par Daniela.
- Vous pouvez enregistrer les réunions organisées par Tous.
- Daniela ne peut pas enregistrer les réunions organisées par Tous.
- Jean ne peut pas enregistrer les réunions organisées par Tous.

Pour en savoir plus sur l’enregistrement de réunions cloud, consultez [Enregistrement de réunion cloud Teams](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Stocker des enregistrements en dehors de votre pays ou région

Cette stratégie contrôle si les enregistrements de réunion peuvent être stockés de manière permanente dans un autre pays ou une autre région. Si elle est activée, les enregistrements ne peuvent pas être migrés. Pour plus d’informations sur les réunions dans le cloud et l’endroit où sont stockés les enregistrements, voir [Teams’enregistrement de réunion cloud.](cloud-recording.md)

## <a name="related-topics"></a>Sujets associés

- [Attribuer des stratégies aux utilisateurs dans Teams](policy-assignment-overview.md)
- [Enregistrement de réunion dans le cloud](cloud-recording.md)