---
title: Prise en charge du matériel de périphérique Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5b2d730181426d5b23463816d13a6f3b0e502b0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Prise en charge du matériel de périphérique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-12-14_

Vous devez mettre en place des configurations matérielles spécifiques avant de déployer des téléphones IP et des périphériques analogiques.

Les téléphones IP exécutant Lync Phone Edition prennent en charge la fonctionnalité Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) et Power over Ethernet (PoE).Pour utiliser le protocole LLDP-MED, le commutateur doit prendre en charge les normes IEEE802.1AB et ANSI/TIA-1057. Pour utiliser PoE, il doit prendre en charge la norme PoE802.3AF ou 802.3at.

Pour utiliser LLDP-MED, l’administrateur doit activer LLDP dans la fenêtre de la console du commutateur et définir la stratégie réseau LLDP-MED à l’aide de l’ID du réseau local virtuel (VLAN) de voix correct.

En outre, si votre déploiement inclut des appareils analogiques, vous devez configurer la passerelle analogique pour utiliser Lync Server et la passerelle doit être l’une des suivantes :

  - Un adaptateur de téléphone analogique (ATA)

  - Une passerelle analogique PSTN

  - Un Survivable Branch Appliance qui inclut une passerelle analogique PSTN

  - Un Survivable Branch Appliance qui inclut une passerelle PSTN communiquant avec un adaptateur de téléphone analogique (ATA)

Pour en savoir plus sur la configuration d’une passerelle analogique, voir la section sur la planification [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) du déploiement des périphériques analogiques dans la bibliothèque TechNet Lync Server 2010. (Les périphériques analogiques fonctionnent de la même manière dans Lync Server 2013 que dans Lync Server 2010.)

<div>


> [!IMPORTANT]  
> Vous pouvez configurer le commutateur pour Enhanced 9-1-1 (E9-1-1) si celui-ci prend en charge cette fonctionnalité.



</div>

</div>

<span> </span>

</div>

</div>

</div>

