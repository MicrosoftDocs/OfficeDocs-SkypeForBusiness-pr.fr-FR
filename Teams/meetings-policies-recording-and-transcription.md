---
title: Gérer les stratégies de réunion pour l’enregistrement et la transcription
author: mkbond007
ms.author: mabond
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
ms.openlocfilehash: da7a5d43231abcb00339f2ffc2c57c7e90ff2d2e
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646363"
---
# <a name="meeting-policy-settings-for-recording--transcription"></a>Paramètres de stratégie de réunion pour l’enregistrement & transcription

Cet article décrit les paramètres de stratégie de réunion spécifiques à l’enregistrement et à la transcription, notamment les suivants :

- [Autoriser la transcription](#allow-transcription)
- [Autoriser l’enregistrement dans le cloud](#allow-cloud-recording)
- [Stocker des enregistrements en dehors de votre pays ou région](#store-recordings-outside-of-your-country-or-region)

## <a name="allow-transcription"></a>Autoriser la transcription

Il s’agit d’une combinaison d’une stratégie par organisateur et par utilisateur. Ce paramètre détermine si les fonctionnalités de légende et de transcription sont disponibles lors de la lecture des enregistrements de réunion. La personne qui a lancé l'enregistrement doit activer ce paramètre pour que ces fonctionnalités fonctionnent avec son enregistrement.

L’activation de ce paramètre crée une copie de la transcription stockée avec l’enregistrement de la réunion, ce qui active **Recherche**, **CC** et **Transcriptions** sur l’enregistrement de réunion.

La transcription des réunions enregistrées est actuellement prise en charge uniquement pour les utilisateurs qui définissent leur langue ou parlent l’anglais dans Teams réunions.

## <a name="allow-cloud-recording"></a>Autoriser l’enregistrement dans le cloud

Ce paramètre est une combinaison d’une stratégie par organisateur et par utilisateur et détermine si les réunions peuvent être enregistrées. L’enregistrement peut être démarré par l’organisateur de la réunion ou par un autre participant à la réunion si le paramètre de stratégie est activé pour le participant et s’il s’agit d’un utilisateur authentifié de la même organisation.

Les personnes extérieures à votre organisation, telles que les utilisateurs fédérés et anonymes, ne peuvent pas démarrer l’enregistrement. Les utilisateurs invités ne peuvent ni démarrer ni arrêter l’enregistrement.

![Capture d’écran montrant les options d’enregistrement](media/meeting-policies-recording.png)

Examinons l’exemple suivant.

|Utilisateur |Stratégie de réunion  |Autoriser l’enregistrement dans le Cloud |
|---------|---------|---------|
|Daniela | Global   | Désactivé |
|Geneviève | Location1MeetingPolicy | Activé|
|John (utilisateur externe) | Non applicable | Non applicable|

- Les réunions organisées par Daniela ne peuvent pas être enregistrées.
- Amanda ne peut pas enregistrer les réuni ons organisées par Daniela.
- Les réunions organisées par Amanda peuvent être enregistrées.
- Daniela ne peut pas enregistrer les réuni ons organisées par Amanda.
- John ne peut pas enregistrer les réuni ons organisées par Amanda.

Pour en savoir plus sur l’enregistrement de réunions cloud, consultez [Enregistrement de réunion cloud Teams](cloud-recording.md).

## <a name="store-recordings-outside-of-your-country-or-region"></a>Stocker des enregistrements en dehors de votre pays ou région

Cette stratégie contrôle si les enregistrements de réunion peuvent être stockés définitivement dans un autre pays ou région. S’il est activé, les enregistrements ne peuvent pas être migrés. Pour plus d’informations sur les réunions cloud et l’emplacement de stockage des enregistrements, consultez [Teams’enregistrement de réunion cloud](cloud-recording.md).

## <a name="related-topics"></a>Voir aussi

- [Attribuer des stratégies aux utilisateurs dans Teams](policy-assignment-overview.md)
- [Enregistrement de réunion cloud](cloud-recording.md)
