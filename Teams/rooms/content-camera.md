---
title: Découvrir comment configurer les appareils photo de contenu-Microsoft teams
ms.author: kenwith
author: kenwith
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
description: Utilisez une caméra de contenu dans une salle de Microsoft Teams, qui interagit avec un logiciel de traitement d’image pour permettre aux présentateurs de dessiner sur un tableau blanc analogique.
ms.openlocfilehash: ecd9c20c7f479c548d0ab9b4c3db8bbec945e79f
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43157807"
---
# <a name="content-cameras"></a>Caméras de contenu

Vous pouvez désormais utiliser une caméra de contenu avec un système de salle Microsoft Teams. Une caméra de contenu interagit avec un logiciel spécial de traitement des images et un tableau blanc pour permettre au présentateur de dessiner sur un tableau blanc analogique et de partager le contenu avec des participants distants.

Pour obtenir des exemples de fonctionnalités de caméra de contenu, consultez la vidéo suivante.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurer une caméra de contenu

> [!NOTE]
> Restez toujours dans le code de bâtiment de votre pays ou de votre région, qui peut définir une distance minimum entre le plancher ou une prescription pour la sécurisation de l’équipement monté au plafond pour le rafting ou l’autre structure. Suivez les instructions de montage du matériel fourni avec l’appareil photo que vous avez sélectionné. Les kits de montage d’appareil photo OEM incluent une caméra, des extensions USB 2,0 et des câbles nécessaires.

La taille du tableau blanc utilisé pour le partage affecte la position de la caméra. Les recommandations en matière de taille de tableau sont les suivantes :

- 3 à 6 pieds (0,9-1,8 m)
- 6 à 9 m (1,8-2,7 m) large, recommandé
- entre 9 et 12 m (2,7-3,6 m), prise en charge
- Au-dessus d’une largeur de 12 mètres (3,6), la caméra couvre entre 9 et 12 mètres.

## <a name="camera-location"></a>Emplacement de la caméra

L’emplacement idéal d’une caméra de contenu est centré verticalement et horizontalement sur le tableau blanc. Les codes de bâtiment locaux peuvent présenter des restrictions de hauteur qui nécessitent une élévation de la caméra supérieure à la partie supérieure du tableau blanc.

Vous pouvez installer la caméra jusqu’à 6. (152 mm) plus haut que le haut du tableau blanc et centré sur le tableau blanc, comme illustré ci-dessous. Assurez-vous que l’image de l’appareil photo comporte au moins 6. (152 mm) bordure sur les deux côtés horizontalement. Vous pouvez utiliser l’aperçu de l’appareil photo dans l’application Microsoft teams pour déterminer l’emplacement final de la caméra.

