---
title: Configurer les paramètres réseau - Routage basé sur l’emplacement
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des régions réseau, des sites et des sous-réseaux pour Location-Based routage pour le routage direct.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 75aa7b4968ca2a549c35edbccdf6d87bd7df3106
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562613"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurer les paramètres de réseau pour le routage géodépendant

Cet article explique comment configurer les paramètres réseau pour Location-Based routage. Si vous ne l’avez pas déjà fait, lisez [Plan Location-Based Routage pour le routage direct pour](location-based-routing-plan.md) passer en revue les autres étapes à suivre avant de configurer les paramètres réseau.

Après avoir déployé le routage direct dans votre organisation, les étapes suivantes sont de créer et de configurer des régions réseau, des sites réseau et des sous-réseaux réseau.

## <a name="define-network-regions"></a>Définir des régions réseau

Une région réseau contient une collection de sites réseau et interconnecte différentes parties d’un réseau dans plusieurs zones géographiques. Pour savoir comment configurer des régions réseau, consultez [Gérer la topologie de votre réseau pour les fonctionnalités cloud dans Teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Définir des sites réseau

Un site réseau représente un emplacement où votre organisation a un lieu physique, tel qu’un bureau, un ensemble de bâtiments ou un campus. Vous devez associer chaque site réseau de votre topologie à une région réseau. Pour savoir comment configurer des sites réseau, consultez [Gérer la topologie de votre réseau pour les fonctionnalités cloud dans Teams](manage-your-network-topology.md).

Une bonne pratique pour Location-Based routage consiste à créer un site distinct pour chaque emplacement doté d’une connectivité réseau téléphonique commuté (RTC) unique. Vous pouvez créer un site activé pour le routage Location-Based ou un site qui n’est pas activé pour Location-Based routage. Par exemple, vous souhaiterez peut-être créer un site qui n’est pas activé pour Location-Based routage afin d’autoriser les utilisateurs qui sont activés pour Location-Based routage à passer des appels RTC lorsqu’ils se déplacent vers ce site.

## <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Chaque sous-réseau doit être associé à un site réseau spécifique. Vous pouvez associer plusieurs sous-réseaux au même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau. Pour savoir comment configurer des sous-réseaux réseau, consultez  [Gérer la topologie de votre réseau pour les fonctionnalités cloud dans Teams](manage-your-network-topology.md).

Pour Location-Based routage, les sous-réseaux IP à l’emplacement où les points de terminaison Teams peuvent se connecter au réseau doivent être définis et associés à un réseau défini pour appliquer le contournement payant. Cette association de sous-réseaux permet à Location-Based routage de localiser géographiquement les points de terminaison pour déterminer si un appel RTC donné doit être autorisé. Les sous-réseaux IPv6 et IPv4 sont pris en charge. Lorsque vous déterminez si un point de terminaison Teams se trouve sur un site, Location-Based routage recherche d’abord une adresse IPv6 correspondante. Si aucune adresse IPv6 n’est présente, Location-Based contrôle le routage pour une adresse IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Définir des adresses IP approuvées (sous-réseaux externes)

Les adresses IP approuvées sont les adresses IP externes Internet du réseau d’entreprise et sont utilisées pour déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise. Pour savoir comment configurer des adresses IP approuvées, consultez [Gérer la topologie de votre réseau pour les fonctionnalités cloud dans Teams](manage-your-network-topology.md).

Si l’adresse IP externe de l’utilisateur correspond à une adresse IP figurant dans la liste d’adresses IP approuvées, Location-Based contrôle le routage pour déterminer le sous-réseau interne où se trouve le point de terminaison de l’utilisateur. Si l’adresse IP externe de l’utilisateur ne correspond à aucune adresse IP définie dans la liste d’adresses IP approuvées, le point de terminaison est classé comme étant à un emplacement inconnu et tous les appels RTC à destination ou en provenance d’un utilisateur activé pour Location-Based routage sont bloqués.

## <a name="next-steps"></a>Étapes suivantes

Accédez à [Activer le routage Location-Based pour le routage direct](location-based-routing-enable.md).

## <a name="related-topics"></a>Sujets associés

- [Paramètres réseau pour les fonctionnalités de voix cloud dans Teams](cloud-voice-network-settings.md)
