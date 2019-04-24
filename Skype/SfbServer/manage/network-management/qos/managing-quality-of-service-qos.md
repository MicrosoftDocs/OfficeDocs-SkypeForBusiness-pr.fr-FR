---
title: Gestion de la qualité de Service (QoS)
ms.reviewer: ''
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Qualité de Service (QoS) est une technologie réseau utilisée dans certaines organisations, afin d’offrir une expérience utilisateur optimale pour les communications audio et vidéos.
ms.openlocfilehash: e8d5cf9da3be6537d4531683cfbbb9e437b66b77
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245361"
---
# <a name="managing-quality-of-service-qos-in-skype-for-business-server"></a>Gestion de la qualité de Service (QoS) dans Skype pour Business Server


Qualité de Service (QoS) est une technologie réseau utilisée dans certaines organisations, afin d’offrir une expérience utilisateur optimale pour les communications audio et vidéos. QoS plus couramment utilisés sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau en concurrence pour une petite quantité de bande passante disponible, Quality of Service permet aux administrateurs d’assigner priorité supérieure aux paquets exécution des données audio ou vidéo. En attribuant à ces paquets une priorité plus élevée, les communications audio et vidéos sont susceptibles d’exécuter plus rapidement et avec une interruption moins, que les sessions de réseau impliquant des transferts de fichiers, navigation sur le web ou des sauvegardes de base de données. C'est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.


> [!NOTE]  
> En règle générale, la qualité de Service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez la qualité de service, vous configurez vos serveurs et les routeurs pour prendre en charge des paquets de marquage ; Toutefois, vous configurez ces périphériques afin de prendre en charge le marquage d’une manière particulière des paquets. Vous ne pouvez pas supposer que la qualité de Service est pris en charge sur Internet ou sur d’autres réseaux. Même si la qualité du Service est pris en charge sur d’autres réseaux, il est aucune garantie QoS sera ne configuré de la même manière que vous configuré le service sur votre réseau.

Skype pour Business Server ne nécessite pas de qualité de Service ; Si vous n’utilisez pas actuellement QoS il n’est pas nécessaire d’installer le service avant d’installer Skype pour Business Server. Si vous rencontrez une quantité considérable de perte de paquets sur votre réseau, la méthode recommandée pour contourner ce problème consiste à ajouter la bande passante supplémentaire. Si l’ajout de plus de bande passante n’est pas possible, vous souhaitez implémenter la qualité de Service à la place.

Skype pour Business Server offre une prise en charge complète de la qualité de Service : que signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Skype pour Business Server dans son infrastructure réseau existante. Pour ce faire, vous devez effectuer les tâches suivantes :

  - [Activation de QoS pour les appareils non basés sur Windows](enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres appareils (tels que les iPhones) qui exécutent d'autres systèmes d'exploitation. Bien que vous pouvez utiliser Skype pour Business Server pour activer et désactiver la qualité de Service pour les périphériques, vous pouvez généralement utiliser le produit pour modifier les codes DSCP utilisés par ces périphériques.

  - [Configuration des plages de ports et une stratégie de qualité de Service pour vos serveurs de conférence, Application et de médiation](configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. Avec Skype pour Business Server, vous ne pas activer ou désactiver la qualité de Service, par exemple, définir une valeur de la propriété la valeur True ou False. Au lieu de cela, vous activez la qualité de Service à la configuration des plages de ports puis en créant et en appliquant la stratégie de groupe. Si vous décidez ultérieurement ne pas utiliser QoS vous pouvez « désactiver » qualité de Service en supprimant les objets de stratégie de groupe appropriés.

  - [Plages de ports de configuration et une stratégie de qualité de Service pour vos serveurs Edge](configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs. Configuration d’une stratégie de qualité de Service ne doit être effectuée que pour la partie interne de vos serveurs de périphérie. C’est parce que la qualité de Service est conçue pour une utilisation sur votre réseau interne et non sur Internet.

- [Plages de ports de configuration et une stratégie de qualité de Service pour vos clients dans Skype pour Business Server](configuring-port-ranges-for-your-skype-clients.md)  Ces plages de ports s’appliquent uniquement aux ordinateurs clients et sont généralement différents dans les plages de ports configurées sur vos serveurs. Notez que Skype pour Business Server ne prend pas en charge QoS pour Windows les systèmes d’exploitation autres que Windows 10.