![Diagramme de placement d’une caméra de contenu](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distances de caméra

À l’aide de marqueurs de tableau blanc standard, l’utilisation optimale de votre télécommande consiste à partager les traits d’encre dans la plage 1 à 2 mm par pixel dans l’image de l’appareil photo de contenu, et les meilleurs résultats utilisent 1,5 mm par pixel. Toutes les caméras prises en charge garantissent une résolution 1920 x 1080 et certaines peuvent dépasser cette résolution.

La distance entre l’appareil photo et le tableau blanc est associée à la résolution de l’appareil photo et HFoV pour déterminer la distance du tableau blanc. Le tableau suivant montre des exemples de distances pour différentes tailles de tableaux blancs. Vous pouvez utiliser ces valeurs comme points de départ pour déterminer le positionnement final de l’appareil photo de contenu.

**Distance de l’appareil photo sur le tableau blanc**

| Caméra HFoV |3 ft (0,91 m)     | 1,80 m (1,8 m)    | 9 ft (2,74 m)        |12:00.  (3,65 m)         | Distance maximum sur le tableau blanc  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80 °         | 1,79 m 0,54. | 3,58 m 1,09.  | 5,36 m 1,6.    |7,15 m 2,17. |7,51 m 2,28. |
| 90 °         | 1,5 m 0,45. | 3,00 m 0,91.   | 4,5 m 1,37.    |6,0 m 1,82.    |6,3 m 1,92. |
| 100 °        | 1,26 m 0,38.| 2,52 m 0,77.   | 3,78 m 1,15.   |5,03 m 1,53.   |5,29 m 1,61. |
| 110 °        | 1,05 m 0,32.| 2,10 m 0,64.   | 3,15 m 0,96.   |4,2 m 1,28.    |4,41 m 1,31. |
| 120 °        | 0,87 m 0,26.| 1,73 m 0,52.   | 2,60 m 0,79.   |3,46 m 1,05.   |3,64 m 1,10. |
|             |               |                  |                  |        |                    |                  |

La distance entre l’appareil photo de contenu et le mur sur lequel est monté le tableau blanc dépend du HFoV de ce modèle de caméra, qui varie. Vous pouvez rapprocher les webcams avec un HFoV plus grand (120, par exemple) plus près du mur et utiliser un HFoV plus étroit pour l’éloigner du mur. Vérifiez le HFoV avant de commencer l’installation de l’appareil photo sélectionné.

Si vous disposez de tableaux blancs dont la taille est supérieure à 12 mètres (3,65 m) ou qu’il n’y a pas de coin (par exemple, tableaux blancs de type mur plein), vous pouvez placer la caméra n’importe où dans le milieu. Le logiciel d’amélioration sélectionne une zone du milieu s’il ne parvient pas à trouver des angles de tableau blanc.

> [!NOTE]
> Vous pouvez utiliser une bande de couleur foncée ou d’autres éléments pour créer une zone de caméra de contenu définie sur un tableau blanc mural.
>
> Vous pouvez choisir de monter la caméra sur un trépied amovible au lieu d’un montage permanent. Placez le trépied centré sur le tableau blanc. Ce paramétrage peut être temporaire ou utilisé pour lequel il n’y a pas de risque de cogner l’équipement. Si vous utilisez un montage temporaire, n’oubliez pas que l’amélioration du contenu sera affectée si vous déplacez l’appareil photo après le partage initial et que vous devez le repartager pour corriger le mouvement.
>
> Un tableau de rédaction qui n’est pas blanche n’est pas pris en charge.

## <a name="supported-cameras"></a>Caméras prises en charge

Pour déterminer si vous pouvez utiliser un appareil photo comme caméra de contenu, reportez-vous à la rubrique [versions de microprogramme certifiées pour les périphériques audio et vidéo USB](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

Pour plus d’informations, consultez la rubrique Marketplace Microsoft teams Marketplace pour les kits de caméras de contenu pris en charge sur [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Paramètres de l’appareil photo

Une fois la caméra installée dans la salle, configurez-la sur la console Microsoft teams salles de cette salle :

1. Sélectionnez **Settings** ![l’icône](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)paramètres des paramètres, connectez-vous en tant qu’administrateur, puis sélectionnez Paramètres de l' **appareil**.
2. Dans la section **valeurs par défaut de l’appareil photo** , sélectionnez l’appareil photo de contenu et assurez-vous que l’option **améliorations du contenu** est sélectionnée.
3. Facultatif Si la caméra a été installée à l’envers, car la caméra a été montée à partir du plafond, activez l’option **faire pivoter l’appareil photo 180 °** .
4. Sélectionnez **enregistrer et quitter**.

![Configuration de la caméra de contenu](../media/content-camera.png)

Vous pouvez également ajuster ces paramètres à distance à l’aide d’un [fichier de configuration XML](xml-config-file.md).

## <a name="see-also"></a>Voir aussi

[Gérer les paramètres de la console salles de Microsoft teams à distance à l’aide d’un fichier de configuration XML](xml-config-file.md)

[Configuration requise pour Microsoft teams](requirements.md)


