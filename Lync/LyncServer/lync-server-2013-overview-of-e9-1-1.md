---
title: 'Lync Server 2013 : Vue d’ensemble du service E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of E9-1-1
ms:assetid: c01e6774-bc9f-4c5b-a60b-478b7317b2b7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412936(v=OCS.15)
ms:contentKeyID: 48185290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48b261ed0b173c85ccd076be14d65aa456558830
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="051af-102">Vue d’ensemble du service E9-1-1 dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="051af-102">Overview of E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="051af-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="051af-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="051af-104">Microsoft Lync Server 2013 prend en charge les appels Enhanced 9-1-1 (E9-1-1) à partir des clients Lync et des appareils Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="051af-104">Microsoft Lync Server 2013 supports Enhanced 9-1-1 (E9-1-1) calling from Lync clients and Lync Phone Edition devices.</span></span> <span data-ttu-id="051af-105">Lorsque vous configurez Lync Server pour E9-1-1, les appels d’urgence placés dans Lync 2013 ou Lync Phone Edition incluent des informations de lieu de réponse d’urgence de la base de données de service des informations d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="051af-105">When you configure Lync Server for E9-1-1, emergency calls placed from Lync 2013 or Lync Phone Edition include Emergency Response Location (ERL) information from the Location Information service database.</span></span> <span data-ttu-id="051af-106">ERLs se compose d’adresses postales et d’autres informations qui vous permettent d’identifier un emplacement plus précis dans les bâtiments d’Office et dans d’autres installations mutualisées.</span><span class="sxs-lookup"><span data-stu-id="051af-106">ERLs consist of civic (that is, street) addresses and other information that helps to identify a more precise location in office buildings and other multitenant facilities.</span></span> <span data-ttu-id="051af-107">Lorsqu’un utilisateur effectue un appel d’urgence, Lync Server route le son de l’appel, ainsi que les informations d’emplacement et de rappel, par le biais d’un serveur de médiation vers un fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="051af-107">When a user makes an emergency call, Lync Server routes the call audio, along with the location and callback information, through a Mediation Server to an E9-1-1 service provider.</span></span> <span data-ttu-id="051af-108">Le prestataire de services E9-1-1 utilise l’adresse postale de l’appelant pour acheminer l’appel vers le point d’accès de la sécurité publique (PSAPI) qui répond à l’emplacement de l’appelant, et il envoie une clé de requête de service d’urgence (ESQK), utilisée par le PSAPI pour rechercher le son de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="051af-108">The E9-1-1 service provider uses the civic address of the caller to route the call to the Public Safety Answering Point (PSAP) that serves the caller's location, and sends along an Emergency Service Query Key (ESQK) that the PSAP uses to look up the caller's ERL.</span></span>

<span data-ttu-id="051af-109">Lync Server prend en charge deux méthodes de routage des appels d’urgence vers un fournisseur de services E9-1-1 :</span><span class="sxs-lookup"><span data-stu-id="051af-109">Lync Server supports two methods for routing emergency calls to an E9-1-1 service provider:</span></span>

  - <span data-ttu-id="051af-110">une connexion de jonction SIP (Session Initiation Protocol) vers un fournisseur de services E9-1-1 certifié ;</span><span class="sxs-lookup"><span data-stu-id="051af-110">A Session Initiation Protocol (SIP) trunk connection to a qualified E9-1-1 service provider</span></span>

  - <span data-ttu-id="051af-111">une passerelle ELIN (Emergency Location Identification Number) vers un fournisseur de services E9-1-1 du réseau téléphonique commuté (RTC).</span><span class="sxs-lookup"><span data-stu-id="051af-111">An Emergency Location Identification Number (ELIN) gateway to a public switched telephone (PSTN)-based E9-1-1 service provider</span></span>

