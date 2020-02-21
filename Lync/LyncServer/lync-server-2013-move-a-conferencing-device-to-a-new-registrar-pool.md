---
title: 'Lync Server 2013 : déplacer un périphérique de conférence vers un nouveau pool de serveurs d’inscriptions'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move a conferencing device to a new Registrar pool
ms:assetid: 26e02ca3-e881-4f90-8bf0-b13649108100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994025(v=OCS.15)
ms:contentKeyID: 51803934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79ac6a28c475c8ec08584788fdb868d2ce30e143
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-conferencing-device-to-a-new-registrar-pool-in-lync-server-2013"></a><span data-ttu-id="94958-102">Déplacer un périphérique de conférence vers un nouveau pool de serveurs d’inscriptions dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94958-102">Move a conferencing device to a new Registrar pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94958-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="94958-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="94958-104">Déplacez un périphérique de conférence d’un pool de serveurs d’inscriptions vers un autre à l’aide de la cmdlet **Move-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="94958-104">Move a conferencing device from one Registrar pool to another by using the **Move-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="94958-105">Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="94958-105">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94958-106">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="94958-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="moving-a-conferencing-device-to-a-new-registrar-pool"></a><span data-ttu-id="94958-107">Migration d’un périphérique de conférence vers un nouveau pool de serveurs d’inscriptions</span><span class="sxs-lookup"><span data-stu-id="94958-107">Moving a Conferencing Device to a New Registrar Pool</span></span>

  - <span data-ttu-id="94958-108">Pour déplacer un périphérique de conférence, vous devez spécifier l’identité de la salle à déplacer, puis définir le paramètre Target sur le nom de domaine complet (FQDN) du pool de serveurs d’inscriptions vers lequel l’appareil sera déplacé.</span><span class="sxs-lookup"><span data-stu-id="94958-108">To move a conferencing device, you must specify the identity of the room to be moved, and then set the Target parameter to the fully qualified domain name (FQDN) of the Registrar pool the device will be moved to.</span></span> <span data-ttu-id="94958-109">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="94958-109">For example:</span></span>
    
        Move-CsMeetingRoom -Target "atl-cs-001.litwareinc.com" -Identity "Room 14"

</div>

<span data-ttu-id="94958-110">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="94958-110">For details, see the Help topic for the [Move-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Move-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

