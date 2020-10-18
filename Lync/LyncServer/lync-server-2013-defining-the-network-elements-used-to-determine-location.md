---
title: 'Lync Server 2013 : définition des éléments réseau utilisés pour déterminer l’emplacement'
description: 'Lync Server 2013 : définition des éléments réseau utilisés pour déterminer l’emplacement.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the network elements used to determine location
ms:assetid: 7538779d-055d-44ed-8dd7-11c45fc1b9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398567(v=OCS.15)
ms:contentKeyID: 48184508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a77ad0a7d704bf2cc43118db45d9bcfb89daa327
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576280"
---
# <a name="defining-the-network-elements-used-to-determine-location-in-lync-server-2013"></a><span data-ttu-id="3408c-103">Définition des éléments réseau utilisés pour déterminer l’emplacement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3408c-103">Defining the network elements used to determine location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3408c-104">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="3408c-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="3408c-105">Si vous configurez votre infrastructure Lync Server pour qu’elle prenne en charge la détection automatique de l’emplacement du client, vous devez d’abord décider des éléments réseau que vous allez utiliser pour mapper les appelants vers les emplacements.</span><span class="sxs-lookup"><span data-stu-id="3408c-105">If you are setting up your Lync Server infrastructure to support automatic client location detection, you first need to decide which network elements you are going to use to map callers to locations.</span></span> <span data-ttu-id="3408c-106">Dans Lync Server 2013, vous pouvez associer les éléments de réseau Layer 2 et Layer 3 suivants avec des emplacements :</span><span class="sxs-lookup"><span data-stu-id="3408c-106">In Lync Server 2013, you can associate the following Layer 2 and Layer 3 network elements with locations:</span></span>

  - <span data-ttu-id="3408c-107">Adresses BSSID (Basic Service Set Identification) des points d’accès sans fil (WAP) (couche 2)</span><span class="sxs-lookup"><span data-stu-id="3408c-107">Wireless access point (WAP) Basic Service Set Identification (BSSID) addresses (Layer 2)</span></span>

  - <span data-ttu-id="3408c-108">Port commuté LLDP (couche 2)</span><span class="sxs-lookup"><span data-stu-id="3408c-108">LLDP switch port (Layer 2)</span></span>

  - <span data-ttu-id="3408c-109">ID de châssis commuté LLDP (couche 2)</span><span class="sxs-lookup"><span data-stu-id="3408c-109">LLDP switch chassis IDs (Layer 2)</span></span>

  - <span data-ttu-id="3408c-110">Sous-réseaux IP (couche 3)</span><span class="sxs-lookup"><span data-stu-id="3408c-110">IP subnets (Layer 3)</span></span>

  - <span data-ttu-id="3408c-111">Adresses MAC des clients (couche 2)</span><span class="sxs-lookup"><span data-stu-id="3408c-111">Client MAC addresses (Layer 2)</span></span>

<span data-ttu-id="3408c-112">Les éléments réseau sont répertoriés par ordre de priorité.</span><span class="sxs-lookup"><span data-stu-id="3408c-112">The network elements are listed in order of precedence.</span></span> <span data-ttu-id="3408c-113">Si un client peut être localisé à l’aide de plusieurs éléments réseau, Lync Server utilise l’ordre de priorité pour déterminer le mécanisme à utiliser.</span><span class="sxs-lookup"><span data-stu-id="3408c-113">If a client can be located by using more than one network element, Lync Server uses the order of precedence to determine which mechanism to use.</span></span>

<span data-ttu-id="3408c-114">Les sections suivantes abordent plus en détail l’utilisation de chaque élément réseau.</span><span class="sxs-lookup"><span data-stu-id="3408c-114">The following sections provide more details for using each network element.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3408c-115">Lorsque vous utilisez des éléments réseau pour mapper des appelants vers des emplacements, il est très important de maintenir la base de données du service informations d’emplacement à jour.</span><span class="sxs-lookup"><span data-stu-id="3408c-115">When you use network elements to map callers to locations, it is of utmost importance that you keep the Location Information service database up-to-date.</span></span> <span data-ttu-id="3408c-116">Par exemple, si vous ajoutez ou modifiez un élément réseau, comme un point d’accès sans fil, vous devez supprimer l’ancienne entrée et ajouter la nouvelle entrée dans la base de données d’emplacements.</span><span class="sxs-lookup"><span data-stu-id="3408c-116">For example, if you add or change a network element, such as adding a WAP, you must delete the old entry and add the new entry in the location database.</span></span>



