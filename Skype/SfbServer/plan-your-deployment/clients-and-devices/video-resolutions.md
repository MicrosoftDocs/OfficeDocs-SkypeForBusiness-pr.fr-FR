---
title: Skype Entreprise résolutions vidéo clientes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Résumé : Examinez la vidéo client requise lors de la planification de Skype Entreprise Server.'
ms.openlocfilehash: 26a47854ac4223a527635111a0c1b25a66d63706
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395066"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype Entreprise résolutions vidéo clientes
 
**Résumé :** Examinez la vidéo client requise lors de la planification de Skype Entreprise Server.
  
Cet article décrit la prise en charge du matériel vidéo pour les appels vidéo Skype Entreprise et explique comment déterminer la qualité vidéo attendue pour différentes configurations d’ordinateur, de tablette et d’appareil mobile. 
  
Les professionnels de l’informatique trouveront ces informations utiles pour évaluer l’aptitude des ordinateurs portables déjà utilisés dans leur organisation, ou à prendre en compte pour une utilisation. Ils peuvent également rechercher des informations [sur des appareils Microsoft Teams sur](https://www.microsoft.com/microsoft-teams/across-devices/device) des appareils spécifiques.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Windows de bureau, Mac et tablettes vidéo requises et fonctionnalités

Skype Entreprise utilise l’accélération matérielle pour le codage et le décodage vidéo basés sur la norme H.264/MPEG-4 Part 10 Advanced Video Coding. Cela permet aux ordinateurs dont la vitesse d’horloge du processeur est inférieure d’encoder et décoder des vidéos de résolution supérieure. La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.
  
Consultez également [Windows configuration matérielle requise pour Mac](https://products.office.com/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Configuration matérielle requise pour la vidéo

|**Fonctionnalité**|**Configuration requise**|
|:-----|:-----|
|Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)  <br/> |• La carte graphique doit prendre en charge DirectX 9.0 et exposer DXVA2_ModeH264_VLD_NoFGT mode décodage et l’API DirectX 9.  <br/> • Le dernier pilote de carte graphique doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : chipset requis  <br/> |Les solutions d’encodage vidéo matériel accéléré Intel suivantes sont pris en charge :  <br/> • Puces Intel HD Graphics 2000, 2500, 3000 et 4000 de deuxième et troisième générations (ou versions ultérieures) avec des encodeurs vidéo matériels intégrés. L’installation du pilote Intel HD Graphics 15.28.9.2884 ou du pilote le plus récent contenant les éléments suivants est requise :  <br/> • Pilote d’affichage 9.17.10.2884 ou pilote le plus récent  <br/> • HMFT (Hardware Media Foundation Transform) version 3.12.10.31 ou la dernière version HMFT  <br/> Les solutions d’encodage vidéo matériel accéléré AMD suivantes sont pris en charge :  <br/> • Moteur de codec vidéo AMD, disponible dans plusieurs cartes graphiques discrètes et dans les unités de traitement accéléré intégrées des processeurs accélérés AMD A-Series. Le pilote AMD Video Codec Engine 9.12.0.0 ou supérieur doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : caméra requise  <br/> |Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.  <br/> **Remarque :** Skype Entreprise prend en charge les caméras UVC 1.5 avec Windows 8 ou Windows 8.1, qui inclut la prise en charge d’UVC 1.5. Comme Windows 7 n’inclut pas la prise en charge d’UVC 1.5, Skype Entreprise traite les caméras UVC 1.5 comme des caméras normales sans prise en charge du codage matériel. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Détermination des fonctionnalités de codage et de décodage vidéo H.264

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
|424 x 240  <br/> |424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)  <br/> |1 cœur et VideoEncodeScore ≥ 4,0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |4 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |S/O  <br/> |
   
**Ordinateur avec DXVA mais sans encodeur matériel accéléré**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Configuration requise**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080  <br/> |1 cœur et VideoEncodeScore ≥ 3,0  <br/> |
|640 x 360  <br/> |1920 x 1080  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|960 x 540  <br/> |1920 x 1080  <br/> |2 cœurs et VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920 x 1080  <br/> |4 cœurs et VideoEncodeScore ≥ 6,7  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |4 cœurs et VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. Par conséquent, la fonctionnalité de codage d’un ordinateur sans encodeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8.1, où le score WinSAT maximal est de 9,9. 
  
**Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Configuration requise**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080  <br/> |Intel HD Graphics deuxième et troisième générations  <br/> |
|1920 x 1080  <br/> |1920 x 1080  <br/> |Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Fonctionnalités vidéo d’appareil mobile

Le tableau suivant décrit les résolutions vidéo maximales disponibles sur les appareils mobiles pris en charge. Pour plus d’informations sur la prise en charge des appareils mobiles, [comparaison des fonctionnalités du client mobile pour Skype Entreprise](mobile-feature-comparison.md).
  
|**Fonctionnalité**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Résolution maximale d’encodage H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et ultérieures  <br/> |VGA : iPad 2 et ultérieures/iPad mini 1 et ultérieures  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et ultérieures  <br/> |Jusqu’à VGA en fonction du modèle d’appareil  <br/> |
|Résolution maximale de décodage H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et ultérieures  <br/> |VGA : iPad 2 et ultérieures/iPad mini 1 et ultérieures  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et ultérieures  <br/> |Jusqu’à VGA en fonction du modèle d’appareil  <br/> |
   