<span data-ttu-id="051af-112">Lorsque vous utilisez un fournisseur de services SIP Trunk E9-1-1, vous ajoutez ERLs à la base de données de service d’information d’emplacement, puis vous validez les emplacements par rapport au Guide d’adresses du maître d’adresses (MSAG) qui est géré par le fournisseur de service E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="051af-112">When you use a SIP trunk E9-1-1 service provider, you add ERLs to the Location Information service database, and then validate the locations against a Master Street Address Guide (MSAG) that is maintained by the E9-1-1 service provider.</span></span> <span data-ttu-id="051af-113">Si un fournisseur de services E9-1-1 reçoit un appel sans informations d’emplacement ou avec un emplacement non validé par rapport à la base de données MSAG, il achemine l’appel vers un centre national/régional d’intervention en cas d’appels d’urgence (ECRC), où un personnel spécialement formé essaie d’obtenir par téléphone l’emplacement précis de l’appelant, puis achemine manuellement l’appel vers le centre PSAP approprié.</span><span class="sxs-lookup"><span data-stu-id="051af-113">If an E9-1-1 service provider receives a call that doesn’t have location information or has a location that has not been validated against the MSAG, the E9-1-1 service provider routes the call to a national/regional Emergency Call Response Center (ECRC), which is staffed with specially trained personnel who verbally obtain the caller’s location, if possible, and manually route the call to the appropriate PSAP.</span></span> <span data-ttu-id="051af-114">(Certains fournisseurs de services E9-1-1 de jonction SIP transmettent également aux clients un numéro SDA (sélection directe à l’arrivée) RTC vers le centre ECRC, qui offre un autre moyen d’acheminer les appels 9-1-1 si la jonction SIP échoue pour une raison quelconque.)</span><span class="sxs-lookup"><span data-stu-id="051af-114">(Some SIP trunk E9-1-1 service providers also provide customers with a PSTN direct inward dialing (DID) number to the ECRC, which provides an alternate means of routing 9-1-1 calls, if the SIP trunk fails for any reason.)</span></span>

<span data-ttu-id="051af-115">Contrairement aux téléphones PBX (Time Division Multiplexing) et aux téléphones PBX (PBX) sur IP, qui ont des emplacements fixes, un point de terminaison Lync peut être très mobile.</span><span class="sxs-lookup"><span data-stu-id="051af-115">Unlike time division multiplexing (TDM) and IP-based private branch exchange (PBX) phones, which have fixed locations, a Lync endpoint can be very mobile.</span></span> <span data-ttu-id="051af-116">Lorsque vous déployez la fonctionnalité E9-1-1, Lync Server vous permet de vérifier qu’il n’y a aucune information sur l’appelant, l’appel d’urgence peut être acheminé vers le PSAPI qui dessert l’emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="051af-116">When you deploy the E9-1-1 feature, Lync Server helps to ensure that no matter where a caller is located, the emergency call can be routed to the PSAP that serves the caller’s location.</span></span> <span data-ttu-id="051af-117">Par exemple, si un utilisateur travaille habituellement au siège social de sa société situé à Redmond (Washington), mais qu’il effectue un appel d’urgence à partir d’un ordinateur installé dans la succursale de Wichita (Kansas), le fournisseur de services E9-1-1 de réseau RTC ou de jonction SIP achemine l’appel vers le centre téléphonique de sécurité publique de Wichita et non celui de Redmond.</span><span class="sxs-lookup"><span data-stu-id="051af-117">For example, if a user’s main office is located in Redmond, Washington, but the user places an emergency call from a computer in a branch office in Wichita, Kansas, the SIP trunk or PSTN-based E9-1-1 service provider will route the call to the PSAP in Wichita, not to the PSAP in Redmond.</span></span>

