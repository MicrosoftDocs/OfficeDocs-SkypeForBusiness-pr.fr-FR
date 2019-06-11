---
title: 'Lync Server 2013: gestion de la qualité de service (QoS)'
ms.reviewer: ''
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
ms.openlocfilehash: 96f25d35f0d96c9e1681c6b4d2c2c3b3079aad34
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>Gestion de la qualité de service (QoS) dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-11-07_

La qualité de service (QoS) est une technologie de réseau utilisée dans certaines organisations pour vous permettre d’offrir une interface utilisateur optimale pour les communications audio et vidéo. La qualité de service (QoS) est souvent utilisée sur les réseaux disposant d’une bande passante limitée: il existe un grand nombre de paquets réseau en concurrence d’une faible quantité de bande passante disponible, ce qui permet aux administrateurs d’affecter des priorités plus élevées aux paquets. transport de données audio ou vidéo. La transmission de ces paquets est une priorité plus élevée, les communications audio et vidéo sont susceptibles de s’exécuter plus vite, et en moins d’interruption, que les sessions réseau impliquant des transferts de fichiers, la navigation sur le Web ou des sauvegardes de bases de données. C'est la raison pour laquelle la priorité « Meilleur effort » est affectée aux paquets réseau utilisés pour les transferts de fichiers ou les sauvegardes de bases de données.

<div>


> [!NOTE]  
> En règle générale, la qualité de service s’applique uniquement aux sessions de communication sur votre réseau interne. Lorsque vous implémentez QoS, vous configurez vos serveurs et routeurs pour prendre en charge le marquage des paquets. Toutefois, vous configurez ces appareils pour prendre en charge le marquage des paquets d’une manière spécifique. Vous ne pouvez pas supposer que la qualité de service sera prise en charge sur Internet ou sur d’autres réseaux. Même si la qualité de service est prise en charge sur d’autres réseaux, il n’existe aucune garantie de configuration de la qualité de service (QoS) par le biais du service de votre réseau.



</div>

Microsoft Lync Server 2013 ne nécessite pas de qualité de service. Si vous n’utilisez pas actuellement QoS, vous n’avez pas besoin d’installer le service avant d’installer Lync Server 2013. Si vous subissez une quantité considérable de perte de paquets sur votre réseau, la méthode recommandée pour résoudre ce problème consiste à ajouter de la bande passante supplémentaire. Si l’ajout de bande passante n’est pas possible, il est possible que vous souhaitiez implémenter la qualité de service.

Lync Server 2013 offre une prise en charge complète de la qualité de service: cela signifie que les organisations qui utilisent déjà QoS peuvent facilement intégrer Lync Server dans leur infrastructure réseau existante. Pour cela, vous devez effectuer les tâches suivantes:

  - [Activation de la qualité de service (QoS) dans Lync Server 2013 pour les appareils qui ne sont pas basés sur Windows](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md). Par défaut, QoS est désactivée pour les ordinateurs et autres appareils (tels que les iPhones) qui exécutent d'autres systèmes d'exploitation. Bien que vous puissiez utiliser Lync Server pour activer et désactiver la qualité de service des appareils, vous ne pouvez pas utiliser le produit pour modifier les codes DSCP utilisés par ces appareils.

  - Configurez des [plages de ports dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). Vous devez réserver un ensemble unique de ports pour différents types de paquets, tels que les paquets audio et vidéo. Avec Lync Server 2013, vous n’activez ou ne désactivez pas la qualité de service, par exemple, la définition d’une valeur de propriété sur true ou false. Au lieu de cela, vous activez la qualité de service en configurant des plages de ports, puis en créant et en appliquant une stratégie de groupe. Si vous décidez de ne pas utiliser la qualité de service (QoS), vous pouvez désactiver la qualité de service en supprimant les objets de stratégie de groupe appropriés.

  - [Vous configurez des plages de port pour vos serveurs Edge dans Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md). Bien que cela ne soit pas requis, vous pouvez configurer vos serveurs Edge de façon à utiliser les mêmes plages de ports que vos autres serveurs.

  - [Configuration de plages de ports pour vos clients Microsoft Lync dans Lync Server 2013](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md). Ces plages de port s’appliquent uniquement aux ordinateurs clients et ne sont généralement pas les mêmes que les plages de ports configurées sur vos serveurs.

  - [Configurer une stratégie de qualité de service dans Lync Server 2013 pour vos serveurs de conférence, d’application et de médiation](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md). Ces stratégies déterminent les codes DSCP appliqués à différents types de paquets.

  - [Configurer une stratégie de qualité de service pour vos serveurs Edge a/V dans Lync Server 2013](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md). Cette opération ne doit être effectuée que pour le côté interne de vos serveurs Edge. La qualité de service est alors conçue pour une utilisation sur votre réseau interne et non sur Internet.

  - [Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients exécutant Windows 7 ou Windows 8](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md). Notez que Microsoft Lync Server 2013 ne prend pas en charge la qualité de service (QoS) pour d’autres systèmes d’exploitation Windows, tels que Windows Vista ou Windows XP.

  - [Configuration de la qualité de service sur les appareils Microsoft Lync Phone Edition dans Lync Server 2013](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md). Par défaut, la qualité de service (QoS) est activée pour les appareils Lync Phone Edition. Toutefois, vous souhaiterez peut-être modifier la valeur DSCP par défaut afin de vous assurer que tous les paquets audio de votre organisation utilisent le même code DSCP.

<div>


> [!NOTE]  
> Si vous utilisez Microsoft Windows Server 2012 ou Windows Server 2012 R2, vous pourriez être intéressé par le nouvel ensemble d’applets de cmdlet Windows PowerShell disponibles pour gérer la qualité de service sur cette plateforme. Pour plus d’informations, consultez la section qualité du réseau des applets de [https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)service dans Windows PowerShell à l’adresse.



</div>

</div>

<span> </span>

</div>

</div>

</div>

