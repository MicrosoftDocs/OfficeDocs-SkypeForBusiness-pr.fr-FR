---
title: Configurer les paramètres réseau-routage en fonction de l’emplacement
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
audience: admin
ms.service: msteams
search.appverid: MET150
description: Découvrez comment créer et configurer des zones, des sites et des sous-réseaux réseau pour le routage direct.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8025467a0581c95a40551244948a8e6b7c0ecbc8
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372054"
---
# <a name="configure-network-settings-for-location-based-routing"></a>Configurer les paramètres de réseau pour le routage géodépendant

Si vous ne l’avez pas encore fait, lisez [la section routage en fonction de l’emplacement pour le routage direct](location-based-routing-plan.md) pour réviser les autres étapes que vous devez effectuer avant de configurer les paramètres réseau pour le routage en fonction de l’emplacement.

Cet article décrit comment configurer les paramètres réseau pour le routage sur site. Après avoir déployé le routage direct du système téléphonique au sein de votre organisation, les étapes suivantes permettent de créer et de configurer les zones du réseau, les sites réseau et les sous-réseaux réseau.

## <a name="define-network-regions"></a>Définir des régions réseau

Une région réseau contient une collection de sites du réseau et interconnecte diverses parties d’un réseau à différentes zones géographiques. Pour plus d’informations sur la configuration des zones du réseau, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).

## <a name="define-network-sites"></a>Définir des sites réseau

Un site réseau correspond à un emplacement où votre organisation a une place physique, par exemple un bureau, un ensemble de bâtiments ou un campus. Vous devez associer chaque site réseau dans votre topologie à une région réseau. Pour plus d’informations sur la façon de configurer les sites réseau, voir [gérer les fonctionnalités de réseau pour le Cloud dans teams](manage-your-network-topology.md).

Il est recommandé de créer un site distinct pour chaque emplacement ayant une connectivité PSTN unique. Vous pouvez créer un site activé pour le routage de géolocalisation ou un site qui n’est pas activé pour le routage sur site. Par exemple, vous souhaiterez peut-être créer un site qui n’est pas activé pour le routage géolocalisation pour permettre aux utilisateurs qui sont activés pour le routage de l’emplacement d’effectuer des appels RTC lors de l’itinérance de ce site.

## <a name="define-network-subnets"></a>Définir des sous-réseaux réseau

Chaque sous-réseau doit être associé à un site réseau spécifique. Vous pouvez associer plusieurs sous-réseaux avec le même site réseau, mais vous ne pouvez pas associer plusieurs sites au même sous-réseau. Pour plus d’informations sur la configuration des sous-réseaux du réseau, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).

Pour le routage basé sur l’emplacement, les sous-réseaux IP situés à l’emplacement où les points de terminaison d’équipe peuvent se connecter au réseau doivent être définis et associés à un réseau défini pour l’application du contournement du numéro. Cette association de sous-réseaux permet le routage de géolocalisation pour localiser les points de terminaison géographiquement pour déterminer si un appel RTC donné doit être autorisé. Les sous-réseaux IPv6 et IPv4 sont pris en charge. Lorsque vous déterminez si un point de terminaison d’équipes est situé sur un site, le routage en fonction de l’emplacement vérifie une adresse IPv6 correspondante. Si aucune adresse IPv6 n’est présente, le routage sur la base de l’emplacement vérifie la présence d’une adresse IPv4.

## <a name="define-trusted-ip-addresses-external-subnets"></a>Définir des adresses IP approuvées (sous-réseaux externes)

Les adresses IP approuvées correspondent aux adresses IP externes Internet du réseau d’entreprise et permettent de déterminer si le point de terminaison de l’utilisateur se trouve à l’intérieur du réseau d’entreprise. Pour plus d’informations sur la configuration des adresses IP approuvées, voir [gérer la topologie de votre réseau pour les fonctionnalités du Cloud dans teams](manage-your-network-topology.md).

Si l’adresse IP de l’utilisateur correspond à une adresse IP figurant dans la liste d’adresses IP autorisées, le routage sur la base de l’emplacement vérifie le sous-réseau interne sur lequel se trouve le point de terminaison de l’utilisateur. Si l’adresse IP de l’utilisateur ne correspond pas à une adresse IP définie dans la liste d’adresses IP autorisées, le point de terminaison est considéré comme qui se trouve à un emplacement inconnu et tout appel RTC à ou à partir d’un utilisateur qui est autorisé à utiliser le routage de géolocalisation est bloqué.

## <a name="next-steps"></a>Étapes suivantes

Accédez à [activer le routage en fonction de l’emplacement pour le routage direct](location-based-routing-enable.md).

## <a name="related-topics"></a>Voir aussi

- [Paramètres réseau pour les fonctionnalités vocales de Cloud dans teams](cloud-voice-network-settings.md)
