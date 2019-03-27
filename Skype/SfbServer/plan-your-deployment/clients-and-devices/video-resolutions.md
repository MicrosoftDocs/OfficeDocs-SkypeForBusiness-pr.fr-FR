---
title: Skype pour la résolution vidéo du client Business
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Résumé : Passez en revue la configuration requise de client vidéo lors de la planification pour Skype pour Business Server.'
ms.openlocfilehash: a17e3e269f24e74c5403c053723d544898560f34
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886689"
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype pour la résolution vidéo du client Business
 
**Résumé :** Passez en revue la configuration requise de client vidéo lors de la planification pour Skype pour Business Server.
  
Cet article décrit la prise en charge du matériel vidéo pour Skype pour les appels vidéo professionnels et explique comment déterminer la qualité vidéo attendue pour différentes ordinateur Tablet PC et configurations de périphérique mobile. 
  
PROFESSIONNELS de l’informatique utiles ces informations pour évaluer l’adéquation des ordinateurs portables déjà en cours d’utilisation dans leur organisation, ou sous le compte à utiliser. Ils peuvent également rechercher le [Catalogue de Solutions](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pour plus d’informations sur des appareils spécifiques.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Bureau Windows, Mac et tablettes exigences vidéo et les capacités

Skype pour les entreprises utilise l’accélération matérielle pour le codage vidéo et de décodage basés sur la norme H.264/MPEG-4 partie 10 Advanced Video Coding. Cela permet aux ordinateurs avec une vitesse d’horloge du processeur pour coder et décoder résolution. La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.
  
Consultez également la [configuration matérielle Windows et Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Configuration requise du matériel vidéo

|**Fonctionnalité**|**Condition requise**|
|:-----|:-----|
|Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)  <br/> |• La carte graphique doit prendre en charge DirectX 9.0 et expose le mode de décodage DXVA2_ModeH264_VLD_NoFGT et l’interface API DirectX 9.  <br/> • Le pilote de carte graphique le plus récent doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : chipset requis  <br/> |Les solutions d’encodage vidéo matériel accéléré Intel suivantes sont prises en charge :  <br/> • Deuxième et troisième génération Intel HD Graphics 2000, 2500, 3000 et 4000 chipsets (ou versions ultérieures) avec encodeurs vidéo matériel intégrés. L’installation du pilote 15.28.9.2884 Intel HD Graphics ou version ultérieure contenant les éléments suivants est requise :  <br/> • Affichage pilote 9.17.10.2884 ou le plus récent  <br/> • Foundation de support matériel transformer version (HMFT) 3.12.10.31 ou le HMFT le plus récent  <br/> Les solutions d’encodage vidéo matériel accéléré AMD suivantes sont prises en charge :  <br/> • Moteur de Codec vidéo AMD, qui est disponible dans plusieurs cartes graphiques et intégrée accéléré unités de traitement de processeurs accéléré de série A AMD. Le pilote de moteur de Codec vidéo AMD 9.12.0.0 ou ultérieure doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : caméra requise  <br/> |Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.  <br/> **Remarque :** Skype pour les entreprises prend en charge les caméras UVC 1,5 avec Windows 8 ou Windows 8.1, qui inclut la prise en charge de 1,5 UVC. Étant donné que Windows 7 n’inclut pas de prise en charge de 1,5 UVC, Skype pour les entreprises traite UVC 1,5 caméras comme caméras régulières avec aucun matériel codage prise en charge. <br/> |
   
### <a name="determining-h264-video-encoding-and-decoding-capabilities"></a>Identification des fonctionnalités d’encodage et de décodage vidéo H.264

En règle générale, quatre facteurs principaux déterminent les capacités d’encodage et de décodage maximales d’une configuration donnée :
  
- Prise en charge du décodage matériel accéléré avec DXVA
    
- Prise en charge de l’encodage matériel accéléré
    
- Nombre de cœurs physiques
    
- Indice de performance Windows (WEI)
    
L’Outil d’évaluation système Windows (WinSAT) détermine l’indice WEI. Quand vous exécutez l’outil WinSAT, il génère un document XML d’évaluation formelle sur l’ordinateur dans le dossier %windir%\Performance\WinSAT\DataStore. Ce fichier XML contient les deux scores suivants qui sont essentiels pour déterminer les capacités d’encodage et de décodage :
  
- La valeur VideoEncodeScore indique la capacité d’encodage vidéo logiciel de l’ordinateur.
    
- La valeur GraphicsScore indique la capacité d’encodage matériel accéléré de l’ordinateur.
    
Les trois tableaux suivants expliquent les capacités d’encodage et de décodage maximales pour différents types de PC en fonction de l’accélération matérielle prise en charge. Pour des résolutions de 640x360 et supérieures, la fréquence d’images maximale prise en charge est de 30 images par secondes (i/s). Pour des résolutions inférieures à 640x360, la fréquence d’images maximale prise en charge est de 15 i/s.
  
**Ordinateur sans DXVA et sans encodeur matériel accéléré**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Condition requise**|
|:-----|:-----|:-----|
|424x240  <br/> |424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)  <br/> |1 cœur et VideoEncodeScore ≥ 4,0  <br/> |
|640x360  <br/> |640x360  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1280x720  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640x360  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|1280x720  <br/> |1280x720  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |N/A  <br/> |
   
**Ordinateur avec DXVA mais sans encodeur matériel accéléré**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Condition requise**|
|:-----|:-----|:-----|
|424x240  <br/> |1920x1080  <br/> |1 cœur et VideoEncodeScore ≥ 3,0  <br/> |
|640x360  <br/> |1920x1080  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|960x540  <br/> |1920x1080  <br/> |2 cœurs et VideoEncodeScore ≥ 6,0  <br/> |
|1280x720  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 6,7  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |4 cœurs et VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. C’est pourquoi la capacité d’encodage d’un ordinateur sans encodeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8.1, pour lequel le score WinSAT est de 9,9 au maximum. 
  
**Ordinateur avec DXVA et avec un encodeur matériel accéléré Intel HD Graphics**

|**Résolution d’encodeur compatible**|**Résolution de décodeur compatible**|**Condition requise**|
|:-----|:-----|:-----|
|1280x720  <br/> |1920x1080  <br/> |Intel HD Graphics deuxième et troisième générations  <br/> |
|1920x1080  <br/> |1920x1080  <br/> |Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Capacité vidéo des appareils mobiles

Le tableau suivant décrit la résolution vidéo maximale disponible sur les appareils mobiles pris en charge. Pour plus d’informations sur la prise en charge de l’appareil mobile, [comparaison des fonctionnalités de client Mobile pour Skype pour les entreprises](mobile-feature-comparison.md).
  
|**Fonctionnalité**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Résolution d’encodage maximale H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et version ultérieure  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu'à VGA en fonction du modèle de périphérique  <br/> |
|Résolution de décodage maximale H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et version ultérieure  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu'à VGA en fonction du modèle de périphérique  <br/> |
   

