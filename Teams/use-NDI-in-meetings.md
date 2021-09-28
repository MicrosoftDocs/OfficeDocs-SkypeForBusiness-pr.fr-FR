---
title: Diffuser le contenu d’une réunion
author: CarolynRowe
ms.author: crowe
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser NDI et SDI pour diffuser du contenu de réunion Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65e47ccfa1963e8e95e13a1c8b94e1e051ff709c
ms.sourcegitcommit: 84706d0b3b93c1bc72baac830fefd3f0a87c5ad1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/27/2021
ms.locfileid: "59941879"
---
# <a name="broadcast-meeting-content"></a>Diffuser le contenu d’une réunion 



Teams propose deux options de diffusion du contenu Teams réunion : Network Device Interface (NewTek NDI®) et SDI (Serial Digital Interface) :

- La technologie NewTek NDI® est une solution moderne pour connecter des périphériques multimédias (par exemple, une caméra de studio et un mixer). Au lieu d’utiliser des connexions physiques, la technologie NDI® active la connectivité sur un intranet local, y compris sur un ordinateur local.

  La technologie NDI® est devenue une solution du secteur standard pour la production de contenu en direct pour les flux et a acquis une connaissance et une adoption significatives du monde de la diffusion professionnelle.

- SDI est utilisé dans les productions de diffusion depuis 1989 et est pris en charge sur la plupart des périphériques de studio hérités. Les périphériques des systèmes vidéo AJA et Blackmagic Design offrent une connectivité aux anciens périphériques de diffusion qui utilisent SDI.

> [!NOTE]
> La fonctionnalité De matériel sortant vidéo qui prend en charge le SDI est actuellement dans la version Preview.

Les ® NDI et SDI sont pris en charge dans tous les paramètres régionaux.

L’accès à l’utilisation de NDI et SDI est déterminé par la stratégie de réunion de l’utilisateur qui tente d’activer la fonctionnalité. Pour la solution la plus sécurisée, ne pas activer le paramètre de diffusion en continu local comme paramètre global.


## <a name="enable-broadcast-features"></a>Activer les fonctionnalités de diffusion

Pour activer les fonctionnalités de ® de diffusion NDI et SDI pour un utilisateur :

1. L’administrateur des locataires doit permettre à l’utilisateur final d’activer la diffusion en continu locale pour sa stratégie de réunion. 

2. L’utilisateur final doit activer la diffusion en continu locale pour son client spécifique.


Pour activer l’utilisateur final, vous pouvez utiliser le Centre Teams’administration Teams PowerShell comme suit.

Dans le centre Teams d’administration, sélectionnez Stratégies de **réunion > vidéo Audio &** et **sélectionnez Autoriser la diffusion en continu NDI.**

Pour utiliser PowerShell, utilisez l'Set-CsTeamsMeetingPolicy de cmdlet comme suit :

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Une fois cette modification remplie, l’utilisateur final doit activer la diffusion en continu locale pour son client spécifique à partir **de Paramètres**  >  **autorisations.** Pour plus d’informations, [voir Diffusion audio et vidéo à partir de Teams.](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3)





