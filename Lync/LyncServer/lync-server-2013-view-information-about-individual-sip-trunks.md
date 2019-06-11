---
title: 'Lync Server 2013: afficher des informations sur les Trunks SIP individuels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c7d29c7318c8fb6d1cd08775853eb46b1c898d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="fc0f0-102">Afficher des informations sur les lignes SIP individuelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc0f0-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc0f0-103">_**Dernière modification de la rubrique:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fc0f0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fc0f0-104">Les Trunks SIP sont utilisés pour connecter le réseau téléphonique de Lync Server 2013 voix sur IP avec le réseau téléphonique public commuté.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="fc0f0-105">Dans la version précédente du produit, les Trunks permettaient le routage des appels sortants d’un serveur de médiation vers une passerelle RTC et chaque passerelle était limitée à un seul Trunk.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="fc0f0-106">Par conséquent, une passerelle RTC et un Trunk SIP étaient essentiellement identiques.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="fc0f0-107">Pour les administrateurs, cela signifie qu’ils pouvaient afficher les informations relatives à une ligne SIP individuelle en consultant les informations relatives à la passerelle RTC associée.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="fc0f0-108">Dans Lync Server 2013, il est possible que plusieurs Trunks puissent désormais être attribuées à une seule passerelle PSTN; Cela signifie que les passerelles et les liaisons ne sont plus une seule et même.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="fc0f0-109">Cela signifie que les administrateurs doivent utiliser la nouvelle applet de commande [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur un Trunk SIP individuel.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="fc0f0-110">Vous pouvez exécuter l’applet de commande Get-CsTrunk à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fc0f0-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fc0f0-111">Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».</span><span class="sxs-lookup"><span data-stu-id="fc0f0-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="fc0f0-112">Pour afficher des informations sur toutes vos jonctions SIP</span><span class="sxs-lookup"><span data-stu-id="fc0f0-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="fc0f0-113">La commande suivante retourne des informations relatives à toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="fc0f0-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="fc0f0-114">Pour afficher les informations relatives à une jonction SIP spécifique</span><span class="sxs-lookup"><span data-stu-id="fc0f0-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="fc0f0-115">La commande suivante retourne uniquement les informations relatives à la jonction SIP ayant l’identité PstnGateway 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="fc0f0-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="fc0f0-116">Affichage des informations pour toutes les lignes SIP attribuées à un pool</span><span class="sxs-lookup"><span data-stu-id="fc0f0-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="fc0f0-117">Dans cet exemple, les informations relatives à toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com sont retournées :</span><span class="sxs-lookup"><span data-stu-id="fc0f0-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

