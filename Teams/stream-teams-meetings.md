---
title: Diffuser en continu Teams réunions
author: KarliStites
ms.author: kastites
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: Découvrez comment configurer et gérer la diffusion en continu pour vos Teams réunion.
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127544"
---
# <a name="stream-teams-meetings"></a>Diffuser en continu Teams réunions

Cet article vous aide à configurer la diffusion en continu pour Teams réunions.

## <a name="what-is-streaming-and-how-does-it-work"></a>Qu’est-ce que la diffusion en continu et comment fonctionne-t-elle ?

La diffusion en continu permet à votre organisation de développer votre portée et offre aux participants d’autres options de réunion. Lorsque vous activez la diffusion en continu, les organisateurs peuvent diffuser des réunions et des webinaires sur des points de terminaison externes en fournissant une URL Real-Time Messaging Protocol (RTMP) et une clé d’accès à l’application de diffusion en continu personnalisée dans Teams.

> [!NOTE]
> Vous ne pouvez pas diffuser d’événements en direct.

## <a name="set-up-streaming-with-powershell"></a>Configurer la diffusion en continu avec PowerShell

Vous pouvez configurer votre organisation pour la diffusion en continu avec PowerShell. Pour l’instant, cette stratégie n’est pas disponible dans Teams centre d’administration. La stratégie par utilisateur est utilisée pour spécifier **qui peut** activer la diffusion en direct. Cette option est désactivée par défaut.

Vous pouvez utiliser l’attribut suivant dans la Windows PowerShell **cmdlet Set-CsTeamsMeetingPolicy** pour configurer la diffusion en continu. Pour plus d’informations sur l’let, voir [Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)

- LiveStreamingMode

Définissez **LiveStreamingMode** sur **Activé** pour activer les fonctionnalités de diffusion en continu pour un ou plusieurs utilisateurs.

> [!IMPORTANT]
> Vous devez activer l’inscription aux réunions pour que vos organisateurs puisse diffuser des webinaires. Pour plus d’informations, voir [Configurer des webinaires.](set-up-webinars.md)

### <a name="assign-the-policy"></a>Affecter la stratégie

Pour plus d’informations sur l’affectation de stratégies avec PowerShell, voir Attribuer des [stratégies dans Teams.](policy-assignment-overview.md)

## <a name="related-topics"></a>Sujets associés

- [Attribuer des stratégies dans Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Démarrage rapide : réunions, webinaires et événements en direct](quick-start-meetings-live-events.md)