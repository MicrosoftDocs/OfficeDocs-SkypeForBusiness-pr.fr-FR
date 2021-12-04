---
title: Découvrir comment configurer des caméras de contenu - Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Utilisez une caméra de contenu dans une salle Microsoft Teams, qui interagit avec le logiciel de traitement des images pour permettre aux présentateurs de dessiner sur un tableau blanc analogique.
ms.openlocfilehash: 913d7fbc9593c1753c3cb4b59d44a4101e687178
ms.sourcegitcommit: 7eb66cb2955b17e89e1c162b6ca1b9bdb18189b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/04/2021
ms.locfileid: "61306139"
---
# <a name="content-cameras"></a>Caméras de contenu

Vous pouvez désormais utiliser une caméra de contenu avec un Microsoft Teams de salle. Une caméra de contenu interagit avec un logiciel spécial de traitement des images et un tableau blanc pour permettre à un présentateur de dessiner sur un tableau blanc analogique et de partager le contenu avec des participants distants.

Consultez la vidéo suivante pour obtenir des exemples de fonctionnalités de caméra de contenu.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurer une caméra de contenu

> [!NOTE]
> Vous pouvez toujours respecter le code de bâtiment de votre pays ou région, qui peut définir une distance minimale par rapport au plancher ou une obligation de sécuriser l’équipement par plafond à un bâtiment ou à une autre structure. Suivez les instructions de montage pour le matériel fourni avec l’appareil photo que vous avez sélectionné. Les kits de montage de caméra OEM incluent un appareil photo, des extensions USB 2.0 et un cabling requis.

La taille du tableau blanc utilisé pour le partage affecte la position de l’appareil photo. Les recommandations en matière de taille de tableau sont les suivantes :

- 3 à 6 pieds (0,9-1,8 m) de large — Pris en charge
- 6-9 p. (1,8-2,7 m) de largeur — Recommandé
- Largeur : 9 à 12 pieds (2,7 à 3,6 m) — Pris en charge
- Au-dessus de 12 pieds (3,6 m) de large : l’appareil photo couvre 9 à 12 pieds (2,7 à 3,6 m) et fait le reste.

## <a name="camera-location"></a>Emplacement de l’appareil photo

Le placement idéal d’une caméra de contenu est centré verticalement et horizontalement sur le tableau blanc. Les codes de bâtiment locaux peuvent avoir des restrictions de hauteur qui nécessitent que l’appareil photo soit élevé au-dessus du haut du tableau blanc.

Vous pouvez installer l’appareil photo jusqu’à 6 dans. (152 mm) au-dessus du tableau blanc et centré sur le tableau blanc, comme illustré. Assurez-vous que l’image de l’appareil photo en contient au moins 6. (152 mm) bordure horizontale des deux côtés. Vous pouvez utiliser l’aperçu de la caméra dans l Salles Microsoft Teams pour déterminer la position finale de la caméra.

