---
title: Spécifications des salles Microsoft Teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: En savoir plus sur la configuration requise pour la prise en charge des salles de Microsoft Teams, notamment le choix de l’appareil, des microphones, des haut-parleurs, des caméras et des écrans appropriés.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 554ce35c640b97c0deb9291e6c797b9302bee50c
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576936"
---
# <a name="microsoft-teams-rooms-requirements"></a>Spécifications des salles Microsoft Teams

Les salles Microsoft Teams s’adaptent à différentes tailles de pièces en utilisant une grande variété de périphériques audio et vidéo certifiés en fonction de la taille et de l’utilisation de la salle. En sélectionnant l’appareil et la console appropriés, ainsi que les micros, haut-parleurs, appareils photo et affichages appropriés, vous pouvez déployer les salles Microsoft Teams dans des espaces de toute taille, à partir de Huddle et de salles de conférence de grande taille.  L’ensemble des périphériques audio et vidéo certifiés disponibles pour configurer votre salle est disponible dans la [Galerie d’appareils](https://products.office.com/microsoft-teams/across-devices).

Cet article résume la configuration requise pour le déploiement et la configuration des appareils pour la prise en charge des salles Microsoft Teams.

Votre déploiement nécessite la création d’un compte comme décrit dans [Déployer les salles Microsoft Teams](rooms-deploy.md) et configurer les consoles de réunion, comme décrit dans [Configurer une console des salles Microsoft Teams](console.md).

Voir aussi :

- [Licences de complément Skype Entreprise](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Options de licence en fonction de votre offre : Salles Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Les salles Microsoft Teams se connectent à Microsoft Teams, Skype Entreprise Server 2019, Skype Entreprise Server 2015 ou Skype Entreprise Online, et peuvent participer à des réunions hébergées par l’un de ces services.
>
> Les plateformes antérieures telles que Lync Server 2013 ne sont pas prises en charge par les salles Microsoft Teams. Les salles de Microsoft Teams ne sont pas prises en charge dans Microsoft 365 ou Office 365 géré par 21Vianet ou dans les environnements GCC-High ou DoD.
>
> Si vous avez un serveur Exchange local, les salles Microsoft Teams nécessitent l’utilisation d’Exchange Server 2013 SP1 ou d’une version ultérieure.

## <a name="hardware-requirements"></a>Configuration matérielle minimale requise
Un déploiement de matériel inclut une sélection d’un système de salle Microsoft Teams, combiné avec des périphériques audio et vidéo certifiés, ainsi qu'une solution de câblage permettant d'intégrer ces dispositifs entre eux.  Ces options sont décrites ici.

**Systèmes de salle Microsoft Teams pris en charge**

Tous les appareils et offres groupées actuels de salle Microsoft Teams sont disponibles dans la [Vitrine de produits des systèmes de salle de réunion](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processeur|Mémoire RAM|Disque|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC- B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 Go |128 Go |
  |[Crestron Flex UC-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 Go |128 Go |
  [UC Crestron Flex-C140-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 Go |128 Go|
  |[Crestron Flex UC-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 Go |128 Go |
  |[UC Crestron Flex-MX150-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 Go |128 Go |
   [Crestron Flex UC-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 Go |128 Go|
  |[Crestron Flex UC-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 Go|128 Go|
  |[HP Elite Slice pour salles de réunion G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 Go |128 Go |
  |[Élément audio HP Elite G2 prêt avec les Salles Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 Go |128 Go |
  |[Partenariat HP Slice prêt avec Logitech appuyé]( https://www.logitech.com/en-us/video-collaboration/partners/hp.html)|Core i5|8 Go|128 Go|
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 Go |128 Go |
  |[Logitech TAP avec Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 Go |128 Go |
  |[Le centre de réflexion Logitech et le centre de M920 Tiny](https://www.logitech.com/en-us/video-collaboration/partners/lenovo.html)|Core i5|8 Go |128 Go|
  |[Yealink MVC300 avec Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 Go |128 Go |
  |[Yealink MVC500 avec Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 Go |128 Go |
  |[Yealink MVC800 avec Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 Go|128 Go|
  |[Yealink MVC900 avec Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 Go|128 Go|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 Go | 128 Go|
  [Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 Go | 128 Go|
  [Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 Go | 128 Go|
  [Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 Go | 128 Go|
  ||||||

> [!NOTE]
> - Les processeurs Core M3 ne sont pas pris en charge.
> - Vous avez besoin d’un lecteur USB de 32 Go ou plus, configuré comme support d’installation Windows 10 amorçable pour Windows 10 Entreprise.

**Tablettes Surface Pro prises en charge pour les systèmes de style d’amarrage**

  |Tablet|Processeur|Mémoire RAM|Disque|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 Go ou 8 Go |128 Go ou plus |
  |Surface Pro </br>(5e génération) |Core i5 |8 Go ou 4 Go |128 Go ou plus |
  |Surface Pro 4 |Core i5 |8 Go ou 4 Go |128 Go ou plus |

- Les appareils surface Pro nécessitent une des options de la station d’accueil suivantes :

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versions de microprogramme certifiées pour les périphériques audio et vidéo USB

Ces appareils sont disponibles dans la [Vitrine de produits d'accessoires pour le système de salle de bains](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) et [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Périphériques des Salles Microsoft Teams|Version du micrologiciel certifiée | L'appareil photo prend en charge le contenu de l'utilisation de l'appareil photo|
|:--- |:--- | :--- |
|[Avereuse 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Toile Huddly](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Caméra Jabra Panacast](https://www.jabra.com/business/video-conferencing/jabra-panacast)|3.8.22|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   |  8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio : 1.0.172 <br/> Vidéo : 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   |  1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Appareil-photo Poly Eagle Eye Cube](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   |  1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Micro de table Shure MXA 310 ](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 avec micro de matrice de plafond Intellimix](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Biamp Tesira premier plan AVB VT4 DSP audio fixe](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Microphone Sennheiser TeamConnect Ceiling 2](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2: 1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 son DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp parlé TCM-microphone au plafond XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Haut-parleur biamp Desono C-IC6 plafond](https://www.biamp.com/products/tesira-speakers)| Version de microcontrôle audio : 3,15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X (MIC)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Version de microcontrôle audio : 3,15|
|[Bose ControlSpace EX-440C DSP + </br>Amplificateur Bose P2600A AmpLink +</br> Microphone Sennheiser TCC2 Ceiling + </br> Haut-parleur Bose EdgeMax EM180 Ceiling](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink + Sennheiser TCC2 micro + </br> Bose DesignMax DM2C-P plafond](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
||||||



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

|Type de salle|Nombre de personnes|Distance maximale recommandée entre le microphone et le haut-parleur|Appareil par taille de salle maximum|Commentaires|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'   |2 à 4  |1,5 m  |Logitech Connect  |Les appareils Logitech Connect comprennent une caméra. Ils doivent donc être placés à l’avant de la salle (pas au centre de la table) pour capturer les participants locaux à la réunion. |
|**Small** <br/> 16' x 16'  |4 à 6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |Le volume de lecture peut être limité pour des salles plus grandes.  |
|**Moyen** <br/> 18' x 20'  |6 à 12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Les périphériques Logitech MeetUp comprennent une caméra. Ils doivent donc être placés à l’avant de la salle (pas au centre de la table) pour capturer les participants locaux à la réunion. <br/> En général, les salles avec des tables longues ou en U peuvent bénéficier de microphones satellitaires. <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  |
|**Large** <br/> 15' x 32'  |12 à 16  |3 m <br/> Cette distance s’applique également à la zone couverte par chaque microphone satellitaire connecté.  |Logitech Group + microphones satellitaires <br/> Polycom Trio+ microphones satellitaires <br/> Polycom CX5100 + microphones satellitaires <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + microphones satellitaires  |Tous les périphériques audio répertoriés dans cette ligne prennent en charge les options de microphone satellite. <br/> CX5100 comprend une caméra 360 degrés intégrée de manière à ce que le périphérique puisse être positionné au centre de la table. <br/> Le SP 220 MS doit être utilisé dans la configuration en cascade.  |

**Périphériques vidéo certifiés des salles Microsoft Teams**

|Type de salle|Nombre de personnes|Appareil par taille de salle maximale|Commentaires|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  |2 à 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Small** <br/> 16' x 16'  |4 à 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro est souvent livré avec Logitech Group  |
|**Moyen** <br/> 18' x 20'  |6 à 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Large** <br/> 15' x 32'  |12 à 16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

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
