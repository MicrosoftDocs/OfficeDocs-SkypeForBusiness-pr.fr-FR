---
title: Migrer des périphériques analogiques
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate analog devices
ms:assetid: ad072916-87ed-4d44-8289-aab87da86250
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721846(v=OCS.15)
ms:contentKeyID: 49733779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66866ee7cb6dafecb2c30b53d04a50f849f09c94
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-analog-devices"></a><span data-ttu-id="4d603-102">Migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="4d603-102">Migrate analog devices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d603-103">_**Dernière modification de la rubrique:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4d603-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4d603-104">Lync Server prend en charge les appareils analogiques.</span><span class="sxs-lookup"><span data-stu-id="4d603-104">Lync Server provides support for analog devices.</span></span> <span data-ttu-id="4d603-105">Plus précisément, les appareils analogiques pris en charge sont les téléphones analogiques et les Fax analogiques.</span><span class="sxs-lookup"><span data-stu-id="4d603-105">Specifically, the supported analog devices are analog audio phones and analog fax machines.</span></span> <span data-ttu-id="4d603-106">Vous pouvez configurer les passerelles qualifiées pour prendre en charge l’utilisation d’appareils analogiques dans votre environnement Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d603-106">You can configure the qualified gateways to support the use of analog devices in your Lync Server environment.</span></span> <span data-ttu-id="4d603-107">Après avoir effectué une migration de Lync Server 2010 vers Lync Server 2013, vous devez également déplacer les objets de contact associés aux périphériques analogiques.</span><span class="sxs-lookup"><span data-stu-id="4d603-107">After you migrate from Lync Server 2010 to Lync Server 2013, you must also migrate the contact objects associated with the analog devices.</span></span> <span data-ttu-id="4d603-108">Utilisez Lync Server Management Shell pour récupérer tous les objets de contact associés aux appareils analogiques Lync Server 2010, puis déplacez ces objets vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d603-108">Use Lync Server Management Shell to first retrieve all contact objects associated with the Lync Server 2010 analog devices, and then move those objects to the Lync Server 2013 pool.</span></span>

<div>

## <a name="to-migrate-analog-devices"></a><span data-ttu-id="4d603-109">Pour migrer des périphériques analogiques</span><span class="sxs-lookup"><span data-stu-id="4d603-109">To migrate analog devices</span></span>

1.  <span data-ttu-id="4d603-110">Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="4d603-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4d603-111">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="4d603-111">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net

3.  <span data-ttu-id="4d603-112">Vérifiez que tous les objets de contact ont été déplacés vers le pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d603-112">Verify that all contact objects have been moved to the Lync Server 2013 pool.</span></span> <span data-ttu-id="4d603-113">À partir de la ligne de commande, tapez :</span><span class="sxs-lookup"><span data-stu-id="4d603-113">At the command line, type:</span></span>
    
        Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}

4.  <span data-ttu-id="4d603-114">Vérifiez que tous les objets de contact sont désormais associés au pool Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4d603-114">Verify that all the contact objects are now associated with the Lync Server 2013 pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

