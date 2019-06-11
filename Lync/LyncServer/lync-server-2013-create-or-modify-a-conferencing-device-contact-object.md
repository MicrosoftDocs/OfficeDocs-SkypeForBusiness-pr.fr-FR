---
title: 'Lync Server 2013: création ou modification d’un objet de contact de périphérique de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b468b2338d115e7b646c28fd4d0b310b6e132d79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="297b4-102">Créer ou modifier un objet de contact de l’appareil de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="297b4-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="297b4-103">_**Dernière modification de la rubrique:** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="297b4-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="297b4-104">Pour créer un objet de salle de conférence, commencez par créer un compte d’utilisateur Active Directory pour représenter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="297b4-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="297b4-105">Vous pouvez ensuite utiliser l’applet de passe **Enable-CsMeetingRoom** pour permettre au compte de fonctionner en tant qu’appareil de conférence.</span><span class="sxs-lookup"><span data-stu-id="297b4-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="297b4-106">Si vous devez modifier les propriétés d’un appareil de conférence existant, utilisez l’applet de passe **Set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="297b4-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="297b4-107">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="297b4-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="297b4-108">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="297b4-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="297b4-109">Création d’un périphérique de conférence</span><span class="sxs-lookup"><span data-stu-id="297b4-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="297b4-110">Une fois que vous avez créé le compte d’utilisateur Active Directory qui représente le nouvel appareil de conférence, activez-le à l’aide de l’applet de contrôle **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="297b4-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="297b4-111">N’oubliez pas d’inclure a) l’identité de l’appareil de conférence, b) du pool de bureaux d’enregistrement dans lequel le compte de la salle sera hébergé et l’adresse SIP doit être attribuée à ce compte.</span><span class="sxs-lookup"><span data-stu-id="297b4-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="297b4-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="297b4-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="297b4-113">Modification d’un appareil de conférence</span><span class="sxs-lookup"><span data-stu-id="297b4-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="297b4-114">Pour modifier les valeurs de propriétés d’un appareil de conférence existant, utilisez l’applet de passe **Set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="297b4-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="297b4-115">Par exemple, la commande suivante met à jour le numéro de téléphone (LineUri) associé à un appareil de conférence:</span><span class="sxs-lookup"><span data-stu-id="297b4-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="297b4-116">Pour plus d’informations, consultez les rubriques d’aide de l’applet de connexion [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) et de l’applet de connexion [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="297b4-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

