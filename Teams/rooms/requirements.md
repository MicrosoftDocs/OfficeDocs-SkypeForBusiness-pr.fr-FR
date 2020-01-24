---
title: Configuration requise pour Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Cet article présente la configuration requise pour la prise en charge des salles de Microsoft Teams.
ms.openlocfilehash: 33c72c4261b37427fba3d4c853ef2a6d9600e269
ms.sourcegitcommit: f017e38095098d4d28c71241dddac53538be79d7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2020
ms.locfileid: "41506876"
---
# <a name="microsoft-teams-rooms-requirements"></a>Configuration requise pour Microsoft teams

Les salles de Microsoft teams sont mises à niveau en fonction de la taille et de l’utilisation de votre grande variété de périphériques audio et vidéo certifiés. En sélectionnant le périphérique et la console à droite, combinés avec des micros, des haut-parleurs, des appareils photo et des écrans adaptés à l’espace, vous pouvez déployer des salles de Microsoft teams dans des espaces de n’importe quelle taille à partir de très petits Huddle vers le haut dans les espaces de conférences très volumineux. et des salles de  Le jeu complet de tous les périphériques audio et vidéo certifiés disponibles qui peuvent être utilisés pour configurer votre salle est disponible dans la [Galerie de périphériques](https://products.office.com/microsoft-teams/across-devices).

Cet article décrit la configuration requise pour le déploiement et la configuration des appareils pour la prise en charge des salles de Microsoft Teams.

Votre déploiement implique la création d’un compte comme décrit dans la rubrique [déploiement de salles de Microsoft teams](rooms-deploy.md) et configuration de consoles de réunion, comme décrit dans [la rubrique Configurer une console Microsoft teams](console.md).

Vous pouvez également consulter les rubriques suivantes :

- [Licences de complément Skype Entreprise](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Options de licence basées sur votre plan : salles de Microsoft teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Les salles de Microsoft teams se connectent à Microsoft Teams, à Skype entreprise Server 2019, à Skype entreprise Server 2015 ou à Skype entreprise Online et pourront participer à des réunions hébergées par l’un de ces services.
>
> Les plates-formes précédentes comme Lync Server 2013 ne sont pas prises en charge par Microsoft teams salles. Les salles de Microsoft Teams ne sont pas prises en charge dans Office 365 géré par 21Vianet ou dans les environnements GCC-High ou DoD.
>
> Si vous disposez d’un serveur Exchange locaux, Microsoft teams salles nécessite l’utilisation de Exchange Server 2013 SP1 ou version ultérieure.

## <a name="hardware-requirements"></a>Configuration matérielle requise
Un déploiement de matériel inclut une sélection d’un système de salle Microsoft Teams, associé à des périphériques audio et vidéo certifiés, ainsi qu’une solution de câblage permettant d’intégrer ces périphériques ensemble.  Ces options sont décrites dans cet article.

**Systèmes de salle Microsoft teams pris en charge**

Tous les appareils et ensembles de pièces Microsoft teams actuels sont disponibles dans l’ensemble de [produits systèmes de salle](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processeur|RAM|Disque|
  |:-----|:-----|:-----|:-----|
  |[UC Crestron Flex-M130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 Go |128 GO |
  |[Crestron Flex UC-B130-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 Go |128 GO |
  |[UC Crestron Flex-B140-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 Go |128 GO |
  |[UC Crestron Flex-M150-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) + [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Principaux i7|8 Go |128 GO |
  [UC Crestron Flex-B160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Principaux i7|8 Go |128 GO|
  |[UC Crestron Flex-C160-T](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Principaux i7|8 Go|128 GO|
  |[HP Elite Slice pour salles de réunion G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 Go |128 GO |
  |[Périphérique audio G2 G2 compatible avec les salles de Microsoft teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 Go |128 GO |
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 Go |128 GO |
  |[Logitech appuyé](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 Go |128 GO |
  |[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 Go|128 GO|
  |[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 Go |128 GO |
  |[Yealink MVC300](https://www.yealink.com/products_154.html)|Core i5|8 Go |128 GO |
  ||||||

> [!NOTE]
> - Les processeurs Core M3 ne sont pas pris en charge.
> - Vous avez besoin d’un lecteur USB de 32 Go ou supérieur configuré comme support amorçable d’installation Windows pour Windows 10 entreprise.

**Tablettes surface Pro prises en charge pour les systèmes de type ancrage**

  |Tablette|Processeur|RAM|Disque|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 Go ou 8 Go |128 Go ou plus |
  |Surface Pro </br>(5e génération) |Core i5 |8 Go ou 4 Go |128 Go ou plus |
  |Surface Pro 4 |Core i5 |8 Go ou 4 Go |128 Go ou plus |

- Une des options de station d accueil suivantes pour fixer une tablette sur la table de la salle de réunion.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versions de micrologiciel certifiées pour les périphériques USB audio et vidéo

Ces appareils sont disponibles dans le [système de salle Showcase](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) et [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Périphérique de salle Microsoft teams|Version du microprogramme certifié | Caméra prenant en charge l’utilisation de l’appareil photo|
|:--- |:--- | :--- |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | &#x2714; |
|[Logitech brio](https://www.logitech.com/product/brio)   |V 2.2.50| &#x2714; |
|[Logitech 930e](http://www.logitech.com/product/c930e-webcam)   |  8.0.914   | &#x2714; |
|[Logitech bénéficient](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](http://www.logitech.com/product/meetup-conferencecam)   |Audio — 1.0.172 <br/> Vidéo : 1.0.156  |
|[Logitech ConferenceCam Connect](http://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](http://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](http://www.logitech.com/product/conferencecam-ptz-pro)   |  1.1.219   |
|[Logitech PTZ Pro 2](http://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   |  1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Polycom trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Sennheiser SP30T](https://en-us.sennheiser.com/sp-30)  |3.2.63  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Processeur d’audioconférence Shure Intellimix P300](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 matrice de tableau](https://www.shure.com/en-US/products/microphones/mxa310) | 4,1 |
|[Shure Intellimix P300 le processeur audio Conferening](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 avec Intellimix plafond](https://www.shure.com/en-US/products/microphones/mxa910) | 4,1|
|[Biamp Tesira AVB VT4 fixe audio](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Micro TeamConnect plafond 2 Sennheiser](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [TESIRA ex-UBT](https://www.biamp.com/products/tesira/tesira-expanders)&Dagger; |  Biamp DSP : 3.12.0.15  </br></br> TCC2:1.3.3 </br></br> EX-UBT : 3.12.0.15 |  |
||||||

&Dagger;Les clients peuvent choisir l’interface Dante ou le commutateur réseau recommandée par biamp/Sennheiser pour ce bundle.

#### <a name="usb-extenders"></a>Extensions USB

- Les ports USB sur les stations d’accueil de tablette sont compatibles USB 3.0. Vous pouvez utiliser une extension USB 2. x, mais cela vous permet de limiter les vitesses USB 2. x à l’extrémité extrême. Les unités Extender ne sont pas recommandées pour les périphériques USB 3,0.
- Une extension doit répondre aux spécifications USB 2.0 ou plus récentes.
  - Les stations d’accueil de tablette prennent en charge au moins deux phases d’extension de concentrateur USB externe. Si vous connectez plus de deux concentrateurs USB en série, contactez le fabricant de votre Dock pour vérifier qu’il prend en charge la connexion de série.
  - Connexion GbE dans la salle. Câble Ethernet de longueur adéquate
  - Jusqu’à 2 1080-p est affiché avec les connexions HDMI. Câbles HDMI de la longueur appropriée.

> [!NOTE]
> Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille. Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs.
>
> Les salles de Microsoft teams n’utilisent pas de clavier. Si nécessaire, l’administrateur doit utiliser le clavier visuel. Un clavier ou une souris USB sera requis lors de la création d’images de l’appareil Microsoft Teams.

Le tableau suivant fournit des recommandations pour les périphériques en fonction de la taille de la salle :

**Périphériques audio certifiés Microsoft teams**

|Type de salle|Nombre de personnes|Distance maximum recommandée du microphone au haut-parleur|Appareil par taille de salle maximum|Commentaires|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'   |2 – 4  |1,5 m  |Logitech Connect  |Les périphériques Logitech Connect incluent une caméra qui doit être positionnée au premier plan de la salle (et non au centre de tableaux) pour capturer les participants de la réunion locale. |
|**Petite** <br/> 16' x 16'  |4 à 6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |Le volume de lecture peut être limité pour les salles de grande taille.  |
|**Moyenne** <br/> 18' x 20'  |6 – 12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Les périphériques Logitech MeetUp comprennent une caméra. Ils doivent donc être placés à l’avant de la salle (pas au centre de la table) pour capturer les participants locaux à la réunion. <br/> En règle générale, il est possible de faire en sorte qu’il soit possible de disposer de microphones de satellites. <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  |
|**Grande** <br/> 15' x 32'  |12-16  |3 m <br/> Cette distance s’applique également à la surface couverte par chaque micro-satellite connecté.  |Logitech Group + microphones satellitaires <br/> Polycom Trio+ microphones satellitaires <br/> Polycom CX5100 + microphones satellitaires <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + microphones satellitaires  |Tous les périphériques audio répertoriés dans cette ligne prennent en charge les options de microphone satellite. <br/> CX5100 inclut une caméra 360 de niveau intégré pour que l’appareil puisse être placé au centre de la table. <br/> SP 220 MS doit être utilisé dans une configuration en chaîne.  |

**Périphériques vidéo certifiés Microsoft teams**

|Type de salle|Nombre de personnes|Appareil par taille de salle maximale|Commentaires|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9'  |2 – 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Petite** <br/> 16' x 16'  |4 à 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro est souvent livré avec Logitech Group  |
|**Moyenne** <br/> 18' x 20'  |6 – 12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Grande** <br/> 15' x 32'  |12-16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > La résolution de l'écran à l’avant de la salle doit être définie pour ne pas être supérieure à 1920 x 1080 pixels.

## <a name="required-software-downloads"></a>Téléchargements de logiciels requis

Pour créer votre propre image de salles de Microsoft Teams, suivez les instructions de la procédure de [configuration d’une console de salle Microsoft teams](console.md). Ces instructions vous guident dans le téléchargement de tous les logiciels nécessaires à l’installation.

> [!NOTE]
> Des professionnels de l'informatique devront accéder aux fichiers ISO Windows 10 Entreprise via leur contrat de licences en volume.

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) est un téléchargement facultatif que vous pouvez utiliser pour approvisionner des comptes de salle Microsoft Teams.

## <a name="see-also"></a>Voir aussi

[Parcourez toutes les offres](https://products.office.com/microsoft-teams/across-devices/devices)

[Plan pour les salles de Microsoft teams](rooms-plan.md)

[Déploiement de salles de Microsoft teams](rooms-deploy.md)

[Configurer une console de salle Microsoft teams](console.md)

[Gérer Microsoft Teams Rooms](rooms-manage.md)

[Licences de module complémentaire Skype Entreprise](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
