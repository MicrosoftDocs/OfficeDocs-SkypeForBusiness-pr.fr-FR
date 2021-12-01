---
title: Stratégies d’enregistrement des événements en direct
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: christi.balaki
audience: admin
search.appverid: MET150
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: En savoir plus sur les stratégies d’enregistrement d’événements en direct.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 80489f699004ed7dbcb8d7493c32a7bc26e3e25e
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257342"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Stratégies d’enregistrement d’événements en direct Microsoft Teams

Plusieurs options s’offrent à vous pour enregistrer Microsoft Teams événement en direct. Les options d’enregistrement sont définies à l’aide de stratégies d’enregistrement. Cet article décrit les différents paramètres.

Les options d’enregistrement sont définies à l’aide de la commande PowerShell [Set-CsTeamsMeetingBroadcastPolicy.](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy)

## <a name="scheduling-and-option-behaviors"></a>Planification et comportements des options

Deux options d’organisateur sont disponibles lors de la planification de l’enregistrement d’un événement en direct :

- Enregistrement disponible pour les producteurs et les présentateurs

  - Fichier d’enregistrement : fournit un fichier d’enregistrement que les producteurs et les présentateurs peuvent télécharger une fois l’événement terminé.

- Enregistrement disponible pour les participants

  - DVR : un enregistreur vidéo numérique (DVR) permet aux participants de rembobiner et de suspendre pendant l’événement

  - VOD : une vidéo à la demande permet aux participants de les regarder une fois l’événement terminé

## <a name="broadcast-recording-policy-setting"></a>Paramètre de stratégie d’enregistrement de diffusion

Dans le cadre de la stratégie de diffusion, vous pouvez activer ou désactiver l’enregistrement d’un événement en direct à partir d’un paramètre.

| &nbsp;| Enregistrement disponible pour les producteurs et les présentateurs | Enregistrement disponible pour les participants |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Toujours enregistrer               | Désactivé et sélectionné                                | Activé et sélectionné         |
| L’organisateur peut enregistrer ou non | Activé et sélectionné par défaut                  | Activé et sélectionné par défaut   |
| N’enregistrez jamais               | Désactivé et non sélectionné                            | Désactivé et non sélectionné      |

## <a name="storage-and-persistence-behavior"></a>Stockage et de persistance

| Option                                       | État   | DVR                                                   | VOD                                                     | Enregistrement                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Enregistrement disponible pour les participants | Sélectionné     | DVR est disponible et le Azure Media Services (AMS) est stocké pendant 180 jours | Les participants peuvent accéder à l’événement et le regarder                     |                              |
|                                                  | Non sélectionné | DVR est disponible et le bien AMS est stocké pendant 180 jours | Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé |                              |
||Désactivé (non sélectionné)|DVR est disponible et l’actif AMS est supprimé après l’événement|Le participant ne sera pas autorisé à accéder à l’événement une fois celui-ci terminé||
| Enregistrement disponible pour les producteurs et les présentateurs | Sélectionné     |                                                           |                                                             | Un mp4 est créé et stocké pendant 180 jours |
|                                                  | Non sélectionné |                                                           |                                                             | Aucun fichier n’est créé           |

### <a name="related-topics"></a>Sujets associés

- [Comprendre un événement en direct Teams](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les paramètres d’événements en direct dans Teams](configure-teams-live-events.md)
- [Teams de réunion en nuages](../cloud-recording.md)
