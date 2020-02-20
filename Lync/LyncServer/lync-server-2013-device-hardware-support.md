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

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="c9f4e-102">Prise en charge du matériel de périphérique dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9f4e-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9f4e-103">_**Dernière modification de la rubrique :** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="c9f4e-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="c9f4e-104">Vous devez mettre en place des configurations matérielles spécifiques avant de déployer des téléphones IP et des périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="c9f4e-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="c9f4e-105">Les téléphones IP exécutant Lync Phone Edition prennent en charge la fonctionnalité Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) et Power over Ethernet (PoE).</span><span class="sxs-lookup"><span data-stu-id="c9f4e-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="c9f4e-106">Pour utiliser le protocole LLDP-MED, le commutateur doit prendre en charge les normes IEEE802.1AB et ANSI/TIA-1057.</span><span class="sxs-lookup"><span data-stu-id="c9f4e-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="c9f4e-107">Pour utiliser PoE, il doit prendre en charge la norme PoE802.3AF ou 802.3at.</span><span class="sxs-lookup"><span data-stu-id="c9f4e-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="c9f4e-108">Pour utiliser LLDP-MED, l’administrateur doit activer LLDP dans la fenêtre de la console du commutateur et définir la stratégie réseau LLDP-MED à l’aide de l’ID du réseau local virtuel (VLAN) de voix correct.</span><span class="sxs-lookup"><span data-stu-id="c9f4e-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="c9f4e-109">En outre, si votre déploiement inclut des appareils analogiques, vous devez configurer la passerelle analogique pour utiliser Lync Server et la passerelle doit être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="c9f4e-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="c9f4e-110">Un adaptateur de téléphone analogique (ATA)</span><span class="sxs-lookup"><span data-stu-id="c9f4e-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="c9f4e-111">Une passerelle analogique PSTN</span><span class="sxs-lookup"><span data-stu-id="c9f4e-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="c9f4e-112">Un Survivable Branch Appliance qui inclut une passerelle analogique PSTN</span><span class="sxs-lookup"><span data-stu-id="c9f4e-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="c9f4e-113">Un Survivable Branch Appliance qui inclut une passerelle PSTN communiquant avec un adaptateur de téléphone analogique (ATA)</span><span class="sxs-lookup"><span data-stu-id="c9f4e-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="c9f4e-114">Pour en savoir plus sur la configuration d’une passerelle analogique, voir la section sur la planification [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) du déploiement des périphériques analogiques dans la bibliothèque TechNet Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="c9f4e-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="c9f4e-115">(Les périphériques analogiques fonctionnent de la même manière dans Lync Server 2013 que dans Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="c9f4e-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9f4e-116">Vous pouvez configurer le commutateur pour Enhanced 9-1-1 (E9-1-1) si celui-ci prend en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="c9f4e-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

