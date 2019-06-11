---
title: Prise en charge du matériel de périphérique dans Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da92e5f8d37ae5112ccea2d2b33f7f2b0186dfcf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831434"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a>Prise en charge du matériel de périphérique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-12-14_

Des configurations matérielles spécifiques doivent être en place avant le déploiement de téléphones IP et d’appareils analogiques.

Sur les téléphones IP exécutant Lync Phone Edition, le protocole de découverte des couches de connexion (LLDP-MED) et Power over Ethernet (PoE) sont pris en charge.Pour tirer parti de LLDP-MED, le commutateur doit prendre en charge les normes IEEE 802.1 AB et ANSI/TIA-1057. Pour tirer parti de la PoE, le commutateur doit prendre en charge le mode PoE 802.3 AF ou 802.3 au.

Pour activer LLDP-MED, l’administrateur doit activer LLDP en utilisant la fenêtre console de basculement et définir la stratégie réseau LLDP-MED avec l’ID VLAN valide.

De plus, si votre déploiement inclut des appareils analogiques, vous devez configurer la passerelle analogique pour utiliser Lync Server et la passerelle doit être l’un des éléments suivants:

  - Un adaptateur de téléphone analogique (ATA)

  - Passerelle analogique PSTN

  - Une unité de branchement Survivable qui inclut une passerelle analogique PSTN

  - Une unité de branchement Survivable qui inclut une passerelle RTC qui communique avec un disque ATA

Pour plus d’informations sur la configuration d’une passerelle analogique, voir la section «planification de [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) déploiement de périphériques analogiques» dans la bibliothèque TechNet de Lync Server 2010. (Les appareils analogiques fonctionnent de la même manière dans Lync Server 2013 que dans Lync Server 2010.)

<div>


> [!IMPORTANT]  
> Si le commutateur prend en charge cette option, vous pouvez configurer le commutateur pour Enhanced 9-1-1 (E9-1-1).



</div>

</div>

<span> </span>

</div>

</div>

</div>

