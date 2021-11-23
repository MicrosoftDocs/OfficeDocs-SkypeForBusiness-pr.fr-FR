---
title: Contrôleurs de frontière de session certifiés pour le routage direct
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Découvrez quels contrôleurs de frontière de session (SBC) ont été certifiés pour le routage direct.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 97f8ffbf6613ca4106a68284c8e889375a7b0feb
ms.sourcegitcommit: b3b295557d494f77a7ebd9f49ec55f2507da956c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/22/2021
ms.locfileid: "61135197"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>Contrôleurs de frontière de session certifiés pour le routage direct

Microsoft établit des partenariats avec certains fournisseurs de contrôleurs SBC afin de certifier leurs SBC pour une utilisation avec un routage direct.

Microsoft collabore avec chaque fournisseur pour :

- Travaillez conjointement sur les protocoles d’interconnexion SIP.
- Effectuez des tests intensifs à l’aide d’un laboratoire tiers. Seuls les appareils qui réussissent les tests sont certifiés.
- Exécutez des tests quotidiens avec tous les appareils certifiés dans les environnements de production et de préproduction. La validation des périphériques en préproduction permet de s'assurer que les nouvelles versions de code de routage direct dans le cloud fonctionneront avec les SBC certifiés.
- Établissez un processus de support commun avec les fournisseurs SBC.

  > [!NOTE]
  > Microsoft prend uniquement en charge le système téléphonique si un ou plusieurs appareils certifiés sont connectés via le routage direct. En cas de problème, le client doit d’abord contacter le support technique des fournisseurs SBC. Si nécessaire, le fournisseur SBC fait remonter le problème à Microsoft via des canaux internes. Microsoft se réserve le droit de rejeter les cas de support où un appareil non certifié est connecté au système téléphonique via le routage direct. Si Microsoft détermine que le problème de routage direct d’un client concerne l’appareil SBC d’un fournisseur, le client devra contacter de nouveau le fournisseur SBC pour obtenir de l’aide.
  >
  > La certification est accordée à des versions de microprogramme SBC spécifiques. Les versions de microprogramme SBC ci-dessous sont certifiées et prises en charge. Les versions de microprogramme supérieures à celles qui sont documentées sont prises en charge tant que la version principale.mineure est identique.
  >
  > Exemple :
  >
  > - Pris en charge 6.10.258 – dans ce cas, nous prenons également en charge les versions de firmware 6.10. (258 ou supérieures).
  > - Recommandé 6.20.100 – dans ce cas, nous recommandons également les versions de firmware 6.20. (100 ou supérieures).
  > - Pour toute question relative à la prise en charge d'une version spécifique, contactez votre fournisseur SBC.

Les tableaux qui suivent répertorient les appareils certifiés pour le routage direct. (Pour plus d’informations sur les fournisseurs SBC qui prennent en charge l’optimisation des médias locaux, consultez [Configurer l’optimisation des médias locaux pour le routage direct](direct-routing-media-optimization-configure.md).)

