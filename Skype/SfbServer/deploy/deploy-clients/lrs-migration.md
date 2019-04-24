---
title: Migrer des périphériques Lync salle système salles d’équipes Microsoft
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Lisez cette rubrique pour savoir comment migrer des périphériques de système de salle de Lync pour utiliser le logiciel Microsoft équipes salles.
ms.openlocfilehash: 2d9187643d8ffa72a843cbd72a47f4fd4a564f6e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32219394"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a>Migrer les appareils Lync salle système (KR) salles d’équipes Microsoft

Les appareils Lync salle système (KR) avec le logiciel système Version 1 (v1 SRS) Skype salle a atteint la [fin de la prise en charge sur le 9 octobre 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018). Cela signifie que logiciel v1 de systèmes de salle Skype n’est plus aura les mises à jour ou les correctifs plus. Il est conseillé aux utilisateurs avec des périphériques de système de salle Lync l’utilisation du système de salle Skype v1 logiciel pour mettre à niveau leurs appareils salles d’équipes Microsoft.

Fonctionnement des logiciels Microsoft équipes salles avec Microsoft Teams outre Skype pour les services Business Server et en ligne pour les réunions et les appeler sur toutes les salles d’équipes Microsoft périphériques pris en charge.

Votre de périphériques existant **peut** continuer à fonctionner après la fin d’un système de salle de Skype v1 prennent en charge. Toutefois, si ce logiciel accède à un bogue doit Microsoft publie un correctif logiciel, il ne sera pas être pris en charge. V1 SRS utilise TLS 1.0 / 1.1 qui sera déconseillé par Microsoft à l’avenir. Pour plus d’informations sur [la préparation pour TLS 1.0/1.1 désapprobation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608). Salles d’équipes Microsoft consiste à ajouter la prise en charge pour TLS 1.2 et continueront de fonctionner après le 31 octobre 2018. Skype pour les entreprises locale clients ne désactivez pas TLS 1.0/1.1 jusqu'à ce que les salles d’équipes Microsoft annonce la prise en charge pour TLS 1.2 indépendamment des instructions générales sur désapprobation TLS 1.0/1.1.

## <a name="which-devices-are-affected"></a>Les périphériques sont affectés ?

Voici la liste des périphériques qui sont affectées par cette modification :

- Crestron RL
- [Crestron RL2](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [Systèmes de salle actives](https://support.smarttech.com/en/hardware/room-systems-skype)
- [CX8000 de Polycom](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a>Options de mise à niveau

Il existe plusieurs options de mise à niveau des systèmes de salle de Lync pour la nouvelle génération de salles d’équipes Microsoft.

### <a name="crestron-hardware-trade-in-program"></a>Programme de reprise de matériel Crestron

Crestron fournira une mise à niveau pour le [système SR Crestron](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou l’équivalent pour tous les clients Non-Crestron Lync salle système (par exemple à puce ou Polycom LRS). Afficher les détails de ce programme [ici](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, -->[courrier électronique](mailto:lrsupgrade@crestron.com) Prise en charge Crestron LRS.  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a>Mise à niveau Crestron RL2 salles d’équipes Microsoft

Les clients existants Crestron RL2 (également appelé Crestron RL200) pouvant vous procurer un kit de mise à niveau pour mettre à niveau en cours RL2 à l’aide de RL3 un pour un coût minimal par périphérique. Afficher les détails de ce programme [ici](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).

### <a name="smart-room-systems-upgrade"></a>Mise à niveau des systèmes de salle Active

Pour les clients KR actives, en dehors du programme de reprise Crestron matérielle, à puce fonctionne également à fournir une solution de mise à niveau vers Microsoft équipes salles. Cette mise à niveau est fournie par actives Technologies Inc. aux clients sous support technique. Veuillez consulter plus d’informations sur cette [ici](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).


## <a name="what-should-you-do"></a>Comment procéder ?

Il est recommandé de que planifier la mise à jour des périphériques Lync salle système Microsoft équipes salles avant désapprobation TLS 1.0/1.1 à l’aide des options de mise à niveau mentionnées ci-dessus. En outre, vous pouvez également envisager de remplacement de périphériques existants avec de nouveaux périphériques certifiés pour les salles d’équipes Microsoft. Pour plus d’informations, consultez [équipements de salle](https://aka.ms/roomdevices) et également jeter un œil à la [Configuration requise de salles d’équipes Microsoft](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).  

> [!NOTE]
> La fonctionnalité tactile et le tableau blanc n’est pas encore pris en charge dans les salles d’équipes Microsoft. Prise en charge tactile et tableau blanc est actuellement planifiée pour les salles d’équipes Microsoft et est ajouté dans 2019.

> [!NOTE]
> Logiciel de salles d’équipes Microsoft prend en charge le protocole TLS 1.2 à compter du 14 décembre 2018 avec la version de l’application 4.0.64.0. Pour les clients sur site, permettant la communication via TLS 1.2 pour les salles d’équipes Microsoft requiert Skype pour Business Server 2015 Cumulative Update 9 (cumulative 9) ou Skype pour Business Server 2019 Cumulative Update 1 (CU1). La modification ne devrait pas affecter Skype pour les clients professionnels en ligne comme client change avant et arrière conforme.
