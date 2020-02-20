---
title: 'Lync Server 2013 : définition de la configuration requise pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0406286f4f9d8251743fe6ff3a4807dff277fe92
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154706"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="492ff-102">Définition de la configuration requise pour voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="492ff-102">Defining your requirements for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="492ff-103">_**Dernière modification de la rubrique :** 2012-08-07_</span><span class="sxs-lookup"><span data-stu-id="492ff-103">_**Topic Last Modified:** 2012-08-07_</span></span>

<span data-ttu-id="492ff-104">Cette rubrique fournit une vue d’ensemble des éléments à prendre en compte concernant les régions, les sites et les liens entre les sites de votre topologie et la façon dont ils sont importants lorsque vous déployez voix entreprise.</span><span class="sxs-lookup"><span data-stu-id="492ff-104">This topic provides an overview of the considerations you need to make about the regions, sites, and the links between sites in your topology and how those are important when you deploy Enterprise Voice.</span></span> <span data-ttu-id="492ff-105">Pour plus d’informations pour vous aider à prendre ces décisions, voir [paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="492ff-105">For details to help you make these decisions, see [Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md) in the Planning documentation.</span></span>

<div>

## <a name="sites-and-regions"></a><span data-ttu-id="492ff-106">Sites et régions</span><span class="sxs-lookup"><span data-stu-id="492ff-106">Sites and Regions</span></span>

<span data-ttu-id="492ff-107">Tout d’abord, identifiez les sites de votre topologie dans lesquels vous allez déployer voix entreprise et les régions réseau auxquelles ces sites appartiennent.</span><span class="sxs-lookup"><span data-stu-id="492ff-107">First, identify the sites in your topology where you will deploy Enterprise Voice and the network regions to which those sites belong.</span></span> <span data-ttu-id="492ff-108">En particulier, pensez à la façon dont vous allez assurer la connectivité PSTN (réseau téléphonique commuté) vers chaque site.</span><span class="sxs-lookup"><span data-stu-id="492ff-108">In particular, consider how you will provide public switched telephone network (PSTN) connectivity to each site.</span></span> <span data-ttu-id="492ff-109">Pour des raisons pratiques et logistiques, les régions auxquelles ces sites appartiennent peuvent être un facteur déterminant.</span><span class="sxs-lookup"><span data-stu-id="492ff-109">For manageability and logistical reasons, the regions to which these sites belong can be a deciding factor.</span></span> <span data-ttu-id="492ff-110">Déterminez l’emplacement où les passerelles seront déployées localement, où Survivable Branch Appliances (SBA) seront déployés et où vous pouvez configurer des jonctions SIP (localement ou sur le site central) vers un fournisseur de services de téléphonie Internet (téléphonie Internet).</span><span class="sxs-lookup"><span data-stu-id="492ff-110">Decide where gateways will be deployed locally, where Survivable Branch Appliances (SBAs) will be deployed, and where you can configure SIP trunks (either locally or at the central site) to an Internet telephony service provider (ITSP).</span></span>

</div>

<div>

## <a name="network-links-between-sites"></a><span data-ttu-id="492ff-111">Liaisons réseau entre sites</span><span class="sxs-lookup"><span data-stu-id="492ff-111">Network Links Between Sites</span></span>

<span data-ttu-id="492ff-112">Vous devez également tenir compte de l’utilisation de la bande passante que vous attendez sur les liaisons réseau entre votre site central et ses sites de succursale.</span><span class="sxs-lookup"><span data-stu-id="492ff-112">You also need to consider the bandwidth usage that you expect on the network links between your central site and its branch sites.</span></span> <span data-ttu-id="492ff-113">Si vous avez ou envisagez de déployer des liaisons de réseau étendu (WAN) résilientes entre les sites, nous vous recommandons de déployer une passerelle sur chaque site de succursale afin de fournir une terminaison de numérotation directe vers l’intérieur pour les utilisateurs de ces sites.</span><span class="sxs-lookup"><span data-stu-id="492ff-113">If you have, or plan to deploy, resilient WAN links between sites, we recommend that you deploy a gateway at each branch site to provide local direct inward dial (DID) termination for users at those sites.</span></span> <span data-ttu-id="492ff-114">Si vous disposez de liaisons de réseau étendu résistantes, alors que la bande passante de l’une d’elles risque d’être limitée, configurez la fonctionnalité de contrôle d’admission des appels sur celle-ci.</span><span class="sxs-lookup"><span data-stu-id="492ff-114">If you have resilient WAN links, but the bandwidth on a WAN link is likely to be constrained, configure call admission control for that link.</span></span> <span data-ttu-id="492ff-115">Si vous n’avez pas de liaisons WAN résilientes, que vous hébergez moins de 1000 utilisateurs sur votre site de succursale et que vous ne disposez pas des administrateurs Lync Server formés en local, nous vous recommandons de déployer un Survivable Branch appliance sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="492ff-115">If you do not have resilient WAN links, host fewer than 1000 users at your branch site, and do not have local trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Appliance at the branch site.</span></span> <span data-ttu-id="492ff-116">Si vous hébergez entre 1000 et 5000 utilisateurs sur votre site de succursale, si vous ne disposez pas d’une connexion WAN résiliente et si vous disposez d’administrateurs Lync Server formés, nous vous recommandons de déployer un serveur Survivable Branch Server avec une petite passerelle sur le site de succursale.</span><span class="sxs-lookup"><span data-stu-id="492ff-116">If you host between 1000 and 5000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available, we recommend that you deploy a Survivable Branch Server with a small gateway at the branch site.</span></span> <span data-ttu-id="492ff-117">Envisagez aussi d’activer le contournement de média sur les liaisons limitées si vous disposez d’un homologue de passerelle qui prend en charge cette fonctionnalité.</span><span class="sxs-lookup"><span data-stu-id="492ff-117">Consider also enabling media bypass on constrained links if you have a gateway peer that supports media bypass.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="492ff-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="492ff-118">See Also</span></span>


[<span data-ttu-id="492ff-119">Paramètres réseau pour les fonctionnalités avancées de voix entreprise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="492ff-119">Network settings for the advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

