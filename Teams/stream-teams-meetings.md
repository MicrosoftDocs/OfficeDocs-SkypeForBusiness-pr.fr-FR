---
title: Diffuser en continu des réunions Teams
author: MicrosoftHeidi
ms.author: heidip
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
description: Découvrez comment configurer et gérer la diffusion en continu pour vos réunions Teams.
ms.openlocfilehash: b8394abfe66ecde6813e383e0473bcdca2a0ad9f
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67707001"
---
# <a name="stream-teams-meetings"></a>Diffuser en continu des réunions Teams

Cet article vous aidera à configurer la diffusion en continu pour les réunions Teams.

## <a name="what-is-streaming-and-how-does-it-work"></a>Qu’est-ce que le streaming et comment fonctionne-t-il ?

La diffusion en continu permet à votre organisation d’étendre votre portée et offre aux participants à la réunion plus d’options de réunion. Lorsque vous activez la diffusion en continu, les organisateurs peuvent diffuser en continu des réunions et des webinaires vers des points de terminaison externes en fournissant une URL et une clé rtMP (Messaging Protocol) Real-Time à l’application de diffusion en continu personnalisée intégrée dans Teams.

> [!NOTE]
> Vous ne pouvez pas diffuser des événements en direct.

## <a name="set-up-streaming-with-powershell"></a>Configurer la diffusion en continu avec PowerShell

Vous pouvez configurer votre organisation pour la diffusion en continu avec PowerShell. Actuellement, cette stratégie n’est pas disponible dans le Centre d’administration Teams. La stratégie par utilisateur est utilisée pour spécifier **qui** peut activer la diffusion en continu en direct. Cette option est désactivée par défaut.

Vous pouvez utiliser l’attribut suivant dans l’Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** pour configurer la diffusion en continu. Pour plus d’informations sur l’applet de commande, consultez [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

Définissez **LiveStreamingMode** sur **Enabled** pour activer les fonctionnalités de streaming pour un ou plusieurs utilisateurs.

> [!IMPORTANT]
> Vous devez activer l’inscription à la réunion pour que vos organisateurs puissent diffuser des webinaires en continu. Pour plus d’informations, consultez [Configurer des webinaires](set-up-webinars.md).

### <a name="assign-the-policy"></a>Affecter la stratégie

Pour plus d’informations sur l’affectation de stratégies avec PowerShell, consultez [Affecter des stratégies dans Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Rubriques connexes

- [Affecter des stratégies dans Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Démarrage rapide : réunions, webinaires et événements en direct](quick-start-meetings-live-events.md)