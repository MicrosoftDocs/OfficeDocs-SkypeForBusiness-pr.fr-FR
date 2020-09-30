---
title: Utiliser NDI dans Microsoft teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment utiliser NDI dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a1b756cfdb56de533d4dd170f301dc38e4b3b529
ms.sourcegitcommit: 45064a0020a1231e17967c74f082106c68213ea0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48308167"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Utiliser la technologie de® NDI dans Microsoft teams

 NewTek NDI® (Network Device Interface) est une solution moderne de connexion des appareils multimédias (par exemple, une caméra et un mixeur Studio). Au lieu d’utiliser des connexions physiques, NDI® technologie permet une connectivité via un intranet local, y compris sur un ordinateur local.

NDI® technologie est devenue une solution standard pour la production de contenus en direct et de sensibilisation et d’adoption dans le monde de la diffusion professionnelle.

Skype a déjà ajouté des fonctionnalités de® NDI à Skype au plus tard 2018. Microsoft teams utilise cette fonctionnalité pour améliorer l’utilisation de la réunion.

NDI® technologie est limitée à un réseau local et ne doit être considérée qu’une partie du flux de travail de production, et non d’une solution de diffusion.

## <a name="turn-on-ndi-technology"></a>Activation de la technologie de® NDI

NDI® technologie nécessite deux étapes pour être activée pour un utilisateur.

1. L’administrateur client doit activer la propriété « AllowNDIStreaming » dans CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Une fois cette modification remplie, l’utilisateur final doit activer la technologie de® NDI pour son client spécifique à partir des autorisations de **paramètres**  >  **Permissions**.

Lorsqu’un utilisateur rejoint une réunion, un message s’affiche indiquant que la réunion est en cours de diffusion. Si les utilisateurs ne veulent pas être inclus dans la diffusion, ils devront les supprimer de la réunion.

L’image ci-après illustre le message d’une bannière qu’un utilisateur voit dans une réunion Teams.

![Image de la bannière de technologie NDI® qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

La bannière comporte un lien vers la [politique de confidentialité Microsoft](https://aka.ms/teamsprivacy).

## <a name="supported-locales-and-user-types"></a>Paramètres régionaux et types d’utilisateurs pris en charge

NDI® technologie est prise en charge dans tous les pays/régions. Les utilisateurs suivants sont inclus dans un flux de technologie de® NDI, mais tous les utilisateurs ne peuvent pas accéder au flux de technologie NDI® :

- In-client-support complet, fourni en fonction de sonnerie/IDClient/Id_utilisateur (géré par la stratégie de réunion)
- Federated – aucun flux d’accès (même si la technologie® est activée)<sup>1</sup>
- Freemium-pas d’accès aux flux
- Anonyme-accès sans flux
- Invité – aucun flux d’accès  

<sup>1</sup> les appareils ont un paramètre de technologie NDI® activé par défaut. Si un participant à une réunion utilise un appareil sur lequel NDI® technologie est désactivé, il doit activer NDI technologie de®.
