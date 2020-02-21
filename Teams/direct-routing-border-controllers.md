---
title: Liste des contrôleurs de frontière de session certifiés pour le routage direct
ms.author: crowe
ms.reviewer: NMuravlyannikov
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
description: Microsoft établit des partenariats avec certains fournisseurs de contrôleurs SBC afin de certifier que leurs produits fonctionnent avec un routage direct.
ms.openlocfilehash: 3e442a2afd61c3d5c39ac8edc89fa128131ac468
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214410"
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
| [CodesAudio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20 a. 250   |     |    |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20 a. 250   |     |    |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  7.20 a. 250  |    |    |    
|                                                                                                                     | SBC-9000  |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  7.20 a. 250 |    |    |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 7.2       | <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> |   Non |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 7.2       |  <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> | Non   |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 7.2       |  <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul>  |Non|    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 7.2       |   <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> |  Non  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 7.2       |   <ul> <li>Intrado ERS </li> <li>Intrado EGW</li> <li> Mobilité du ciel en rouge </li> </ul> |   Non |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v 8.0.3 (Build 537)     |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |         |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v 8.0.3 (Build 537)     |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |           |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v 8.0.3 (Build 216)    |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>    |           |    
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       V1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |    |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>  |    |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>  |    |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |    |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>  |    |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> Intrado ERS </li> <li>Intrado EGW </li> </ul>   |    |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v3.16.2      |     |    |    

Le tableau suivant répertorie les appareils qui sont vérifiés en matière d’interopérabilité entre le routage direct et les appareils analogiques.

|                                                       Fournisseur                                                        |       Product       | Jugé
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [CodesAudio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |

Pour nous faire part de vos commentaires sur les équipes, par exemple des idées de nouvelles fonctionnalités, voir [UserVoice](https://microsoftteams.uservoice.com) Notez la certification accordée à une version majeure. Cela signifie que le microprogramme avec n’importe quel numéro dans le microprogramme SBC après la version principale est pris en charge.