<span data-ttu-id="051af-118">Lorsque vous utilisez une passerelle ELIN, vous ajoutez également ERLs à la base de données de service des informations d’emplacement, mais vous incluez également un numéro ELIN pour chaque emplacement.</span><span class="sxs-lookup"><span data-stu-id="051af-118">When you use an ELIN gateway, you also add ERLs to the Location Information service database, but you include also an ELIN number for each location.</span></span> <span data-ttu-id="051af-119">Ce numéro devient le numéro d’appel d’urgence durant l’appel d’urgence.</span><span class="sxs-lookup"><span data-stu-id="051af-119">The ELIN number becomes the emergency calling number during the emergency call.</span></span> <span data-ttu-id="051af-120">Vous devez alors vous assurer que votre opérateur RTC télécharge les numéros ELIN vers la base de données ALI (Automatic Location Identification.</span><span class="sxs-lookup"><span data-stu-id="051af-120">You must then make sure that your PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="051af-121">Les appareils analogiques connectés à Lync ne peuvent pas recevoir les informations d’emplacement du service d’information d’emplacement ou transmettre l’emplacement au fournisseur de services E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="051af-121">Lync-connected analog devices cannot receive location information from the Location Information service or transmit location to the E9-1-1 service provider.</span></span> <span data-ttu-id="051af-122">Si vous faites appel à un fournisseur de services E9-1-1 de jonction SIP et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous avez deux options :</span><span class="sxs-lookup"><span data-stu-id="051af-122">If you use the SIP trunk E9-1-1 service provider option and need to support E9-1-1 from analog phones, you have two options:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="051af-123"><STRONG></STRONG>&nbsp;Option&nbsp;PS&nbsp;-Ali classique si vous avez des passerelles RTC locales sur chaque site sur lequel sont déployés les téléphones analogiques et chaque téléphone analogique, vous pouvez configurer la localisation de l’appareil analogique directement auprès d’un fournisseur de services PS-Ali.</span><span class="sxs-lookup"><span data-stu-id="051af-123"><STRONG>Traditional PS-ALI option</STRONG>&nbsp;&nbsp;&nbsp;If you have local PSTN gateways at each site where analog phones are deployed and each analog phone has a DID, you can provision the analog device’s location directly with a Private Switch/Automatic Location Identification (PS-ALI) service provider.</span></span> <span data-ttu-id="051af-124">Dans ce cas, vous devez configurer des stratégies de voix Lync spécialement conçues et les affecter aux objets de contact de l’appareil analogique de sorte que les appels E9-1-1 à partir de ces téléphones soient acheminés directement par l’intermédiaire de la passerelle locale vers le fournisseur RTC qui service le site (au lieu de router le appel vers un E9-1-1 fournisseur de services SIP Trunk).</span><span class="sxs-lookup"><span data-stu-id="051af-124">In this case, you configure specially-crafted Lync voice policies and assign them to the analog device contact objects so that E9-1-1 calls from those phones route directly through the local gateway to the PSTN provider that services the site (instead of routing the call to an E9-1-1 service provider SIP trunk).</span></span> <span data-ttu-id="051af-125">Lorsqu’un appel d’urgence est passé, une base de données d’un fournisseur PS-ALI associé à la jonction RTC mappe le numéro SDA de chaque téléphone analogique à un emplacement physique et fournit cet emplacement au centre PSAP.</span><span class="sxs-lookup"><span data-stu-id="051af-125">When an emergency call is placed, a database at a PS-ALI provider that is associated with the PSTN trunk maps the DID of each analog phone to a physical location and provides this location to the PSAP.</span></span> <span data-ttu-id="051af-126">Ces enregistrements doivent être mis à jour avec le fournisseur de services PS-ALI chaque fois que les téléphones changent d’ERL.</span><span class="sxs-lookup"><span data-stu-id="051af-126">These records must be updated with the PS-ALI service provider every time phones are moved to different ERLs.</span></span></P>
> <LI>
> <P><span data-ttu-id="051af-127"><STRONG></STRONG>&nbsp;Option&nbsp;de&nbsp;prestataire de services E9-1-1 vous pouvez inscrire le téléphone DIDS et son ERLs correspondant auprès du prestataire de services E9-1-1, s’il est pris en charge par le fournisseur de service E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="051af-127"><STRONG>E9-1-1 service provider option</STRONG>&nbsp;&nbsp;&nbsp;You can register the analog phone DIDs and their corresponding ERLs with the E9-1-1 service provider, if this is supported by the E9-1-1 service provider.</span></span> <span data-ttu-id="051af-128">Si le fournisseur reçoit un appel de Lync Server qui n’inclut pas de données PIDF-Low, le fournisseur peut voir s’il existe une correspondance de base de données sur le numéro DID de la personne qui appelle.</span><span class="sxs-lookup"><span data-stu-id="051af-128">If the provider receives a call from Lync Server that doesn’t include PIDF-LO data, the provider can see if there is a database match on the calling party’s DID number.</span></span> <span data-ttu-id="051af-129">En utilisant la propriété ERL Récupérée de sa base de données, le fournisseur peut automatiquement diriger l’appel d’urgence vers le champ PSAPI approprié, et le champ PSAPI reçoit le message de la part de l’appareil analogique et un enregistrement ESQK qui permet au répartiteur de Rechercher l’emplacement de l’appelant.</span><span class="sxs-lookup"><span data-stu-id="051af-129">By using the ERL retrieved from its database, the provider can automatically route the emergency call to the correct PSAP, and the PSAP will receive the DID of the analog device and an ESQK record that allows the dispatcher to lookup the caller’s location.</span></span></P></LI></UL><span data-ttu-id="051af-p108">Si vous utilisez l’option de passerelle ELIN et souhaitez permettre l’utilisation de la fonction E9-1-1 à partir de téléphones analogiques, vous pouvez configurer l’emplacement du périphérique analogique directement avec le fournisseur de services PS-ALI, comme décrit dans la première option ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="051af-p108">If you use the ELIN gateway option and need to support E9-1-1 from analog phones, you can provision the analog device's location directly with the PS-ALI service provider, as described in the first option above.    </span></span></div>

<span data-ttu-id="051af-131">Du point de vue du serveur Lync, le processus E9-1-1 peut être divisé en deux étapes :</span><span class="sxs-lookup"><span data-stu-id="051af-131">From a Lync Server perspective, the E9-1-1 process can be separated into two stages:</span></span>

  - <span data-ttu-id="051af-132">Étape 1 : acquisition d’un emplacement</span><span class="sxs-lookup"><span data-stu-id="051af-132">Stage 1: Acquiring a location</span></span>

  - <span data-ttu-id="051af-133">Étape 2 : acheminement de l’appel d’urgence vers un fournisseur de services E9-1-1</span><span class="sxs-lookup"><span data-stu-id="051af-133">Stage 2: Routing the emergency call to an E9-1-1 service provider</span></span>

<span data-ttu-id="051af-134">Cette section décrit le déroulement de ces deux étapes.</span><span class="sxs-lookup"><span data-stu-id="051af-134">This section describes how these stages work.</span></span>

<span data-ttu-id="051af-135">Si vous souhaitez configurer votre infrastructure pour détecter automatiquement l’emplacement du client, vous devez d’abord décider quels éléments réseau vous utiliserez pour mapper les appelants aux emplacements.</span><span class="sxs-lookup"><span data-stu-id="051af-135">If you plan to configure your infrastructure to automatically detect client location, first you need to decide which network elements you will use to map callers to locations.</span></span> <span data-ttu-id="051af-136">Pour plus d’informations sur les options disponibles, voir [définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span><span class="sxs-lookup"><span data-stu-id="051af-136">For details about the possible options, see [Defining the network elements used to determine location in Lync Server 2013](lync-server-2013-defining-the-network-elements-used-to-determine-location.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="051af-137">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="051af-137">In This Section</span></span>

  - [<span data-ttu-id="051af-138">Acquisition d’un emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="051af-138">Acquiring a location in Lync Server 2013</span></span>](lync-server-2013-acquiring-a-location.md)

  - [<span data-ttu-id="051af-139">Routage des appels E9-1-1 avec une jonction SIP dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="051af-139">Routing E9-1-1 calls by using a SIP trunk in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md)

  - [<span data-ttu-id="051af-140">Routage des appels E9-1-1 via une passerelle ELIN dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="051af-140">Routing E9-1-1 calls by using an ELIN gateway in Lync Server 2013</span></span>](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

