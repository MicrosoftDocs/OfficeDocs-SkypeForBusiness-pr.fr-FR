---
title: Gestion de la qualité de service (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l’utilisateur final pour les communications audio et vidéo.
ms.openlocfilehash: aa7012a664c7075c06a6bd104921e1cac680e798
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831978"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestion de la qualité de service (QoS) dans Skype Entreprise Server


La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l’utilisateur final pour les communications audio et vidéo. QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau simultanés pour une quantité de bande passante disponible relativement faible, la Qualité de service permet aux administrateurs d’affecter une priorité supérieure aux paquets transportant des données audio ou vidéo. Le fait d’affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s’effectuer plus rapidement, et avec moins d’interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. C’est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.


> [!NOTE]  
> En règle générale, la Qualité de service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs afin de prendre en charge le marquage de paquets ; toutefois, vous configurez ces périphériques pour que cette prise en charge s’effectue d’une manière particulière. Vous ne pouvez pas considérer que la Qualité de service sera prise en charge sur Internet ou sur d’autres réseaux. Même si c’est le cas, il n’est pas garanti que la configuration de QoS sera identique à celle que vous avez faite de ce service sur votre réseau.

Skype Entreprise Server ne nécessite pas la qualité de service ; si vous n’utilisez pas QoS actuellement, il n’est pas nécessaire d’installer le service avant d’installer Skype Entreprise Server. Si vous rencontrez une perte considérable de paquets sur votre réseau, il est recommandé d’ajouter de la bande passante supplémentaire afin de résoudre ce problème. Si ce n’est pas possible, vous pouvez alors implémenter la Qualité de service à la place.

Skype Entreprise Server offre une prise en charge complète de la qualité de service : cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer des Skype Entreprise Server à leur infrastructure réseau existante. Pour cela, vous devez effectuer les tâches suivantes :

  - [Activation de la QoS pour les appareils qui ne sont pas basés sur Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres périphériques (tels que les iPhones) qui exécutent d’autres systèmes d’exploitation. Bien que vous pouvez utiliser Skype Entreprise Server pour activer et désactiver la qualité de service pour les appareils, vous ne pouvez généralement pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

  - [Configuration des plages de ports et d’une](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)stratégie de qualité de service pour vos serveurs de conférence, d’application et de médiation. Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. Avec Skype Entreprise Server vous n’activez pas ou ne désactivez pas la qualité de service en activant une valeur de propriété sur True ou False. Au lieu de cela, vous activez la Qualité de service en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez par la suite de ne pas utiliser QoS, vous pouvez simplement « désactiver » ce service en supprimant les objets de stratégie de groupe appropriés.

  - [Configuration des plages de ports et d’une stratégie de qualité de service pour vos serveurs Edge.](configuring-port-ranges-for-your-edge-servers.md) Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. La configuration d’une stratégie de qualité de service ne doit être effectuée que pour le côté interne de vos serveurs Edge. En effet, la Qualité de service est conçue pour être utilisée sur votre réseau interne, et non sur Internet.

- [Configuration des plages de ports et d’une stratégie de](configuring-port-ranges-for-your-skype-clients.md) qualité de service pour vos clients dans Skype Entreprise Server  Ces plages de ports s’appliquent uniquement aux ordinateurs clients et sont généralement différentes des plages de ports configurées sur vos serveurs. Notez que Skype Entreprise Server ne prend pas en charge la QoS pour les Windows d’exploitation autres que Windows 10.


