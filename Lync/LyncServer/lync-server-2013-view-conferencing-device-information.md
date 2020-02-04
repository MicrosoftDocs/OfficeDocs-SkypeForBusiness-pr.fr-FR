---
title: 'Lync Server 2013 : afficher les informations de périphérique de conférence'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing device information
ms:assetid: 838bdbf8-8b68-4eb6-8fa3-45bfd5b0b1cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994043(v=OCS.15)
ms:contentKeyID: 51803954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5355ae418e53c44cc61340b57910993ac2afea2c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-device-information-in-lync-server-2013"></a><span data-ttu-id="20391-102">Afficher les informations de périphérique de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20391-102">View conferencing device information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20391-103">_**Dernière modification de la rubrique :** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="20391-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="20391-104">Vous pouvez afficher des informations sur les appareils de conférence configurés pour une utilisation au sein de votre organisation à l’aide de Windows PowerShell et de l’applet **de passe Get-CsMeetingRoom** .</span><span class="sxs-lookup"><span data-stu-id="20391-104">You can view information about the conferencing devices configured for use in your organization by using Windows PowerShell and the **Get-CsMeetingRoom** cmdlet.</span></span> <span data-ttu-id="20391-105">Exécutez l’applet de commande **Get-CsMeetingRoom** à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20391-105">Run the **Get-CsMeetingRoom** cmdlet from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="20391-106">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».</span><span class="sxs-lookup"><span data-stu-id="20391-106">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<span data-ttu-id="20391-107">Si vous utilisez l’applet de passe **Get-CsMeetingRoom** sans aucun paramètre, elle renvoie des informations sur tous vos périphériques de conférence.</span><span class="sxs-lookup"><span data-stu-id="20391-107">If you use the **Get-CsMeetingRoom** cmdlet without any parameters, it returns information about all your conferencing devices.</span></span> <span data-ttu-id="20391-108">Les paramètres facultatifs permettent de filtrer les informations de différentes manières.</span><span class="sxs-lookup"><span data-stu-id="20391-108">Optional parameters provide different ways for you to filter information.</span></span> <span data-ttu-id="20391-109">Pour plus d’informations, consultez la section paramètres de [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span><span class="sxs-lookup"><span data-stu-id="20391-109">For details, see the Parameters section of [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom).</span></span>

<div>


<div>

## <a name="viewing-information-about-all-your-conferencing-devices"></a><span data-ttu-id="20391-110">Affichage d’informations sur tous vos périphériques de conférence</span><span class="sxs-lookup"><span data-stu-id="20391-110">Viewing Information about All Your Conferencing Devices</span></span>

  - <span data-ttu-id="20391-111">Pour afficher les détails de tous vos appareils de conférence, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée :</span><span class="sxs-lookup"><span data-stu-id="20391-111">To view details about all your conferencing devices, type the following command in the Lync Server Management Shell, and then press Enter:</span></span>
    
        Get-CsMeetingRoom
    
    <span data-ttu-id="20391-112">Cette applet de commande renvoie des informations similaires à ce qui suit pour chaque appareil de conférence.</span><span class="sxs-lookup"><span data-stu-id="20391-112">This cmdlet returns information similar to the following for each conferencing device.</span></span> <span data-ttu-id="20391-113">Notez que l’exemple ci-après illustre les informations que vous verrez lors de l’exécution de cette cmdlet :</span><span class="sxs-lookup"><span data-stu-id="20391-113">Note that this example shows only some of the information that you’ll see when you run this cmdlet:</span></span>
    
        ContactOptionFlags                : 64
        OwnerUrn                          : urn:device:roomsystem
        OriginatorSid                     :
        SamAccountName                    : room12129
        UserPrincipalName                 : room1219@litwareinc.com
        FirstName                         : 
        LastName                          :
        WindowsEmailAddress               :
        Sid                               : S-1-5-21-2831376166-2963252556-2165051629-1257
        LineServerURI                     :
        AudioVideoDisabled                : False
        IPPBXSoftPhoneRoutingEnabled      : False
        RemoteCallControlTelephonyEnabled : False
        PrivateLine                       :
        AcpInfo                           : {}
        HostedVoiceMail                   :
        DisplayName                       : Room 1219

</div>

<div>

## <a name="viewing-information-about-a-specific-conferencing-device"></a><span data-ttu-id="20391-114">Affichage d’informations sur un appareil de conférence spécifique</span><span class="sxs-lookup"><span data-stu-id="20391-114">Viewing Information about a Specific Conferencing Device</span></span>

  - <span data-ttu-id="20391-115">Pour afficher des informations pour un appareil de conférence spécifique, incluez le paramètre Identity suivi de l’identité de l’appareil de conférence (en général, le nom d’affichage Active Directory).</span><span class="sxs-lookup"><span data-stu-id="20391-115">To view information for a specific conferencing device, include the Identity parameter followed by the conferencing device identity (typically, the Active Directory display name).</span></span> <span data-ttu-id="20391-116">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="20391-116">For example:</span></span>
    
        Get-CsMeetingRoom -Identity "Room 1219"

</div>

<span data-ttu-id="20391-117">Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) .</span><span class="sxs-lookup"><span data-stu-id="20391-117">For details, see the Help topic for the [Get-CsMeetingRoom](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingRoom) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

