---
title: Migrer des appareils Lync Room System vers Salles Microsoft Teams
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
description: Lisez cette rubrique pour découvrir comment migrer des appareils Lync Room System pour utiliser le Salles Microsoft Teams logiciel.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a700e66a966035b52a3036210e39c09612ed18b5df34430545987c51c40575f8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54301070"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrer des appareils Lync Room System (LRS) vers Salles Microsoft Teams

Le support des appareils Lync Room System (LRS) avec le logiciel Skype Room System version 1 (SRS v1) a pris fin le 9 octobre [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018) Cela signifie que Skype Room Systems v1 ne recevra plus de mises à jour de produit ou de correctifs. Les clients disposant d’appareils de salle Lync utilisant Skype Room v1 sont invités à mettre à niveau leurs appareils vers les salles Microsoft Teams.

Salles Microsoft Teams logiciel fonctionne avec Microsoft Teams en plus des services Skype Entreprise Server online pour les réunions et les appels sur tous Salles Microsoft Teams appareils pris en charge.

Vos appareils existants **peuvent continuer à** fonctionner après la fin de Skype prise en charge du logiciel Room System v1. Toutefois, si ce logiciel se produit après un bogue logiciel qui nécessite la publication d’un correctif par Microsoft, il ne sera pas pris en charge. SRS v1 utilise TLS 1.0/1.1 que Microsoft utilisera à l’avenir. Vous pouvez en savoir plus sur la préparation de la retrait de [TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608) 

## <a name="which-devices-are-affected"></a>Quels appareils sont concernés ?

Voici la liste des appareils concernés par ce changement :

- Crestron RL
- [Crestron RL2](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [Systèmes de salle intelligente](https://support.smarttech.com/en/hardware/room-systems-skype)
- [Polycom CX8000](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Options de mise à niveau

Plusieurs options s’offrent à vous pour mettre à niveau les systèmes de salle Lync vers la nouvelle génération de Salles Microsoft Teams.

### <a name="crestron-hardware-trade-in-program"></a>Hardware Trade-in program (Matériel de pointe)

Crestron proposera une mise à niveau du système [SR de Crestron SR](https://www.crestron.com/products/featured-solutions/crestron-sr) ou un équivalent pour tous les clients Non-Crestron Lync Room System (par exemple, Smart ou Polycom LRS). Consultez les détails de ce [programme ici ou](https://support.crestron.com/app/answers/answer_view/a_id/1000220) <!-- For details, -->[e-mail](mailto:lrsupgrade@crestron.com) Prise en charge de Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Upgrade to Salles Microsoft Teams

Les clients existants de Crestron RL2 (également appelés RL200) peuvent acquérir un kit de mise à niveau pour mettre à niveau la version actuelle de RL2 vers RL3 à l’aide d’un coût minimal par appareil. Consultez les détails de ce [programme ici.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)

### <a name="smart-room-systems-upgrade"></a>Mise à niveau des systèmes de salle SMART Room

Pour les clients SMART LRS, à l’exception du programme de cérité du matériel de Crestron, SMART travaille également à la fourniture d’une solution pour la mise à niveau vers Salles Microsoft Teams. Cette mise à niveau sera fournie par SMART Technologies Inc. au client sous support technique. Consultez plus d’informations à ce [sujet ici.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)


## <a name="what-should-you-do"></a>Que devez-vous faire ?

Nous vous recommandons de planifier la mise à jour des appareils Lync Room System Salles Microsoft Teams avant la dés déconseillation de TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus. En outre, vous pouvez également envisager de remplacer les appareils existants par de nouveaux appareils certifiés Salles Microsoft Teams. Pour [plus d’informations,](https://aka.ms/roomdevices) consultez les appareils De salle et consultez [la Salles Microsoft Teams requise.](/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)  


> [!NOTE]
> Salles Microsoft Teams prend en charge le protocole TLS 1.2 à partir du 14 décembre 2018 avec la version d’application 4.0.64.0. Pour les clients locaux, l’activation de la communication sur TLS 1.2 pour Salles Microsoft Teams nécessite la mise à jour cumulative Skype Entreprise Server 9 (CU9) ou la mise à jour cumulative Skype Entreprise Server 2019 1 (CU1). La modification ne doit pas affecter Skype Entreprise online, car les modifications apportées aux clients sont conformes en conformité avec l’avant et l’arrière.