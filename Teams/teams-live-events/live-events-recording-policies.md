---
title: Stratégies d’enregistrement des événements en direct
author: CarolynRowe
ms.author: crowe
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
description: Découvrez les stratégies d’enregistrement d’événements en direct.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ae98255edf26843e59839192a9f20096182bfa2
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794112"
---
# <a name="live-event-recording-policies-in-microsoft-teams"></a>Stratégies d’enregistrement d’événements en direct dans Microsoft Teams

Vous disposez de plusieurs options pour enregistrer un événement en direct Microsoft Teams. Les options d’enregistrement sont définies à l’aide de stratégies d’enregistrement. Cet article décrit les différents paramètres.

Les options d’enregistrement sont définies à l’aide de la commande PowerShell [Set-CsTeamsMeetingBroadcastPolicy](/powershell/module/skype/set-csteamsmeetingbroadcastpolicy).

## <a name="scheduling-and-option-behaviors"></a>Comportements de planification et d’option

Il existe deux options d’organisateur lors de la planification d’un enregistrement d’événement en direct :

- Enregistrement disponible pour les producteurs et les présentateurs

  - Fichier d’enregistrement : fournit un fichier d’enregistrement que les producteurs et les présentateurs peuvent télécharger une fois l’événement terminé.

- Enregistrement disponible pour les participants

  - DVR : Un enregistreur vidéo numérique (DVR) permet aux participants de rembobiner et de s’interrompre pendant l’événement

  - VOD : une vidéo à la demande (VOD) permet aux participants de regarder une fois l’événement terminé

## <a name="broadcast-recording-policy-setting"></a>Paramètre de stratégie d’enregistrement de diffusion

Dans le cadre de la stratégie de diffusion, vous pouvez activer ou désactiver l’enregistrement pour un événement en direct.

| &nbsp;| Enregistrement disponible pour les producteurs et les présentateurs | Enregistrement disponible pour les participants |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------- |
| Toujours enregistrer               | Désactivé et sélectionné                                | Activé et sélectionné         |
| L’organisateur peut enregistrer ou non | Activé et sélectionné par défaut                  | Activé et sélectionné par défaut   |
| Ne jamais enregistrer               | Désactivé et non sélectionné                            | Désactivé et non sélectionné      |

## <a name="storage-and-persistence-behavior"></a>Comportement de stockage et de persistance

| Option                                       | État   | DVR                                                   | VOD                                                     | Enregistrement                |
| ------------------------------------------------ | ------------ | --------------------------------------------------------- | ----------------------------------------------------------- | ---------------------------- |
| Enregistrement disponible pour les participants | Sélectionné     | DVR est disponible et la ressource Azure Media Services (AMS) est stockée pendant 180 jours | Le participant peut accéder à l’événement et l’observer                     |                              |
|                                                  | Non sélectionné | DVR est disponible et la ressource AMS est stockée pendant 180 jours | Le participant n’aura pas accès à l’événement une fois l’événement terminé |                              |
||Désactivé (non sélectionné)|DVR est disponible et la ressource AMS est supprimée après l’événement|Le participant n’aura pas accès à l’événement une fois l’événement terminé||
| Enregistrement disponible pour les producteurs et les présentateurs | Sélectionné     |                                                           |                                                             | Un MP4 est créé et stocké pendant 180 jours |
|                                                  | Non sélectionné |                                                           |                                                             | Aucun fichier n’est créé           |

### <a name="related-topics"></a>Sujets associés

- [Comprendre un événement en direct Teams](what-are-teams-live-events.md)
- [Offre pour les événements en direct Teams](plan-for-teams-live-events.md)
- [Configurer les paramètres d’événements en direct dans Teams](configure-teams-live-events.md)
- [Enregistrement des réunions de clouds Teams](../cloud-recording.md)
