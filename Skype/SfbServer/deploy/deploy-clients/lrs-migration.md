---
title: Migration des périphériques Lync salle système vers le système de salle Skype version 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Lisez cette rubrique pour savoir comment migrer des périphériques de système de salle de Lync pour utiliser le système de salle Skype v2 logiciel.
ms.openlocfilehash: b6c11e101ab3984f934dab1a9e06d80df3ce5e4f
ms.sourcegitcommit: 80e1983fd631b8ad63c902375f1128faa957e374
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/09/2018
ms.locfileid: "25450647"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a>Migrer les appareils Lync salle système (KR) au système de salle Skype v2 
Les appareils Lync salle système (KR) avec le logiciel système Version 1 (v1 SRS) Skype salle atteindra [la fin de la prise en charge sur le 9 octobre 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Cela signifie que le logiciel de v1 Skype salle systèmes ne recevra pas les mises à jour ou les correctifs après cette date. Il est conseillé aux utilisateurs avec des périphériques de système de salle Lync l’utilisation du système de salle Skype v1 logiciel pour mettre à niveau leurs périphériques au système de salle Skype version 2 (v2 SRS).

Logiciel système Version 2 (v2 SRS) Skype salle fonctionne avec Microsoft Teams outre Skype pour les services Business Server et en ligne pour les réunions et les appeler sur tous les périphériques de SRS v2 pris en charge.

Votre de périphériques existant **peut** continuer à fonctionner après la fin d’un système de salle de Skype v1 prennent en charge. Ce logiciel sera atteint finalement un bogue logiciel dont a besoin Microsoft publie un correctif, ou peut-être un cas où un protocole de communication existant utilisé par les modifications du logiciel système de salle Skype v1 ou n’est plus pris en charge. Un tel changement connu est désapprobation de TLS 1.0 / 1.1 dans Microsoft Office 365. Pour plus d’informations sur [la préparation pour TLS 1.0/1.1 désapprobation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).  

## <a name="which-devices-are-affected"></a>Les périphériques sont affectés ?
Voici la liste des périphériques qui sont affectées par cette modification :
- [Systèmes de salle actives](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [CX8000 de Polycom](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- Crestron RL

## <a name="upgrade-options"></a>Options de mise à niveau
Il existe plusieurs options de mise à niveau des systèmes de salle de Lync pour la nouvelle génération de systèmes de salle Skype (SRS v2).

### <a name="crestron-hardware-trade-in-program"></a>Programme de reprise de matériel Crestron
Crestron fournira une mise à niveau pour le [système SR Crestron](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou l’équivalent pour tous les clients Non-Crestron Lync salle système. Afficher les détails de ce programme [ici](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [messagerie](mailto:lrsupgrade@crestron.com) prise en charge Crestron LRS.  


### <a name="crestron-rl2-to-rl3"></a>Crestron RL2 à RL3
Les clients existants Crestron RL2 (également appelé Crestron RL200) peuvent obtenir un package de mise à niveau pour mettre à niveau en cours RL2 à l’aide de RL3 un pour un coût minimal par périphérique. Afficher les détails de ce programme [ici](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [messagerie](mailto:lrsupgrade@crestron.com) prise en charge Crestron LRS.  


### <a name="smart-room-systems-upgrade"></a>Mise à niveau des systèmes de salle Active 
Pour les clients KR actives, en dehors du programme de reprise Crestron matériel, Microsoft et à puce fonctionnent également à fournir une solution de mise à niveau vers le système de salle Skype v2. Cette mise à niveau sera proposée par puce pour tous les clients existants de kr actives. Plus de détails de ce programme seront fournies dans 2018 octobre sur cette page. Assurez-vous que retour des mises à jour.

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a>Comment procéder ?
Nous vous recommandons de que vous envisagez de mettre à jour des périphériques Lync salle système pour systèmes de salle Skype v2 avant désapprobation TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus. En outre, vous pouvez également envisager de remplacement de périphériques existants avec de nouveaux périphériques certifiés pour SRS v2. Pour plus d’informations, consultez [équipements de salle](https://aka.ms/roomdevices) et également jeter un œil à [v2 Skype salle requise](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> Fonctionnalité tactile et le tableau blanc n’est pas encore pris en charge dans le système de salle Skype v2. Prise en charge tactile et tableau blanc se trouve dans la file d’attente pour le système de salle Skype v2 et est ajouté dans CY2019 H1.

> [!NOTE]
> Logiciel Skype salle système V2 n’autorise pas actuellement protocole TLS 1.2. Prise en charge TLS 1.2 est en cours de traitement et sera exécuté avant TLS 0/1/1.1 désapprobation. Clients upgradging à SRS v2 ne s’affiche pas n’importe quel impact de désapprobation TLS 1.0/1.1 sur les appareils de salle version la plus récente de SRS v2 application en cours d’exécution.
