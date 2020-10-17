---
title: 'Lync Server 2013 : routage des appels E9-1-1 à l’aide d’une passerelle ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a3fb7a36680ff3ef35de44d53fc10a676d46242
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511241"
---
# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a><span data-ttu-id="13b6e-102">Routage des appels E9-1-1 à l’aide d’une passerelle ELIN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="13b6e-102">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="13b6e-103">_**Dernière modification de la rubrique :** 2013-02-05_</span><span class="sxs-lookup"><span data-stu-id="13b6e-103">_**Topic Last Modified:** 2013-02-05_</span></span>

<span data-ttu-id="13b6e-104">Certains partenaires dans le programme d’interopérabilité ouverte des communications unifiées fournissent des passerelles ELIN (Emergency Location Identification Number) certifiées, qui peuvent servir d’alternative à une connexion de jonction SIP à un fournisseur de services E9-1-1 certifié.</span><span class="sxs-lookup"><span data-stu-id="13b6e-104">Some partners in the Unified Communications Open Interoperability Program provide qualified Emergency Location Identification Number (ELIN)-capable gateways, which can serve as an alternative to a SIP trunk connection to a qualified E9-1-1 service provider.</span></span> <span data-ttu-id="13b6e-105">Les passerelles ELIN prennent en charge la connectivité RNIS ou CAMA (Centralized Automatic Message Accounting) aux services E9-1-1 basé sur le réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="13b6e-105">ELIN gateways support ISDN or Centralized Automatic Message Accounting (CAMA) connectivity to public switched telephone network (PSTN)-based E9-1-1 services.</span></span> <span data-ttu-id="13b6e-106">Pour plus d’informations sur les partenaires qui fournissent des passerelles ELIN et des liens vers leurs documents, reportez-vous à [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425) .</span><span class="sxs-lookup"><span data-stu-id="13b6e-106">For details about partners who provide ELIN gateways and links to their documentation, see [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).</span></span>

<span data-ttu-id="13b6e-107">Comme les connexions de jonction SIP aux fournisseurs de services E9-1-1, les passerelles ELIN permettent également de router un appel d’urgence vers le point de réponse publique (PSAPI) le plus approprié de l’appelant, mais ces passerelles utilisent un ELIN comme identificateur d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="13b6e-107">Like SIP trunk connections to E9-1-1 service providers, ELIN gateways also provide the means of routing an emergency call to the caller's most appropriate Public Safety Answering Point (PSAP), but these gateways use an ELIN as the location identifier.</span></span> <span data-ttu-id="13b6e-108">Vous définissez numéros pour chaque lieu de réponse d’urgence (ERL) de votre organisation (pour plus d’informations, consultez la rubrique [Managing locations for Elin Gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span><span class="sxs-lookup"><span data-stu-id="13b6e-108">You define ELINs for each Emergency Response Location (ERL) in your organization (for details, see [Managing locations for ELIN gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).</span></span>

