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
description: Microsoft établit des partenariats avec certains fournisseurs de contrôleurs SBC afin de certifier que leurs produits fonctionnent avec un routage direct.
ms.openlocfilehash: 5fa0cb728beed0f308a4d168cd149ef1e75e2809
ms.sourcegitcommit: 9fd23cf0e03dd8fcf7ed04ef09dcdac048ebb44a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/18/2019
ms.locfileid: "37572244"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Liste des contrôleurs de frontière de session certifiés pour le routage direct

Microsoft établit des partenariats avec certains fournisseurs de contrôleurs SBC afin de certifier leurs SBC pour une utilisation avec un routage direct. 

Avec chaque fournisseur, Microsoft : 

- Collabore avec les fournisseurs SBC sur leurs protocoles d'interconnexion SIP.
- Mène des tests intensifs via un laboratoire tiers ; seuls les périphériques qui passent les tests sont certifiés. 
- Mène des tests quotidiens avec tous les périphériques certifiés en environnements de production et de préproduction. La validation des périphériques en préproduction permet de s'assurer que les nouvelles versions de code de routage direct dans le cloud fonctionneront avec les SBC certifiés. 
- Dispose d'une procédure de support commun avec les fournisseurs SBC.


  > [!NOTE]
  > Microsoft ne prend en charge un système téléphonique que si un ou plusieurs périphériques certifiés sont connectés en routage direct. Microsoft se réserve le droit de rejeter les cas de support où un périphérique non certifié est connecté au système téléphonique en routage direct. 

Le tableau suivant reprend les périphériques certifiés pour le routage direct. 

[En savoir plus sur le routage direct](https://aka.ms/dr). Si vous avez des questions sur le programme de certification des SBC pour le routage direct, envoyez un e-mail à l'adresse drsbccertification@microsoft.com


|                                                       Fournisseur                                                        |       Product       | Contournement autre que média | Contournement de média | Version du logiciel |
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|
| [CodesAudio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20 a. 250   |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20 a. 250   |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pending     |  7.20 a. 250  |
|                                                                                                                     | SBC-9000  |     &#10004;     |   &#10004;     |  7.20 a. 250   |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  7.20 a. 250 |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V6.2       |
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V6.2       |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V6.2       |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V6.2       |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V6.2       |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v8.0.1     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v8.0.1     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v8.0.1    |
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |   Pending    |       V1.4       |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  | 
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |                                             
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v3.16.2      |

Pour nous envoyer des commentaires sur des produits sur Teams, par exemple des idées de nouvelles fonctionnalités, consultez le site [UserVoice](https://microsoftteams.uservoice.com) Notez la certification accordée à une version majeure. Cela signifie que le microprogramme avec n’importe quel numéro dans le microprogramme SBC après la version principale est pris en charge.