![Diagramme de placement de la caméra de contenu.](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distances de l’appareil photo

À l’aide de marqueurs de tableau blanc classiques, l’expérience utilisateur à distance optimale consiste à partager des traits d’encre dans la plage de 1 à 2 mm par pixel dans l’image de la caméra de contenu, et les meilleurs résultats utilisent 1,5 mm par pixel. Toutes les caméras prise en charge offrent une résolution de 1920 x 1080, et certaines peuvent dépasser cette résolution.

La distance de la caméra par rapport au tableau blanc se combine avec la résolution de l’appareil photo et le champ horizontal de vue (HFoV) pour déterminer la distance par rapport au tableau blanc. Le tableau suivant présente des exemples de distances pour différentes tailles de tableau blanc. Vous pouvez utiliser ces valeurs comme points de départ pour déterminer le placement final de la caméra de contenu.

**Distance de l’appareil photo du tableau blanc**

| Caméra HFoV |3 p. (0,91 m)     | 6 p. (1,8 m)    | 9 p. (2,74 m)        |12 pieds.  (3,65 m)         | Distance maximale du Tableau blanc  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1,79 p. (0,54 m) | 3,58 p. (1,09 m)  | 5,36 p. (1,6 m)    |7,15 p. (2,17 m) |7,51 p. (2,28 m) |
| 90°         | 1,5 pied (0,45 m) | 3,00 M. (0,91 m)   | 4,5 p. (1,37 m)    |6,0 p. (1,82 m)    |6,3 pieds (1,92 m) |
| 100°        | 1,26 p. (0,38 m)| 2,52 p. (0,77 m)   | 3,78 p. (1,15 m)   |5,03 p. (1,53 m)   |5,29 p. (1,61 m) |
| 110°        | 1,05 p. (0,32 m)| 2,10 m. (0,64 m)   | 3,15 p. (0,96 m)   |4,2 p. (1,28 m)    |4,41 p. (1,31 m) |
| 120°        | 0,87 p. (0,26 m)| 1,73 p. (0,52 m)   | 2,60 m. (0,79 m)   |3,46 pieds (1,05 m)   |3,64 p. (1,10 m) |
             

La distance entre la caméra de contenu et le mur sur lequel le tableau blanc est installé dépend du HFoV pour ce modèle de caméra, qui varie. Installez les caméras avec un HFoV plus grand (120 degrés par exemple) plus proche du mur, et les caméras dont le HFoV est plus étroit et plus éloigné du mur. Vérifiez le HFoV avant de commencer à installer l’appareil photo choisi.

Si vous avez des tableaux blancs d’une taille supérieure à 12 pieds (3,65 m) ou sans coins (comme les tableaux blancs muraux complets), vous pouvez placer l’appareil photo n’importe où au milieu. Le logiciel d’amélioration sélectionne une zone au milieu s’il ne parvient pas à trouver les coins du tableau blanc.

> [!NOTE]
> Vous pouvez utiliser une bande de couleur foncée ou d’autres éléments pour créer une zone de caméra de contenu définie sur un tableau blanc entièrement muré. Cela permet aux participants à la salle de savoir quand ils dessinent dans une zone prise par la caméra de contenu.
>
> Vous pouvez choisir que l’appareil photo soit installé sur unpode moveable au lieu d’un montage permanent. Placez lepode centré sur le tableau blanc. Cette configuration peut être temporaire ou utilisée lorsqu’il y a peu de risque de couplage sur l’équipement. Si vous utilisez un montage temporaire, n’oubliez pas que l’amélioration du contenu sera impactée si vous déplacez la caméra après le partage initial et que vous devrez partager à nouveau pour corriger le mouvement.
>
> Les tableaux d’écriture non blancs ne sont pas pris en charge.

## <a name="supported-cameras"></a>Appareils photo pris en charge

Pour déterminer si vous pouvez utiliser une caméra comme caméra de contenu, reportez-vous aux versions de microprogramme certifiés pour les [périphériques audio et vidéo USB.](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)

Ou, consultez la place de marché Microsoft Teams de vos appareils pour obtenir des kits d’appareil photo de contenu pris en charge [sur aka.ms/teamsdevices.](https://aka.ms/teamsdevices)

## <a name="camera-settings"></a>Paramètres de la caméra

Une fois la caméra installée dans la salle, installez-la sur la console d’Salles Microsoft Teams de cette salle :

1. Sélectionnez **Paramètres** Paramètres icône. Connectez-vous en tant ![ qu’administrateur, ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) puis **sélectionnez Périphériques.**
2. Dans la section **Caméra de contenu,** sélectionnez la caméra de contenu et assurez-vous que l’option Améliorations **du** contenu est sélectionnée.
3. (Facultatif) Si l’appareil photo a été installé à l’envers parce qu’il était installé à partir du plafond, vérifiez l’option Faire pivoter la caméra de contenu **à 180°.**
4. Sélectionnez **Enregistrer et quitter.**

![Configuration de la caméra de contenu.](../media/content-camera1.png)

Vous pouvez également ajuster ces paramètres à distance à l’aide [d’un fichier de configuration XML.](xml-config-file.md)

## <a name="see-also"></a>Voir aussi

[Gérer les paramètres Salles Microsoft Teams d’une console à distance avec un fichier de configuration XML](xml-config-file.md)

[Spécifications des salles Microsoft Teams](requirements.md)