<span data-ttu-id="13b6e-109">Lorsque vous utilisez une passerelle ELIN pour les appels d’urgence, vous utilisez la même infrastructure Lync Server E9-1-1 que vous utiliserez pour une connexion de jonction SIP.</span><span class="sxs-lookup"><span data-stu-id="13b6e-109">When you use an ELIN gateway for emergency calls, you use the same Lync Server E9-1-1 infrastructure that you would use for a SIP trunk connection.</span></span> <span data-ttu-id="13b6e-110">Autrement dit, la base de données du service informations d’emplacement fournit l’emplacement au client Lync Server, et la stratégie d’emplacement active la fonctionnalité et définit le routage.</span><span class="sxs-lookup"><span data-stu-id="13b6e-110">That is, the Location Information service database provides the location to the Lync Server client, and the location policy enables the feature and defines the routing.</span></span> <span data-ttu-id="13b6e-111">Toutefois, avec une passerelle ELIN, vous devez ajouter le numéros à la base de données du service informations d’emplacement et faire en sorte que votre opérateur RTC les télécharge dans la base de données ALI (Automatic location identification).</span><span class="sxs-lookup"><span data-stu-id="13b6e-111">With an ELIN gateway, however, you need to add the ELINs to the Location Information service database and have your PSTN carrier upload them to the Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="13b6e-112">Lorsqu’un client Lync obtient son emplacement à partir du service d’informations d’emplacement, l’emplacement inclut le ELIN.</span><span class="sxs-lookup"><span data-stu-id="13b6e-112">When a Lync client obtains its location from the Location Information service, the location includes the ELIN.</span></span> <span data-ttu-id="13b6e-113">Pendant un appel d’urgence, le ELIN est inclus avec l’emplacement envoyé à la passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="13b6e-113">During an emergency call, the ELIN is included with the location sent to the ELIN gateway.</span></span> <span data-ttu-id="13b6e-114">La passerelle ELIN identifie l’appel comme un appel d’urgence et permute le numéro de l’appelant avec le ELIN.</span><span class="sxs-lookup"><span data-stu-id="13b6e-114">The ELIN gateway identifies the call as an emergency call and swaps the calling party's number with the ELIN.</span></span> <span data-ttu-id="13b6e-115">La passerelle ELIN achemine ensuite l’appel vers le RTC avec le ELIN comme numéro d’appel.</span><span class="sxs-lookup"><span data-stu-id="13b6e-115">The ELIN gateway then routes the call to the PSTN with the ELIN as the calling number.</span></span> <span data-ttu-id="13b6e-116">Le fournisseur PSTN E9-1-1 recherche le ELIN dans la base de données ALI, qui est une base de données associée à la base de données de guide des adresses principales (MSAG).</span><span class="sxs-lookup"><span data-stu-id="13b6e-116">The PSTN E9-1-1 provider looks up the ELIN in the ALI database, which is a companion database to the Master Street Address Guide (MSAG) database.</span></span> <span data-ttu-id="13b6e-117">Le RTC envoie ensuite l’appel au site PSAPI le plus approprié en fonction de la recherche ALI, et le PSAPI envoie d’abord des répondeurs à l’emplacement de l’appelant en fonction de la recherche ALI.</span><span class="sxs-lookup"><span data-stu-id="13b6e-117">The PSTN then sends the call to the most appropriate PSAP based on the ALI lookup, and the PSAP sends first responders to the caller's location based on the ALI lookup.</span></span> <span data-ttu-id="13b6e-118">Le numéro d’appel est mis en cache sur la passerelle ELIN pour une durée prédéfinie pour les rappels.</span><span class="sxs-lookup"><span data-stu-id="13b6e-118">The calling number is cached on the ELIN gateway for a predefined amount of time for callbacks.</span></span> <span data-ttu-id="13b6e-119">Au cours d’un rappel, le PSAPI atteint la passerelle ELIN, qui permute le ELIN pour le numéro DID (direct Inward dialing) de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="13b6e-119">During a callback, the PSAP reaches the ELIN gateway, which swaps the ELIN for the caller's direct inward dialing (DID) number.</span></span>

<span data-ttu-id="13b6e-120">Les passerelles ELIN prennent en charge les appels d’urgence provenant uniquement du réseau de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="13b6e-120">ELIN gateways support emergency calls only from within your organization's network.</span></span> <span data-ttu-id="13b6e-121">Elles ne prennent pas en charge ceux passés en dehors de votre réseau.</span><span class="sxs-lookup"><span data-stu-id="13b6e-121">They do not support emergency calls made from outside your network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="13b6e-122">Pour plus d’informations sur l’utilisation d’une connexion de jonction SIP pour les appels d’urgence, voir <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">routage des appels E9-1-1 à l’aide d’une jonction SIP dans Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="13b6e-122">For details about using a SIP trunk connection for emergency calls, see <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="13b6e-123">Le diagramme suivant montre comment un appel d’urgence est acheminé de Lync Server vers PSAPI lorsque vous utilisez une passerelle ELIN.</span><span class="sxs-lookup"><span data-stu-id="13b6e-123">The following diagram shows how an emergency call is routed from Lync Server to the PSAP when you use an ELIN gateway.</span></span>

