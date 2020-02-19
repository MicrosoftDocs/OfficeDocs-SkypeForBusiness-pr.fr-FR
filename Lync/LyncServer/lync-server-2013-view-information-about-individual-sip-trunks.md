---
title: 'Lync Server 2013 : affichage des informations sur les jonctions SIP individuelles'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about individual SIP trunks
ms:assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721847(v=OCS.15)
ms:contentKeyID: 49733780
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bda72dbe9745ca49d90e28824ea11371fbc2c680
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-individual-sip-trunks-in-lync-server-2013"></a><span data-ttu-id="39f18-102">Afficher des informations sur les jonctions SIP individuelles dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="39f18-102">View information about individual SIP trunks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="39f18-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="39f18-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="39f18-104">Les jonctions SIP sont utilisées pour connecter le réseau téléphonique IP de Lync Server 2013 avec le réseau téléphonique commuté public.</span><span class="sxs-lookup"><span data-stu-id="39f18-104">SIP trunks are used to connect Lync Server 2013 Voice over IP phone network with the Public Switched Telephone Network.</span></span> <span data-ttu-id="39f18-105">Dans la version précédente du produit, les jonctions étaient utilisées pour acheminer les appels sortants d’un serveur de médiation vers une passerelle PSTN et chaque passerelle était limitée à une jonction unique.</span><span class="sxs-lookup"><span data-stu-id="39f18-105">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="39f18-106">Par conséquent, une passerelle PSTN et une jonction SIP étaient fondamentalement identiques.</span><span class="sxs-lookup"><span data-stu-id="39f18-106">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="39f18-107">Pour les administrateurs, cela signifie qu’ils pouvaient afficher des informations sur une jonction SIP individuelle en affichant simplement des informations sur la passerelle PSTN associée.</span><span class="sxs-lookup"><span data-stu-id="39f18-107">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>

<span data-ttu-id="39f18-108">Dans Lync Server 2013, toutefois, plusieurs jonctions peuvent désormais être attribuées à une seule passerelle PSTN ; Cela signifie que les passerelles et les jonctions ne sont plus de l’un et le même.</span><span class="sxs-lookup"><span data-stu-id="39f18-108">In Lync Server 2013, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="39f18-109">En retour, cela signifie que les administrateurs doivent utiliser la nouvelle cmdlet [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) pour afficher des informations sur une jonction SIP individuelle.</span><span class="sxs-lookup"><span data-stu-id="39f18-109">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/Get-CsTrunk) cmdlet in order to view information about an individual SIP trunk.</span></span>

<span data-ttu-id="39f18-110">La cmdlet Get-CsTrunk peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="39f18-110">The Get-CsTrunk cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="39f18-111">Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="39f18-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="39f18-112">Pour afficher les informations de toutes vos jonctions SIP</span><span class="sxs-lookup"><span data-stu-id="39f18-112">To view information for all your SIP trunks</span></span>

  - <span data-ttu-id="39f18-113">La commande suivante retourne des informations sur toutes les jonctions SIP utilisées dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="39f18-113">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
        Get-CsTrunk

</div>

<div>

## <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="39f18-114">Pour afficher les informations d’une jonction SIP spécifique</span><span class="sxs-lookup"><span data-stu-id="39f18-114">To view information for a specific SIP trunk</span></span>

  - <span data-ttu-id="39f18-115">Cette commande renvoie des informations uniquement pour la jonction SIP avec l’identité PstnGateway : 192.168.0.240 :</span><span class="sxs-lookup"><span data-stu-id="39f18-115">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
        Get-CsTrunk -Identity "PstnGateway:192.168.0.240"

</div>

<div>

## <a name="viewing-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="39f18-116">Affichage des informations pour toutes les jonctions SIP affectées à un pool</span><span class="sxs-lookup"><span data-stu-id="39f18-116">Viewing Information for All the SIP Trunks Assigned to a Pool</span></span>

  - <span data-ttu-id="39f18-117">Dans cet exemple, les informations sont renvoyées pour toutes les jonctions SIP affectées au pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="39f18-117">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

