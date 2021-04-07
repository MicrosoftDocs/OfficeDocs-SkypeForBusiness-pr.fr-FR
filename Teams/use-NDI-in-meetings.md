---
title: Utiliser NDI dans Microsoft Teams
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
ms.openlocfilehash: e26c6a7ad92353e083c67d0dad777e980a83fdfe
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598463"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Utiliser la technologie ® NDI dans Microsoft Teams

 La technologie NewTek NDI® (Network Device Interface) est une solution moderne pour connecter des périphériques multimédias (par exemple, une caméra de studio et un mixer). Au lieu d’utiliser des connexions physiques, la technologie NDI® active la connectivité sur un intranet local, y compris sur un ordinateur local.

La technologie NDI® est devenue une solution du secteur standard pour la production de contenu en direct pour les flux et a acquis une connaissance et une adoption significatives du monde de la diffusion professionnelle.

Skype a ajouté précédemment NDI®-out à Skype fin 2018. Microsoft Teams utilise cette fonctionnalité pour améliorer l’expérience de réunion.

La technologie NDI® est limitée à un réseau local et ne doit être considérée qu’comme faisant partie du flux de travail de production, et non d’une solution de diffusion.

## <a name="turn-on-ndi-technology"></a>Activer la technologie NDI®

La technologie ® NDI nécessite deux étapes pour être mise en marche pour un utilisateur.

1. L’administrateur des locataires doit activer la propriété « AllowNDIStreaming » dans CsTeamsMeetingPolicy.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
```

2. Une fois cette modification remplie, l’utilisateur final doit activer la technologie NDI® de son client spécifique à partir des  >  **autorisations de paramètres.**

Lorsqu’un utilisateur rejoint une réunion, un message l’avertit de la diffusion de la réunion. Si les utilisateurs ne souhaitent pas être inclus dans la diffusion, ils doivent abandonner la réunion.

L’image suivante montre le message bannière qu’un utilisateur voit dans une réunion Teams.

![Bannière technologie ® NDI qui s’affiche dans une réunion Teams.](media/NDI-disclosure.png)

La bannière est un lien vers la politique [de confidentialité de Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® est activé par session uniquement. Lors de la prochaine connexion, l’utilisateur doit l’activer avant d’utiliser NDI®.

## <a name="supported-locales-and-user-types"></a>Paramètres régionaux et types d’utilisateur pris en charge

La technologie ® NDI est prise en charge dans tous les paramètres régionaux. Les utilisateurs suivants sont inclus dans un flux de technologie NDI® mais tous ne peuvent pas accéder au flux de technologie NDI® :

- Dans le client : support total, livré en fonction de l’anneau/tenantId/userId (contrôlé par la stratégie Réunions)
- Fédérés – aucun accès aux flux (même s’ils ont NDI® sur)<sup>1</sup>
- Premium - pas d’accès aux flux
- Anonyme – aucun accès aux flux
- Invité – aucun accès aux flux  

<sup>1 Les</sup> appareils ont un paramètre ® NDI qui est par défaut. Si un participant à la réunion utilise un appareil avec la technologie NDI® est éteinte, il doit activer la technologie ® NDI.
