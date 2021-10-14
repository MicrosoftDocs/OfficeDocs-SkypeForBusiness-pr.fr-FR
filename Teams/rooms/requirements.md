---
title: Spécifications des salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Découvrez les conditions requises pour la prise en charge Salles Microsoft Teams, notamment le choix du périphérique, des microphones, des haut-parleurs, des caméras et de l’affichage appropriés.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b0cd552a743df29cc16ca40df2ebe6e48dda95fe
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356462"
---
# <a name="microsoft-teams-rooms-requirements"></a>Spécifications des salles Microsoft Teams

Salles Microsoft Teams plusieurs tailles de pièce. salles Teams utiliser un large éventail de périphériques audio et vidéo certifiés en fonction de la taille et de l’utilisation de la salle. En sélectionnant le périphérique et la console principaux appropriés, combinés avec des microphones, des haut-parleurs, des caméras et des écrans appropriés à l’espace, vous pouvez déployer Salles Microsoft Teams dans des espaces de n’importe quelle taille, des petits espaces de conférence jusqu’aux grands espaces de conférence et aux salles de conférence.  L’ensemble des périphériques audio et vidéo certifiés disponibles pour configurer votre salle est disponible dans la [Galerie d’appareils](https://products.office.com/microsoft-teams/across-devices).

Cet article résume la configuration requise pour le déploiement et la configuration des appareils pour la prise en charge des salles Microsoft Teams.

Votre déploiement nécessite la création d’un compte comme décrit dans [Déployer les salles Microsoft Teams](rooms-deploy.md) et configurer les consoles de réunion, comme décrit dans [Configurer une console des salles Microsoft Teams](console.md).

Reportez-vous à :

- [Licences de complément Skype Entreprise](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Options de licence en fonction de votre offre : Salles Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Les salles Microsoft Teams se connectent à Microsoft Teams, Skype Entreprise Server 2019, Skype Entreprise Server 2015 ou Skype Entreprise Online, et peuvent participer à des réunions hébergées par l’un de ces services.
>
> Les plateformes antérieures telles que Lync Server 2013 ne sont pas prises en charge par les salles Microsoft Teams. Salles Microsoft Teams n’est pas pris en charge dans Microsoft 365 ou Office 365 les environnements 21Vianet ou DoD.
>
> Si vous avez un serveur Exchange local, les salles Microsoft Teams nécessitent l’utilisation d’Exchange Server 2013 SP1 ou d’une version ultérieure.

## <a name="hardware-requirements"></a>Configuration matérielle minimale requise
Un déploiement de matériel inclut une sélection d’un système de salle Microsoft Teams, combiné avec des périphériques audio et vidéo certifiés, ainsi qu'une solution de câblage permettant d'intégrer ces dispositifs entre eux.  Ces options sont décrites ici.

**Systèmes de salle Microsoft Teams pris en charge**

Tous les appareils et offres groupées actuels de salle Microsoft Teams sont disponibles dans la [Vitrine de produits des systèmes de salle de réunion](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processeur|Mémoire RAM|Disque|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC- B130-T avec Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC-B140-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 Go |128 Go |
  [Crestron Flex UC-C140-T with Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 Go |128 Go|
  |[Crestron Flex UC-M150-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  +  [CCS-NT-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 Go |128 Go |
  |[Crestron Flex UC-MX150-T with Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 Go |128 Go |
   [Crestron Flex UC-B160-T with Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 Go |128 Go|
  |[Crestron Flex UC-C160-T avec Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 Go|128 Go|
  |[Crestron Flex UC-MMX30-T avec UC Presentation Presentation (UC-PR) et ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC-BX30-T avec UC Presentation Presentation (UC-PR) et ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC-CX100-T avec UC Presentation Presentation (UC-PR) et ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC-B30-T avec ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5|8 Go |128 Go |
   |[Crestron Flex UC-C100-T avec ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5|8 Go |128 Go |
   |[Crestron Flex UC-M50-T avec ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5|8 Go |128 Go |
   |[Crestron Flex UC-M70-T avec ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5|8 Go |128 Go |
   |[Crestron Flex UC-MX50-T avec ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5|8 Go |128 Go |
   |[Crestron Flex UC-MX70-T avec ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5|8 Go |128 Go |
  |[Crestron Mercure Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 Go |128 Go |
  |[Dell OptiPlex 7080 avec Logitech TAP](https://www.dell.com/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 Go |128 Go|
  |Dell OptiPlex 7080 Compute avec Poly GC8 Console | Core i5 |8 Go |128 Go|
  |[HP Elite Slice pour salles de réunion G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 Go |128 Go |
  |[Élément audio HP Elite G2 prêt avec les Salles Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 Go |128 Go |
  |[Partenaire Secteur HP prêt avec Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 Go|128 Go| 
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 Go |128 Go |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 Go |128 Go|
  |Lenovo ThinkSmart Core Kit |Core i5|8 Go|128 Go|
  |[Logitech Tap with Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 Go |128 Go |
  |Logitech Tap and Intel Tiger Canyon NUC PC |Core i5|8 Go|128 Go|
  |[Logitech Tap et Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 Go |128 Go|
  |[Poly G10-T avec Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 Go | 128 Go|
  |[Yealink MVC300 avec Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 Go |128 Go |
  |[Yealink MVC500 with Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 Go |128 Go |
  |[Yealink MVC800 avec Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 Go|128 Go|
  |[Yealink MVC900 with Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 Go|128 Go|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 Go | 128 Go|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 Go | 128 Go|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 Go | 128 Go|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 Go | 128 Go|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 Go | 128 Go|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 Go | 128 Go|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 Go | 128 Go|
  |Yealink MVC660|Core i5|8 Go | 128 Go|
  |Yealink MVC640|Core i5|8 Go | 128 Go|
  |Yealink MVC320|Core i5|8 Go | 128 Go|
  
  
> [!NOTE]
> - Les processeurs Core M3 ne sont pas pris en charge.
> - Vous avez besoin d’un lecteur USB de 32 Go ou plus, configuré comme support d’installation Windows 10 amorçable pour Windows 10 Entreprise.

**Tablettes Surface Pro prises en charge pour les systèmes de style d’amarrage**

  |Tablet|Processeur|Mémoire RAM|Disque|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 Go ou 8 Go |128 Go ou plus |
  |Surface Pro </br>(5e génération) |Core i5 |8 Go ou 4 Go |128 Go ou plus |
  |Surface Pro 4 |Core i5 |8 Go ou 4 Go |128 Go ou plus |

- Surface Pro l’une des options de station d’accueil suivantes est nécessaire pour les appareils :

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versions de microprogramme certifiées pour les périphériques audio et vidéo USB

Ces appareils sont disponibles dans la [Vitrine de produits d'accessoires pour le système de salle de bains](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) et [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Périphériques des Salles Microsoft Teams|Version du micrologiciel certifiée | L'appareil photo prend en charge le contenu de l'utilisation de l'appareil photo|
|:--- |:--- | :--- |
|[Aver VC520 Pro Camera + SpeakerPhone](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Système de conférence Aver VC520 PRO2](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Aver VB342+ Barre son de la caméra](https://www.averusa.com/products/conference-camera/vb342plus) | Barre son : 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7400.03 |
|[Aver VB130 Camera Soundbar](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Hub de conférence Biamp Devio SCR-20CX Web-Based avec microphone plafond](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Hub de conférence Biamp Devio SCR-20TX Web-Based avec microphone tabletop](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Bldly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Iqdly](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Appareil photo IQ bldly](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Jabra Journalcast3 Appareil photo](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Barre vidéo JabraCast 50](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|1.9.3|
|[Lenovo ThinkSmart Cam Camera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   |  8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Cat Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Cat Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio : 1.0.172 <br/> Vidéo : 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   |  1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva00](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Appareil-photo Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   |  1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[PolySoin C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Poly Studio P15 Video Bar](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[MONDES SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[SDES SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[MONDES SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[DONT LE SP30T EST EN COURS](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[MICS Développer 80T + 2 Extension](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Téléphone portable — 4.6.55 <br/> Extension Mic — 0.2.314|
|[DONT LESS développent la capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[YealinkTEXTC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[YealinkTEXTC40 All-in-one Video bar](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/products/mixers/p300)+</br></br> [Micro de table Shure MXA 310 ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 avec micro de matrice de plafond Intellimix](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/products/mixers/p300)+</br></br> [Mic de matrice de tableau MXA 310 De Shure ](https://www.shure.com/products/microphones/mxa310) +</br></br> [Haut-parleur de plafond MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP : 4.1.11 </br> MXA310 Table Array mic: 4.1.41 </br> Haut-parleur MXN5W-C : 1.0.4 |
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/products/mixers/p300) + </br></br> [Shure MXA 910 avec le micro du tableau de plafond Intellimix](https://www.shure.com/products/microphones/mxa910) +</br></br> [Haut-parleur de plafond MXN5W-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP : 4.1.11 </br> MXA910 Ceiling Array mic: 4.1.41 </br> Haut-parleur MXN5W-C : 1.0.4 |
|[Microphone de tableau linéaire MXA 710 MXA 2ft](https://www.shure.com/products/microphones/mxa710) + </br></br> [Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/products/mixers/p300) +</br></br> [Haut-parleur de plafond MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP : 4.4.8 </br> Haut-parleur MXN5-C : 1.1.1 |
|[Microphone de tableau linéaire wallé MXA 710 4ft](https://www.shure.com/products/microphones/mxa710) + </br></br> [Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/products/mixers/p300) +</br></br> [Haut-parleur de plafond MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP : 4.4.8 </br> Haut-parleur MXN5-C : 1.1.1 |
|[Shure MXA 910 avec microphone de tableau de plafond Intellimix](https://www.shure.com/products/microphones/mxa910) + </br> [Logiciel de salle Shure Intellimix](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Logiciel de salle Shure Intellimix : 3.0.4.14 </br> Shure MXA 910 avec microphone de tableau de plafond Intellimix : 4.4.11 </br> Plusieurs haut-parleurs MXN5-C : 1.2.1 </br> Crestron UC-C100-T : version du système d’exploitation IOT 19h2/20h2 avec la version de l’application MTR 4.8.31.0 </br> BIOS : ASUS Tek Computer INC 9934 27/08/2020 </br> UC : i5-9500TCPU </br> Mémoire physique : 8 Go de RAM |
|[Biamp Tesira premier plan AVB VT4 DSP audio fixe](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Microphone Sennheiser TeamConnect Ceiling 2](https://sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Micro de plafond Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Biamp Desono C-IC6 ceiling mounted loudspeaker](https://www.biamp.com/products/tesira-speakers)| Audio FW version : 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(Micro tableau)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UETT]() |Audio FW version : 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Amplificateur Bose P2600A AmpLink +</br> Microphone Sennheiser TCC2 Ceiling + </br> Haut-parleur Bose EdgeMax EM180 Ceiling](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink Amplifier + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier +</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Haut-parleur DesignMax DM2C -LP Ceiling](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Haut-parleur de plafond EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |
|QSC Q-SYS Core[(110f,](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/) [8 Flex,](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/) [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/)ou [NV-32-H)](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)+ </br> [Sennheiser TCC2 Ceiling Microphone](https://en-us.sennheiser.com/tcc2) + </br> QSC Amplifier[(série SPA](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) ou [série CX-Q)](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)+ </br> [Haut-parleurs de série QSC AcousticDesign](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> Caméra IP QSC[(PTZ-IP 20x60,](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/) [PTZ-IP 12x72)](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)facultatif + </br> [Pont USB QSC Q-SYS I/O](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) facultatif | QSC Q-SYS Core, caméra PTZ-IP et pont USB I/O : QSC Q-SYS Designer 9.0.1-2104.022 </br> Sennheiser TCC2 Ceiling Microphone: TCC2 - 1.5.1, Dante 1.2.0 </br> Amplifiers QSC : N/A </br> Haut-parleurs de la série QSC AcousticDesign : N/A | 


&Dagger; Les clients peuvent choisir l’interface Dante ou le commutateur réseau recommandé par biamp/Sennheiser pour cette offre groupée.

#### <a name="usb-extenders"></a>Extensions USB

- Les ports USB sur les stations d’accueil de tablettes sont compatibles USB 3.0. Vous pouvez utiliser une extension USB 2.x, mais cela vous limite aux vitesses USB 2.x à l'extrémité. Les extensions ne sont pas recommandées pour les périphériques USB 3.0.
- Une extension doit répondre aux spécifications USB 2.0 ou plus récentes.
  - Les stations d’accueil de tablette prennent en charge au moins deux phases d’extension de concentrateur USB externe. Si vous connectez plus de deux concentrateurs USB en série, contactez le fabricant de la station d’accueil pour confirmer qu’il prend en charge la connexion en série.
  - Connexion GbE dans la salle. Câble Ethernet de longueur adéquate
  - Jusqu’à deux écrans 1080 pixels avec connexions HDMI. Câbles HDMI de la longueur appropriée.

> [!NOTE]
> Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille. Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs.
>
> Les salles Microsoft Teams n’utilisent pas de clavier. Si nécessaire, l’administrateur doit utiliser le clavier visuel. Un clavier ou une souris USB sera nécessaire lors de la création de l’image de l’appareil des salles Microsoft Teams.

Les tableaux suivants fournissent des recommandations pour les périphériques basés sur la taille de la salle :

**Périphériques audio certifiés des salles Microsoft Teams**

|Type de salle|Nombre de personnes|Distance maximale recommandée entre le microphone et le haut-parleur|
|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'   |2 à 4  |1,5 m  |
|**Small** <br/> 16' x 16'  |4 à 6  |2,0 m  |
|**Moyen** <br/> 18' x 20'  |6 à 12  |2,4 m  |
|**Large** <br/> 15' x 32'  |12 à 16  |3 m <br/> Cette distance s’applique également à la zone couverte par chaque microphone satellitaire connecté.  |

**Périphériques vidéo certifiés des salles Microsoft Teams**

|Type de salle|Nombre de personnes|
|:-----|:-----|
|**Focus** <br/> 10' x 9'  |2 à 4  |
|**Small** <br/> 16' x 16'  |4 à 6  |
|**Moyen** <br/> 18' x 20'  |6 à 12  |
|**Large** <br/> 15' x 32'  |12 à 16  |

 > [!NOTE]
 > La résolution de l'écran à l’avant de la salle doit être définie pour ne pas être supérieure à 1920 x 1080 pixels.

## <a name="required-software-downloads"></a>Téléchargement des logiciels requis

Pour créer votre propre image de salles Microsoft Teams, suivez les instructions dans [Configurer une console de salle Microsoft Teams](console.md). Ces instructions vous guident tout au long du processus de téléchargement de tous les logiciels nécessaires à l’installation.

> [!NOTE]
> Les professionnels de l’informatique ont besoin d’accéder aux fichiers ISO Windows 10 Entreprise à l’aide de leur contrat de licence en volume.

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) est un téléchargement facultatif que vous pouvez utiliser pour configurer les comptes des salles Microsoft Teams.

## <a name="see-also"></a>Voir aussi

[Parcourir toutes les offres](https://products.office.com/microsoft-teams/across-devices/devices)

[Planifier les Salles Microsoft Teams](rooms-plan.md)

[Déployer les Salles Microsoft Teams](rooms-deploy.md)

[Configurer une console des salles Microsoft Teams](console.md)

[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Licences de complément Skype Entreprise](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
