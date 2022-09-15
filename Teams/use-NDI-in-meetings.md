---
title: Diffuser du contenu de réunion
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: aalinne
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser NDI et SDI pour diffuser du contenu de réunion dans Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc185a22c7ea4d849008989da29f50a8f98ebb9d
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706811"
---
# <a name="broadcast-meeting-content"></a>Diffuser du contenu de réunion 



Teams propose deux options pour diffuser du contenu de réunion Teams : Network Device Interface (NewTek NDI®) et Serial Digital Interface (SDI) :

- La technologie NewTek NDI® est une solution moderne pour connecter des appareils multimédias (comme une caméra de studio et un mixer). Au lieu d’utiliser des connexions physiques, la technologie NDI® permet la connectivité sur un intranet local, y compris sur un ordinateur local.

  La technologie NDI® est devenue une solution industrielle standard pour la production de contenu en direct pour les flux et a acquis une sensibilisation et une adoption significatives dans le monde de la diffusion professionnelle.

- SDI est utilisé dans les productions de diffusion depuis 1989 et est pris en charge sur la plupart des appareils matériels studio hérités. Les appareils matériels d’AJA Video Systems et blackmagic Design fournissent une connectivité aux appareils de diffusion hérités qui utilisent SDI.

> [!NOTE]
> La fonctionnalité Video Hardware Out prise en charge par SDI est actuellement disponible en préversion.

La technologie NDI® et SDI est prise en charge dans tous les paramètres régionaux.

L’accès à l’utilisation de NDI et de SDI est déterminé par la stratégie de réunion pour l’utilisateur qui tente d’activer la fonctionnalité. Pour la solution la plus sécurisée, n’activez pas le paramètre de streaming local en tant que paramètre global.


## <a name="enable-broadcast-features"></a>Activer les fonctionnalités de diffusion

Pour activer les fonctionnalités de diffusion NDI® et SDI pour un utilisateur :

1. L’administrateur client doit permettre à l’utilisateur final d’activer le streaming local pour sa stratégie de réunion. 

2. L’utilisateur final doit activer le streaming local pour son client spécifique.


Pour activer l’utilisateur final, vous pouvez utiliser le centre Administration Teams ou Teams PowerShell comme suit.

Dans le Centre d’administration Teams, accédez aux **stratégies de réunion > vidéo audio &** et sélectionnez **Diffusion locale**.

Pour utiliser PowerShell, utilisez l’applet de commande Set-CsTeamsMeetingPolicy comme suit :

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

Une fois cette modification remplie, l’utilisateur final doit activer la diffusion en continu locale pour son client spécifique à partir **des autorisations** >  de **paramètres**. Pour plus d’informations, consultez [Diffusion audio et vidéo à partir de Teams](https://support.microsoft.com/office/broadcasting-audio-and-video-from-teams-with-ndi-technology-e91a0adb-96b9-4dca-a2cd-07181276afa3).





