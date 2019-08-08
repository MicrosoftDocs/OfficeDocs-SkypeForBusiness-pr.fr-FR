---
title: Migrer des appareils de système de salle Lync vers des salles Microsoft teams
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Consultez cette rubrique pour découvrir comment migrer des appareils de système de salle Lync pour utiliser le logiciel de salle Microsoft Teams.
ms.openlocfilehash: d07f214707253dc91495da1d219ed84dab2eec5d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243365"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migration de périphériques LRS (Lync Room System) vers des salles Microsoft teams

Les appareils LRS (Lync Room System) avec le logiciel Skype Room System version 1 (SRS v1) ont atteint la [fin de la prise en charge le 9 octobre 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Cela signifie que le logiciel Skype salle Systems v1 n’obtiendra plus les mises à jour de produits ou correctifs. Les clients disposant d’appareils de bureau Lync utilisant le logiciel Skype Room System v1 sont invités à mettre à niveau leurs périphériques vers les salles de Microsoft Teams.

Le logiciel de salle Microsoft teams fonctionne avec Microsoft teams en plus de Skype entreprise Server et services en ligne pour les réunions et les appels sur tous les appareils Microsoft teams compatibles pris en charge.

Vos appareils existants **** continuent à fonctionner après la fin de la prise en charge des logiciels de la version v1 du système de salle Skype. Toutefois, si ce logiciel rencontre un bogue logiciel qui nécessite Microsoft pour publier un correctif, il ne sera pas pris en charge. SRS v1 utilise TLS 1.0/1,1 qui sera déconseillé par Microsoft dans le futur. Vous pouvez en savoir plus sur la [préparation de la désapprobation TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). La prise en charge de TLS 1,2 par Microsoft teams est prise en charge jusqu’au 31 octobre 2018. Les clients locaux Skype entreprise ne peuvent pas désactiver TLS 1.0/1.1 tant que Microsoft Teams ne annonce pas la prise en charge de TLS 1,2, quelles que soient les recommandations générales relatives à la désactivation de TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Quels appareils sont concernés?

Voici la liste des appareils concernés par ce changement:

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Systèmes de salle intelligente](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Options de mise à niveau

Plusieurs options s’offrent à vous pour effectuer la mise à niveau de systèmes de salle Lync vers la nouvelle génération de salles Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Programme d’échange de matériel Crestron

Crestron fournira une mise à niveau vers le [système Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou équivalent pour tous les clients de systèmes de salle non Crestron (par exemple, intelligent ou Polycom LRS). Consultez les détails de ce programme [ici](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, -->[courrier électronique](mailto:lrsupgrade@crestron.com) Crestron LRS support.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Crestron RL2 mise à niveau vers les salles de Microsoft teams

Les clients Crestron RL2 (également désignés sous le nom de Crestron RL200) peuvent acquérir un kit de mise à niveau pour mettre à niveau le RL2 actuel vers RL3 en utilisant un coût minimal par appareil. Pour plus d’informations sur ce programme, voir [ici](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Mise à niveau des systèmes de salle intelligente

Pour les clients intelligents de LRS, à l’exception du programme d’échange de matériel Crestron, intelligent consiste également à proposer une solution de mise à niveau vers Microsoft Teams. Cette mise à niveau sera fournie par SMART Technologies Inc. au client en vertu du support technique. Veuillez en savoir plus à [](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)ce propos.


## <a name="what-should-you-do"></a>Que faire?

Nous vous conseillons de planifier la mise à jour des périphériques du système de salle Lync vers les salles de votre application avant TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus. Par ailleurs, vous pouvez également envisager de remplacer des appareils existants par de nouveaux appareils certifiés pour les salles Microsoft Teams. Pour plus d’informations, consultez la section [périphériques de salle](https://aka.ms/roomdevices) et prenez en revue la [Configuration requise pour Microsoft teams](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> La fonctionnalité d’interaction et de tableau blanc n’est pas encore prise en charge dans Microsoft Teams. La prise en charge des entrées et des tableaux blancs est actuellement prévue pour les salles Microsoft teams et sera ajoutée à 2019.

> [!NOTE]
> Le logiciel de salles de Microsoft teams prend en charge le protocole TLS 1,2 au 14 décembre 2018 avec la version 4.0.64.0. Pour les clients sur site, l’activation de la communication via TLS 1,2 pour les salles Microsoft teams nécessite Skype entreprise Server 2015 cumulative Update 9 (CU9) ou Skype entreprise Server 2019 cumulative update 1 (CU1). Le changement ne devrait pas affecter les clients de Skype entreprise Online, car les modifications apportées au client sont conformes et en amont.
