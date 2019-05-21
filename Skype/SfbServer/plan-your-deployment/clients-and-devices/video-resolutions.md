---
title: Résolutions vidéo sur le client Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Résumé: passez en revue la configuration requise pour la vidéo client lors de la planification de Skype entreprise Server.'
ms.openlocfilehash: 15fd424f7ad2e11d473e49e271c7fbf1db83b45c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277278"
---
# <a name="skype-for-business-client-video-resolutions"></a>Résolutions vidéo sur le client Skype entreprise
 
**Résumé:** Passez en revue la configuration requise pour la vidéo client lors de la planification de Skype entreprise Server.
  
Cet article décrit la prise en charge de matériel vidéo pour les appels vidéo Skype entreprise et explique comment déterminer la qualité vidéo prévue pour différentes configurations d’ordinateur, de tablette et d’appareil mobile. 
  
Ces informations peuvent être utiles pour les professionnels de l’informatique pour évaluer la pertinence des ordinateurs portables déjà utilisés au sein de leur organisation ou en considération. Ils peuvent également rechercher des informations sur des appareils spécifiques dans le [catalogue de solutions](https://partnersolutions.skypeforbusiness.com/solutionscatalog) .
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Configurations et capacités requises pour les ordinateurs de bureau Windows, Mac et tablette

Skype entreprise utilise l’accélération matérielle pour le codage et le décodage vidéo en fonction de la norme de codage vidéo avancée H. 264/MPEG-4 partie 10. Cela permet aux ordinateurs dotés de basses vitesses d’horloge pour encoder et décoder une vidéo de résolution supérieure. La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.
  
Voir également [Configuration matérielle requise pour Windows et Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Configuration requise du matériel vidéo

|**Fonctionnalité**|**Condition requise**|
|:-----|:-----|
|Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)  <br/> |• La carte graphique doit prendre en charge DirectX 9,0 et doit exposer le mode de décodage DXVA2_ModeH264_VLD_NoFGT et l’API DirectX 9.  <br/> • Le pilote le plus récent pour la carte graphique doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : chipset requis  <br/> |Les solutions d’encodage vidéo matériel accéléré Intel suivantes sont prises en charge :  <br/> • Chipsets Intel HD 2000, 2500, 3000 et 4000 de deuxième et troisième génération (ou versions ultérieures) avec encodeurs vidéo intégrés. L’installation du pilote 15.28.9.2884 Intel HD Graphics ou version ultérieure contenant les éléments suivants est requise :  <br/> • Pilote d’affichage 9.17.10.2884 ou le pilote le plus récent  <br/> • Hardware Media Foundation transformation (HMFT) version 3.12.10.31 ou le dernier HMFT  <br/> Les solutions d’encodage vidéo matériel accéléré AMD suivantes sont prises en charge :  <br/> • Moteur de codec vidéo AMD, qui est disponible dans plusieurs cartes graphiques discrètes et dans les unités de traitement intégrées accélérées de processeurs de la série AGP. Le pilote du moteur du codec vidéo AMD 9.12.0.0 ou une version ultérieure doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : caméra requise  <br/> |Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.  <br/> **Remarque:** Skype entreprise prend en charge les UVC 1,5 avec Windows 8 ou Windows 8,1, qui incluent la prise en charge de UVC 1,5. Dans la mesure où Windows 7 n’inclut pas la prise en charge de UVC 1,5, Skype entreprise traite les caméras UVC 1,5 comme des caméras normales sans prise en charge du codage matériel. <br/> |
   
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

Le tableau suivant décrit les résolutions vidéo maximum disponibles sur les appareils mobiles pris en charge. Pour plus d’informations sur la prise en charge des appareils mobiles, voir [comparaison des fonctionnalités des clients mobiles pour Skype entreprise](mobile-feature-comparison.md).
  
|**Fonctionnalité**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Résolution d’encodage maximale H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et version ultérieure  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu’à VGA en fonction du modèle d’appareil  <br/> |
|Résolution de décodage maximale H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et version ultérieure  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu’à VGA en fonction du modèle d’appareil  <br/> |
   

