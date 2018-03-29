---
title: Skype pour les résolutions vidéo du client entreprise
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 8f68f4c2-3194-487c-bd2f-fbe71ba8ad70
description: 'Résumé : Passez en revue les exigences vidéo client lors de la planification pour Skype pour Business Server 2015.'
ms.openlocfilehash: fea2ae1aaa0e75248f9b1102bdfd9ebd5d03afb5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-client-video-resolutions"></a>Skype pour les résolutions vidéo du client entreprise
 
**Résumé :** Passez en revue les exigences vidéo client lors de la planification pour Skype pour Business Server 2015.
  
Cet article décrit la prise en charge de matériel vidéo de Skype pour les appels vidéo professionnels et explique comment déterminer la qualité vidéo attendue pour divers ordinateur Tablet PC et configurations des appareils mobiles. 
  
Professionnels de l’informatique utiles cette information pour évaluer l’adéquation des ordinateurs portables en cours d’utilisation dans leur organisation, ou envisagées pour utilisation. Ils peuvent également rechercher le [Catalogue des Solutions](https://partnersolutions.skypeforbusiness.com/solutionscatalog) pour plus d’informations sur des périphériques spécifiques.
  
## <a name="windows-desktop-mac-and-tablet-video-requirements-and-capabilities"></a>Bureau de Windows, les besoins de vidéo Mac et les Tablet PC et les capacités

Skype pour entreprise utilise l’accélération matérielle de vidéo de codage et de décodage basés sur la norme H.264/MPEG-4 partie 10 avancée codage vidéo. Ceci permet aux ordinateurs avec une vitesse d’horloge du processeur pour coder et décoder la vidéo de résolution supérieure. La configuration requise pour le matériel vidéo dépend de la configuration de l’ordinateur et de la résolution vidéo souhaitée.
  
Consultez également [requise pour Windows et Mac](https://products.office.com/en-us/office-system-requirements).
  
### <a name="video-hardware-requirements"></a>Configuration requise du matériel vidéo

|**Fonctionnalité**|**Exigence**|
|:-----|:-----|
|Décodage matériel accéléré H.264 à l’aide de l’accélération vidéo DirectX (DXVA)  <br/> |• Carte de graphique doit prendre en charge les DirectX 9.0 et expose le mode de décodage de DXVA2_ModeH264_VLD_NoFGT et de l’API de 9 DirectX.  <br/> • Le dernier pilote de carte graphique doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : chipset requis  <br/> |Les solutions d’encodage vidéo matériel accéléré Intel suivantes sont prises en charge :  <br/> • Les chipsets graphiques 2000, 2500, 3000, 4000 et deuxième et de troisième génération Intel HD (ou versions ultérieures) avec les codeurs vidéo intégré de matériel. L’installation du pilote 15.28.9.2884 Intel HD Graphics ou version ultérieure contenant les éléments suivants est requise :  <br/> • Le pilote d’affichage 9.17.10.2884 ou le pilote le plus récent  <br/> • Base de support matériel transformer le version (HMFT) 3.12.10.31 ou la dernière HMFT  <br/> Les solutions d’encodage vidéo matériel accéléré AMD suivantes sont prises en charge :  <br/> • Moteur de Codec vidéo AMD, qui est disponible dans plusieurs cartes graphiques séparées et intégrée accéléré des unités de traitement de processeurs, AMD série A accéléré. Le pilote de moteur de Codec vidéo AMD 9.12.0.0 ou ultérieure doit être installé.  <br/> |
|Encodage matériel accéléré H.264 : caméra requise  <br/> |Caméras vidéo USB avec encodeur matériel H.264 intégré conforme à la spécification USB Video Class (UVC) version 1.5.  <br/> **Remarque :** Skype pour entreprise prend en charge les caméras UVC 1.5 avec Windows 8 ou Windows 8.1, qui prend en charge UVC 1.5. Car Windows 7 n’inclut pas de prise en charge de UVC 1.5, Skype pour entreprise traite UVC 1.5 caméras comme des caméras régulières avec aucun codage prise en charge de matériel. <br/> |
   
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
  
**Ordinateur sans DXVA et sans matériel accéléré de codeur**

|**Résolution du codeur capable**|**Résolution du décodeur capable**|**Exigence**|
|:-----|:-----|:-----|
|424 x 240  <br/> |424x240 (640x360 à 15 i/s pour des scénarios de réception uniquement)  <br/> |1 cœur et VideoEncodeScore ≥ 4,0  <br/> |
|640 x 360  <br/> |640 x 360  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1280 x 720  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|640 x 360  <br/> |1920 x 1080.  <br/> |4 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|1280 x 720  <br/> |1280 x 720  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1280 x 720  <br/> |1920 x 1080.  <br/> |4 cœurs et VideoEncodeScore ≥ 7,3  <br/> |
|1920 x 1080.  <br/> |1920 x 1080.  <br/> |N/A  <br/> |
   
**Ordinateur avec DXVA mais sans matériel accéléré de codeur**

|**Résolution du codeur capable**|**Résolution du décodeur capable**|**Exigence**|
|:-----|:-----|:-----|
|424 x 240  <br/> |1920 x 1080.  <br/> |1 cœur et VideoEncodeScore ≥ 3,0  <br/> |
|640 x 360  <br/> |1920 x 1080.  <br/> |2 cœurs et VideoEncodeScore ≥ 4,5  <br/> |
|960 x 540  <br/> |1920 x 1080.  <br/> |2 cœurs et VideoEncodeScore ≥ 6,0  <br/> |
|1280 x 720  <br/> |1920 x 1080.  <br/> |4 cœurs et VideoEncodeScore ≥ 6,7  <br/> |
|1920 x 1080.  <br/> |1920 x 1080.  <br/> |4 cœurs et VideoEncodeScore ≥ 8,2  <br/> |
   
> [!NOTE]
> Le score WinSAT sur Windows 7 est limité à un maximum de 7,9. C’est pourquoi la capacité d’encodage d’un ordinateur sans encodeur matériel accéléré ne peut être obtenue que sur Windows 8 ou Windows 8.1, pour lequel le score WinSAT est de 9,9 au maximum. 
  
**Ordinateur avec DXVA et Intel HD graphique matériel accéléré de codeur**

|**Résolution du codeur capable**|**Résolution du décodeur capable**|**Exigence**|
|:-----|:-----|:-----|
|1280 x 720  <br/> |1920 x 1080.  <br/> |Intel HD Graphics deuxième et troisième générations  <br/> |
|1920 x 1080.  <br/> |1920 x 1080.  <br/> |Intel HD Graphics deuxième et troisième générations avec GraphicsScore ≥ 5,0  <br/> |
   
## <a name="mobile-device-video-capabilities"></a>Capacité vidéo des appareils mobiles

Le tableau suivant décrit la résolution vidéo maximale disponible sur les périphériques mobiles pris en charge. Pour plus d’informations sur la prise en charge de périphériques mobiles, [comparaison des fonctionnalités de client Mobile de Skype pour les entreprises](mobile-feature-comparison.md).
  
|**Fonctionnalité**|**Windows Phone**|**iPhone**|**iPad**|**Android**|
|:-----|:-----|:-----|:-----|:-----|
|Résolution d’encodage maximale H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et version ultérieure  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu'à VGA en fonction du modèle de périphérique  <br/> |
|Résolution de décodage maximale H.264  <br/> |VGA  <br/> |QVGA : iPhone 4S  <br/> VGA : iPhone 5  <br/> 720p : iPhone 5S et version ultérieure  <br/> |VGA : iPad 2 et version ultérieure/iPad mini 1 et version ultérieure  <br/> 720p : iPad Air/iPad mini 2/iPad Pro et version ultérieure  <br/> |Jusqu'à VGA en fonction du modèle de périphérique  <br/> |
   