</div>

<div>

## <a name="wireless-access-point"></a><span data-ttu-id="3408c-117">Point d’accès sans fil</span><span class="sxs-lookup"><span data-stu-id="3408c-117">Wireless Access Point</span></span>

<span data-ttu-id="3408c-118">Lorsqu’un client se connecte au réseau via une liaison sans fil, la demande d’emplacement utilise l’adresse BSSID du point d’accès sans fil pour déterminer son emplacement.</span><span class="sxs-lookup"><span data-stu-id="3408c-118">When a client connects to the network wirelessly, the location request uses the BSSID address of the WAP to determine its location.</span></span> <span data-ttu-id="3408c-119">Si le client est en déplacement, le point d’accès sans fil indiqué risque de ne pas être le plus proche et il est même possible de sélectionner un point d’accès sans fil se trouvant à un autre étage du bâtiment.</span><span class="sxs-lookup"><span data-stu-id="3408c-119">If the client is roaming, the WAP indicated may not be the closest one, and it’s even possible to pick up a WAP that is on a different floor of the building.</span></span> <span data-ttu-id="3408c-120">Pour indiquer que l’emplacement est approximatif, vous pouvez ajouter à la valeur de l’emplacement le descripteur Near ou Close to.</span><span class="sxs-lookup"><span data-stu-id="3408c-120">To indicate that the location is approximate, you can prepend the location value with a Near or Close to descriptor.</span></span>

<span data-ttu-id="3408c-121">Cette méthode d’emplacement part du principe que le BSSID de chaque point d’accès sans fil est statique.</span><span class="sxs-lookup"><span data-stu-id="3408c-121">This location method assumes that the BSSID of each WAP is static.</span></span> <span data-ttu-id="3408c-122">Toutefois, si votre fournisseur de points d’accès sans fil utilise des BSSID attribués de manière dynamique, le BSSID obtenu auprès d’un point d’accès sans fil peut changer (cela peut se produire suite à une modification de configuration du point d’accès), et les clients sans fil peuvent se retrouver en situation de ne pas recevoir d’emplacement.</span><span class="sxs-lookup"><span data-stu-id="3408c-122">However, if your WAP vendor uses dynamically-assigned BSSIDs, the BSSID that is obtained from a WAP could change (this can happen following a WAP configuration change), and wireless clients could be left in a situation where they don’t receive a location.</span></span> <span data-ttu-id="3408c-123">Pour éviter cette possibilité, vous devez remplir la base de données du service informations d’emplacement avec ERL pour toutes les adresses BSSID possibles utilisées par chaque WAP.</span><span class="sxs-lookup"><span data-stu-id="3408c-123">To prevent this possibility, you need to populate the Location Information service database with ERLs for all possible BSSID addresses used by each WAP.</span></span>

</div>

<div>

## <a name="lldp-ports-and-switches"></a><span data-ttu-id="3408c-124">Ports et commutateurs LLDP</span><span class="sxs-lookup"><span data-stu-id="3408c-124">LLDP Ports and Switches</span></span>

