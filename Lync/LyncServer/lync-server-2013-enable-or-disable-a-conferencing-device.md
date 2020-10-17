---
title: 'Lync Server 2013 : activation ou désactivation d’un périphérique de conférence'
description: 'Lync Server 2013 : activer ou désactiver un périphérique de conférence.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a conferencing device
ms:assetid: d5140e38-d015-4706-9bde-cf2fa748c36b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994070(v=OCS.15)
ms:contentKeyID: 51803981
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 761bc19536c889cced68ff586753f6800df0da59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558080"
---
# <a name="enable-or-disable-a-conferencing-device-in-lync-server-2013"></a><span data-ttu-id="d6082-103">Activer ou désactiver un périphérique de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6082-103">Enable or disable a conferencing device in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6082-104">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d6082-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d6082-105">Activer et désactiver un périphérique de conférence à l’aide de la cmdlet **Enable-CsMeetingRoom** et de l’applet de commande **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="d6082-105">Enable and disable a conferencing device by using the **Enable-CsMeetingRoom** cmdlet and the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="d6082-106">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d6082-106">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d6082-107">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> .</span><span class="sxs-lookup"><span data-stu-id="d6082-107">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="enabling-a-conferencing-device"></a><span data-ttu-id="d6082-108">Activation d’un périphérique de conférence</span><span class="sxs-lookup"><span data-stu-id="d6082-108">Enabling a Conferencing Device</span></span>

  - <span data-ttu-id="d6082-109">Pour activer un périphérique de conférence, utilisez la cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="d6082-109">To enable a conferencing device, use the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="d6082-110">Lors de l’activation d’un périphérique de conférence, vous devez inclure a) l’identité de l’appareil de conférence, b) le pool de serveurs d’inscriptions où le compte de salle sera hébergé et c) l’adresse SIP à attribuer à ce compte.</span><span class="sxs-lookup"><span data-stu-id="d6082-110">When enabling a conferencing device, you must include a) the conferencing device identity, b) the Registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="disabling-a-conferencing-device"></a><span data-ttu-id="d6082-111">Désactivation d’un périphérique de conférence</span><span class="sxs-lookup"><span data-stu-id="d6082-111">Disabling a Conferencing Device</span></span>

  - <span data-ttu-id="d6082-112">Pour désactiver un périphérique de conférence, utilisez l’applet de commande **Disable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="d6082-112">To disable a conferencing device, use the **Disable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="d6082-113">Assurez-vous que vous spécifiez l’identité du périphérique de conférence à désactiver :</span><span class="sxs-lookup"><span data-stu-id="d6082-113">Make sure that you specify the identity of the conferencing device to be disabled:</span></span>
    
        Disable-CsMeetingRoom -Identity "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<span data-ttu-id="d6082-114">Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) et la cmdlet [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="d6082-114">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Disable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Disable-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

