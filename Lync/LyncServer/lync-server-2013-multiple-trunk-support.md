---
title: 'Lync Server 2013 : prise en charge de plusieurs tronçons'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a2f8e9bea40532486d75e76887e35b496df8631
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039127"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="3544b-102">Prise en charge de plusieurs tronçons dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3544b-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3544b-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3544b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3544b-104">La fonctionnalité Lync Server 2013 prend en charge plusieurs associations entre les passerelles et les serveurs de médiation.</span><span class="sxs-lookup"><span data-stu-id="3544b-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="3544b-105">Ces associations sont établies en définissant une jonction, qui est une association logique entre un pool de serveurs de médiation et une passerelle de réseau téléphonique commuté (RTC), un contrôleur de frontière de session (SBC) ou un PBX IP.</span><span class="sxs-lookup"><span data-stu-id="3544b-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="3544b-106">Utilisez le générateur de topologie pour associer des passerelles aux serveurs de médiation (c’est-à-dire, des jonctions).</span><span class="sxs-lookup"><span data-stu-id="3544b-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="3544b-107">Pour attribuer ou supprimer une jonction dans Lync Server 2013, vous devez d’abord définir une jonction dans le générateur de topologies.</span><span class="sxs-lookup"><span data-stu-id="3544b-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="3544b-108">Une jonction se compose de l’Association suivante : nom de domaine complet (FQDN) du serveur de médiation, port d’écoute du serveur de médiation, nom de domaine complet de la passerelle et port d’écoute de la passerelle.</span><span class="sxs-lookup"><span data-stu-id="3544b-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="3544b-109">Pour configurer plusieurs jonctions, vous pouvez créer plusieurs associations entre la même passerelle et le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3544b-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="3544b-110">Cela procure une résistance supplémentaire à l’infrastructure voix entreprise, ce qui est particulièrement utile dans les scénarios d’interopérabilité PBX (Private Branch Exchange).</span><span class="sxs-lookup"><span data-stu-id="3544b-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="3544b-111">Lorsqu’une jonction est définie, elle doit être associée à un itinéraire.</span><span class="sxs-lookup"><span data-stu-id="3544b-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="3544b-112">Pour associer une jonction à un itinéraire, vous définissez un nom simple pour la jonction dans le générateur de topologie.</span><span class="sxs-lookup"><span data-stu-id="3544b-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="3544b-113">Ce nom simple est utilisé comme nom de jonction dans le panneau de configuration Lync Server, où des jonctions peuvent être associées à des itinéraires.</span><span class="sxs-lookup"><span data-stu-id="3544b-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="3544b-114">Le nom de jonction simple est utilisé comme nom de passerelle à partir de Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3544b-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="3544b-115">L’administrateur doit sélectionner une jonction par défaut associée à un serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3544b-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="3544b-116">Dans le générateur de topologies, cliquez avec le bouton droit sur le serveur de médiation associé, puis cliquez sur **Propriétés**.</span><span class="sxs-lookup"><span data-stu-id="3544b-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="3544b-117">Spécifiez la passerelle par défaut pour le serveur de médiation.</span><span class="sxs-lookup"><span data-stu-id="3544b-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="3544b-118">Le diagramme suivant illustre les différentes jonctions qui sont définies pour chaque serveur de médiation et passerelle.</span><span class="sxs-lookup"><span data-stu-id="3544b-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="3544b-119">**Routage de jonction M-N**</span><span class="sxs-lookup"><span data-stu-id="3544b-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="3544b-120">![Plusieurs affectations de jonctions.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Plusieurs affectations de jonctions.")</span><span class="sxs-lookup"><span data-stu-id="3544b-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

