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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9a82174fd09106f623bcf0f9a03a99c2978253ec
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615110"
---
# <a name="use-ndi-technology-in-microsoft-teams"></a>Utiliser la technologie ® NDI dans Microsoft Teams

 La technologie NewTek NDI® (Network Device Interface) est une solution moderne pour connecter des périphériques multimédias (par exemple, une caméra de studio et un mixer). Au lieu d’utiliser des connexions physiques, la technologie NDI® active la connectivité sur un intranet local, y compris sur un ordinateur local.

La technologie NDI® est devenue une solution du secteur standard pour la production de contenu en direct pour les flux et a acquis une connaissance et une adoption significatives du monde de la diffusion professionnelle.

Skype des fonctionnalités de ® NDI précédemment ajoutées à Skype fin 2018. Microsoft Teams utilise cette fonctionnalité pour améliorer l’expérience de réunion.

La technologie NDI® est limitée à un réseau local et ne doit être considérée qu’comme faisant partie du flux de travail de production, et non d’une solution de diffusion.

## <a name="turn-on-ndi-technology"></a>Activer la technologie NDI®

La technologie ® NDI nécessite deux étapes pour être mise en marche pour un utilisateur.

1. L’administrateur des locataires doit permettre à l’utilisateur final d’activer NDI pour sa stratégie de réunion. Cette action peut être effectuée de manière individuelle sur le portail d’administration Teams ou via Teams PowerShell par la propriété _AllowNDIStreaming_ dans CsTeamsMeetingPolicy.

    ```PowerShell
    Set-CsTeamsMeetingPolicy -Identity MEETING_POLICY -AllowNDIStreaming $true
    ```

2. Une fois cette modification remplie, l’utilisateur final doit activer la technologie NDI® de son client à partir de **Paramètres**  >  **autorisations.**

Après avoir été allumé pour un utilisateur et son client particulier, l’utilisateur peut activer NDI via le menu de dépassement de capacité et sélectionner « Diffuser sur NDI ».

Une fois que vous avez commencé le NDI et qu’un point de terminaison est abonné à un flux NDI, un message l’informe que la réunion est en cours de diffusion. Si les utilisateurs ne souhaitent pas être inclus dans la diffusion, ils doivent abandonner la réunion.

L’image suivante montre le message bannière qu’un utilisateur voit dans une Teams réunion.

![bannière technologie ® he NDI qui s’affiche dans une Teams réunion.](media/NDI-disclosure.png)

La bannière est un lien vers la politique [de confidentialité de Microsoft.](https://aka.ms/teamsprivacy)

> [!NOTE]
> NDI® est activé par session uniquement. Lors de la prochaine réunion, l’utilisateur doit l’activer avant d’utiliser NDI®.

## <a name="supported-locales-and-user-types"></a>Paramètres régionaux et types d’utilisateur pris en charge

La technologie ® NDI est prise en charge dans tous les paramètres régionaux.

L’accès à l’utilisation de NDI est déterminé par la stratégie de réunion de l’utilisateur qui tente d’activer la fonctionnalité. Pour la solution la plus sécurisée, n’tournez pas la stratégie NDI en tant que paramètre global.
