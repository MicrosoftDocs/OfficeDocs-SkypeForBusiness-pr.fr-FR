---
title: Résolutions vidéo client Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Résumé : consultez la configuration requise pour la vidéo client lors de la planification de Skype entreprise Server.'
ms.openlocfilehash: 126c19d817a2cd656b7d581e0d467db80e4969e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027975"
---
# <a name="skype-for-business-client-video-resolutions"></a>Résolutions vidéo client Skype entreprise
 
**Résumé :** Passez en revue la configuration vidéo requise pour le client lors de la planification de Skype entreprise Server.
  
Cet article décrit la prise en charge du matériel vidéo pour les appels vidéo Skype entreprise et explique comment déterminer la qualité vidéo attendue pour différentes configurations d’ordinateur, de tablette et d’appareil mobile. 
  
Les professionnels de l’informatique trouveront ces informations utiles pour évaluer la pertinence des ordinateurs portables déjà utilisés dans leur organisation ou en tenant compte de leur utilisation. Ils peuvent également rechercher des informations sur des appareils spécifiques dans le [catalogue de solutions](https://partnersolutions.skypeforbusiness.com/solutionscatalog) .
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Configuration requise et fonctionnalités des ordinateurs de bureau Windows, Mac et tablette

Skype entreprise utilise l’accélération matérielle pour le codage et le décodage vidéo en fonction de la norme de codage vidéo avancée H. 264/MPEG-4 part 10. Cela permet aux ordinateurs ayant des vitesses d’horloge de l’UC moindres de coder et de décoder une vidéo plus haute résolution. La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.
  
Consultez également la [Configuration matérielle requise pour Windows et Mac](https://products.office.com/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Configuration matérielle requise pour la vidéo

|**Fonctionnalité**|**Configuration requise**|
|:-----|:-----|
|Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)  <br/> |• La carte graphique doit prendre en charge DirectX 9,0 et exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT et l’API DirectX 9.  <br/> • Le pilote de carte graphique le plus récent doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : chipset requis  <br/> |Les solutions de codage vidéo avec accélération matérielle Intel suivantes sont prises en charge :  <br/> • Chipsets Intel HD Graphics 2000, 2500, 3000 et 4000 de deuxième et troisième génération (ou versions ultérieures) avec encodeurs vidéo matériel intégrés. L’installation du pilote Intel HD Graphics 15.28.9.2884 ou le pilote le plus récent contenant les éléments suivants sont requis :  <br/> • Pilote d’affichage 9.17.10.2884 ou le pilote le plus récent  <br/> • Hardware Media Foundation Transform (HMFT) version 3.12.10.31 ou le dernier HMFT  <br/> Les solutions de codage vidéo avec accélération matérielle AMD suivantes sont prises en charge :  <br/> • Moteur de codec vidéo AMD, disponible dans plusieurs cartes graphiques discrètes et dans des unités de traitement accélérées intégrées de processeurs accélérés de la série AMD A-Series. Le pilote du moteur de codec vidéo AMD 9.12.0.0 ou une version ultérieure doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : caméra requise  <br/> |Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.  <br/> **Remarque :** Skype entreprise prend en charge les caméras UVC 1,5 avec Windows 8 ou Windows 8,1, qui inclut la prise en charge de UVC 1,5. Étant donné que Windows 7 n’inclut pas la prise en charge de UVC 1,5, Skype entreprise traite les appareils photo UVC 1,5 comme des appareils photo standard sans prise en charge du codage matériel. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Détermination des fonctionnalités de codage et de décodage vidéo H. 264

En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :
  
- Prise en charge du décodage matériel accéléré avec DXVA
    
- Prise en charge de l’encodage matériel accéléré
    
- Nombre de cœurs physiques
    
- Indice de performance Windows (WEI)
    
L’Outil d’évaluation système Windows (WinSAT) détermine l’indice WEI. Quand vous exécutez l’outil WinSAT, il génère un document XML d’évaluation formelle sur l’ordinateur dans le dossier %windir%\Performance\WinSAT\DataStore. Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d’encodage et de décodage :
  
- La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.
    
- La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.
    
Les trois tableaux suivants expliquent les capacités d’encodage et de décodage maximales pour différents types de PC en fonction de l’accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d’images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d’images maximale prise en charge est de 15 i/s.
  
**Ordinateur sans DXVA et sans encodeur matériel accéléré**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Configuration requise**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)  <br/> |1 cœur et VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/A  <br/> |
   
**Ordinateur avec DXVA mais sans encodeur matériel accéléré**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Configuration requise**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 cœur et VideoEncodeScore ≥ 3,0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 cœurs et VideoEncodeScore ≥ 6,0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. Par conséquent, la fonctionnalité de codage pour un ordinateur dépourvu de codeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8,1, où le score WinSAT maximal est de 9,9. 
  
**Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Configuration requise**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Intel HD Graphics deuxième et troisième générations  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Fonctionnalités de vidéo d’appareil mobile

Le tableau suivant décrit la résolution vidéo maximale disponible sur les appareils mobiles pris en charge. Pour plus d’informations sur la prise en charge des appareils mobiles, consultez la rubrique [relative à la fonctionnalité de client mobile pour Skype entreprise](mobile-feature-comparison.md).
  
|**Fonctionnalité**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Résolution maximale de H. 264  <br/> |VGA  <br/> |QVGA : iPhone-n  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et versions ultérieures  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures  <br/> 720p : iPad air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu’à VGA en fonction du modèle d’appareil  <br/> |
|Résolution de décodage maximale H. 264  <br/> |VGA  <br/> |QVGA : iPhone-n  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et versions ultérieures  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et versions ultérieures  <br/> 720p : iPad air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu’à VGA en fonction du modèle d’appareil  <br/> |
   

