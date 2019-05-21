---
title: Gestion de la qualité de service (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La qualité de service (QoS) est une technologie de réseau utilisée dans certaines organisations pour vous permettre d’offrir une interface utilisateur optimale pour les communications audio et vidéo.
ms.openlocfilehash: fbc10c5e94706348b7e3f66687b4868a9feb44ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279402"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestion de la qualité de service (QoS) dans Skype entreprise Server


La qualité de service (QoS) est une technologie de réseau utilisée dans certaines organisations pour vous permettre d’offrir une interface utilisateur optimale pour les communications audio et vidéo. La qualité de service (QoS) est souvent utilisée sur les réseaux disposant d’une bande passante limitée: il existe un grand nombre de paquets réseau en concurrence d’une faible quantité de bande passante disponible, ce qui permet aux administrateurs d’affecter des priorités plus élevées aux paquets. transport de données audio ou vidéo. La transmission de ces paquets est une priorité plus élevée, les communications audio et vidéo sont susceptibles de s’exécuter plus vite, et en moins d’interruption, que les sessions réseau impliquant des transferts de fichiers, la navigation sur le Web ou des sauvegardes de bases de données. C'est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.


> [!NOTE]  
> En règle générale, la qualité de service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs pour prendre en charge le marquage des paquets. Toutefois, vous configurez ces appareils pour prendre en charge le marquage des paquets d’une manière spécifique. Vous ne pouvez pas supposer que la qualité de service sera prise en charge sur Internet ou sur d’autres réseaux. Même si la qualité de service est prise en charge sur d’autres réseaux, il n’existe aucune garantie de configuration de la qualité de service (QoS) par le biais du service de votre réseau.

Skype entreprise Server n’exige aucune qualité de service. Si vous n’utilisez pas actuellement QoS, vous n’avez pas besoin d’installer le service avant d’installer Skype entreprise Server. Si vous subissez une quantité considérable de perte de paquets sur votre réseau, la méthode recommandée pour résoudre ce problème consiste à ajouter de la bande passante supplémentaire. Si l’ajout de bande passante n’est pas possible, il est possible que vous souhaitiez implémenter la qualité de service.

Skype entreprise Server offre une prise en charge totale de la qualité de service: cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Skype entreprise Server à leur infrastructure réseau existante. Pour cela, vous devez effectuer les tâches suivantes:

  - [Activation de la qualité de service (QoS) pour les appareils qui ne sont pas basés sur Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres appareils (tels que les iPhones) qui exécutent d'autres systèmes d'exploitation. Même si vous pouvez utiliser Skype entreprise Server pour activer et désactiver la qualité de service des appareils, vous ne pouvez pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

  - [Configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. Avec Skype entreprise Server, vous n’activez ou ne désactivez pas la qualité de service, par exemple, la définition d’une valeur de propriété sur true ou false. Au lieu de cela, vous activez la qualité de service en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez de ne pas utiliser la qualité de service (QoS), vous pouvez désactiver la qualité de service en supprimant les objets de stratégie de groupe appropriés.

  - [La configuration de plages de ports et d’une stratégie de qualité de service pour vos serveurs de périphérie](configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. La configuration d’une stratégie de qualité de service ne doit être exécutée que pour le côté interne de vos serveurs Edge. La qualité de service est alors conçue pour une utilisation sur votre réseau interne et non sur Internet.

- [Configuration de plages de ports et d’une politique de qualité de service pour vos clients dans Skype entreprise Server](configuring-port-ranges-for-your-skype-clients.md)  Ces plages de port s’appliquent uniquement aux ordinateurs clients et sont généralement différentes de celles configurées sur vos serveurs. Notez que Skype entreprise Server ne prend pas en charge la qualité de service (QoS) pour les systèmes d’exploitation Windows autres que Windows 10.


