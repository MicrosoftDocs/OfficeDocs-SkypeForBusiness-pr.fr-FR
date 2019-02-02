---
title: Terminologie de routage basée sur l’emplacement
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
search.appverid: MET150
description: Découvrez la terminologie et concepts associés à routage basé sur un emplacement pour le routage Direct.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f0f399dab4097a69ef9d7a90865b81eeb206b54
ms.sourcegitcommit: 9f767b48e5f0eaf43869cba9c42ba3ba3225bcf6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/02/2019
ms.locfileid: "29715444"
---
# <a name="location-based-routing-terminology"></a>Terminologie de routage basée sur l’emplacement 

Voici quelques termes et les concepts utilisés dans la documentation de routage basé sur l’emplacement. Il est judicieux de vous familiariser avec ces concepts et termes avant d’arriver plus loin dans la documentation.

|Terme  |Description  |
|---------|---------|
|Régions réseau     | Une région réseau contient une collection de sites réseau. Par exemple, si votre organisation dispose de nombreux sites situés en Inde, vous pouvez choisir de désigner « Inde » comme une région réseau.        |
|Sites réseau    | Un site réseau représente un emplacement où votre organisation a un lieu physique, comme un bureau, un ensemble de bâtiments ou un site. Sites réseau sont définies comme un ensemble de sous-réseaux IP. Meilleure pratique pour le routage basé sur l’emplacement consiste à créer un site distinct pour chaque emplacement disposant d’une connectivité PSTN unique.  Chaque site de réseau doit être associé à une région réseau. Vous pouvez créer un site qui est activé pour le routage basé sur l’emplacement ou un site qui n’est pas activé pour le routage basé sur l’emplacement. Par exemple, vous souhaiterez peut-être créer un site qui n’est pas activé pour le routage de gÉodÉpendante permettre aux utilisateurs activés pour le routage emplacement effectuer des appels PSTN lorsqu’elles se trouvent sur ce site. Notez que sites réseau peuvent également être utilisés pour activer et configurer l’appel d’urgence.        |
|Sous-réseaux     |Sous-réseaux IP à l’emplacement où les points de terminaison équipes peuvent se connecter au réseau doivent être définies et associés à un réseau défini pour appliquer le contournement de média payant. Plusieurs sous-réseaux peuvent être associés au même site réseau, mais plusieurs sites n’est peut-être pas associés à un même sous-réseau. Cette association de sous-réseaux permet de routage emplacement rechercher les points de terminaison géographiquement pour déterminer si un appel RTC donné doit être autorisé. Sous-réseaux à la fois IPv4 et IPv6 sont prises en charge. Pour déterminer si un point de terminaison équipes se trouve sur un site, en fonction de routage commence pour une adresse IPv6 correspondante. Si une adresse IPv6 n’est pas présent, routage basé sur l’emplacement de recherche une adresse IPv4. <br><br>Prise en charge d’IPv6 est en cours et sera disponible par disponibilité générale de routage basé sur l’emplacement.          |
|Adresse IP externe de confiance    |Les adresses IP externes approuvés sont les adresses IP externes d’Internet du réseau d’entreprise. Ils déterminent si le point de terminaison de l’utilisateur est à l’intérieur du réseau d’entreprise avant de vérification pour une correspondance de site spécifique. Si l’adresse IP externe de l’utilisateur correspond à une adresse IP qui est définie dans la liste approuvée, en fonction de routage vérifie le sous-réseau interne où se trouve le point de terminaison de l’utilisateur. Si l’adresse IP externe de l’utilisateur ne correspond à n’importe quelle adresse IP qui est défini dans la liste approuvée, le point de terminaison est classé comme étant situé à un emplacement inconnu et tous les appels PSTN vers ou à partir d’un utilisateur qui est activé pour le routage basé sur l’emplacement sont bloquées.          |

### <a name="related-topics"></a>Rubriques connexes
- [Planifier le routage par emplacement pour le routage Direct](location-based-routing-plan.md)
- [Configurer les paramètres réseau pour le routage basé sur l’emplacement](location-based-routing-configure-network-settings.md)
- [Activer le routage par emplacement pour le routage Direct](location-based-routing-enable.md)
