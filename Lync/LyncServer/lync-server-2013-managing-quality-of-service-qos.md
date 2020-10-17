---
title: 'Lync Server 2013 : gestion de la qualité de service (QoS)'
description: 'Lync Server 2013 : gestion de la qualité de service (QoS).'
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df0e84389cc030cd63fe04c46929bd981a074aec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552720"
---
# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Gestion de la qualité de service (QoS) dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

La Qualité de service (QoS) est une technologie réseau utilisée dans certaines organisations afin de fournir des performances optimales à l’utilisateur final pour les communications audio et vidéo. QoS est le plus souvent utilisée sur les réseaux où la bande passante est limitée : avec un grand nombre de paquets réseau simultanés pour une quantité de bande passante disponible relativement faible, la Qualité de service permet aux administrateurs d’affecter une priorité supérieure aux paquets transportant des données audio ou vidéo. Le fait d’affecter une priorité supérieure à ces paquets permet aux communications audio et vidéo de s’effectuer plus rapidement, et avec moins d’interruption, que les sessions réseau impliquant des opérations telles que des transferts de fichiers, de la navigation web ou des sauvegardes de bases de données. C’est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.

<div>


> [!NOTE]  
> En règle générale, la Qualité de service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs afin de prendre en charge le marquage de paquets ; toutefois, vous configurez ces périphériques pour que cette prise en charge s’effectue d’une manière particulière. Vous ne pouvez pas considérer que la Qualité de service sera prise en charge sur Internet ou sur d’autres réseaux. Même si c’est le cas, il n’est pas garanti que la configuration de QoS sera identique à celle que vous avez faite de ce service sur votre réseau.



</div>

Microsoft Lync Server 2013 n’exige pas la qualité de service ; Si vous n’utilisez pas actuellement QoS, il n’est pas nécessaire d’installer le service avant d’installer Lync Server 2013. Si vous rencontrez une perte considérable de paquets sur votre réseau, il est recommandé d’ajouter de la bande passante supplémentaire afin de résoudre ce problème. Si ce n’est pas possible, vous pouvez alors implémenter la Qualité de service à la place.

Lync Server 2013 offre une prise en charge complète de la qualité de service : cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Lync Server dans leur infrastructure réseau existante. Pour cela, vous devez effectuer les tâches suivantes :

  - [Activation de la qualité de service dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres périphériques (tels que les iPhones) qui exécutent d’autres systèmes d’exploitation. Bien que vous puissiez utiliser Lync Server pour activer et désactiver la qualité de service pour les appareils, vous ne pouvez généralement pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

  - [Configuration des plages de ports dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. Avec Lync Server 2013, vous n’activez pas ou ne désactivez pas la qualité de service, par exemple, en définissant une valeur de propriété sur true ou sur false. Au lieu de cela, vous activez la Qualité de service en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez par la suite de ne pas utiliser QoS, vous pouvez simplement « désactiver » ce service en supprimant les objets de stratégie de groupe appropriés.

  - [Configuration des plages de ports pour vos serveurs Edge dans Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs.

  - [Configuration des plages de ports pour vos clients Microsoft Lync dans Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Ces plages de ports s’appliquent uniquement aux ordinateurs clients et ne sont généralement pas les mêmes que les plages de ports configurées sur vos serveurs.

  - [Configuration d’une stratégie de qualité de service dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Ces stratégies déterminent les codes DSCP appliqués aux différents types de paquets.

  - [Configuration d’une stratégie de qualité de service pour vos serveurs Edge a/V dans Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Cette opération ne doit être effectuée que pour le côté interne de vos serveurs Edge. En effet, la Qualité de service est conçue pour être utilisée sur votre réseau interne, et non sur Internet.

  - [Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients s’exécutant sur Windows 7 ou Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Notez que Microsoft Lync Server 2013 ne prend pas en charge QoS pour d’autres systèmes d’exploitation Windows, tels que Windows Vista ou Windows XP.

  - [Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition dans Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Par défaut, la qualité de service est activée pour les appareils Lync Phone Edition. Vous pouvez toutefois modifier la valeur DSCP par défaut afin de garantir que tous les paquets audio de votre organisation utilisent le même code DSCP.

<div>


> [!NOTE]  
> Si vous utilisez Microsoft Windows Server 2012 ou Windows Server 2012 R2, le nouvel ensemble d’applets de commande Windows PowerShell disponible pour la gestion de la qualité de service sur cette plateforme est susceptible de vous intéresser. Pour plus d’informations, reportez-vous à Network Quality of service cmdlets in Windows PowerShell à l’adresse [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps) .



</div>

</div>

<span> </span>

</div>

</div>

</div>

