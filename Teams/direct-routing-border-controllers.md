---
title: Contrôleurs de bordure de session certifiés pour le routage direct
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: L’administrateur peut en savoir plus sur les contrôleurs de bordure de session (SBCs) qui ont été certifiés pour le routage direct.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d0a4f5846b120559b2fbaea97e191f1740ad4be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901829"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Liste des contrôleurs de frontière de session certifiés pour le routage direct

Microsoft établit des partenariats avec certains fournisseurs de contrôleurs SBC afin de certifier leurs SBC pour une utilisation avec un routage direct. 

Microsoft travaille avec chaque fournisseur pour : 

- Travaillez conjointement avec les protocoles d’interconnexion SIP.
- Effectuez des tests intensifs à l’aide d’un laboratoire tiers. Seuls les appareils qui passent les tests sont certifiés. 
- Exécutez des tests quotidiens avec tous les appareils certifiés en environnement de production et de pré-production. La validation des périphériques en préproduction permet de s'assurer que les nouvelles versions de code de routage direct dans le cloud fonctionneront avec les SBC certifiés. 
- Établissez un processus d’assistance conjointe avec les fournisseurs de SBC.


  > [!NOTE]
  > Microsoft ne prend en charge que le système téléphonique s’il est connecté par le biais du routage direct. Microsoft se réserve le droit de rejeter les cas de support où un appareil non certifié est connecté au système téléphonique via le routage direct. 

Le tableau suivant reprend les périphériques certifiés pour le routage direct. 

[En savoir plus sur le routage direct](https://aka.ms/dr). Si vous avez des questions sur le programme de certification de SBC pour le routage direct, contactez drsbccertification@microsoft.com.


|                                                       Fournisseur                                                        |       Product       | Contournement non multimédia | Contournement de média | Version du logiciel | Validé auprès des fournisseurs de E911 | ELIN compatible
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [CodesAudio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256)   | <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul> |  &#10004;  |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256)   | <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256)   |   <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256)   |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256)  |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |    
|                                                                                                                     | SBC-9000  |     &#10004;     |   &#10004;     |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256)   | <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  7.20 pris en charge A. 250 (recommandée 7.20 A. 256) |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>   |  &#10004;  |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       7,2 pris en charge (recommandé 8,2)       | <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul> |    |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       7,2 pris en charge (recommandé 8,2)       |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       7,2 pris en charge (recommandé 8,2)       |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       7,2 pris en charge (recommandé 8,2)       |   <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       7,2 pris en charge (recommandé 8,2)       |   <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.0.3 (Build 537)     |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> Intrado ERS </li> <li>Intrado EGW </li> <li> Mobilité du ciel en rouge </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.0.3 (Build 537)     |  <ul> <li>[Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> Intrado ERS </li> <li>Intrado EGW </li> <li> Mobilité du ciel en rouge </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.0.3 (Build 216)    |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> Intrado ERS </li> <li>Intrado EGW </li> <li> Mobilité du ciel en rouge </li> </ul>    |     &#10004;     |   
| | Séries de EdgeMarc |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1,4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>   |  &#10004;  |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [Routage de l’emplacement dynamique de la bande passante](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li>  </ul>  |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      3,20 pris en charge (recommandé 4,0)        |     |    |    
|                     [Changer de bouton](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4,7      |     |    |    

Le tableau suivant répertorie les appareils qui sont vérifiés en matière d’interopérabilité entre le routage direct et les appareils analogiques.

|                                                       Fournisseur                                                        |       Product       | Jugé
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [CodesAudio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [CodesAudio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [»](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Version du logiciel : 8.1.1 (Build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [»](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Version du logiciel : 8.1.1 (Build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |


Pour nous faire part de vos commentaires sur les équipes, par exemple des idées de nouvelles fonctionnalités, voir [UserVoice](https://microsoftteams.uservoice.com) Notez la certification accordée à une version majeure. Cela signifie que le microprogramme avec n’importe quel numéro dans le microprogramme SBC après la version principale est pris en charge.
