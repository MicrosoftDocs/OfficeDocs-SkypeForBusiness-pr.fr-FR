---
title: Configuration requise pour Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: Cet article présente la configuration requise pour la prise en charge des salles de Microsoft Teams.
ms.openlocfilehash: a964511cbb0df2cd4d6843589423e1b7cbe88cd0
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243354"
---
# <a name="microsoft-teams-rooms-requirements"></a>Configuration requise pour Microsoft teams

Cet article présente la configuration requise pour la prise en charge des salles de Microsoft Teams. 

Votre déploiement implique la création d’un compte comme décrit dans la rubrique [déploiement de salles de Microsoft teams](room-systems-v2.md) et configuration de consoles de réunion, comme décrit dans [la rubrique Configurer une console Microsoft teams](console.md).

Vous pouvez également consulter les rubriques suivantes:

- [Licences de complément Skype Entreprise](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Options de licence basées sur votre plan: salles de Microsoft teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Les salles de Microsoft teams sont conçues pour une utilisation avec Microsoft Teams, Skype entreprise Server 2019, Skype entreprise Server 2015 ou Skype entreprise online. <br><br>Les plateformes antérieures comme Lync Server 2013 ne sont pas censées fonctionner avec les salles Microsoft Teams.

> [!NOTE]
> Si vous disposez d’un serveur Exchange locaux, Microsoft teams salles nécessite l’utilisation de Exchange Server 2013 SP1 ou version ultérieure.

## <a name="hardware-requirements"></a>Configuration matérielle requise

Les salles de Microsoft teams s’adaptent aux différentes tailles de pièces par le biais d’accessoires en fonction des périphériques audio et vidéo. Le matériel répertorié dans cet article prend en charge les modes de réunion Skype et Teams. Les périphériques audio et vidéo se connectent à des salles Microsoft teams via une connexion USB ou HDMI sur l’appareil d’ancrage. Autres éléments nécessaires :

- Disque USB de 32 Go ou plus volumineux que vous configurez comme média d’installation Windows pour Windows 10 entreprise.

- Une des tablettes ou consoles suivantes :

**Tablettes prises en charge**

|Tablette|Processeur|RAM|Disque|
|:-----|:-----|:-----|:-----|
|Surface Pro 6| |Core i5||16 Go ou 8 Go |128 Go ou plus |
|Surface Pro (5e génération) |Core i5 |8 Go ou 4 Go |128 Go ou plus |
|Surface Pro 4 |Core i5 |8 Go ou 4 Go |128 Go ou plus |

- Une des options de station d accueil suivantes pour fixer une tablette sur la table de la salle de réunion.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Polycom MSR Series](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


**Autres consoles Microsoft teams salles prises en charge**

|Console|Processeur|RAM|Disque|
|:-----|:-----|:-----|:-----|
|[UC Crestron Flex-M130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 Go |128 GO |
|[Crestron Flex UC-B130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 Go |128 GO |
|[UC Crestron Flex-B140-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 Go |128 GO |
|[UC Crestron Flex-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Principaux i7|8 Go |128 GO |
[UC Crestron Flex-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Principaux i7|8 Go |128 GO|
|[UC Crestron Flex-C160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Principaux i7|8 Go|128 GO|
|[HP Elite Slice pour salles de réunion G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 Go |128 GO | 
|[Périphérique audio G2 G2 compatible avec les salles de Microsoft teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 Go |128 GO | 
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 Go |128 GO | 
|[Logitech appuyé](https://www.logitech.com/en-us/product/microsoft-rooms)|Core i5|8 Go |128 GO |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 Go|128 GO|
|[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 Go |128 GO |
|||||

> [!NOTE]
> Les processeurs Core M3 ne sont pas pris en charge.

**Versions de micrologiciel certifiées pour les périphériques USB audio et vidéo**

|Périphériques de salle Microsoft teams|Version du microprogramme certifiée pour les salles de Microsoft teams|
|:-----|:-----|
|[Logitech bénéficient](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam) <br/> |1.2.4 |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio — 1.0.172 <br/> Vidéo: 1.0.156 <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0 <br/> 1.1.684 <br/> |
|[Logitech Group](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778 <br/> |
|[Logitech 930e](http://www.logitech.com/en-us/product/c930e-webcam) <br/> |  8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> |  1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0 <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> |  1.2.0.70232 <br/> |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html) <br/> |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0 <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15 <br/> |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30) <br/> |2.1.52 <br/>|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0 <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0 <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23 <br/> |
|[Yamaha YVC 1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100c <br/> |

- **Extensions USB**:

  - Les ports USB sur les stations d’accueil de tablette sont compatibles USB 3.0. Vous pouvez utiliser une extension USB 2. x, mais elle vous permet d’utiliser des vitesses USB 2. x à la fin extrême, et cette option n’est pas recommandée pour les périphériques USB 3,0.

  - Une extension doit répondre aux spécifications USB 2.0 ou plus récentes.

  - Les stations d’accueil de tablette prennent en charge au moins deux phases d’extension de concentrateur USB externe. Si vous avez besoin d’une connexion de plus de deux Hubs USB en série, contactez le fabricant de votre Dock pour vérifier qu’il est pris en charge.

- Connexion GbE dans la salle. Câble Ethernet de longueur adéquate

- Jusqu’à 2 1080-p est affiché avec les connexions HDMI. Câbles HDMI de la longueur appropriée.

> [!NOTE]
> Un téléviseur utilisé comme écran à l’avant de la salle doit prendre en charge/permettre la fonctionnalité CEC (Consumer Electronics Control ) HDMI afin de pouvoir basculer automatiquement sur une source vidéo active depuis le mode veille. Cette fonctionnalité n’est pas prise en charge sur tous les téléviseurs. 

> [!NOTE]
> Les salles de Microsoft teams n’utilisent pas de clavier. Si nécessaire, l’administrateur doit utiliser le clavier visuel. Un clavier ou une souris USB sera requis lors de la création d’images de l’appareil Microsoft Teams. 

Le tableau suivant fournit des recommandations pour les périphériques en fonction de la taille de la salle :

**Périphériques audio certifiés Microsoft teams**

|Type de salle|Nombre de personnes|Distance maximum recommandée du microphone au haut-parleur|Appareil par taille de salle maximum|Commentaires|
|:-----|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9' <br/> |2 – 4 <br/> |1,5 m <br/> |Logitech Connect <br/> |Les périphériques Logitech Connect comprennent une caméra. Ils doivent donc être placés à l’avant de la salle (pas au centre de la table) pour capturer les participants locaux à la réunion. <br/> |
|**Petite** <br/> 16' x 16' <br/> |4 à 6 <br/> |2,0 m <br/> |Jabra 510 <br/> Sennheiser SP20 <br/> |Le volume de lecture peut être limité pour des salles plus grandes. <br/> |
|**Moyenne** <br/> 18' x 20' <br/> |6 – 12 <br/> |2,4 m <br/> |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS <br/> |Les périphériques Logitech MeetUp comprennent une caméra. Ils doivent donc être placés à l’avant de la salle (pas au centre de la table) pour capturer les participants locaux à la réunion. <br/> En règle générale, il est possible de faire en sorte qu’il soit possible de disposer de microphones de satellites. <br/> SP 220 MS doit être utilisé dans une configuration en chaîne. <br/> |
|**Grande** <br/> 15' x 32' <br/> |12-16 <br/> |3 m <br/> Cette distance s’applique également à la surface couverte par chaque micro satellite connecté au périphérique audio. <br/> |Logitech Group + microphones satellitaires <br/> Polycom Trio+ microphones satellitaires <br/> Polycom CX5100 + microphones satellitaires <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + microphones satellitaires <br/> |Tous les périphériques audio répertoriés dans cette ligne prennent en charge les options de microphone satellite. <br/> CX5100 inclut une caméra 360 de niveau intégré pour que l’appareil puisse être placé au centre de la table. <br/> SP 220 MS doit être utilisé dans une configuration en chaîne. <br/> |

**Périphériques vidéo certifiés Microsoft teams**

|Type de salle|Nombre de personnes|Appareil par taille de salle maximale|Commentaires|
|:-----|:-----|:-----|:-----|
|**Focus** <br/> 10' x 9' <br/> |2 – 4 <br/> |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100 <br/> ||
|**Petite** <br/> 16' x 16' <br/> |4 à 6 <br/> |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100 <br/> |Logitech PTZ Pro est souvent livré avec Logitech Group <br/> |
|**Moyenne** <br/> 18' x 20' <br/> |6 – 12 <br/> |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100 <br/> ||
|**Grande** <br/> 15' x 32' <br/> |12-16 <br/> |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100 <br/> ||

 > [!NOTE]
 > La résolution de l'écran à l’avant de la salle doit être définie pour ne pas être supérieure à 1920 x 1080 pixels.

## <a name="required-software-downloads"></a>Téléchargements de logiciels requis

Pour créer votre propre image de salles de Microsoft Teams, suivez les instructions de la procédure de [configuration d’une console de salle Microsoft teams](console.md). Ces instructions vous guident tout au long du processus d’installation de tous les logiciels nécessaires.

> [!NOTE]
> Des professionnels de l'informatique devront accéder aux fichiers ISO Windows 10 Entreprise via leur contrat de licences en volume.

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) est un téléchargement facultatif que vous pouvez utiliser pour approvisionner des comptes de salle Microsoft Teams.

## <a name="see-also"></a>Voir aussi
[Parcourez toutes les offres](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Plan pour les salles de Microsoft teams](skype-room-systems-v2-0.md)

[Déploiement de salles de Microsoft teams](room-systems-v2.md)

[Configurer une console de salle Microsoft teams](console.md)

[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)

[Licences de module complémentaire Skype Entreprise](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
