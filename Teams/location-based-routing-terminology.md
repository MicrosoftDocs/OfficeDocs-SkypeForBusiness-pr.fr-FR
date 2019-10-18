---
title: Terminologie du routage géodépendant
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.date: 2/1/2019
ms.topic: conceptual
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: Découvrez les concepts de base liés au routage par emplacement pour le routage direct.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9c7a323bb252c254d7422c30251414742608529
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572010"
---
# <a name="location-based-routing-terminology"></a>Terminologie du routage géodépendant

> [!INCLUDE [Preview customer token](includes/preview-feature.md)] 

Voici quelques termes et concepts qui sont utilisés dans la documentation de routage basée sur l’emplacement. Nous vous conseillons de vous familiariser avec les présentes conditions générales et concepts avant de vous familiariser avec la documentation.

|Terme  |Description  |
|---------|---------|
|Régions réseau     | Une région réseau contient une collection de sites réseau. Par exemple, si votre organisation comporte de nombreux sites situés en Inde, vous pouvez choisir de définir « Inde » en tant que région réseau.        |
|Sites réseau    | Un site réseau correspond à un emplacement où votre organisation a une place physique, par exemple un bureau, un ensemble de bâtiments ou un campus. Les sites réseau sont définis comme une collection de sous-réseaux IP. Il est recommandé de créer un site distinct pour chaque emplacement ayant une connectivité PSTN unique.  Chaque site réseau doit être associé à une région réseau. Vous pouvez créer un site activé pour le routage de géolocalisation ou un site qui n’est pas activé pour le routage sur site. Par exemple, vous souhaiterez peut-être créer un site qui n’est pas activé pour le routage géolocalisation pour permettre aux utilisateurs qui sont activés pour le routage de l’emplacement d’effectuer des appels RTC lors de l’itinérance de ce site. Notez que les sites réseau permettent également d’activer et de configurer les appels d’urgence.        |
|Sous-réseaux réseau     |Les sous-réseaux IP situés à l’emplacement où les points de terminaison d’équipe peuvent se connecter au réseau doivent être définis et associés à un réseau défini pour appliquer le contournement du numéro. Plusieurs sous-réseaux pourront être associés à un même site réseau, mais il est possible que plusieurs sites ne soient pas associés à un même sous-réseau. Cette association de sous-réseaux permet le routage de géolocalisation pour localiser les points de terminaison géographiquement pour déterminer si un appel RTC donné doit être autorisé. Les sous-réseaux IPv6 et IPv4 sont pris en charge. Lorsque vous déterminez si un point de terminaison d’équipes est situé sur un site, le routage en fonction de l’emplacement vérifie une adresse IPv6 correspondante. Si aucune adresse IPv6 n’est présente, le routage sur la base de l’emplacement vérifie la présence d’une adresse IPv4. <br><br>
|Adresses IP externes approuvées    |Les adresses IP externes approuvées correspondent aux adresses IP externes Internet du réseau d’entreprise. Ils déterminent si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise avant de rechercher une correspondance de site spécifique. Si l’adresse IP externe de l’utilisateur correspond à une adresse IP définie dans la liste de confiance, le routage au niveau de l’emplacement vérifie le sous-réseau interne sur lequel se trouve le point de terminaison de l’utilisateur. Si l’adresse IP de l’utilisateur ne correspond pas à une adresse IP définie dans la liste de confiance, le point de terminaison est considéré comme qui se trouve à un emplacement inconnu et tout appel RTC à ou à partir d’un utilisateur qui est autorisé à utiliser le routage de géolocalisation est bloqué.          |

### <a name="related-topics"></a>Voir aussi
- [Planifier le routage géodépendant pour le routage direct](location-based-routing-plan.md)
- [Configurer les paramètres de réseau pour le routage géodépendant](location-based-routing-configure-network-settings.md)
- [Activer le routage géodépendant pour le routage direct](location-based-routing-enable.md)