<span data-ttu-id="3408c-p106">Les commutateurs Ethernet gérés qui prennent en charge le protocole LLDP-MED (Link Layer Discovery Protocol-Media Endpoint Discover) peuvent annoncer leur identité et leurs informations de port aux clients compatibles LLDP-MED, lesquelles peuvent alors faire l’objet d’une requête dans la base de données d’emplacements afin de fournir l’emplacement du périphérique. Vous pouvez associer des ERL uniquement sur l’ID du châssis commuté, ou les mapper au niveau du port.</span><span class="sxs-lookup"><span data-stu-id="3408c-p106">Managed Ethernet switches that support Link Layer Discovery Protocol-Media Endpoint Discover (LLDP-MED) can advertise their identity and port information to LLDP-MED compatible clients, which then can be queried against the location database to provide the location of the device. You can associate ERLs solely on the switch chassis ID, or you can map them down to the port level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3408c-127">Lync Server 2013 prend en charge l’utilisation de LLDP-MED pour la détermination des emplacements uniquement des appareils Lync Phone Edition et de Lync 2013 exécutés sur Windows 8.</span><span class="sxs-lookup"><span data-stu-id="3408c-127">Lync Server 2013 supports using LLDP-MED for determining locations only of Lync Phone Edition devices and Lync 2013 running on Windows 8.</span></span> <span data-ttu-id="3408c-128">Si vous devez utiliser des données de couche 2 de niveau commutateur pour déterminer l’emplacement d’autres clients Lync à PC câblés, vous devez utiliser la méthode d’adresse MAC cliente.</span><span class="sxs-lookup"><span data-stu-id="3408c-128">If you need to use switch-level Layer 2 data to determine the location of other wired PC-based Lync clients, you need to use the client MAC address method.</span></span>



</div>

</div>

<div>

## <a name="subnet"></a><span data-ttu-id="3408c-129">Sous-réseau</span><span class="sxs-lookup"><span data-stu-id="3408c-129">Subnet</span></span>

<span data-ttu-id="3408c-130">Les sous-réseaux IP de couche 3 fournissent un mécanisme pris en charge par tous les clients Lync Server qui peut être utilisé pour détecter automatiquement l’emplacement du client.</span><span class="sxs-lookup"><span data-stu-id="3408c-130">Layer 3 IP subnets provide a mechanism supported by all Lync Server clients that can be used to automatically detect client location.</span></span> <span data-ttu-id="3408c-131">L’utilisation de sous-réseaux IP constitue la méthode d’emplacement la plus simple pour configurer et gérer des clients câblés.</span><span class="sxs-lookup"><span data-stu-id="3408c-131">Using IP subnets is the easiest location method to configure and manage wired clients.</span></span> <span data-ttu-id="3408c-132">Avant d’opter pour l’utilisation de sous-réseaux, en revanche, répondez aux questions suivantes pour déterminer si la spécificité de l’emplacement du sous-réseau est suffisamment fine pour localiser un client avec précision :</span><span class="sxs-lookup"><span data-stu-id="3408c-132">Before you decide to use subnets, however, use the following questions to help determine if the location specificity of the subnet is sufficiently fine to accurately locate a client:</span></span>

  - <span data-ttu-id="3408c-133">Un ou plusieurs sous-réseaux des clients couvrent-ils plusieurs étages ?</span><span class="sxs-lookup"><span data-stu-id="3408c-133">Do one or more client subnets cover multiple floors?</span></span>

  - <span data-ttu-id="3408c-134">Un ou plusieurs sous-réseaux couvrent-t-ils plusieurs immeubles ?</span><span class="sxs-lookup"><span data-stu-id="3408c-134">Do one or more subnets cover more than one building?</span></span>

  - <span data-ttu-id="3408c-135">Quelle est la surface couverte par chaque sous-réseau client ?</span><span class="sxs-lookup"><span data-stu-id="3408c-135">How much floor space is covered by each client subnet?</span></span>

<span data-ttu-id="3408c-p109">Si le sous-réseau couvre une zone trop vaste, vous devrez envisager d’utiliser un autre mécanisme pour localiser les clients. Toutefois, si possible, nous recommandons aux clients de réorganiser leur sous-réseau IP afin de respecter les exigences de spécificité d’emplacement ERL plutôt que d’induire le coût et la complexité des solutions SNMP tierces.</span><span class="sxs-lookup"><span data-stu-id="3408c-p109">If the subnet covers too broad an area, you may need to use another mechanism to locate clients. However, if at all practical, we recommend that customers reorganize their IP subnetting to meet the ERL location specificity requirements rather than incurring the cost and complexity of third-party SNMP-based solutions.</span></span>

