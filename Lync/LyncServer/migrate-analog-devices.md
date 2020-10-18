---
title: Migrer des périphériques analogiques
description: Migrer des périphériques analogiques.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f7f92142fb6a3ced37cded1a223038ec1876d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579400"
---
# <a name="migrate-analog-devices"></a><span data-ttu-id="091eb-103">Migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="091eb-103">Migrate analog devices</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="091eb-104">_**Dernière modification de la rubrique :** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="091eb-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="091eb-105">Lync Server prend en charge les périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="091eb-105">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="091eb-106">Les périphériques analogiques pris en charge sont plus précisément des téléphones audio analogiques et des télécopieurs analogiques.</span><span class="sxs-lookup"><span data-stu-id="091eb-106">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="091eb-107">Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="091eb-107">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="091eb-108">Après avoir effectué une migration de Lync Server 2010 vers Lync Server 2013, vous devez également migrer les objets contact associés aux appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="091eb-108">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="091eb-109">Utilisez Lync Server Management Shell pour récupérer tous les objets contact associés aux appareils analogiques Lync Server 2010, puis déplacez ces objets vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="091eb-109">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="091eb-110">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="091eb-110">To migrate analog devices</span></span>

1.  <span data-ttu-id="091eb-111">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="091eb-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="091eb-112">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="091eb-112">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="091eb-113">Vérifiez que tous les objets contact ont été déplacés vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="091eb-113">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="091eb-114">Sur la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="091eb-114">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="091eb-115">Vérifiez que tous les objets contact sont maintenant associés au pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="091eb-115">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