<span data-ttu-id="13b6e-124">**Routage des appels E9-1-1 vers une passerelle ELIN**</span><span class="sxs-lookup"><span data-stu-id="13b6e-124">**Routing E9-1-1 calls with an ELIN gateway**</span></span>

<span data-ttu-id="13b6e-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span><span class="sxs-lookup"><span data-stu-id="13b6e-125">![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")</span></span>

1.  <span data-ttu-id="13b6e-126">Une INVITE SIP INVITE contenant l’emplacement, le numéro de rappel de l’appelant et l’URL de notification (facultatif) et le numéro de rappel de conférence est acheminée vers Lync Server.</span><span class="sxs-lookup"><span data-stu-id="13b6e-126">A SIP INVITE containing the location, the caller's callback number, and the (optional) Notification URL and conference callback number is routed to Lync Server.</span></span>

2.  <span data-ttu-id="13b6e-127">Lync Server correspond au numéro d’urgence, puis achemine l’appel (en fonction de la valeur d' **utilisation PSTN** définie dans la stratégie d’emplacement applicable) vers un serveur de médiation et de là, vers une passerelle Elin.</span><span class="sxs-lookup"><span data-stu-id="13b6e-127">Lync Server matches the emergency number and then routes the call (based on the **PSTN Usage** value defined in the applicable location policy) to a Mediation Server, and from there to an ELIN gateway.</span></span>

3.  <span data-ttu-id="13b6e-128">La passerelle ELIN achemine l’appel via une jonction RNIS ou CAMA vers le réseau téléphonique commuté.</span><span class="sxs-lookup"><span data-stu-id="13b6e-128">The ELIN gateway routes the call over an ISDN or CAMA trunk to the PSTN.</span></span>

4.  <span data-ttu-id="13b6e-p106">Le réseau téléphonique commuté identifie l’appel comme un appel d’urgence et l’achemine vers un routeur sélectif E9-1-1 du réseau. Le routeur sélectif E9-1-1 recherche le numéro de l’appelant dans la base de données ALI afin d’obtenir l’emplacement géographique correspondant. Le routeur sélectif E9-1-1 envoie l’appel au centre PSAP le plus approprié en fonction des informations d’emplacement récupérées à partir de la base de données ALI.</span><span class="sxs-lookup"><span data-stu-id="13b6e-p106">The PSTN identifies the call as an emergency call and routes it to an E9-1-1 selective router in the network. The E9-1-1 selective router looks up the caller's number in the ALI database to obtain the geographical location. The E9-1-1 selective router sends the call to the most appropriate PSAP based on the location information that was retrieved from the ALI database.</span></span>

5.  <span data-ttu-id="13b6e-132">Si vous avez configuré la stratégie d’emplacement pour les notifications, un ou plusieurs responsables de la sécurité de votre organisation reçoivent un message instantané spécial de notification d’urgence Lync.</span><span class="sxs-lookup"><span data-stu-id="13b6e-132">If you configured the location policy for notifications, one or more of your organization’s security officers are sent a special Lync emergency notification instant message.</span></span> <span data-ttu-id="13b6e-133">Ce message apparaît toujours sur leur écran et contient le nom, le numéro de téléphone, l’heure et l’emplacement de l’appelant, ce qui permet au personnel chargé de la sécurité de répondre rapidement à l’appel d’urgence par un message instantané ou vocal.</span><span class="sxs-lookup"><span data-stu-id="13b6e-133">This message always pops up on the security officers’ screen(s) and contains the caller’s name, phone number, time, and location, enabling security personnel to quickly respond to the emergency caller by using an instant message or voice.</span></span>

6.  <span data-ttu-id="13b6e-p108">Si l’appel est interrompu prématurément, le centre d’appels de la sécurité publique utilise le numéro d’identification de l’emplacement en cas d’urgence pour contacter l’appelant directement. La passerelle ELIN remplace le numéro d’identification de l’emplacement en cas d’urgence par le numéro SDA (sélection directe à l’arrivée).</span><span class="sxs-lookup"><span data-stu-id="13b6e-p108">If the call is broken prematurely, the PSAP uses the ELIN to contact the caller directly. The ELIN gateway swaps the ELIN for the caller's DID.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