</div>

<div>

## <a name="client-mac-address"></a><span data-ttu-id="3408c-138">Adresse MAC d’un client</span><span class="sxs-lookup"><span data-stu-id="3408c-138">Client MAC Address</span></span>

<span data-ttu-id="3408c-139">Pour utiliser l’adresse MAC d’un ordinateur client pour localiser un appelant, vous avez besoin de commutateurs Ethernet gérés, et vous devez déployer une solution SNMP tierce capable de découvrir les adresses MAC des clients Lync connectés à (ou via) ces commutateurs.</span><span class="sxs-lookup"><span data-stu-id="3408c-139">To use a client computer's MAC address to locate a caller, you need managed Ethernet switches, and you must deploy a third-party SNMP solution that can discover the MAC addresses of Lync clients connected to (or through) those switches.</span></span> <span data-ttu-id="3408c-140">La solution SNMP interroge continuellement les commutateurs gérés pour obtenir les mappages actuels des adresses MAC de point de terminaison connectées à chaque port et obtient les IP de port correspondants.</span><span class="sxs-lookup"><span data-stu-id="3408c-140">The SNMP solution continually polls the managed switches to get the current mappings of the endpoint MAC addresses connected to each port and obtains the corresponding port IDs.</span></span> <span data-ttu-id="3408c-141">Pendant la demande d’un client Lync au service d’informations d’emplacement, le service informations d’emplacement interroge l’application tierce à l’aide de l’adresse MAC du client, puis renvoie les ID de port et les adresses IP Switch correspondantes.</span><span class="sxs-lookup"><span data-stu-id="3408c-141">During a Lync client’s request to the Location Information service, the Location Information service queries the third-party application by using the client’s MAC address, and then returns any matching switch IP addresses and port IDs.</span></span> <span data-ttu-id="3408c-142">Le service d’informations d’emplacement utilise ces informations pour interroger son câblage de couche 2 publié pour un enregistrement correspondant et renvoie l’emplacement au client.</span><span class="sxs-lookup"><span data-stu-id="3408c-142">The Location Information service uses this information to query its published Layer 2 wiremap for a matching record and returns the location to the client.</span></span> <span data-ttu-id="3408c-143">Si vous utilisez cette option, vérifiez que les identifiants de port de commutateur sont cohérents entre l’application SNMP et les enregistrements de la base de données d’emplacements publiés.</span><span class="sxs-lookup"><span data-stu-id="3408c-143">If you use this option, make sure that the switch port identifiers are consistent between the SNMP application and the published location database records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3408c-144">Certaines solutions SNMP tierces peuvent prendre en charge les commutateurs d’accès non gérés ; si le commutateur qui dessert le client Lync est non géré mais comporte une liaison montante vers un commutateur de distribution géré, le commutateur géré peut signaler à l’application SNMP les adresses MAC des clients connectés au commutateur d’accès.</span><span class="sxs-lookup"><span data-stu-id="3408c-144">Some third-party SNMP solutions can support unmanaged access switches; if the switch that services the Lync client is unmanaged but has an uplink to a managed distribution switch, the managed switch can report back to the SNMP application the MAC addresses of the clients connected to the access switch.</span></span> <span data-ttu-id="3408c-145">Ces informations permettent au service d’informations d’emplacement d’identifier l’emplacement de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="3408c-145">This information enables the Location Information service to identify the location of the user.</span></span> <span data-ttu-id="3408c-146">Toutefois, il est possible d’affecter un seul ERL à tous les ports sur le commutateur non géré, afin que la spécificité de l’emplacement soit disponible uniquement au niveau du châssis du commutateur d’accès, et non au niveau du port.</span><span class="sxs-lookup"><span data-stu-id="3408c-146">However, it is possible to assign only a single ERL to all ports on the unmanaged switch, so the location specificity is available only at the chassis level of the access switch, not the port level.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