[En savoir plus sur le routage direct](https://aka.ms/dr).
Si vous avez des questions sur le programme de certification SBC pour le routage direct, contactez drsbccertification@microsoft.com. Remarque : nous n’acceptons pas de nouvelles nominations pour la certification jusqu’à nouvel avis.
<br/>

## <a name="certified-sbc-vendors"></a>Fournisseurs SBC certifiés

|                                                       Fournisseur                                                        |       Product       | Contournement non multimédia | Contournement de média | Version logicielle requise | 911 Fournisseur de services compatible* | Compatible NILU |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Prise en charge 7.20A.258 (recommandé 7.40A.100)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Prise en charge 7.20A.258 (recommandé 7.40A.100)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Prise en charge 7.20A.258 (recommandé 7.40A.100)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Prise en charge 7.20A.258 (recommandé 7.40A.100)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   &#10004;     |  Pris en charge 7.20A.250 (recommandé 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000  SBC  |     &#10004;     |   &#10004;     |  Prise en charge 7.20A.258 (recommandé 7.40A.100)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Prise en charge 7.20A.258 (recommandé 7.40A.100) |  &#10004;    |  &#10004;  |   
|                                                                                                                     | Mediant Cloud Edition SBC  |     &#10004;     |   &#10004;     |  Prise en charge 7.20A.258 (recommandé 7.40A.100) |  &#10004;    |  &#10004;  |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Pris en charge 8.2 et 7.2 (Recommandé 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Pris en charge 8.2 et 7.2 (Recommandé 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Pris en charge 8.2 et 7.2 (Recommandé 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Pris en charge 8.2 et 7.2 (Recommandé 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Pris en charge 8.2 et 7.2 (Recommandé 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x ou 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x ou 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x ou 9.x    |   &#10004;    |     &#10004;     |
| | Série EdgeMarc |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Pris en charge 3.20 (recommandé 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 pour le contournement du média)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) pour routeurs de services intégrés de la série 1000        |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r pris en charge (17.6.1a recommandé)         |    &#10004;     |   |  
|                                   |     Cisco Unified Border Element (CUBE) pour les routeurs de services intégrés de la série 4000        |     &#10004;   | &#10004; |   IOS XE Amsterdam 17.2.1r pris en charge (17.6.1a recommandé)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) pour le routeur de services cloud de la série 1000V       |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r pris en charge (17.3.3 recommandé)         |    &#10004;     |    |  
|                                 |     Cisco Unified Border Element (CUBE) pour les routeurs des services d’agrégation de la série 1000      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.2.1r pris en charge (17.6.1a recommandé)         |    &#10004;     |    |
|                                 |     Cisco Unified Border Element (CUBE) pour les plateformes Edge Catalyst 8000      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.3.2 pris en charge (17.6.1a recommandé)      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Contrôleur de frontière de session Avaya pour Entreprise (ASBCE)    |     &#10004;     |       &#10004;     |       Version 8.1.1 (8.1.2 pour le contournement du média)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Contrôleur de bordure de session Nokia    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Contrôleur de bordure de session Nokia    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       Prise en charge de la version 5.0 (recommandé 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Lien d’attache    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unify OpenScape Session Border Controller   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Réseaux Enghouse](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    SBC BorderNet dialogique   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [Technologies M5 (anciennement Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Série Mediatrix Sentinel   |     &#10004;     |         |      DGW 48.0.2340 (DGW recommandé 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Voix hyperconvergée   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

\* **Fournisseurs de services 911**

- [Routage d’emplacement dynamique de bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Service de routage d’urgence intrado (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Passerelle d’urgence intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

<br/>

## <a name="support-for-local-media-optimization"></a>Prise en charge de l’optimisation des médias locaux

Le tableau suivant décrit les fournisseurs SBC qui prennent en charge L’[optimisation des médias locaux](direct-routing-media-optimization.md). 

| Fournisseur | Product |    Version logicielle requise |
|:------------|:-------|:-------|
| [CodesAudio](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.258 | 
|            |  Mediant 2600 SBC |  7.20A.258 | 
|            |  Mediant 4000 SBC |  7.20A.258 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.258 | 
|            |  Mediant Virtual Edition SBC |   7.20A.258 | 
|            |  Mediant Cloud Edition SBC | 7.20A.258 |
| [SBC Core du ruban](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)   |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [SBC Edge du ruban](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |




## <a name="direct-routing-and-analog-devices-interoperability"></a>Interopérabilité des périphériques analogiques et de routage direct

Le tableau suivant répertorie les appareils vérifiés pour l’interopérabilité entre le routage direct et les périphériques analogiques.

|                                                       Fournisseur                                                        |       Product       | Les administrateurs
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Carte téléphonique analogique multiplateforme ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 Software Version 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 Software Version 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Logiciel VME version 8.3.0.1.2 |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Version logicielle : 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Version logicielle : 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 302. Version logicielle : 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 304. Version logicielle : 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 2900A. Version logicielle : 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4806. Version logicielle : 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4808. Version logicielle : 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Ruban](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 6000. Version logicielle : 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode avec Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Pour nous faire part de vos commentaires sur Teams, tels que des idées de nouvelles fonctionnalités, consultez [Uservoice](https://microsoftteams.uservoice.com).


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Notez la certification accordée à une version majeure. Cela signifie que le microprogramme avec n’importe quel nombre dans le microprogramme SBC suivant la version principale est pris en charge.
