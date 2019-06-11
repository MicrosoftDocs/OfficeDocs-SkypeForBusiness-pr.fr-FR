---
title: 'Lync Server 2013: prise en charge de plusieurs Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 156db04ceb26809c7043f30e9e01ea0071e0a31d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="f9f7f-102">Prise en charge de plusieurs Trunks dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9f7f-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9f7f-103">_**Dernière modification de la rubrique:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="f9f7f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="f9f7f-104">La fonctionnalité Lync Server 2013 prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="f9f7f-105">Pour ce faire, vous devez définir une ligne Trunk, qui est une association logique entre une grappe de serveurs de médiation et une passerelle de réseau téléphonique commuté (PSTN), un contrôleur de bordure de session (SBC) ou un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="f9f7f-106">Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des Trunks).</span><span class="sxs-lookup"><span data-stu-id="f9f7f-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="f9f7f-107">Pour attribuer ou supprimer un Trunk dans Lync Server 2013, vous devez commencer par définir un Trunk dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="f9f7f-108">Un Trunk est composé de l’Association suivante: nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="f9f7f-109">Pour configurer plusieurs Trunks, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="f9f7f-110">Cela fournit une résilience supplémentaire à l’infrastructure voix entreprise, qui est particulièrement utile dans les scénarios d’interopération de PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="f9f7f-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="f9f7f-111">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="f9f7f-112">Pour associer un Trunk à un itinéraire, vous devez définir un nom simple pour le Trunk dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="f9f7f-113">Ce nom simple est utilisé en tant que nom du Trunk dans le panneau de configuration de Lync Server, dans lequel les lignes peuvent être associées aux itinéraires.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="f9f7f-114">Le nom de Trunk simple est utilisé comme nom de passerelle de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="f9f7f-115">L’administrateur doit sélectionner une Trunk par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="f9f7f-116">Dans le générateur de topologie, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="f9f7f-117">Spécifiez la passerelle par défaut du serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="f9f7f-118">Le diagramme suivant illustre les différentes liaisons définies pour chaque serveur et passerelle de médiation.</span><span class="sxs-lookup"><span data-stu-id="f9f7f-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="f9f7f-119">**Routage de l’interligne M-N**</span><span class="sxs-lookup"><span data-stu-id="f9f7f-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="f9f7f-120">![Plusieurs affectations de Trunk.] (images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Plusieurs affectations de Trunk.")</span><span class="sxs-lookup"><span data-stu-id="f9f7f-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

