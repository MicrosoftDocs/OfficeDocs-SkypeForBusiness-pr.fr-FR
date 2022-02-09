---
title: Configurer les paramètres réseau - Routage basé sur l’emplacement
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des régions, des sites et des sous-réseaux réseau pour Location-Based routage direct.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b2686cb0171a6d7725e76ca6de4338c350c3296f
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457214"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurer les paramètres de réseau pour le routage géodépendant

Cet article décrit comment configurer les paramètres réseau pour le Location-Based routage. Si vous ne l’avez pas déjà fait, lisez [Planifier Location-Based routage pour le routage](location-based-routing-plan.md) direct afin d’examiner les autres étapes à suivre avant de configurer les paramètres réseau.

Après avoir déployé le routage direct dans votre organisation, les étapes suivantes sont la création et la création de régions réseau, de sites réseau et de sous-réseaux.

## <a name="define-network-regions"></a>Définir les régions réseau

Une région réseau contient un ensemble de sites réseau et interconnecte différentes parties d’un réseau sur plusieurs zones géographiques. Pour savoir comment configurer les régions réseau, voir Gérer votre topologie de réseau pour les fonctionnalités [cloud dans Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Définir des sites réseau

Un site réseau représente un emplacement où votre organisation dispose d’un lieu physique, tel qu’un bureau, un ensemble de bâtiments ou un campus. Vous devez associer chaque site réseau de votre topologie à une région réseau. Pour savoir comment configurer des sites réseau, voir Gérer votre [topologie de réseau pour les fonctionnalités cloud dans Teams](manage-your-network-topology.md).

Une meilleure pratique en matière Location-Based routage des appels consiste à créer un site distinct pour chaque emplacement  dispose d’une connectivité réseau téléphonique commuté (RSTN) unique. Vous pouvez créer un site activé pour le routage Location-Based ou un site non activé pour l'Location-Based routage. Par exemple, vous pouvez créer un site non activé pour le routage Location-Based afin d’autoriser les utilisateurs activés pour le routage Location-Based à effectuer des appels RSTN lorsqu’ils sont en itinérance vers ce site.

## <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Chaque sous-réseau doit être associé à un site réseau spécifique. Vous pouvez associer plusieurs sous-réseaux au même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau. Pour savoir comment configurer des sous-réseaux, voir Gérer votre topologie de réseau pour les fonctionnalités [cloud dans Teams](manage-your-network-topology.md).

Pour Location-Based routage, les sous-réseaux IP à l’emplacement où les points de terminaison Teams peuvent se connecter au réseau doivent être définis et associés à un réseau défini pour appliquer la dérivation toll. Cette association de sous-réseaux permet Location-Based routage de recherche des points de terminaison géographiquement afin de déterminer si un appel PSTN donné doit être autorisé. Les sous-réseaux IPv6 et IPv4 sont pris en charge. Pour déterminer si un point de terminaison Teams est situé sur un site, l'Location-Based routage vérifie d’abord la recherche d’une adresse IPv6 correspondante. Si une adresse IPv6 n’est pas présente, Location-Based routage recherche une adresse IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Définir des adresses IP fiables (sous-réseaux externes)

Les adresses IP fiables sont les adresses IP externes Internet du réseau d’entreprise et sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve dans le réseau d’entreprise. Pour savoir comment configurer des adresses IP fiables, voir Gérer votre [topologie](manage-your-network-topology.md) de réseau pour les fonctionnalités cloud dans Teams.

Si l’adresse IP externe de l’utilisateur correspond à une adresse IP qui se trouve dans la liste d’adresses IP fiables, le routage Location-Based vérifie le sous-réseau interne où se trouve le point de terminaison de l’utilisateur. Si l’adresse IP externe de l’utilisateur ne correspond à aucune adresse IP définie dans la liste d’adresses IP de confiance, le point de terminaison est considéré comme étant à un emplacement inconnu et tous les appels PSTN entre un utilisateur activé pour le routage Location-Based sont bloqués.

## <a name="next-steps"></a>Étapes suivantes

Allez à [Activer Location-Based routage pour le routage direct](location-based-routing-enable.md).

## <a name="related-topics"></a>Sujets associés

- [Paramètres réseau pour les fonctionnalités vocales cloud dans Teams](cloud-voice-network-settings.md)
