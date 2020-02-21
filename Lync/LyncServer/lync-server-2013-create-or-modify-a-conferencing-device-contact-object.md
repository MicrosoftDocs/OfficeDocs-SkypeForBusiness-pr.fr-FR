---
title: 'Lync Server 2013 : création ou modification d’un objet contact de l’appareil de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing device Contact object
ms:assetid: 62ed64be-379c-417d-9453-511881cf5604
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994035(v=OCS.15)
ms:contentKeyID: 51803945
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74808a2deae4f7fa52e1a48fcbd415205eca93cf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-device-contact-object-in-lync-server-2013"></a><span data-ttu-id="3900c-102">Création ou modification d’un objet contact de périphérique de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3900c-102">Create or modify a conferencing device Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3900c-103">_**Dernière modification de la rubrique :** 2013-10-02_</span><span class="sxs-lookup"><span data-stu-id="3900c-103">_**Topic Last Modified:** 2013-10-02_</span></span>

<span data-ttu-id="3900c-104">Pour créer un objet de salle de conférence, commencez par créer un compte d’utilisateur Active Directory pour représenter l’appareil.</span><span class="sxs-lookup"><span data-stu-id="3900c-104">To create a conferencing room object, first create an Active Directory user account to represent the device.</span></span> <span data-ttu-id="3900c-105">Ensuite, utilisez l’applet de commande **Enable-CsMeetingRoom** pour permettre à ce compte de fonctionner en tant que périphérique de conférence.</span><span class="sxs-lookup"><span data-stu-id="3900c-105">Then, use the **Enable-CsMeetingRoom** cmdlet to enable that account to function as a conferencing device.</span></span> <span data-ttu-id="3900c-106">Si vous devez modifier les propriétés d’un périphérique de conférence existant, utilisez la cmdlet **Set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="3900c-106">If you need to change the properties of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span>

<span data-ttu-id="3900c-107">Ces applets de commande peuvent être exécutées à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3900c-107">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3900c-108">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="3900c-108">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>


<div>

## <a name="creating-a-conferencing-device"></a><span data-ttu-id="3900c-109">Création d’un périphérique de conférence</span><span class="sxs-lookup"><span data-stu-id="3900c-109">Creating a Conferencing Device</span></span>

  - <span data-ttu-id="3900c-110">Une fois que vous avez créé le compte d’utilisateur Active Directory qui représente le nouveau périphérique de conférence, activez-le à l’aide de la cmdlet **Enable-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="3900c-110">After you create the Active Directory user account that represents the new conferencing device, enable it by using the **Enable-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="3900c-111">N’oubliez pas d’inclure a) l’identité de l’appareil de conférence, b) le pool de serveurs d’inscriptions dans lequel le compte de salle sera hébergé et c, l’adresse SIP à attribuer à ce compte.</span><span class="sxs-lookup"><span data-stu-id="3900c-111">Be sure to include a) the conferencing device identity, b) the registrar pool where the room account will be homed, and c) the SIP address to be assigned to that account.</span></span> <span data-ttu-id="3900c-112">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="3900c-112">For example:</span></span>
    
        Enable-CsMeetingRoom -Identity "Redmond Conferencing device" -RegistrarPool "atl-cs-001.litwareinc.com" -SipAddress "sip:RedmondMeetingRoom@litwareinc.com"

</div>

<div>

## <a name="modifying-a-conferencing-device"></a><span data-ttu-id="3900c-113">Modification d’un périphérique de conférence</span><span class="sxs-lookup"><span data-stu-id="3900c-113">Modifying a Conferencing Device</span></span>

  - <span data-ttu-id="3900c-114">Pour modifier les valeurs des propriétés d’un périphérique de conférence existant, utilisez la cmdlet **Set-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="3900c-114">To modify the property values of an existing conferencing device, use the **Set-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="3900c-115">Par exemple, la commande suivante met à jour le numéro de téléphone (LineUri) associé à un périphérique de conférence :</span><span class="sxs-lookup"><span data-stu-id="3900c-115">For example, the following command updates the phone number (LineUri) associated with a conferencing device:</span></span>
    
        Set-CsMeetingRoom -Identity "Redmond Conferencing device" -LineUri "tel:+12065551219"

</div>

<span data-ttu-id="3900c-116">Pour plus d’informations, reportez-vous aux rubriques d’aide pour la cmdlet [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) et la cmdlet [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="3900c-116">For details, see the Help topics for the [Enable-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Enable-CsMeetingRoom) cmdlet and the [Set-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Set-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

