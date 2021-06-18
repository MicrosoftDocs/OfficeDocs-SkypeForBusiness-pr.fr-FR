---
title: Migrer des appareils Lync Room System vers des salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Lisez cette rubrique pour découvrir comment migrer des appareils Lync Room System pour utiliser le logiciel Salles Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7e850b5f5f0f210abf7defc2e53cc510c5c0b0c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117522"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrer des appareils Lync Room System (LRS) vers des salles Microsoft Teams

Les appareils Lync Room System (LRS) avec le logiciel Skype Room System version 1 (SRS v1) ont pris fin au support le 9 octobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Cela signifie que Skype Room Systems v1 ne recevra plus de mises à jour de produit ou de correctifs. Les clients disposant d’appareils de salle Lync utilisant Skype Room v1 sont invités à mettre à niveau leurs appareils vers les salles Microsoft Teams.

Le logiciel Salles Microsoft Teams fonctionne avec Microsoft Teams en plus des services Skype Entreprise Server et Online pour les réunions et les appels sur tous les appareils pris en charge par les salles Microsoft Teams.

Vos appareils existants **peuvent continuer à** fonctionner après la fin de la prise en charge du logiciel Skype Room System v1. Toutefois, si ce logiciel se produit après un bogue logiciel qui nécessite la publication d’un correctif par Microsoft, il ne sera pas pris en charge. SRS v1 utilise TLS 1.0/1.1 que Microsoft utilisera à l’avenir. Vous pouvez en savoir plus sur la préparation de la retrait de [TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>Quels appareils sont concernés ?

Voici la liste des appareils concernés par ce changement :

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Systèmes de salle intelligente](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Options de mise à niveau

Plusieurs options sont disponibles pour mettre à niveau les systèmes de salle Lync vers la nouvelle génération de salles Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Hardware Trade-in program (Matériel de pointe)

Crestron proposera une mise à niveau du système [SR de Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) ou un équivalent pour tous les clients Non-Crestron Lync Room System (par exemple, Smart ou Polycom LRS). Consultez les détails de ce [programme ici ou](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[e-mail](mailto:lrsupgrade@crestron.com) Prise en charge de Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Mise à niveau de Crestron RL2 vers des salles Microsoft Teams

Les clients existants de Crestron RL2 (également appelés RL200) peuvent acquérir un kit de mise à niveau pour mettre à niveau la version actuelle de RL2 vers RL3 à l’aide d’un coût minimal par appareil. Consultez les détails de ce [programme ici.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Mise à niveau des systèmes de salle SMART Room

Pour les clients SMART LRS, à l’exception du programme de cérité du matériel de Crestron, SMART travaille également à la fourniture d’une solution pour la mise à niveau vers des salles Microsoft Teams. Cette mise à niveau sera fournie par SMART Technologies Inc. au client sous support technique. Consultez d’autres informations à ce [sujet ici.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Que devez-vous faire ?

Nous vous recommandons de planifier la mise à jour des appareils Lync Room System vers les salles Microsoft Teams avant la dés déconseillation de TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus. En outre, vous pouvez également envisager de remplacer les appareils existants par de nouveaux appareils certifiés pour les salles Microsoft Teams. Pour [plus d’informations,](https://aka.ms/roomdevices) consultez les appareils de salle et consultez la requise [pour les salles Microsoft Teams.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Le logiciel Salles Microsoft Teams prend en charge le protocole TLS 1.2 à partir du 14 décembre 2018 avec la version 4.0.64.0 de l’application. Pour les clients locaux, l’activation de la communication via TLS 1.2 pour les salles Microsoft Teams nécessite la mise à jour cumulative 9 de Skype Entreprise Server 2015 ou de la mise à jour cumulative 1 (CU1) de Skype Entreprise Server 2019. Cette modification ne doit pas affecter les clients Skype Entreprise Online, car les modifications apportées aux clients sont conformes aux exigences en temps et en arrière.